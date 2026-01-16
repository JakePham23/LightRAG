# Hướng dẫn Cài đặt và Chạy LightRAG WebUI

Thực hiện các bước sau để xây dựng giao diện web (WebUI) và cấu hình backend cho LightRAG.

## 1. Thiết lập Môi trường Python (Backend)

Đảm bảo bạn đã kích hoạt môi trường ảo Python của dự án:

```bash
python -m venv .venv
source .venv/bin/activate
```

## 2. Xây dựng WebUI (Frontend)

Sử dụng `bun` để cài đặt và build giao diện web. Đảm bảo bạn đang ở thư mục gốc của dự án trước khi chạy các lệnh sau:

```bash
cd lightrag_webui
bun install --frozen-lockfile
bun run build
cd ..
```

_Lưu ý: Sau khi build xong, các file tĩnh của web sẽ được backend phục vụ._

## 3. Cấu hình Môi trường (.env)

Thiết lập file cấu hình cho server:

1.  **Tạo file `.env`**: Copy từ file mẫu `.env.example`.
    ```bash
    cp env.example2 .env
    ```

2.  **Chỉnh sửa `.env`**:
    *   Mở file `.env` vừa tạo.
    *   Có thể thay đổi `LLM_MODEL` hoặc các cấu hình API key nếu cần thiết.
    *   **QUAN TRỌNG:** **KHÔNG** thay đổi tên model embedding (`EMBEDDING_MODEL`) nếu không thực sự cần thiết và hiểu rõ hệ quả, để đảm bảo tính nhất quán của dữ liệu vector đã lưu.

## 4. Chạy Server

Sau khi hoàn tất cài đặt và cấu hình, khởi động server:

```bash
python -m lightrag.api.lightrag_server
```
