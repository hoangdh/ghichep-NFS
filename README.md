## Ghi chép về NFS


### 1. Khái niệm NFS

**NFS** viết tắt của từ **Network Filesystem**, là một giao thức dùng để chia sẻ dữ liệu giữa các máy sử dụng *unix với nhau thông qua môi trường mạng được phát triển bởi SUN.
- Dịch vụ NFS hoạt động theo giao thức TCP với mô hình Client-Server
- Cho phép các client kết nối đến phân vùng chia sẻ và sử dụng như một phân vùng cục bộ
- Hiện tại NFS có 4 phiên bản. NFSv4 là phiên bản đang được sử dụng nhiều nhất và hỗ trợ phát huy tối đa của giao thức NFS
- Một số vấn đề với NFS
	- Không bảo mật, mã hóa dữ liệu
	- Hiệu suất hoạt động trung bình ở mức khá, nhưng không ổn định
	- Dữ liệu phân tán có thể bị phá vỡ nếu có nhiều phiên sử dụng đồng thời
### 2. Thành phần

#### Server
- Là nơi chứa các thư mục, các file chia sẻ
- Đóng vai trò là một filesystem

#### Client
- Yêu cầu thông tin về các file, thư mục được chia sẻ

#### File Handle
- Cách để truy cập một file mà không cần biết tên file
- Tương tác giống như đang làm việc ở trên một filesystem cục bộ

### 3. Giao thức NFS

- NFS là giao thức hoạt động theo cơ chế RPC (Thủ tục gọi hàm từ xa thông qua một cổng mạng bất kỳ nào đó)
- Sử dụng như tài nguyên cục bộ
- Hoạt động theo kiểu stateless
- Được thiết kế dành riêng cho hệ thống Linux

#### Virtual Filesystem (VFS)
- là một filesystem ảo

### 4. Tham khảo

- http://www.slideshare.net/udamale/nfsnetwork-file-system
- http://www.slideshare.net/wind1st/13-samba-nfs-server