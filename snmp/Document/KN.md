# **Một số khái niệm trên SNMP**


### 1. Thành phần.

 * Network  management  station: Là một máy tính chạy chương trình quản lý mạng. Nhiệm vụ của một manager là truy vấn các agent và xử lý thông tin nhận được từ agent.

 * SNMP agent:  Là một chương trình chạy trên thiết bị mạng cần được quản lý,n hiệm vụ của agent là thông tin cho manager.

**Ví dụ** : Để dùng một máy chủ giám sát lưu lượng của một router thì phải cài phần mềm quản lý SNMP trên máy chủ, bật tính năng SNMP (= agent) trên router.

### 2. OID (Object id).

Một thiết bị hỗ trợ SNMP có thể cung cấp nhiều thông tin khác nhau, mỗi thông tin đó gọi là một object. Ví dụ:

*  Máy tính có thể cung cấp các thông tin : tổng số ổ cứng, tổng số port nối mạng, tổng số byte đã truyền/nhận, tên máy tính, tên các process đang chạy, …
*  Router có thể cung cấp các thông tin : tổng số card, tổng số port, tổng số byte đã truyền/nhận, tên router, tình trạng các port của router, …

Mỗi object có một tên gọi và một mã số để nhận dạng object đó, mã số gọi là Object ID (OID). 
### 3. MIB (Management Information Base ).
* Một MIB chứa các thông tin khác nhau về hoạt động của thiết bị mà agent đang giám sát. Phần mềm quản trị SNMP Manager sẽ thu thập thông tin này qua giao thức SNMP.

### 4. Một sô phương thức sử dụng  trên snmp.

* Giao thức SNMPv1 có 5 phương thức hoạt động, tương ứng với 5 loại bản tin :


--------------------------------------


| Phương thức | Tác dụng|
|------------|:---------------|
|GetRequest   |	 Manager gửi GetRequest cho agent để yêu cầu agent cung cấp thông tinnào đó dựa vào ObjectID (trong GetRequest có chứa OID)|
|GetNextRequest |	 Manager gửi GetNextRequest có chứa một ObjectID cho agent để yêu cầu cung cấp thông tin nằm kế tiếp ObjectID đó trong MIB.|
|SetRequest   | 	Manager gửi SetRequest cho agent để đặt giá trị cho đối tượng của agent dựa vào ObjectID.|
|GetResponse  |	Agent gửi GetResponse cho Manager để trả lời khi nhận được GetRequest/GetNextRequest|
|Trap |	 Agent tự động gửi Trap cho Manager khi có một sự kiện xảy ra đối với một object nào đó trong agent.|

*  Mỗi bản tin đều có chứa OID. OID trong GetRequest cho biết nó muốn lấy thông tin của object nào. OID trong GetResponse cho biết nó mang giá trị của object nào. OID trong SetRequest chỉ ra nó muốn thiết lập giá trị cho object nào. OID trong Trap chỉ ra nó thông báo sự kiện xảy ra đối với object nào.


