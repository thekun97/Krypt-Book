# Advanced Encryption Standard (AES) 

AES (Advanced Encryption Standard) là một thuật toán mã hóa khối đối xứng được sử dụng rộng rãi trong các ứng dụng bảo mật thông tin. AES được chọn làm tiêu chuẩn mã hóa đối xứng cho chính phủ Hoa Kỳ vào năm 2001, thay thế cho DES (Data Encryption Standard). 

Thuật toán AES được thiết kế bởi hai nhà mật mã học người Bỉ là Joan Daemen và Vincent Rijmen. Trước khi được chọn làm tiêu chuẩn mã hóa đối xứng cho chính phủ Mỹ, thuật toán AES đã tham gia cuộc thi thiết kế mã hóa đối xứng "Advanced Encryption Standard" (AES) do Chính phủ Mỹ tổ chức dưới tên là "Rijndael" theo tên của hai tác giả. Khi trở thành tiêu chuẩn mã hóa đối xứng, thuật toán được gọi chung là AES.

AES sử dụng một khối mã hóa cố định với kích thước 128 bit (AES-128), 192 bit (AES-192) hoặc 256 bit (AES-256) và một khóa bí mật cùng kích thước để thực hiện quá trình mã hóa và giải mã.

<p align="center">
  <img src="https://privacycanada.net/app/uploads/2019/01/aes-design-diagram.png" />
</p>

## 2. Quá trình mã hóa
Quá trình mã hóa AES được thực hiện thông qua 5 chức năng chính là AddRoundKey, SubBytes, ShiftRows, MixColumns và KeyExpansion.

<p align="center">
  <img src="https://www.researchgate.net/publication/324796235/figure/fig1/AS:619919657926656@1524811772120/Block-diagram-for-AES-encryption-and-decryption.png" />
</p>

**Add round key** 
<p align="center">
  <img src="https://upload.wikimedia.org/wikipedia/commons/a/ad/AES-AddRoundKey.svg" />
</p>

Bước 1: Tạo ra các khóa con từ khóa bí mật đầu vào
Bước 2: Sử dụng các khóa con để thực hiện các vòng mã hóa để mã hóa dữ liệu vào
Bước 3: Áp dụng hàm trộn (substitution) và dịch chuyển (shift) các giá trị trong khối dữ liệu để tạo ra khối mã hóa kế tiếp
Bước 4: Thực hiện các vòng mã hóa và phần cuối cùng để tạo ra khối mã hóa cuối cùng
Quá trình giải mã tương tự với quá trình mã hóa, nhưng sử dụng các phép toán ngược lại để lấy lại dữ liệu gốc từ khối mã hóa.

AES là một thuật toán rất mạnh và được sử dụng rộng rãi trong nhiều lĩnh vực, bao gồm ngân hàng, tài chính, y tế và quân sự.
## 2. Các dạng tấn công
Hiện nay, AES được coi là một thuật toán mã hóa đối xứng rất an toàn và khó bị tấn công nếu sử dụng đúng cách. Tuy nhiên, vẫn tồn tại một số dạng tấn công mà các kẻ tấn công có thể sử dụng để đánh lừa hệ thống bảo mật.
1.  Tấn công side-channel: Kẻ tấn công sử dụng thông tin phụ thu được từ các bên ngoài hệ thống, chẳng hạn như thời gian phản hồi, công suất tiêu thụ điện năng, hoặc âm thanh, để phá vỡ khóa bí mật. Tuy nhiên, các hệ thống AES thường được thiết kế để ngăn chặn các loại tấn công này.
