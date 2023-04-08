
# Zero-Knowledge Proof
Zero-Knowledge Proof (ZKP) là một kỹ thuật được sử dụng trong lĩnh vực mật mã học để xác thực thông tin một cách tin cậy mà không cần tiết lộ thông tin đó. Trong ZKP, người chứng minh có thể chứng minh cho người nhận rằng mình có một thông tin nhất định mà không cần phải tiết lộ nó cho người nhận.

Ví dụ, giả sử người chứng minh muốn chứng minh rằng mình biết mật khẩu đăng nhập vào một tài khoản nhưng không muốn tiết lộ mật khẩu đó cho người nhận. Thay vì tiết lộ mật khẩu, người chứng minh có thể sử dụng ZKP để chứng minh cho người nhận rằng mình biết mật khẩu đó bằng cách thực hiện các bước tính toán phức tạp mà chỉ có người biết mật khẩu mới có thể thực hiện được.

ZKP được ứng dụng trong nhiều lĩnh vực, bao gồm chứng thực danh tính, bầu cử trực tuyến, và bảo mật giao dịch trên blockchain. Kỹ thuật này đóng vai trò quan trọng trong việc đảm bảo tính toàn vẹn và bảo mật thông tin trong các hệ thống mạng thông tin và các ứng dụng trực tuyến.

![Zero-Knowledge Proof (ZKP) — Explained | Chainlink](https://blog.chain.link/wp-content/uploads/2021/07/zero-knowledge-proof-1024x772.png)

## 1.  Thuật toán Zero-Knowledge Proof
Trong ZKP, zk-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge) và zk-STARK (Zero-Knowledge Scalable Transparent Argument of Knowledge) là hai thuật toán ZKP được sử dụng phổ biến nhất hiện nay.

zk-SNARK đã được giới thiệu lần đầu tiên bởi Eli Ben-Sasson và các đồng nghiệp của ông tại Đại học Weizmann vào năm 2013. Thuật toán này đã được sử dụng rộng rãi trong các ứng dụng blockchain như Zcash và Ethereum. zk-SNARK cho phép chứng minh statement với kích thước nhỏ, không tốn quá nhiều tài nguyên tính toán và đảm bảo tính bảo mật cao.

zk-STARK được giới thiệu vào năm 2018 bởi Eli Ben-Sasson và các đồng nghiệp tại Đại học Technion. Thuật toán này có khả năng bảo mật cao hơn so với zk-SNARK, đảm bảo tính phân quyền và không yêu cầu sự tin tưởng vào bên chứng minh. Tuy nhiên, zk-STARK có tốc độ chậm hơn so với zk-SNARK và đòi hỏi nhiều tài nguyên tính toán hơn.

Cả zk-SNARK và zk-STARK đều có tính năng và ưu điểm riêng, và có thể được sử dụng trong nhiều ứng dụng khác nhau. Do đó, lựa chọn thuật toán phù hợp với ứng dụng cụ thể là rất quan trọng để đảm bảo tính bảo mật và hiệu suất của hệ thống.

**zk-SNARK**
Thuật toán zk-SNARK được sử dụng phổ biến trong các ứng dụng blockchain như Zcash và Ethereum. Các ứng dụng này sử dụng zk-SNARK để giữ cho giao dịch trên blockchain được bảo mật và riêng tư. Ví dụ, khi một người dùng thực hiện một giao dịch trên blockchain, zk-SNARK có thể được sử dụng để chứng minh rằng người dùng đó có đủ số dư để thực hiện giao dịch đó mà không cần tiết lộ số dư chính xác của người dùng.
