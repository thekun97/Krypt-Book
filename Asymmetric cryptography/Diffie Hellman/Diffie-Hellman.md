# Diffie-Hellman Key Exchange

Diffie-Hellman là một thuật toán trao đổi khóa công khai được sử dụng để thiết lập khóa bí mật chung giữa hai bên không  tin cậy thông qua kênh truyền công khai. Phương pháp Diffie-Hellman được phát minh bởi Whitfield Diffie và Martin Hellman vào năm 1976 trong bài báo "New Directions in Cryptography" của họ, đăng trên tạp chí IEEE Transactions on Information Theory. Đây là một trong những phát minh quan trọng đầu tiên trong lĩnh vực mã hóa khóa công khai và đã mở ra một thế giới mới cho việc mã hóa thông tin an toàn.

Trước khi Diffie-Hellman ra đời, việc mã hóa thông tin thường được thực hiện bằng cách sử dụng mã hóa đối xứng, trong đó các bên sử dụng cùng một khóa để mã hóa và giải mã thông điệp. Tuy nhiên, việc trao đổi khóa đối xứng là một thách thức, vì khóa phải được truyền qua kênh không an toàn. Nếu một bên tấn công được kênh truyền này, thì họ có thể giải mã các thông tin được truyền tải. Diffie-Hellman đã giải quyết vấn đề này bằng cách sử dụng một phương pháp mã hóa khóa công khai, trong đó các bên có thể tạo ra một khóa chung mà không cần giao tiếp trực tiếp với nhau trước đó. Phương pháp này trở thành một trong những phát minh quan trọng nhất trong lĩnh vực mã hóa khóa công khai.

## 1. Sơ đồ hoạt động
Bên A và bên B cần thiết lập một khóa bí mật chung để sử dụng trong việc mã hóa và giải mã tin nhắn. Để thực hiện điều này, họ thực hiện các bước sau:

![alt text](https://lh3.googleusercontent.com/J4giei4f_sPTetM01Jjc2bdtmmZqNmxH0bp-qL6f9ThSzPkknx6zEeasASXYI_ZhCy8NuJ7P_Vmynjtcwamh_bCmPOoWaX_m1E839PO46AAM3mw9-aSKoV4PG7kqC8rKhHAnXDBGvyJMekgPDk9GxW6xvYjVdHE6PCmlDjbxcrESvl6BJhqtaZqUONhuu13YE-aQ4gzfI3TmKIMLm-eqf-jSmoCmirT6-2RgeSvzqWABWT4kaXKNeauIdMpGqhKh0Cq0DLX2xtsrpY3qOrAFm5sndlMHnkedbrxL3fBHEnyB2vy9zD4YW7xSZmgZ4kMVpHlIgLue_UwKRX-IZXcCaabTwrdjSQ-KsWHo5LAIYFbsPp6aCPf_Z0dDP47FVoiPHofscikLFXdUmIkj44qQza1tJTGK5yh3yvX7eIUqeqjPAGYex65KYYUpgR4BYNdGwDLPLVUvQLhCah3SnFIwXk-bW7TXkVVgEKpGohjhBHYbG72Zjqp0XO8FkBUWLcvxeIRwVIlh5gEy4K8rGGmgeESMc8lAFwzdy9hqLo_ql-gFEFITS9JSWfA50aXndUKBMZR3LaWgRsHamrF-dO1_75eXWKnRz0g7LDZjBFHvBQ3ESH2MnT3sUtYISG99d7qEykAZyzejaYKTp5pVc3rj6GORp_QIn6fXFCLJtYlnDM9Wk4hHu3AiTAhG9BWFx15aazW4wCKsKWmX1THqG3mFP9Vi9eMpLju9NhkSriB-nxe44HB8ZVbQTyDQ58mtGClCbjxG4iRClU8AuQlINkTSCckDib3ZrulFrYrXblnTySEr0NEt2KYiC3DJQsNZaH3RhdMUfYHnfP3QB2aUwI8bNZGPKt3qSZcKgCgkiHILkf1Peb_ADcdxHkODiXmLh6olbmlhOsf5BZoDljBy7ESanb009v54eptI5vw-TcQ4qFWh30R3Ycdvd8f0zPjxpsZxRtRnKvBCqamdjzG90w=w771-h582-s-no?authuser=0)

1.  Alice và Bob thống nhất về một số nguyên tố lớn p và một điểm sinh g của p (cần chọn [số  nguyên tố an toàn](https://vi.wikipedia.org/wiki/S%E1%BB%91_nguy%C3%AAn_t%E1%BB%91_an_to%C3%A0n)).
    
2.  Alice chọn một số ngẫu nhiên a là khóa bí mật và tính toán A = g<sup>a</sup>  mod p. Sau đó, Alice gửi giá trị A cho Bob.
    
3.  Bob chọn một số ngẫu nhiên b là khóa bí mật và tính toán B = g<sup>b</sup> mod p. Sau đó, Bob gửi giá trị B cho Alice.
    
4.  Bên Alice tính toán S = B<sup>a</sup> mod p và Bob sẽ tính S = A<sup>b</sup> mod p.
    
5.  Giá trị S thu được từ cả hai bên đều giống nhau và được sử dụng như một khóa bí mật chung giữa hai bên để mã hóa và giải mã tin nhắn.

## 2. Độ bảo mật
Thuật toán trao đổi khóa Diffie-Hellman (DH) là một thuật toán mật mã có độ bảo mật cao, được sử dụng rộng rãi trong các ứng dụng bảo mật như SSL/ TLS và các hệ thống mật mã khác. Độ bảo mật của thuật toán Diffie-Hellman phụ thuộc vào sự khó khăn của bài toán logarithm rời rạc.

Cụ thể, độ bảo mật của thuật toán DH phụ thuộc vào việc tính toán logarit rời rạc trong trường hữu hạn. Tuy nhiên, việc tính toán logarit rời rạc trong trường hữu hạn được coi là một bài toán khó trong toán học và hiện chưa có giải pháp hiệu quả để giải quyết nó. Điều này đảm bảo rằng ngay cả với các thuật toán tấn công hiện đại nhất, việc tìm ra khóa bí mật của thuật toán DH sẽ rất khó.

Tuy nhiên, một điểm yếu của thuật toán DH là nó không cung cấp tính toàn vẹn dữ liệu hoặc xác thực người gửi, có thể bị tấn công bằng phương pháp Parameter Injection. Do đó, để đảm bảo tính toàn vẹn dữ liệu và xác thực người gửi, cần sử dụng các thuật toán mã hóa và xác thực khác như HMAC hoặc digital signature. Ngoài ra, nếu người dùng sử dụng các tham số không an toàn như các giá trị p và g được chọn quá nhỏ hoặc không được chọn ngẫu nhiên đúng cách, thì thuật toán DH có thể bị tấn công bởi các tấn công phân tích khoảng cách và thuật toán bậc thang.

Vì vậy, để đảm bảo độ bảo mật cao của thuật toán DH, người dùng cần sử dụng các tham số an toàn được khuyến nghị bởi các tiêu chuẩn bảo mật, ví dụ như NIST SP 800-56A hoặc RFC 3526. Ngoài ra, để tăng cường độ bảo mật, nhiều hệ thống còn sử dụng kết hợp thuật toán DH với các thuật toán mã hóa khác như AES.

## 3. Ứng dụng hiện nay

Thuật toán Diffie-Hellman là một thuật toán được sử dụng rộng rãi trong các ứng dụng an ninh và mật mã học. Một số ứng dụng hiện nay của thuật toán Diffie-Hellman:

- SSL/TLS: Diffie-Hellman được sử dụng trong giao thức SSL/TLS để tạo ra khóa chia sẻ bí mật giữa máy khách và máy chủ. Việc sử dụng Diffie-Hellman giúp đảm bảo tính bảo mật và bảo vệ thông tin cá nhân của người dùng khi truy cập các trang web bảo mật.
    
- SSH: Tạo ra khóa chia sẻ bí mật giữa máy khách và máy chủ, đảm bảo tính bảo mật và độ tin cậy của kết nối SSH.
    
- PGP (Pretty Good Privacy): Đảm bảo tính bảo mật và bảo vệ thông tin cá nhân trong các cuộc trao đổi email.
    
- Bitcoin: Bảo vệ tính bảo mật và độ tin cậy của các giao dịch.
    
- VPN: Tăng tính bảo mật và độ tin cậy của kết nối VPN.
    

Điểm chung của việc sử dụng Diffie-Hellman là để tạo ra khóa chia sẻ bí mật giữa các bên truyền thông.
