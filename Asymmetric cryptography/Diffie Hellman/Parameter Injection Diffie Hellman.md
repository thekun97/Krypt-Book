# Parameter Injection Diffie Hellman

Parameter Injection là một kỹ thuật tấn công nhằm thay đổi các tham số của thuật toán để có thể tính toán ra khóa bí mật chung bằng 0 và giải mã các thông điệp được mã hóa bằng khóa này.
Nếu kẻ tấn công có thể ngồi ở giữa phiên trao đổi khóa và sửa đổi các thông báo được truyền, thì hắn có thể kiểm soát khóa và giải mã tất cả lưu lượng. Phương pháp tấn công được mô tả sau đây:

<p align="center">
  <img src="https://lh3.googleusercontent.com/CgeU10cAdH-JGpLptJ3PAMb_iQX9_S4mgfdPndupsM6WsmlNdk1i8b_okJ2O-ExzIL6M1SIXRaojn0EWR66wGpjOPEsZogKSRpxxZuv-pIhwT0_P5_S4OB-gk0fpWUPaIW8TwQH-cA=w2400" />
</p>

Nếu kẻ tấn công thay thế A và B bằng p, thì cả Alice và Bob sẽ tính toán khóa là p<sup>a</sup> mod p  = p<sup>b</sup> mod p = 0. Sau đó, 0 được băm và sử dụng làm khóa đối xứng cho mã hóa AES, vì vậy kẻ tấn công có thể giải mã tất cả các thông điệp.

## Biện pháp bảo mật
- Sử dụng chữ ký số để xác thực các tham số trao đổi khóa được sử dụng.
