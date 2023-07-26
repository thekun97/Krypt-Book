# Schnorr Protocol

Giao thức Schnorr là một thuật toán chứng minh không tiết lộ tri thức (zero-knowledge proof) cho bài toán logarithm rời rạc (discrete logarithm problem). Được đặt tên theo nhà toán học Claus Schnorr, thuật toán này cho phép một bên chứng minh cho bên khác rằng nó có kiến thức về giá trị bí mật, nhưng không tiết lộ giá trị đó.

Giả sử Alice muốn chứng minh cho Bob rằng cô ấy có giá trị bí mật x, và Bob sẽ xác minh việc chứng minh đó mà không biết giá trị của x.

Dưới đây là mô tả cụ thể của giải thuật Schnorr Protocol có tương tác:

Giả sử Prover muốn chứng minh rằng họ biết một giá trị log rời rạc x của một phần tử trong nhóm $h=g^x \in G$, trong đó G là một nhóm bậc q và g làm phần tử sinh của G 

**Bước 1:**

Prover chọn ngẫu nhiên phần tử $r \in Z_{q}$

Tính $u = g^r$

Gửi giá trị u cho Verifier  

**Bước 2:**

Verifier chọn ngẫu nhiên giá trị $c \in Z_{q}$

Gửi giá trị c cho Prover  

**Bước 3:**

Prover tính $z = r + cx$

Gửi giá trị z cho Verifier 

**Bước xác minh:**

Verifier tính toán giá trị $g^z$

Nếu $g^z = u.h^c$ tức là xác minh thành công, và bên xác minh biết rằng bằng chứng được cung cấp bởi bên chứng minh là đáng tin cậy.
