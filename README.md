SCP
==========
#### Tìm hiểu lệnh SCP.

 1. SCP là gì?

- SCP  là lệnh dùng để di chuyển file dữ liệu giữa các máy tính chạy hệ điều hành Linux từ xa chỉ cần biết địa chỉ ip
- SCP dùng ssh để di chuyển dữ liệu, có chế độ bảo mật giống như ssh.

 2. Cài đặt và sử dụng:
  2.1 .Cài đặt scp:
    - cài đặt gói ssh :
     ```
      sudo apt-get install -y openssh-server
    ```
   - Kiểm tra ip của máy:
    ```
       ifconfig
    ```
  2.2. Sử dụng scp:
   
    * Trên hệ điều hành linux:(Ubuntu 12.04):
     
      cú pháp sử dụng:
       ```
    scp [-pqrvBC46 ] [-F ssh_config ] [-S program ] [-P port ] [-c cipher ] [- identity_file ] [-o ssh_option ] [[user@ ] host1 : file1 ] [... ] [[user@ ] host2 : file2 ]
            ```
  option:

   ```
    -c  : Chọn thuật toán mã hóa để sử dụng cho việc mã hóa việc truyền dữ liệu. 
    -i  : Lựa chọn các tập tin mà từ đó nhận dạng (khóa riêng) cho RSA xác thực được đọc
    -p : backup lại file gốc.
    -r : sap chép lại toàn bộ thư mục
    
   ```
  2.3.Áp dụng:
   - Đẩy file giữa hai máy ubuntu:
   ```
       scp ubuntu1204.qcow2 root@'192.168.1.15':/root
   ```
   -Copy  file "foobar.txt" từ remote host đến local host
   
   ```
      scp your_username@remotehost.edu:foobar.txt /some/local/directory
   ```
   ========================================================================================================================
   
   