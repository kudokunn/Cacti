# Firewall trên pfsense
----------------------------

### 1.  Alias 

> Alias cho phép gom nhóm các ports, host hoặc network khác nhau chung nhóm để thiết lập những rules được dễ dàng và nhanh hơn.

![]( pfsense/IMAGE_PFSENSE/alias (7).png)


> Tạo 1 alias add

![]( pfsense/IMAGE_PFSENSE/alias (1).png)

* Host: là một địa chỉ IP cụ thể, một tên DNS, một tên của host nào đó…  
* Network: định nghĩa một mạng cụ thể, ví dụ: 172.16.6.34/24  
* Port: định nghĩa danh sách các port dịch vụ cần áp dụng chính sách.
* URL: là địa chỉ cụ thể như http://google.com

## 2. Rules 

Có thể mở, chặn, truy cập, điều chỉnh hướng đi của các kết nối trong hệ thống mạng thông qua các thiết lập trên Firewall rules.

![]( pfsense/IMAGE_PFSENSE/fire1.png )

> ADD 1 rule 

![]( pfsense/IMAGE_PFSENSE/fire4.png )

* Action 
    * pass: cho phép
    * block: chặn
    *  reject: chặn và có thêm gửi cảnh báo 
* Disaabled: vô hiệu hóa rule

* Protocol: chọn giao thức chưa dịch vụ hoặc port cần cho phép hoặc chặn 

* Source:  
       * Source:Chọn địa chỉ bên trong cần ra ngoài(dải mạng WAN,LAN, Alias)     
       * Source Port Range : chọn dịch vụ cần mở hoặc chặn ở mạng interface cần rule

* Destination:
       * Destination: Chọn địa chỉ hoặc dải mạng đích cần tới 
       * Destination Port Range:dịch vụ cần mở hoặc chặn của mạng cần trỏ tới 
> Sau khi add 

![]( pfsense/IMAGE_PFSENSE/fire5.png )

Floating : rules trên phần này có thể áp dụng cho một interface, hoặc được gán  1 rule dùng chung cho nhiều interface, việc dùng chung một Firewall Rules sẽ giúp giảm bớt các rules, làm cho Firewall server hoạt động hiệu quả và tiết kiệm tài nguyên phần cứng. Floating rules cung cấp các tính năng mở rộng hơn so với inerface rules.
WAN, lAN, OTP1.


## 3. Schedules 
* Setup lịch biểu trên firewall

* chedules Name: Tên của Schedules.
    * Description: Chú thích 
    * Date: click chuột vào ngày cần chọn.
    * Time: Giờ.
    * Chọn Add time.


