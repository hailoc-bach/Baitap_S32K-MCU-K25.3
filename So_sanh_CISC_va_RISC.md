# 1. Giới thiệu khái niệm cơ bản
## 1.1. Kiến trúc CISC (Complex Instruction Set Computer)

CISC là viết tắt của Complex Instruction Set Computer, nghĩa là “máy tính với tập lệnh phức tạp”. Trong kiến trúc này, bộ xử lý được thiết kế để thực hiện một tập hợp lớn các lệnh, mỗi lệnh có thể thực hiện nhiều thao tác phức tạp như tải dữ liệu, xử lý và lưu trữ chỉ trong một lệnh duy nhất.
Mục tiêu của CISC là giảm số lượng lệnh trong chương trình bằng cách làm cho mỗi lệnh thực hiện được nhiều công việc. Các bộ xử lý CISC điển hình như Intel x86, AMD, hay VAX thường có hàng trăm lệnh khác nhau, nhiều chế độ địa chỉ và các thao tác phức tạp trên bộ nhớ.

## 1.2. Kiến trúc RISC (Reduced Instruction Set Computer)

RISC là viết tắt của Reduced Instruction Set Computer, nghĩa là “máy tính với tập lệnh rút gọn”. Kiến trúc này ra đời nhằm đơn giản hóa thiết kế bộ xử lý, tập trung vào việc thực thi các lệnh đơn giản, có độ dài cố định và thực hiện trong một chu kỳ xung nhịp.
Mục tiêu của RISC là tối ưu hóa tốc độ xử lý và hiệu suất sử dụng tài nguyên, bằng cách giảm độ phức tạp phần cứng và tăng khả năng song song hóa. Các bộ xử lý tiêu biểu cho kiến trúc này gồm ARM, MIPS, RISC-V, và PowerPC.

# 2. Ưu điểm và nhược điểm của từng loại kiến trúc
## 2.1. CISC

### Ưu điểm:

Mỗi lệnh có thể thực hiện nhiều thao tác phức tạp → chương trình ngắn gọn hơn.

Giảm khối lượng mã lệnh cần lưu trữ trong bộ nhớ.

Thích hợp với các ngôn ngữ cấp cao, do một lệnh có thể tương ứng với nhiều câu lệnh trong chương trình.

### Nhược điểm:

Tốc độ thực thi mỗi lệnh chậm hơn, do lệnh phức tạp và cần nhiều chu kỳ xung nhịp.

Mạch điều khiển và giải mã lệnh phức tạp → khó thiết kế, tiêu thụ nhiều năng lượng.

Khó tối ưu hóa pipeline vì độ dài và thời gian thực thi các lệnh không đồng nhất.

## 2.2. RISC

### Ưu điểm:

Các lệnh đơn giản, độ dài cố định → dễ dàng thực hiện pipeline, tăng tốc độ xử lý.

Thiết kế phần cứng đơn giản, tiêu thụ điện năng thấp → phù hợp cho thiết bị di động và nhúng.

Dễ mở rộng và tích hợp thêm các tính năng mới (như SIMD, DSP, v.v.).

### Nhược điểm:

Cần nhiều lệnh hơn để thực hiện cùng một công việc như CISC → chương trình dài hơn.

Đòi hỏi bộ nhớ lớn hơn để lưu mã lệnh.

Một số tác vụ phức tạp cần lập trình nhiều bước, khó tối ưu bằng tay.

# 3. So sánh CISC và RISC theo các tiêu chí
| Tiêu chí | **CISC** | **RISC** |
|-----------|-----------|-----------|
| **Cấu trúc tập lệnh** | Tập lệnh phức tạp, mỗi lệnh thực hiện nhiều thao tác. | Tập lệnh đơn giản, mỗi lệnh thực hiện một thao tác cơ bản. |
| **Tốc độ xử lý** | Thấp hơn do mỗi lệnh cần nhiều chu kỳ xung. | Cao hơn do mỗi lệnh chỉ cần 1 chu kỳ hoặc ít chu kỳ. |
| **Kích thước chương trình** | Nhỏ hơn, vì ít lệnh hơn. | Lớn hơn, vì cần nhiều lệnh để làm cùng việc. |
| **Độ phức tạp phần cứng** | Mạch giải mã và điều khiển phức tạp. | Mạch đơn giản, dễ thiết kế và tiết kiệm năng lượng. |
| **Hiệu năng trên mỗi watt** | Thấp hơn. | Cao hơn (rất quan trọng với thiết bị nhúng). |
| **Ứng dụng thực tế** | Intel x86, AMD (máy tính, laptop). | ARM, RISC-V (điện thoại, thiết bị nhúng, IoT). |

---
# 4. Ứng dụng thực tế

CISC:
Họ vi xử lý Intel x86 và AMD Ryzen là ví dụ tiêu biểu. Chúng được sử dụng phổ biến trong máy tính để bàn, máy chủ, và hệ thống yêu cầu tương thích ngược phần mềm cao.

RISC:
Họ ARM (Advanced RISC Machine) là đại diện nổi bật, được sử dụng trong điện thoại thông minh, máy tính bảng, thiết bị IoT, robot nhúng, nhờ tiêu thụ năng lượng thấp và hiệu suất cao trên mỗi watt. Ngoài ra, RISC-V, một kiến trúc mở, đang phát triển mạnh trong các hệ thống nhúng và học thuật.

# 5. Quan điểm cá nhân

Trong bối cảnh phát triển hệ thống nhúng hiện nay, kiến trúc RISC là lựa chọn phù hợp hơn. Lý do chính gồm:

## Hiệu suất năng lượng cao:
Các thiết bị nhúng thường chạy bằng pin hoặc nguồn hạn chế, nên tiêu thụ năng lượng thấp là yếu tố then chốt. RISC, đặc biệt là ARM, đáp ứng rất tốt tiêu chí này.

## Thiết kế phần cứng đơn giản:
Việc tích hợp RISC vào các SoC (System-on-Chip) giúp giảm chi phí và kích thước chip, thuận lợi cho các ứng dụng IoT và di động.

## Khả năng mở rộng và tùy biến:
Các kiến trúc như RISC-V cho phép thiết kế tùy chỉnh, thích hợp cho nghiên cứu và sản xuất các bộ vi điều khiển chuyên biệt.

## Hỗ trợ mạnh mẽ từ cộng đồng và công nghiệp:
Hệ sinh thái ARM và RISC-V phát triển nhanh chóng, có nhiều tài nguyên, trình biên dịch, và hệ điều hành nhúng hỗ trợ.

Vì vậy, trong khi CISC vẫn thống trị thị trường máy tính cá nhân, thì RISC đang trở thành xu hướng chủ đạo trong lĩnh vực hệ thống nhúng, thiết bị di động và IoT, nơi hiệu năng trên mỗi watt và khả năng tùy biến được đặt lên hàng đầu.

# 6. Kết luận

Cả hai kiến trúc CISC và RISC đều có vai trò quan trọng trong ngành vi xử lý. CISC hướng đến hiệu quả phần mềm và tương thích ngược, trong khi RISC tối ưu cho tốc độ, năng lượng và thiết kế nhúng.
Sự phát triển của công nghệ bán dẫn và nhu cầu ngày càng tăng của các thiết bị thông minh khiến RISC – đặc biệt là ARM và RISC-V – trở thành lựa chọn tối ưu cho tương lai của hệ thống nhúng.
