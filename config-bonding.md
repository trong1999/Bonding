- Kiểm tra và tạo thêm card mạng vật lý tùy thuộc vào nhu cầu sử dụng cho bonding
- <img src="https://i.imgur.com/EF8zbkj.png">
- Tạo các file config như sau 
  + **/etc/sysconfig/network-scripts/ifcfg-bond0**
  + <img src="https://i.imgur.com/ngFBXE1.png">
  + **/etc/sysconfig/network-scripts/ifcfg-ens36**
  + <img src="https://i.imgur.com/X7jYKqr.png">
  + **/etc/sysconfig/network-scripts/ifcfg-ens37**
  + <img src="https://i.imgur.com/wznLm3j.png">
- Chọn chế độ load balancing => ở đâu ta sẽ dùng mode=0 (round-robin)
  + **/etc/modprobe.conf**
  + <img src="https://i.imgur.com/0e42FaX.png">
  + miimon=100 : time = miliseconds, sau mỗi mii giây này thì nó sẽ check failures một lần
  + **modprobe bonding**
  + Kiểm tra **cat /proc/net/bonding/bond0**
  + <img src="https://i.imgur.com/4aGaTen.png">
- Khởi động lại network
  + **systemctl restart network.service**
  + Nếu fail, ta check message log
  + <img src="https://i.imgur.com/MjKzQvn.png">
  + **/var/log/message**
  + <img src="https://i.imgur.com/qcre3gi.png">
  + Fix thế nào?
  + **systemctl stop NetworkManager**
  + **systemctl disable NetworkManager**
  + <img src="https://i.imgur.com/N2Myj0P.png">
  + Sau đó start lại netwwork : **systemctl restart network.service**
  + <img src="https://i.imgur.com/HHAXb2m.png">
- Kiểm tra : 
  + **cat /proc/net/bonding/bond0**
  + <img src="https://i.imgur.com/oedaAfb.png">
  + **ip a**
  + <img src="https://i.imgur.com/UOxEVhz.png">
