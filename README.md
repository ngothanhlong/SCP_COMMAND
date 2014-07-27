SCP
==========
#### Tìm hiểu lệnh SCP.

 I. SCP là gì?
- SCP (Secure Copy – Sao chép an toàn) là một ứng dụng sử dụng SSH để mã hóa toàn bộ quá trình chuyển tập tin.
- SCP  là lệnh dùng để di chuyển file dữ liệu giữa các máy tính chạy hệ điều hành Linux từ xa chỉ cần biết địa chỉ ip
- SCP dùng ssh để di chuyển dữ liệu, có chế độ bảo mật giống như ssh.

 II. Cài đặt và sử dụng:
  2.1 .Cài đặt scp:
    - cài đặt gói ssh trên các máy cần trao đổi dữ liệu:
     ```
      sudo apt-get install -y openssh-server
    ```
   - Kiểm tra ip của máy:
    ```
       ifconfig -a 
    ```
  2.2. Sử dụng scp:
   
    * Trên hệ điều hành linux:(Ubuntu 12.04):
     
      cú pháp sử dụng chuẩn:
       ```
       scp [-pqrvBC46 ] [-F ssh_config ] [-S program ] [-P port ] [-c cipher ] [-i identity_file ] [-o ssh_option ] [[user@ ] host1 : file1 ] [... ] [[user@ ] host2 : file2 ]
       
	  ```
  option:
   ```
    -c  : Chọn thuật toán mã hóa để sử dụng cho việc mã hóa việc truyền dữ liệu.
   
    -i  : Lựa chọn các tập tin mà từ đó nhận dạng (khóa riêng) cho RSA xác thực được đọc
	
    -p : backup lại file gốc.
	
    -r : sao chép lại toàn bộ thư mục.
	
	-C : nén  file trong khi thực hiện:
	   
	-v : cung cấp thông tin chi tiết của quá trình.
   ```
	- Cú pháp cơ bản:
	    ```
		  scp <file_name> username@host_remote :/<thư mục>
		```

  2.3.Áp dụng:
     - Mô hình:
	   
         <img src="http://i.imgur.com/9w0qELk.png "> 
		 
		 
     |------------------------------|----------------------------- |
	 | Local : ubuntu1204           | Remote : ubuntu-server-1204  |
	 | ip:    : 192.168.1.14/24     | ip     : 192.168.1.15/24     |
     | -----------------------------|------------------------------|
	 
	 
   - Đẩy file "ubuntu1204.qcow2" lên máy Remote /root:
   ```
       scp ubuntu1204.qcow2 root@'192.168.1.15':/root
   ```
   -Copy  file "foobar.txt" từ remote host sang máy local/home/kvm
   
   ```
      scp  root@:foobar.txt  /home/kvm
   ```
	 -  
   ========================================================================================================================
   * Trên hệ điều hành windows. Ta có thể dùng phần mềm có tính năng tương tự là: WinSCP
   - Dùng để trao đổi dữ liệu giữa máy windows với máy Linux.
   - Tải phần mềm và cài đặt:
     ```
	   http://winscp.net/eng/download.php
	 ```
	- Chạy file .exe để  cài đặt
	 
	
	- Sử dụng winscp: 
	 Đăng nhập vào phần mềm:
	   <img src="http://i.imgur.com/gIdXo3C.png">
	 Giao diện chính phần mềm:
<img src="http://i.imgur.com/NqimEhz.png">


   => Từ giao diện phần mềm copy file từ thư mục trong  máy windows sang máy thư mục trong máy linux . OK đợi đến lúc thành công