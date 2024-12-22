# Hướng Dẫn Chạy Node Miner Volara Trên Ubuntu VPS ( Có thể mua tại Contabo )

Bài hướng dẫn này chủ yếu dành cho việc cài đặt để mine **Volara ($VANA)** trên Linux(Ubuntu). Nếu bạn muốn chạy trên **Windows**, vui lòng tìm hiểu thêm bằng cách tìm **Docker Desktop** hoặc **WSL 2** để biết hướng dẫn cài đặt 

## Yêu Cầu Trước Khi Bắt Đầu
- **Ví có ít nhất 0.1 $VANA ( Mainet )**
- **1 Tài khoản Google ( Khuyến nghị sử dụng tài koản phụ )**
- **1 Tài khoản Twitter** 
  - (*Lưu ý: Twitter có mức độ hoạt động cao sẽ giúp miner được nhiều điểm hơn*)
- Trước khi chạy tool, truy cập vào **[Volara](https://volara.xyz/airdrop)** để kết nối ví và kết nối Twitter.

---

## Các Bước Thực Hiện

### 1. Cập nhật và cài đặt môi trường
- Bỏ qua nếu đã có
```bash
sudo apt update
sudo apt install screen -y

sudo apt update && sudo apt install docker.io -y && sudo systemctl start docker && sudo systemctl enable docker && docker --version
```

### 2. Tạo một phiên làm việc với `screen`
```bash
screen -S volara
```

### 3. Kéo image của Volara Miner từ Docker Hub
```bash
docker pull volara/miner
```

### 4. Thiết lập private key cho ví VANA
Thay `<your_private_key>` bằng private key ví của bạn:
```bash
export VANA_PRIVATE_KEY=<your_private_key>
```

### 5. Chạy Node Miner Volara
```bash
docker run -it -e VANA_PRIVATE_KEY=${VANA_PRIVATE_KEY} volara/miner
```

---

## Các Bước Sau Khi Chạy Node

1. **Ủy quyền truy cập Google Drive**
   - Copy đường dẫn được cung cấp khi chạy lệnh trên.
   - Dán đường dẫn vào trình duyệt và ủy quyền truy cập tài khoản Google Drive.

2. **Nhận code sau khi ủy quyền**
   - Lấy mã code được cung cấp sau khi ủy quyền thành công.
   - Dán mã code vào terminal để tiếp tục.

3. **Đăng nhập tài khoản Twitter**
   - Đăng nhập vào tài khoản Twitter của bạn.
   - Quá trình này hoàn tất và Node bắt đầu chạy.

---

## Hướng Dẫn Quản Lý `screen`
- Để **thoát tạm thời** khỏi phiên `screen` mà không dừng Node:
  ```bash
  Ctrl + A, sau đó nhấn D
  ```

- Để **quay lại phiên** `screen` đã tạo:
  ```bash
  screen -r volara
  ```

- Để xem danh sách các phiên `screen` đang chạy:
  ```bash
  screen -ls
  ```

---

## Cảnh Báo Quan Trọng Về Quyền Riêng Tư
- Không chia sẻ **private key** ví VANA của bạn với bất kỳ ai.
- Cẩn thận khi ủy quyền truy cập **Google Drive** và **Twitter**. Khuyến khích sử dụng tài khoản phụ.
- Theo dõi các cập nhật bảo mật từ dự án Volara để tránh rủi ro.

---

## [TopAME | Chat - Supports](https://t.me/yTopAME)
