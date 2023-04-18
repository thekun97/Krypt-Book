
# MD5 Hash Function

Hàm hash MD5 (viết tắt của Message-Digest algorithm 5) là một thuật toán mã hóa băm (hashing algorithm) được sử dụng để chuyển đổi dữ liệu văn bản đầu vào thành một giá trị băm (hash value) có độ dài cố định là 128 bit.
MD5 được phát triển bởi Ronald Rivest vào năm 1991 để thay thế cho hàm băm trước đó  MD4 và đã được sử dụng rộng rãi trong các ứng dụng bảo mật như xác thực người dùng và kiểm tra tính toàn vẹn của tệp tin. 
## Thuật toán 
MD5 chuyển đổi thông tin đầu vào có chiều dài không cố định thành một kết quả có chiều dài không đổi 128 bit. Dữ liệu đầu vào được chia thành các khối cố định độ dài và thêm các bit bù để đảm bảo kích thước khối dữ liệu đầu vào là bội số của 512 bit (đây được gọi là kỹ thuật "padding"). Cụ thể, MD5 chèn một bit 1 vào cuối dữ liệu đầu vào, sau đó thêm các bit 0 cho đến khi kích thước của khối dữ liệu đầu vào còn lại bằng 64 bit. Sau đó, MD5 sử dụng 64 bit cuối cùng của khối dữ liệu để đại diện mã hóa độ dài của dữ liệu đầu vào.

<p align="center">
<img src="https://images.viblo.asia/63418bec-fc6d-4612-bc2d-047d36c5f212.png">
</p>
Sau khi padding xong, khối dữ liệu đầu vào sẽ được chia thành nhiều khối con có kích thước là 512 bit (64 byte) mỗi khối. MD5 xử lý tuần tự khối con này để tính toán giá trị hash đầu ra.
Đầu tiên, thuật toán khởi tạo một giá trị H0 là một dãy 128 bit, được chia thành 4 từ 32 bit, với ký hiệu và A,B,C và D. Giá trị của các hằng số A,B,C,D như sau:

```
A = 0x67452301
B = 0xefcdab89
C = 0x98badcfe
D = 0x10325476
```

Khối M<sub>1</sub> kết hợp với giá trị khởi tạo H<sub>0</sub>, đi qua hàm F để tính giá trị H<sub>1</sub>, tiếp theo khối M<sub>2</sub> kết hợp với giá trị H<sub>1</sub> để cho ra giá trị H<sub>2</sub>, cứ như vậy cho đến khối M<sub>N</sub> thì kết quả giá trị băm cuối cùng là H<sub>N</sub>

Khối M<sub>i</sub> 512 bit được chia thành 16 khối 32 bit. 16 giá trị này được lặp lại 4 lần tạo thành dãy 64 giá trị.
Việc xử lý một khối thông điệp bao gồm bốn giai đoạn tương tự nhau với 4 dãy 64 giá trị trên, được gọi là vòng; mỗi vòng được tạo thành từ 16 thao tác tương tự dựa trên một hàm phi tuyến, phép cộng modular và phép xoay trái. Hình dưới minh họa một thao tác trong một vòng.
<p align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a5/MD5_algorithm.svg/300px-MD5_algorithm.svg.png">
</p>

Ở mỗi vòng, hàm F sẽ khác nhau như sau:

F<sub>1</sub>(B,C,D) = (B and C) or (not B and D)

F<sub>2</sub>(B,C,D) = (B and D) or (C and not D)

F<sub>3</sub>(B,C,D) = B xor C xor D

F<sub>4</sub>(B,C,D) = C xor (B or not D)


Hiện nay, thuật toán băm MD5 đã không còn được coi là an toàn trong lĩnh vực bảo mật thông tin. Các nhà nghiên cứu đã phát hiện ra nhiều lỗ hổng và tấn công hiệu quả trên thuật toán này. Phương pháp tấn công collision attacks cho phép kẻ tấn công tìm thấy hai thông điệp khác nhau có cùng giá trị băm của hàm MD5 (vấn đề về tính đụng độ). Do đó, nếu cần sử dụng hàm băm để bảo mật thông tin, các thuật toán khác như SHA-2 hay SHA-3 nên được sử dụng thay thế cho MD5.

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
