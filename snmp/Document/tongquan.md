#  Giới thiệu về snmp.

### 1. Khái niệm.
----------------

SNMP – viết tắt của Simple Network Management Protocol (Giao thức quản lý mạng đơn gian) là một tập các thao tác cho phép người quản trị hệ thống có thể thay đổi trạng thái của các thiết bị (có hỗ trợ SNMP), Snmp được thiết kế để quản lý các thiết bị có kết nối mạng như máy tính, switch, router, firewall, ADSL gateway.

 **Ví dụ một số chức năng của SNMP:**
   * Theo dõi tốc độ đường truyền của một router, biết được tổng số byte đã truyền/nhận.
   * Lấy thông tin máy chủ đang có bao nhiêu ổ cứng, mỗi ổ cứng còn trống bao nhiêu.
   * Tự động nhận cảnh báo khi switch có một port bị down.
   * Điều khiển tắt (shutdown) các port trên switch.


### 2. Các phiên bản.
---------------------
 
SNMP bao gồm có 3 version chính.

| Các version| Mô tả |
| -----------|-------------|
| version 1,2 | Không có xác thực mã hóa sử dụng tiêu chuẩn trap gửi thông tin về manager khi có sự cố xảy ra| 
| version 3  |Tương tự như version 1 2 nhưng có xác thực mã hóa và bảo mật cao|

### 3. Ưu điểm. 
--------------
* SNMP được thiết kế để đơn giản hóa quá trình quản lý các thành phần trong mạng, dẫn đến các phần mềm SNMP có thể được phát triển nhanh và tốn ít chi phí.
* SNMP được thiết kế để có thể mở rộng các chức năng quản lý, giám sát. Khi có một thiết bị mới với các thuộc tính mới, tính năng mới thì có thể "custom" SNMP để phục vụ cho riêng mình. 
* SNMP sử dụng giao thức UDP nên tốc độ truyền tải nhanh và  dễ dàng sửa  chữa khi có sự cố.

### 4. Nhược điểm.
----------------

* Không có sự tổng hợp từ nhiều máy quản lý.
* SNMP sử dụng giao thức UDP nên không đảm bảo  được độ chính  xác của các gói  tin.




