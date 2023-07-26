
# Zero-Knowledge Proof
Zero-Knowledge Proof (ZKP) là một kỹ thuật được sử dụng trong lĩnh vực mật mã học để xác thực thông tin một cách tin cậy mà không cần tiết lộ thông tin đó. Trong ZKP, người chứng minh có thể chứng minh cho người nhận rằng mình có một thông tin nhất định mà không cần phải tiết lộ nó cho người nhận.

Ví dụ, giả sử người chứng minh muốn chứng minh rằng mình biết mật khẩu đăng nhập vào một tài khoản nhưng không muốn tiết lộ mật khẩu đó cho người nhận. Thay vì tiết lộ mật khẩu, người chứng minh có thể sử dụng ZKP để chứng minh cho người nhận rằng mình biết mật khẩu đó bằng cách thực hiện các bước tính toán phức tạp mà chỉ có người biết mật khẩu mới có thể thực hiện được.

ZKP được ứng dụng trong nhiều lĩnh vực, bao gồm chứng thực danh tính, bầu cử trực tuyến, và bảo mật giao dịch trên blockchain. Kỹ thuật này đóng vai trò quan trọng trong việc đảm bảo tính toàn vẹn và bảo mật thông tin trong các hệ thống mạng thông tin và các ứng dụng trực tuyến.

![Zero-Knowledge Proof (ZKP) — Explained | Chainlink](https://blog.chain.link/wp-content/uploads/2021/07/zero-knowledge-proof-1024x772.png)

## Định nghĩa 
Một bằng chứng không có kiến ​​thức của một số tuyên bố phải đáp ứng đủ ba tính chất:

**Tính đầy đủ (Completeness)**: nếu tuyên bố là đúng, một người xác minh trung thực (nghĩa là một người tuân thủ đúng quy trình) sẽ bị thuyết phục về sự thật này bởi một người chứng minh trung thực.

**Tính đúng đắn (Soundness)**: nếu tuyên bố đó là sai, không người chứng minh gian lận nào có thể thuyết phục người xác minh trung thực rằng điều đó là đúng.

**Không có kiến thức (Zero-knowledge)**: nếu tuyên bố là đúng, không có người xác minh nào học được bất cứ điều gì khác ngoài thực tế là tuyên bố đó là đúng. Nói cách khác, chỉ cần biết tuyên bố (không phải bí mật) là đủ để tưởng tượng ra một tình huống chứng minh rằng người chứng minh biết bí mật.

ZKP hiện nay thường có 2 dạng Bằng chứng tương tác (Interactive Proof) và bằng chứng không tương tác (Non-interactive Proof).

**Bằng chứng tương tác (Interactive Proof):**
Trong bằng chứng tương tác, quá trình chứng minh bao gồm sự tương tác trực tiếp giữa người chứng minh và người xác minh. Trong quá trình này, người chứng minh gửi các câu hỏi (challenges) đến người xác minh và nhận các câu trả lời (responses) từ người xác minh. Bằng cách lặp lại quá trình này, người xác minh có thể xác nhận tính đúng đắn của tuyên bố. Bằng chứng tương tác đòi hỏi tính truyền thông giữa người chứng minh và người xác minh và thông thường tốn nhiều thời gian.

**Bằng chứng không tương tác (Non-interactive Proof):**
Trái với bằng chứng tương tác, bằng chứng không tương tác cho phép chứng minh được thực hiện một cách độc lập mà không cần tương tác trực tiếp với người xác minh. Trong bằng chứng không tương tác, người chứng minh tạo ra một bằng chứng duy nhất và gửi nó đến người xác minh mà không cần thực hiện bất kỳ tương tác nào khác. Bằng chứng không tương tác thường dựa vào các phép tính mật mã không đổi thời gian như chữ ký số và bằng chứng Zero-Knowledge (ZK-PoK) để chứng minh tính đúng đắn mà không cần tương tác trực tiếp.
