
# Elliptic curve cryptography

Mật mã đường cong elliptic (ECC) là họ hệ thống mật mã khóa công khai hiện đại, dựa trên cấu trúc đại số của đường cong elliptic trên trường hữu hạn và độ khó của bài toán logarit rời rạc trên đường cong elliptic (ECDLP).
ECC triển khai được hầu hết các ứng dụng phổ biến của hệ thống mã hóa bất đối xứng: mã hóa/giải mã, chữ ký số và trao đổi khóa.

ECC được coi là sự kế thừa hiện đại một cách tự nhiên của hệ thống mã RSA, bởi vì ECC sử dụng các khóa có kích thước nhỏ hơn rất nhiều cho mã hóa và chữ ký so với RSA ở cùng một mức độ bảo mật và cho khả năng tạo khóa nhanh, ký nhanh, trao đổi khóa nhanh.
Dựa trên toán học của các đường cong elliptic trên các trường hữu hạn, ECC cung cấp một số nhóm thuật toán: 
- Thuật toán chữ ký số ECC: ECDSA (đối với đường cong cổ điển), EdDSA (đối với đường cong Edwards xoắn)
- Thuật toán mã hóa ECC và lược đồ mã hóa lai như ECIES, EEECC.
- Thuật toán trao đổi khóa: ECDH, X25519, FHMQV.

# 1. Nền tảng
Hãy bắt đầu về ECC bằng cách tìm hiểu ý nghĩa của đường cong elliptic. Chúng ta sẽ nghiên cứu các phương trình Weierstrass, có dạng:

$$
Y^{2} = X^{3} + aX + b 
$$

Trên đường cong elliptic, chúng ta có thể định nghĩa một toán tử mà chúng ta gọi là "cộng điểm". Toán tử này nhận hai điểm trên một số đường cong và tạo ra một điểm thứ ba trên đường cong. Cùng với tập hợp các điểm trên một đường cong elliptic, phép "cộng điểm" định nghĩa một phép toán nhóm giao hoán (Abel).

Vậy chúng ta hiểu phép cộng điểm như thế nào?

![diagram of ECC addition](https://cryptohack.org/static/img/ECClines.svg)

Về mặt hình học, ta có thể hiểu phép cộng điểm P + Q như vậy. Vẽ một đường cong elliptic và đánh dấu hai điểm P, Q dọc theo đường cong với tọa độ x, y của chúng. Vẽ đường thẳng đi qua hai điểm, kéo dài đường thẳng cho đến khi nó cắt đường cong của bạn lần thứ ba. Đánh dấu giao điểm mới này là R. Cuối cùng, lấy phản chiếu của R theo trục x để tạo ra R' = R(x, -y). Kết quả của phép cộng điểm là P + Q = R'

Nếu chúng ta muốn cộng hai điểm giống nhau: P + P thì sao? Chúng ta không thể vẽ một đường duy nhất đi qua một điểm, nhưng chúng ta có thể chọn một đường duy nhất bằng cách tính tiếp tuyến của đường cong tại điểm đó. Tính tiếp tuyến tại điểm P. Tiếp tục kẻ đường thẳng cho đến khi nó cắt đường cong tại điểm R. Phản chiếu điểm này qua trục x: 
P + P = R' = R(x,-y).

Điều gì xảy ra nếu không có điểm giao thứ 3? Đôi khi bạn sẽ chọn hai điểm P, Q và đường thẳng sẽ không chạm vào đường cong nữa. Trong trường hợp này, chúng ta nói rằng đường thẳng giao với điểm (O) là một điểm duy nhất nằm ở cuối mỗi đường thẳng đứng ở vô cực. Như vậy, điểm bổ sung cho một đường cong elip được xác định trong không gian 2D, với một điểm bổ sung nằm ở vô cực.

Hình trên là mặt cắt ngang của đường cong elliptic, dưới đây là hình dạng đường cong trong không gian 3D

<p align="center">
  <img src="https://www.allaboutcircuits.com/uploads/articles/Curve_Cryptography_fig01.gif">
</p>

Phép nhân vô hướng được xác định bằng phép cộng lặp lại: 3P = P + P + P.
Trong elliptic không có phép nhân giữa 2 điểm của đường cong, và **không** có phép chia vô hướng:
Q = 3P => P = Q/3
vì bài toán tìm n là bài toán logarit rời rạc - một bài toán khó có thể giải được trong thời gian đa thức.
