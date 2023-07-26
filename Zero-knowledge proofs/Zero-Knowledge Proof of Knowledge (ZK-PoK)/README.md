# Zero-Knowledge Proof of Knowledge (ZK-PoK)

Zero-Knowledge Proof of Knowledge (ZK-PoK) là một lớp các thuật toán chứng minh không tiết lộ tri thức (zero-knowledge proof) trong lĩnh vực mật mã và an ninh thông tin. 
ZK-PoK cho phép một bên chứng minh cho bên khác rằng họ không chỉ biết giá trị bí mật mà còn chứng minh rằng họ có kiến thức về giá trị bí mật đó.

Ý tưởng của ZK-PoK được hình thành từ hai khái niệm quan trọng:

**Zero-Knowledge Proof (Chứng minh không truyền đạt)**: Là một loại chứng minh mà người chứng minh (Prover) có thể chứng minh một lời khẳng định cho người xác minh (Verifier) mà không tiết lộ bất kỳ thông tin bổ sung nào về lời khẳng định đó. Tức là, sau khi xem xét chứng minh, người xác minh có thể tin rằng lời khẳng định đúng mà không biết thêm thông tin về nó.

**Proof of Knowledge (Chứng minh kiến thức)**: Là một loại chứng minh mà người chứng minh không chỉ chứng minh lời khẳng định đúng mà còn phải chứng minh rằng họ thực sự có kiến thức về thông tin bí mật mà họ đang khẳng định.

Kết hợp cả hai khái niệm trên, ZK-PoK đảm bảo rằng không chỉ người chứng minh có thể xác minh tính đúng đắn của lời khẳng định mà còn phải chứng minh rằng họ thực sự có kiến thức về giá trị bí mật, mà không cần tiết lộ giá trị đó cho người xác minh.

ZK-PoK được ứng dụng rộng rãi trong các hệ thống bảo mật, đặc biệt trong việc xác thực danh tính, chứng thực người dùng mà không cần tiết lộ thông tin nhạy cảm. Ví dụ, trong hệ thống xác thực đăng nhập bằng mật khẩu, người dùng có thể chứng minh rằng họ biết mật khẩu đúng mà không tiết lộ mật khẩu cho hệ thống.
