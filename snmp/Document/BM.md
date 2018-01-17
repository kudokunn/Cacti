# **Bảo mật của SNMP**
----------------------------


 * Một SNMP management station có thể quản lý/giám sát nhiều SNMP element, thông qua hoạt động gửi request và nhận trap.
 * Một SNMP element có thể được cấu hình để chỉ cho phép các SNMP management station nào đó được phép quản lý/giám sát mình.
##### Các cơ chế bảo mật: Community string, view và SNMP access control list.

## 1. Community String.

Community string là một chuỗi ký tự được cài đặt giống nhau trên cả SNMP manager và SNMP agent, đóng vai trò như “mật khẩu” giữa 2 bên khi trao đổi dữ liệu.Community string có 3 loại : Read-community, Write-Community và Trap-Community.
* Read-community: Khi  manager  gửi bản tin đi  có  chứa  Read-Community. Khi agent nhận được bản tin request nó sẽ so sánh Read-community do manager gửi và Read-community mà nó được cài đặt. Nếu 2 chuỗi này giống nhau, agent sẽ trả lời; nếu 2 chuỗi này khác nhau, agent sẽ không trả lời.
* Write-Community: Được dùng trong bản tin SetRequest. Agent chỉ chấp nhận thay đổi dữ liệu khi write- community 2 bên giống nhau.
* Trap-community: Nằm trong bản tin trap của trap sender gửi cho trap receiver. Trap receiver chỉ nhận và lưu trữ bản tin trap khi trap-community 2 bên giống nhau.

## 2. View.
* Một view được  gắn liền với một community string. Tùy vào community string nhận được là gì mà agent xử lý trên view tương ứng.
* Ví dụ : agent định nghĩa read-community “inf” trên view interfaceView, và “sto” trên storageView; khi manager gửi request lấy OID ifNumber với community là “inf” thì sẽ được đáp ứng do ifNumber nằm trong interfaceView

## 3. SNMP access control list.

* SNMP ACL là một danh sách các địa chỉ IP được phép quản lý/giám sát agent, nó chỉ áp dụng riêng cho giao thức SNMP và được cài trên agent. Nếu một manager có IP không được phép trong ACL gửi request thì agent sẽ không xử lý, dù request có community string là đúng.
* Đa số các thiết bị tương thích SNMP đều cho phép thiết lập SNMP ACL



