# OS_10_2019
# NETWORK INTERACTION OF PROCESSES THROUGH SOCKETS  
## Mục tiêu bài lab:  
Làm quen với cơ chế tương tác của các tiến trình từ xa (remote processes) - sockets và những lệnh hệ thống, đảm bảo cung cấp thiết lập kết nối (connection establishment), mất kết nối (disconnection), cũng như truyền và nhận dữ liệu.  
## Mô tả lý thuyết:  
**Socket** là một chương trình giao diện, được cung cấp bởi hệ điều hành cho các quá trình tương tác từ xa của các tiến trình.  
Trong sự phụ thuộc vào các tham số được chọn, sockets có thể hỗ trợ kết nối địa phương, protocols Internet, protocol Novell, X.25,..v..v  
Sockets hỗ trợ trao đổi bằng tin nhắn bằng việc thiết lật kết nối (protocol TCP), đảm bảo truyền tin nhắn có trật tự và nhịp nhàng, và trao đổi bằng tin nhắn mà không cần thiết đặt kết nối (protocol UDP), đảm bảo kết nối nhịp nhàng truyền những tin nhắn có thể bị mất, và thứ tự truyền có thể bị xâm phạm.  

Sockets được tạo ra bởi lệnh:   
````
int socket(int domain, int type, int protocol),
````
trong đó:  
`domain` - xác định loại giao thức truyền thông (Internet, Novell, X.25);   
`type` - xác định loại truyền (đáng tin cậy, không đáng tin cậy);  
`protocol` - đặc điểm kỹ thuật của loại giao thức truyền thông.  

Đối với sockets, sẽ thực hiện chức năng nghe trên máy chủ, địa chỉ bị ràng buộc bởi lệnh gọi sau:  
````
int bind(int s,struct sockaddr *addr,socklen_t addrlen),
````
trong đó:  
s - mô tả sockets;  
addr - con trỏ tới cấu trúc chứa địa chỉ mà socket bị ràng buộc;  
addrlen - kích thước của cấu trúc.  

Đặt sockets vào trạng thái nghe (listening state) bằng cách thực hiện lệnh:  
````
int listen(int s, int backlog),
````
trong đó:  
s - mô tả sockets;  
backlog - kích thước của hàng đợi (queue) kết nối máy khách (clients).  

Nhận 


