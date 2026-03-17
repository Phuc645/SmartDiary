# Cơ sở dữ liệu

Tài liệu này mô tả schema dữ liệu ở mức logic cho SmartDiary (ưu tiên tương thích Supabase/Postgres).

Quy ước chung:

- `Uid`: UUID (Postgres `uuid`), tạo bởi Supabase.
- Thời gian dùng ISO-8601, lưu trong Postgres `timestamptz` (khuyến nghị).

## Bảng `Users`

| Thuộc tính | Dạng | Ghi chú |
|:------|:------|:--------|
| userId | Uid | **PK**. Tạo ra bởi Supabase |
| username | nvarchar100 | Unique (khuyến nghị). Dùng để đăng nhập/hiển thị |
| password | nvarchar100 | Có thể null nếu dùng OAuth/Firebase |
| email | nvarchar100 | Unique (khuyến nghị). Format có `@` |
| firebase_id | nvarchar100 | Unique (khuyến nghị). Lấy từ Firebase |

## Bảng `Diary`

| Thuộc tính | Dạng | Ghi chú |
|:------|:------|:--------|
| diaryId | Uid | **PK**. Tạo ra bởi Supabase |
| userId | Uid | **FK** → `Users.userId` |
| createdDate | datetime | Khuyến nghị `timestamptz`, mặc định `now()` |
| diaryContent | nvarchar1000 | Nội dung nhật ký (plain text) |

## Bảng `Chat_session`

| Thuộc tính | Dạng | Ghi chú |
|:------|:------|:--------|
| chat_session_id | Uid | **PK**. Tạo ra bởi Supabase |
| diaryId | Uid | **FK** → `Diary.diaryId` |
| chatContent | jsonb | Lịch sử hội thoại của session, lưu dạng **mảng message** theo thời gian |

### Quy ước `chatContent` (JSON)

`chatContent` là một JSON array, mỗi phần tử là 1 message.

Ví dụ:

```json
[
  {
    "id": "msg_01",
    "role": "user",
    "content": "Hôm nay mình stress vì công việc…",
    "createdAt": "2026-03-17T08:10:00Z"
  },
  {
    "id": "msg_02",
    "role": "assistant",
    "content": "Mình hiểu. Bạn thử mô tả 3 điều làm bạn căng thẳng nhất…",
    "createdAt": "2026-03-17T08:10:05Z"
  }
]
```

Ràng buộc tối thiểu đề xuất:
- `role`: `"user"` hoặc `"assistant"`
- `content`: string
- `createdAt`: ISO-8601 string (khuyến nghị)
- `id`: string (khuyến nghị, để dễ đồng bộ/chỉnh sửa)
