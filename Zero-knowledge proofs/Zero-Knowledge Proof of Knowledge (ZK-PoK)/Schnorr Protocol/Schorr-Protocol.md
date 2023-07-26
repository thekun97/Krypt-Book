# Schnorr Protocol

Giải thuật Schnorr Protocol là một thuật toán chứng minh không tiết lộ tri thức (zero-knowledge proof) cho bài toán logarithm rời rạc (discrete logarithm problem). Được đặt tên theo nhà toán học Claus Schnorr, thuật toán này cho phép một bên chứng minh cho bên khác rằng nó có kiến thức về giá trị bí mật, nhưng không tiết lộ giá trị đó.

Giả sử Alice muốn chứng minh cho Bob rằng cô ấy có giá trị bí mật x, và Bob sẽ xác minh việc chứng minh đó mà không biết giá trị của x.

Dưới đây là mô tả cụ thể của giải thuật Schnorr Protocol có tương tác:

**Thiết lập:**
Chọn một số nguyên tố lớn p và một số nguyên tố q sao cho q là một ước số của p-1.
Tìm một phần tử nguyên thủy g trong trường modulo p, nghĩa là g là số nguyên tố và g^(p-1) mod p = 1, nhưng g^q mod p ≠ 1.
Chọn một số ngẫu nhiên k thuộc [1, q-1] và tính A = g^k mod p.

**Bước chứng minh:**
Chọn một số ngẫu nhiên r thuộc [1, q-1].
Tính giá trị R = g^r mod p.
Tính giá trị e = H(R || A || m), trong đó H là hàm băm, A là giá trị công khai của người chứng minh (A = g^k mod p), và m là thông điệp cần chứng minh (ví dụ: một thông điệp văn bản).
Tính giá trị s = (r + e*x) mod q, trong đó x là giá trị bí mật và q là một số nguyên tố lớn liên quan đến p.
Gửi bằng chứng (R, s) cho bên xác minh.

**Bước xác minh:**
Bên xác minh tính giá trị e' = H(R || A || m).
Tính giá trị R' = (g^s * A^e') mod p.
Nếu R' = R, tức là xác minh thành công, và bên xác minh biết rằng bằng chứng được cung cấp bởi bên chứng minh là đáng tin cậy.