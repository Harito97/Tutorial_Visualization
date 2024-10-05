# Cách thiết kế trực quan hiệu quả

Mục tiêu của chương này là cung cấp một số **cách để thiết kế hình ảnh trực quan thành công** vì nó là hình ảnh truyền tải thông tin mong muốn đến đối tượng mục tiêu một cách hiệu quả, chính xác. Sẽ có vô số phương pháp khả thi để ánh xạ các thành phần dữ liệu thành các ảnh. Tương tự cũng có rất nhiều công cụ tương tác có thể được cung cấp cho người dùng. Việc lựa chọn các kết hợp kỹ thuật hiệu quả nhất không phải là một quá trình đơn giản.

Một hình ảnh trực quan có thể không hiệu quả vì một số lý do:

+ **quá khó hiểu hoặc phức tạp** để đối tượng người nghe mục tiêu có thể hiểu được
+ một số **dữ liệu bị bóp méo, che khuất**
+ **thiếu hỗ trợ** việc **sửa đổi chế độ xem** hoặc **kiểm soát bản đồ màu**
+ một bản trình bày **không hấp dẫn về mặt thị giác**

Chương này trước tiên trình bày các cân nhắc về [1] **cách thiết kế cho các thành phần mà tác giả cảm thấy cần thiết cho một hình ảnh trực quan** tốt. Sau đó, khám phá [2] **vấn đề thường gặp trong hình ảnh trực quan** và **một số kỹ thuật để tránh** những vấn đề này (khái quát lại những cái của Chapter 3).

## Các bước thiết kế trực quan

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

### Bước 2. Chọn và sửa đổi chế độ xem cho phù hợp

Ngoại trừ các tập dữ liệu khá đơn giản, **một chế độ xem hiếm khi đủ để truyền tải tất cả thông tin** chứa trong dữ liệu. Như vậy điều quan trọng là **phải có thể dự đoán các loại chế độ xem** mà được sử dụng nhiều nhất bởi người dùng thông thường và sau đó **cung cấp trực quan cách điều khiển cài đặt, tùy chỉnh các dạng xem mà người dùng cảm thấy phù hợp**.

Cần ghi nhớ **chế độ xem phù hợp phụ thuộc vào**:

- loại dữ liệu được trình bày
- và nhiệm vụ gắn liền với sự trực quan hóa.
- Mỗi chế độ xem phải có nhãn, cung cấp thông tin rõ ràng, đầy đủ 
- và người dùng cần ít hành động nhất có thể để sửa sang được chế độ xem mà họ thấy phù hợp.

Sau đây là ví dụ **một số hành động** của người dùng để **sửa đổi chế độ xem**:

- **Cuộn và phóng to**: Cần thiết **khi không thể hiển thị toàn bộ dữ liệu** ở độ phân giải mong muốn.
- **Điều khiển bảng màu**: Luôn cần thiết, ít nhất nên **hỗ trợ một số bảng màu khác nhau** để cho phép người dùng điều chỉnh màu sắc riêng lẻ hoặc toàn bộ bảng màu.
- **Điều khiển ánh xạ**: Cho phép người dùng **chuyển đổi giữa các cách hiển thị khác nhau của cùng một dữ liệu**. Lý do vì một số đặc điểm có thể bị ẩn trong ánh xạ này nhưng lại nổi bật trong ánh xạ khác.
- **Điều khiển tỷ lệ**: Cho phép người dùng **thay đổi phạm vi và phân phối giá trị cho một trường dữ liệu trước khi ánh xạ**. Việc lọc và cắt dữ liệu cũng **giúp người dùng tập trung vào các tập con cụ thể**.
- **Điều khiển mức độ chi tiết**: Cung cấp **khả năng loại bỏ hoặc làm nổi bật chi tiết**, hỗ trợ các góc nhìn ở các mức độ khác nhau.

**Lưu ý** cho việc thiết kế chế độ xem và tùy chọn sửa đổi cho người dùng:

- Trong mọi trường hợp, điều cần thiết là các **thao tác xem phải đơn giản, dễ nhớ** cho người dùng và **cung cấp những thông tin phù hợp, chính xác** cho nhiệm vụ.
- Nếu có thể, **thao tác sửa đổi chế độ xem trực tiếp** (trực tiếp có thể thay đổi chế độ xem bằng các thao tác đơn giản: click, gõ phím, ...) **thường được ưa thích**.

### Bước 3. Xác định mật độ thông tin phù hợp

Khi thiết kế trực quan hóa, quan trọng là **xác định lượng thông tin cần hiển thị**. Có hai hệ quả:

+ **Đồ họa thừa**: **Có quá ít thông tin để trình bày**. Ví dụ, việc chỉ cần hiển thị tỷ lệ nam và nữ có thể chỉ dùng một con số. Một số đồ họa có thể cố gắng "làm đầy" thêm thông tin bằng cách hiển thị nhiều giá trị hơn, nhưng trong **những trường hợp này, chỉ cần hiển thị các giá trị dưới dạng văn bản sẽ hiệu quả hơn**.

+ **Thông tin thừa**: **Việc trực quan hóa chứa quá nhiều thông tin** $\to$ nó có thể **gây nhầm lẫn và khó hiểu**. Thông tin quan trọng có thể bị mất trong một giao diện lộn xộn, khiến người xem **khó xác định nơi cần chú ý**.

**Giải pháp** cho **vấn đề quá tải thông tin**:

- **Tùy chọn hiển thị**: Cho phép người dùng **bật hoặc tắt các thành phần khác nhau**, giúp họ **tập trung vào thông tin quan trọng**.
- **Nhiều màn hình**: Sử dụng các **màn hình riêng biệt** để **hiển thị 1 nhóm thông tin cụ thể** mà không gây lộn xộn.
- **Lọc dữ liệu**: **Loại bỏ** các điểm **dữ liệu không quan trọng** để người dùng chỉ **tập trung vào các phần có ý nghĩa**.
- **Tỉ lệ**: Điều chỉnh **kích thước của một số dữ liệu cho phân bổ trên không gian màn hình hợp lý** hơn.

Những giải pháp này giúp tối ưu hóa trực quan hóa, đảm bảo rằng người dùng dễ dàng hiểu và tương tác với thông tin.

### Bước 4. Thêm vào các từ khóa, nhãn và chú thích

Một vấn đề phổ biến trong trực quan hóa là **thiếu thông tin hỗ trợ để người dùng có thể hiểu rõ và chính xác** thông tin truyền tải. Để giải quyết vấn đề đó, chúng ta **cần cung cấp các yếu tố sau**:

+ **Chú thích** chi tiết: **Giải thích dữ liệu** và **phép ánh xạ dữ liệu sang biểu đồ trực quan** được sử dụng.
+ **Lưới và dấu tick**: Hiển thị **các giá trị và phạm vi** của các trường số **khi cần đánh giá chính xác**.
+ **Nhãn trục**: Ghi rõ **đơn vị đo lường trên các trục**.
+ **Chú giải ký hiệu**: Cung cấp **từ khóa cho các ký hiệu**, nằm ở viền hoặc trong một widget riêng.
+ **Giải thích màu sắc**: **Ý nghĩa của màu sắc** sử dụng **trong phép trực quan**, như thanh màu có nhãn.

### Bước 5. Điều chỉnh màu sắc được sử dụng cho phù hợp

**Màu sắc thường bị lạm dụng** trong các biểu đồ, **dẫn đến sự nhầm lẫn hoặc diễn giải sai**.

Thêm nữa, việc **chọn sai bảng màu** hoặc cố gắng **truyền tải quá nhiều thông tin qua màu sắc** có thể làm **giảm hiệu quả trực quan hóa**. 

Đặc biệt, do **màu sắc có thể bị ảnh hưởng bởi môi trường quan sát** và **nhiều người mắc chứng mù màu**, điều này càng làm phức tạp quá trình thiết kế.

Dưới đây là **hướng dẫn sử dụng màu sắc hiệu quả** trong biểu đồ:

+ **Giới hạn số lượng màu sắc**, tránh làm rối mắt người xem.

+ Sử dụng **thêm phương pháp ánh xạ bổ sung**, ví dụ như kết hợp cả màu sắc và kích thước, để dễ dàng truyền đạt thông tin.

+ Ngoài ra, khi tạo bảng màu cho dữ liệu số, có thể **thay đổi sắc độ** (hue) và **độ sáng** (lightness) để giúp dễ phân biệt các mục (entry) với ít máu sắc nhất.

### Bước 6. Bước cuối cùng, đảm bảo thẩm mỹ

Đây là bước chúng ta thực hiện **cân bằng giữa chức năng và hình thức**. Một biểu đồ tốt nên **vừa cung cấp thông tin vừa hấp dẫn về mặt hình ảnh**.

Dưới đây là **hướng dẫn nâng cao tính thẩm mỹ**:

+ **Tập trung**: Nên làm **nổi bật những phần quan trọng nhất** của biểu đồ để người xem **biết nên chú ý vào đâu**. Nếu không có sự nhấn mạnh thích hợp, thông tin quan trọng có thể bị bỏ qua.
+ **Cân bằng**: Sử dụng **không gian màn hình hợp lý**. Đặt các **thành phần chính ở trung tâm** và **tránh nổi bật đường viền** hoặc **khu vực ít quan trọng**.
+ **Đơn giản**: Giữ **lượng thông tin thể hiện trực quan ở mức vừa đủ bằng những thiết kế tối giản**. Nên dùng những hình ảnh đơn giản và tránh dùng các thiết kế phức tạp nếu những thiết kế đơn giản hơn có thể truyền đạt thông điệp tương tự. Một kỹ thuật hữu ích là loại bỏ từng yếu tố và xem xét liệu việc mất thông tin có chấp nhận được không. **Ghi nhớ "tối giản" - đơn giản mà vẫn đạt yêu cầu đặt ra**.

## Các lỗi sai hay gặp khi thiết kế trực quan

