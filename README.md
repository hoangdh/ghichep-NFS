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
- NFS được xây dựng từ 4 giao thức riêng biệt
	- nfs: Đọc ghi, truy cập các file. Thống kê và xác thực
	- mountd: Dùng để mount folder
	- nsm: Giám sát trạng thái của mạng ở client và server
	- nlm: Quản lý các Lock mạng, cho phép tương tác đồng thời

<img src="http://i.imgur.com/SSFaDlc.png" />

#### Virtual Filesystem (VFS)
- là một filesystem ảo
- Chức năng của nó giống như một FS là lưu trữ dữ liệu
- Mỗi file sẽ có một "inode"
- Nhiệm vụ của server là gửi inode của file mà client muốn truy cập
- Server cho phép các client sử dụng inode của file

### 4. Tham khảo

- http://www.slideshare.net/udamale/nfsnetwork-file-system
- http://www.slideshare.net/wind1st/13-samba-nfs-server