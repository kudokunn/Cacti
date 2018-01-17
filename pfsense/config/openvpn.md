# Openvpn trên pfsense
----------------------------

### Bước 1: Tạo certificate cấp phát cho server và user

#### a. Tạo CA(Certificate Authority Authority).

System > Certificate Manager > CAs chọn Add.

![]( pfsense/IMAGE_PFSENSE/openvpn1.jpg )

> Cấu hình tương tự.

![]( pfsense/IMAGE_PFSENSE/Screenshot from 2017-12-14 14-48-00.png)

#### b. Tạo server Certificate 
Chuyển Certificate tab chọn Add.

![]( pfsense/IMAGE_PFSENSE/vpn1.jpg  )

> Cấu hình tương tự 

![]( pfsense/IMAGE_PFSENSE/Screenshot from 2017-12-14 15-45-05.png  ) 

* Common Name điền địa chỉ wan ip. 

#### c. Tạo user.

![]( pfsense/IMAGE_PFSENSE/vpn2.jpg)




## Bước 2: Tải gói "openvpn-client-export" packages

System >  Package Manager > Availables Packages tìm cài đặt gói "openvpn-client-export".

![]( pfsense/IMAGE_PFSENSE/vpn3.jpg)

## Bước 3: Cấu hình VPN sử dụng winzard  method

VPN > OPENVPN > Winzard.

![]( pfsense/IMAGE_PFSENSE/vpn5.jpg)


* Mục Select an Authentication Backend Type chọn "local User ACcess.

* Mục Choose a Certificate Authority (CA) chọn CA khởi tạo trên.

* Mục Choose a Server Certificate chọn Certificate khởi tạo trên,

* Mục server Setup 
          
          * Tích chọn Enable authentication of TLS packets và Automatically generate a shared TLS authentication key.
          * Auth Digest Algorithm : SHA256.
          * Tunnel Network : địa chỉ tunnel muốn đặt
          * Local network: địa chỉ mạng ip la.
          * Concurrent Connections: số lượng máy tối đa được truy cập.

* Mục Firewall Rule Configuration tích chọn Firewall Rule và OpenVPN rule.
Finish kêt thúc 

## Bước 4: Sử dụng openvpn client truy cập 

* VPN > OPENVPN > CLIENT EXPORT > tải file Inline Configurations:

* Trên cli sudo apt-get install openvpn cài đặt vpn.

* Sử dụng lệnh sudo openvpn --config *** (Đường`dẫn thư mục tải file Inline Configurations trên máy).


