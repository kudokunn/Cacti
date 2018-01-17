# Pfsense

## I. Pfsense là gì

pfSense là một ứng dụng có chức năng định tuyến vào tường lửa mạnh và miễn phí, ứng dụng này sẽ cho phép bạn mở rộng mạng của mình mà không bị thỏa hiệp về sự bảo mật.

![pfsense](pfsense/IMAGE_PFSENSE/pfSense-Logo.jpg)

Vì pfsense là một firewall mềm nên cần ít nhất là 2 card mạng một card là wan (internet) và lan (private) .

Chúng ta sẽ thiết lập lại "Virtual Network  Editor"  bằng cách chọn  ""Edit ->  Virtual  Network  Editor"

Thiết lâp lại chế độ 2 card mạng:  1 card  để chế độ Bridged (gắn với card  Ethernet  của laptop  thật ), 1  card để chế độ Hostonly .

## Ưu điểm của pfsense : 
* Hoàn toàn miễn phí, giá cả là ưu thế vượt trội của tường lửa pfsense.
* pfSense hoạt động rất ổn định với hiệu năng cao.
* pfSense không cần phần cứng phải mạnh
* pfSense hoạt động như một thiết bị mạng tổng hợp với đây đủ tính năng
* PfSense hỗ trợ rất nhiều plugin để thiết lập thêm các tính năng hữu ích

## Nhược điểm của pfsense :
* Vì là fiewall mềm nên đối với hệ thống quá lớn sẽ không đảm bảo được.
* Tốc độ và độ bảo mật của hardware firewall tốt hơn software firewall (pfsense).
* Performance pfsense không bằng được firewall cứng.

## II. Cài đặt pfsense

* Bước 1: Tải file iso của pfsense 

Bạn có thể vào địa chỉ sau để tải file ISO của pfSense : [https://nyifiles.pfsense.org/mirror/downloads/](https://nyifiles.pfsense.org/mirror/downloads/pfSense-CE-2.4.1-RELEASE-amd64.iso.gz "64bit" )

* Bước 2: Chọn 1

![pfsense](/uploads/3062d235d63b7d50188bb087cf143ad3/1.JPG)

* Bước 3: Sau khi cài xong 

![pfsense](/uploads/7b264d8129b67f26854fac37e2f34479/2.JPG)

    1. ấn 1 để set card mạng (card nào là lan or wan)

    2. ấn 2 để set ip cho card mạng (có thể set ip và bật dhcp cho card lan)

    3. reset password cho đăng nhập vào pfsenqua wed 

    4. đặt lại mặc định toàn bộ cấu hình

    5. restart máy (có 4 kiểu reboot)

    6. tắt máy 

    7. ping đến ip nào đó or host name 

    8. .....

* Bước 4: Từ 1 máy trong cùng mạng Lan kết nối vào pfsense qua wed
    cú pháp : http://"ip lan pfsense".
    user : admin,
    pass default : pfsense

![pfsense](/uploads/353b8880a1b5028f4446fa8dd66163ab/pfsense.JPG)

* Bước 5: Trong pfsense sẽ có các dịch vụ, giao thức, các rule, ..... để cấu hình 

![pfsense_1](/uploads/7a9e8f947084cac2a0228e45d310f997/pfsense_1.JPG)

* Bước 6: Bật snmp trong service để sử dụng monitor snmp mặc định sẽ chạy ở port 161.

![pfsense_1](pfsense/IMAGE_PFSENSE/Capture.JPG)

* Bước 7: Tích chọn enable snmp bật giao thức và Read Community String để set key kết nối đến

![pfsense_1](pfsense/IMAGE_PFSENSE/pfsensesnmp.JPG)


* Sau khi bật snmp xong và set string để kết nối sẽ sang máy đã cài các phần mềm monitor để theo dõi qua snmp

Install và configure Pfsense
## III.Sử dụng pfSense
* Cấu hình firewall trên pfsense. [tại đây](pfsense/config/firewall.md)

* Cài đặt openvpn. [tại đây]( pfsense/config/openvpn.md )

* Cấu hình thêm interface.

* Tính năng VPN của pfSense hỗ trợ IPSec, OpenVPN và cả PPTP.
* Khả năng kết nối WAN và sự cân bằng tawir của pfSense cũng là một điểm mạnh. Ta hoàn toàn có thể thêm pfSense vào danh sách các giải pháp firewall/router đang phát triển mạnh, giá thành thấp và hoàn toàn miễn phí.
* Việc kiểm tra và ghi các sự kiện trong pfTools hoàn toàn dễ dàng, nó sẽ thể hiện bằng một biểu đồ RRDtool thời gian thực và hiển thị ảo mỗi quá trình trong máy tính chẳng hạn như: lưu lượng, các quá trình của hệ thống...
* Bên cạnh đó còn hỗ trợ các công cụ chuẩn đoán bên trong như traditional traceroute và và packet sniffer giúp cải thiện việc khắc phục sự cố một cách hiệu quả và rất hữu dụng.
* Mặc dù còn hạn chế nhưng khả năng của pfSense hoàn toàn cung cấp, đáp ứng đủ cho một mạng văn phòng, nó cũng dễ dàng quản lý  và cung cấp nhiều tính năng để như trong các sản phẩm thương mại nhưngmột số tính năng đã được sử dụng trong các doanh nghiệp lớn vẫn còn nhiều hạn chế nên pfSense cần được bổ sưng thêm nhiều tính năng mới để đáp ứng cho các doanh nghiệp lớn. 
