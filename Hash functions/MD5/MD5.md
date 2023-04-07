
# MD5 Hash Function

Hàm hash MD5 (viết tắt của Message-Digest algorithm 5) là một thuật toán mã hóa băm (hashing algorithm) được sử dụng để chuyển đổi dữ liệu văn bản đầu vào thành một giá trị băm (hash value) có độ dài cố định là 128 bit.
MD5 được phát triển bởi Ronald Rivest vào năm 1991 để thay thế cho hàm băm trước đó  MD4 và đã được sử dụng rộng rãi trong các ứng dụng bảo mật như xác thực người dùng và kiểm tra tính toàn vẹn của tệp tin. 
## Thuật toán 
MD5 chuyển đổi thông tin đầu vào có chiều dài không cố định thành một kết quả có chiều dài không đổi 128 bit. Dữ liệu đầu vào được chia thành các khối cố định độ dài và thêm các bit bù để đảm bảo kích thước khối dữ liệu đầu vào là bội số của 512 bit (đây được gọi là "padding"). Cụ thể, MD5 chèn một bit 1 vào cuối dữ liệu đầu vào, sau đó thêm các bit 0 cho đến khi kích thước của khối dữ liệu đầu vào còn lại bằng 64 bit. Sau đó, MD5 sử dụng 64 bit cuối cùng của khối dữ liệu đầu vào để mã hóa độ dài của dữ liệu đầu vào.

<p align="center">
<img src="https://images.viblo.asia/63418bec-fc6d-4612-bc2d-047d36c5f212.png">
</p>
Sau khi padding xong, khối dữ liệu đầu vào sẽ được chia thành nhiều khối con có kích thước là 512 bit (64 byte) mỗi khối. MD5 xử lý từng khối con này để tính toán giá trị hash đầu ra.

Tuy nhiên, do các vấn đề liên quan đến tính bảo mật, MD5 đã được thay thế bởi các thuật toán mã hóa băm khác như SHA-1, SHA-256, SHA-3. Cụ thể các vấn đề của MD5:
- Đụng độ: MD5 không đảm bảo tính chống đụng độ (collision resistance), tức là có thể tạo ra hai chuỗi khác nhau nhưng có cùng giá trị băm MD5. Điều này có thể dẫn đến các cuộc tấn công như xâm nhập giả mạo (spoofing) hoặc xâm nhập vào dữ liệu (data injection).

- Tấn công bằng mã hóa ngược (reversing attack): MD5 cũng không đảm bảo tính chống mã hóa ngược (reversibility), tức là từ giá trị băm MD5, có thể dễ dàng tìm ra đầu vào ban đầu. Điều này dẫn đến việc các kẻ tấn công có thể sử dụng các phương pháp như tấn công từ điển (dictionary attack) hoặc tấn công brute-force để tìm ra đầu vào của giá trị băm MD5.

Trong Python, ta có thể sử dụng module hashlib để tính toán giá trị băm MD5 của một chuỗi như sau:
```python
import hashlib
text = "Hello, world!" 
hash_md5 = hashlib.md5(text.encode()).hexdigest() 
print(hash_md5)
```
Kết quả: 

```python
86fb269d190d2c85f6e0468ceca42a20
```
