# RSA cryptosystem

RSA là một thuật toán mã hóa khóa công khai được phát triển bởi Ron Rivest, Adi Shamir và Leonard Adleman vào năm 1977. RSA sử dụng một cặp khóa, gồm một khóa công khai và một khóa bí mật khác nhau, để mã hóa và giải mã thông điệp.

Thuật toán RSA dựa trên tính khó của việc phân tích một số nguyên thành các thừa số nguyên tố lớn. Thuật toán RSA thực hiện việc mã hóa thông điệp bằng cách sử dụng khóa công khai của người nhận, và chỉ người nhận có khóa bí mật tương ứng mới có thể giải mã thông điệp.

Quá trình mã hóa RSA bắt đầu bằng cách chọn hai số nguyên tố lớn p và q. Số n được tính bằng tích của p và q, và được sử dụng để tạo ra khóa công khai và khóa bí mật. Khóa công khai bao gồm hai thành phần: số n và một số e được chọn sao cho e là số nguyên tố cùng nhau với tổng số các thừa số nguyên tố của φ(n) = (p-1) và (q-1). Khóa bí mật bao gồm cũng bao gồm hai thành phần: số n và số d được tính bằng cách tìm số nguyên tố nghịch đảo của e theo modulo φ(n).

Khi người gửi muốn mã hóa thông điệp để gửi cho người nhận, họ sử dụng khóa công khai của người nhận để mã hóa thông điệp. Người nhận sau đó sử dụng khóa bí mật của mình để giải mã thông điệp.

RSA được sử dụng rộng rãi trong các ứng dụng bảo mật, như là một phương tiện để bảo vệ thông tin cá nhân và các dữ liệu quan trọng khác trên mạng. Nó cũng được sử dụng trong các hệ thống thanh toán điện tử và các giao thức bảo mật truyền thông.
## 1. Sơ đồ mã hóa
![alt text](https://lh3.googleusercontent.com/eQ91TLuLMp9XJotjItCmkwhnt0FainHwC6qSPfOG-y7ztMXmRnXEiFoLSW1bt6VnPZn9kYlbFadaNRVIEaPqITkUwf2ASoT1e1nwjuVkbrYUDurZZCGu4DzswShhyfoKu3gYK6R8HA=w2400)
## 2. Độ bảo mật
Hiện nay, mã hóa RSA vẫn được coi là một trong những thuật toán mã hóa khóa công khai phổ biến và mạnh nhất được sử dụng trong các ứng dụng bảo mật. Với cấp độ bảo mật hiện tại, tôi khuyên bạn nên sử dụng khóa độ dài tối thiểu là 2048 bit, có thể bảo vệ thông tin chống lại đa số các cuộc tấn công đáng kể.

Máy tính lượng tử vẫn chưa có thể giải được mật mã RSA hiệu quả. Tuy nhiên, các nhà nghiên cứu đang phát triển các thuật toán giải mã khóa công khai mới dựa trên máy tính lượng tử, như [thuật toán Shor](https://vi.wikipedia.org/wiki/Thu%E1%BA%ADt_to%C3%A1n_Shor), có thể phá các hệ thống mã hóa khóa công khai hiện tại, bao gồm RSA, các máy tính lượng tử cần đủ mạnh để thực hiện các thuật toán này, và hiện nay vẫn chưa có máy tính lượng tử thực tế đủ mạnh để giải mã RSA với độ dài khóa lớn.

Sử dụng khóa kích thước lớn có thể làm cho quá trình mã hóa và giải mã chậm hơn, nhưng đồng thời nó cũng làm cho nó khó khăn hơn đối với bất kỳ kẻ tấn công nào muốn phá vỡ hệ thống mã hóa của bạn. Những ứng dụng mật mã hiện nay đang dần chuyển sang sử dụng mã hóa đường cong Elliptic (ECC) thay vì RSA, bởi ECC cho phép sử dụng khóa có kích thước nhỏ hơn mà vẫn đảm bảo tính bảo mật cao, giúp tăng cường hiệu quả và tốc độ xử lý trong các hệ thống bảo mật.
