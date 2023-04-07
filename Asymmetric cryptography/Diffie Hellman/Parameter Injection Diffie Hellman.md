# Parameter Injection Diffie Hellman

Parameter Injection là một kỹ thuật tấn công nhằm thay đổi các tham số của thuật toán để có thể tính toán ra khóa bí mật chung bằng 0 và giải mã các thông điệp được mã hóa bằng khóa này.
Nếu kẻ tấn công có thể ngồi ở giữa phiên trao đổi khóa và sửa đổi các thông báo được truyền, thì hắn có thể kiểm soát khóa và giải mã tất cả lưu lượng. Phương pháp tấn công được mô tả sau đây:

<p align="center">
  <img src="https://lh3.googleusercontent.com/uwYP8LocO0wHn5rcBEYfz22cKomFrev33h1wsYSgn0APKzxcrHvlAOvEKlYItaTRtQ3qhET9LYbzQ7BUcQ7M9wiMhvIS4hGozwgZ64LeqS-7IKmeF0eFjaDZIpKqbOiq8cjHY_W5mMdyJHOrM27wIe36LIKv2Oa790z8PE7rytby-vFXJFYXPpBDfbgoRN4IPDuBo1dYmYzwvbVNikXNsXUCx4qDwFmMdFXis8quJYFBYBT_WhWraOEBjcjDMoj_6wAWHiIN-pYoAz3xPlb2QOqhQIqfhY22Q9TrgVSGL-KiV-5rWkursJVz5XJCJ9sy3f8xyaaBrAoPVavLo-lp7IouVfdD1e8A3GXv1jtcnv5FhxOhXpf_o94tP5y3oVOsirBM6B2smch0RhYrvcPTS5NcIk6zEHrhWS3g1D_ehzwlEWA1Vmw9umNtXYWlMT0eg0k-FPWnKrj2A2mrub4nZERp3m2UJLVgMVGJCNORTVS35DKMNxefHRseDhJwJ6eyT5RkpD76uys7SqFqzUwrUEVEA9Nt_P9MJ8rZDZd10sL9d0ZKdgjvqDn9l4vket0Sh6q2c1d4wm4pEf_bgdQDb_BgEvNYTcAwRSJW6TzkQtALkMLhy4LxbLt-NwfSE1OyWvWWd4zJJ1Pq7C8YtWALwvSKz77_aIDAWN3_2GLwoTDKMh-oVamBPzfqTrgFS3u0d0e94ZN-Iyh1wtgv1BaKRdIPGDzwhFpDEs6w6fL92iHDYahEbNByzyh_Lsnjd9IXaisr3Fdz0Xb-W4Rgxih3hzDnAtF6917BeFVEwX8dqWKJpWB08uDqRfIcSZ0Xxht8afRIbU6gCrENwwgaLF4A39uqON9FBsoIAppahqJdA37ffM7rG6TXY-owSHbTqUj0Fx3BRipmDW4lNNuP1myqADUk5QCMsTa3P2yHIw4u5I6z5P4NctXZtnRcVHYRueOd1fXXZ9ZT3LnIQ8GCXw=w1602-h746-s-no?authuser=0" />
</p>

Nếu kẻ tấn công thay thế A và B bằng p, thì cả Alice và Bob sẽ tính toán khóa là p<sup>a</sup> mod p  = p<sup>b</sup> mod p = 0. Sau đó, 0 được băm và sử dụng làm khóa đối xứng cho mã hóa AES, vì vậy kẻ tấn công có thể giải mã tất cả các thông điệp.

## Biện pháp bảo mật
- Sử dụng chữ ký số để xác thực các tham số trao đổi khóa được sử dụng.
