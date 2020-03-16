## Bonding là gì ?
- Là quá trình gộp hai hoặc nhiều interface vật lý lại với nhau, tạo thành một interface khác.
- Tăng hiệu suất, dư giả thông lượng network và bandwidth.
- Có hiệu năng cao: khi một interface vật lý bị down thì đường truyền vẫn ổn định.
## Types of
- mode = 0 (balance round-robin)
  +  Ví dụ có hai gói tin được chuyển thì gói 1 là Master, gói là qua Slave 
- mode = 1 (active backup)
  + Chỉ có một slave được hoạt động, nếu slave down thì slave khác mới được dùng.
- mode = 2 (balance XOR)
  + source MAC và destation MAC được XOR với nhau
- mode = 3 (broadcast)
  + nó transmitted mọi thứ trên tất cả các interface slave
- mode = 4 (802.3ad)
  + Nó đã tạo tổng hợp các nhóm có cùng speed.
  + Việc lựa chọn slave cho lưu lượng dựa trên phương thức băm.
- mode = 5 (balance-tlb)
  + Lưu lượng outgoing được phân phối dựa trên current load của mỗi slave, và lưu lượng incoming được nhận bởi current slave
- mode = 6 (balance-alb)
  + không yêu cầu chế độ chuyển đổi đặc biệt, load balance thông qua việc send and reply gói tin ARP cho nhau.
