# Cách thiết kế trực quan hiệu quả

Mục tiêu của chương này là cung cấp một số **cách để thiết kế hình ảnh trực quan thành công** vì nó là hình ảnh truyền tải thông tin mong muốn đến đối tượng mục tiêu một cách hiệu quả, chính xác. Sẽ có vô số phương pháp khả thi để ánh xạ các thành phần dữ liệu thành các ảnh. Tương tự cũng có rất nhiều công cụ tương tác có thể được cung cấp cho người dùng. Việc lựa chọn các kết hợp kỹ thuật hiệu quả nhất không phải là một quá trình đơn giản.

Một hình ảnh trực quan có thể không hiệu quả vì một số lý do:

+ **quá khó hiểu hoặc phức tạp** để đối tượng người nghe mục tiêu có thể hiểu được
+ một số **dữ liệu bị bóp méo, che khuất**
+ **thiếu hỗ trợ** việc **sửa đổi chế độ xem** hoặc **kiểm soát bản đồ màu**
+ một bản trình bày **không hấp dẫn về mặt thị giác**

Chương này trước tiên trình bày các cân nhắc về [1] **cách thiết kế cho các thành phần mà tác giả cảm thấy cần thiết cho một hình ảnh trực quan** tốt. Sau đó, khám phá [2] một số **vấn đề thường gặp trong hình ảnh trực quan** và **một số kỹ thuật để tránh** những vấn đề này.

## Cách bước thiết kế trực quan

Việc tạo hình ảnh hóa bao gồm quyết định cách **ánh xạ các trường dữ liệu thành các hình ảnh**, lựa chọn và triển khai các phương pháp để **sửa đổi chế độ xem** và **chọn lượng dữ liệu cần thiết cho trực quan hóa**.

**Thông tin bổ sung liên quan đến dữ liệu** được hiển thị (ví dụ: nhãn) và **ánh xạ** (ví dụ: khóa màu) cũng rất **cần thiết cho việc diễn giải** và **phải được tích hợp vào hình ảnh**.

Cuối cùng, ít hữu hình hơn, cần cân nhắc đến **tính thẩm mỹ tổng thể** của màn hình **hiển thị kết quả**. Các phần nhỏ được trình bày sau đây sẽ làm rõ hơn các bước trong quy trình đã đề cập.

### Bước 1. Ánh xạ dữ liệu sang biểu diễn trực quan

Để tạo ra hình ảnh trực quan hiệu quả, cần hiểu rõ **ngữ nghĩa của dữ liệu và bối cảnh của người dùng**. Việc **chọn cách hiển thị phù hợp với tư duy của người dùng** sẽ giúp họ **dễ dàng hiểu hình ảnh hơn**. Ngoài ra, nhà thiết kế **nên nhất quán để tránh sự nhầm lẫn**. Ánh xạ dữ liệu trực quan tốt sẽ giúp người dùng diễn giải nhanh hơn vì không phải mất thời gian để hiểu.

Ví dụ, trong [hình 1](...), hình ảnh các hành tinh được sử dụng để vẽ mối quan hệ giữa khoảng cách từ hành tinh đến Mặt Trời và thời gian quỹ đạo của nó. Fig 1. ()

Việc ánh xạ các **thuộc tính dữ liệu không gian**, để diễn giải bề mặt cầu 3 chiều của Trái Đất thành 1 mặt phẳng 2D là cách ánh xạ phổ biến và trực quan nhất được tìm thấy trong các hình ảnh trực quan. Ví dụ này là sớm nhất để tận dụng khả năng của con người trong việc liên hệ vị trí trên mặt phẳng 2D với vị trí trong thế giới ba chiều.

Tương tự như vậy, với sự ra đời của hoạt hình, rõ ràng là việc hiển thị các **tập dữ liệu chuỗi thời gian** thông qua hoạt hình là khá trực quan, với lợi thế bổ sung là cho phép thời gian thay đổi cả về tốc độ và hướng. Fig 2. ()

Một số **ánh xạ dữ liệu trở nên trực quan hơn khi kết hợp với ngữ cảnh cụ thể**:

+ Ví dụ, **ánh xạ nhiệt độ sang màu sắc** rất phổ biến, ví dụ xanh đỏ đại diện cho nhiệt độ thấp và nhiệt độ cao. Fig 3. ()

+ Trong các lĩnh vực như bản đồ học và địa chất, **màu sắc thường được dùng để phân loại đất đai hoặc lớp địa chất**, vì vậy việc chọn màu phải phù hợp với bối cảnh ứng dụng. Fig 4. ()

+ **Chiều cao hoặc độ dài** cũng có thể dùng để **biểu diễn nhiệt độ**, giống như cách chúng ta đọc nhiệt kế. Đối với các bác sĩ, việc dùng độ dài để hiển thị áp lực hoặc các giá trị liên quan có thể rất tự nhiên. Fig 5. ()

Khi **chọn ánh xạ**, cần **xem xét tính tương thích giữa thang dữ liệu và thuộc tính**. Dữ liệu có thứ tự (như tuổi) không nên ánh xạ sang thuộc tính không có thứ tự (như hình dạng). Tương tự, dữ liệu không có thứ tự (như quốc gia) không nên ánh xạ sang thuộc tính có thứ tự (như độ dài). Fig 6. () & Fig 7. ()

Tuy nhiên, **đôi khi cũng thú vị khi kiểm tra dữ liệu bằng các ánh xạ không trực quan**, vì hình ảnh kết quả có thể tiết lộ một thuộc tính thú vị trong dữ liệu. Ví dụ, ánh xạ thời gian để tô màu dọc theo một đường vạch có thể tiết lộ các biến thể về tốc độ hạt mà nếu không thì có thể khó phát hiện. Do đó, **một nguyên tắc chung** hữu ích là **thiết lập các ánh xạ mặc định dựa trên lựa chọn trực quan nhất theo người dùng thông thường**, nhưng, đặc biệt đối với các tác vụ khám phá, cho phép người dùng tùy chỉnh nhiều ánh xạ trực quan khác nhau.

