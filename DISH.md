DISH ra mắt hệ thống nhận dạng phi tập trung và hệ thông loyalty coin được xây dựng trên công nghệ IOG (Input Output Global)

Sáng kiến này là một phần của sự hợp tác lâu dàu giữa DISH và IOG để tạo ra giải pháp blockchain đổi mới để thúc đấy việc áp dụng các công nghệ phi tập trung vào hệ sinh thái DISH.

DISH Network Corporation đã thực hiện bước đầu tiên hướng tới việc ra mắt hệ thống nhận dạng phi tập trung và loyalty coin được xây dựng trên IOG được thiết kế và phát triển. Bước đầu tiên cho phép các khả năng trong cơ sở hạ tầng DISH thông qua dịch vụ nhận dạng Atala PRISM và các tính năng tài sản gốc của Cardano (Cardano's native asset features).

Đối tượng cuối cùng của sự hợp tác này là tạo một khuôn khổ và kỹ thuật số mạnh mẽ và nhận dạng phi tập trung

Nói ngắn gọn, UTXO model là verfication (xác minh) model. Có nghĩa là người dùng submit transaction mà xác định kết quả của quá trình chuyển đổi state, được định nghĩa như là output transactions mới mà người nhận có thể chi tiêu (new transaction outputs spendable by the receiver(s)). Các node sau đó sẽ xác thực nếu consumed inputs là unspent và nếu chữ ký thỏa mãn điều kiện spending.

Account model, nói theo một cách khác, là computational (tính toán) model. Trong model này, users submit transactions hướng dẫn các node rằng sự chuyển đổi state trông như thế nào. Network sẽ tính toán state mới dựa trên sự hướng dẫn đó. Phương thức này đi kèm với các hàm ý cụ thể liên quan đến các giải pháp mở rộng lớp thứ hai như các kênh trạng thái và sharding.

Scalability (Khả năng mở rộng)
Có một vài cách tiếp cận mà chúng ta có thể sử dụng để so sánh khả năng mở rộng của UTxO và account model. Một cách là tập trung vào yêu cầu lưu trữ tổng thể của mỗi hệ thống. Cách khác là để cân nhắc model nào tốt hơn phù hợp cho việc triển khai công nghệ lớp hai trên blockchain chính

Công nghệ lớp thứ hai, state và kênh thanh toán, chuyển sự thay đổi dữ liệu từ blockchain cho một mạng lưới các kênh giao tiếp hai chiều không tin cậy (a dedicated trustless network of bidirectional communication channels)

Cách tiếp cận khác có thể được cho là công nghệ lớp thứ hai là sharding. Sharding là thuật ngữ có nguồn gốc cơ sở dữ liệu truyền thống. Sharding mô tả việc phân vùng cơ sở dữ liệu thành nhiều phân đoạn để giữ cho từng vùng riêng lẻ hoạt động hiệu quả hơn, từ đó cải thiện toàn bộ hệ thống. `Horizen's sidechain` có thể được coi là cơ chế sharding.

Bây giờ chúng ta sẽ so sánh cả hai phương thức và sẽ giả định số user và transaction tương đương nhau.

Size của blockchain
Account model sử dụng bộ nhớ hiệu quả hơn. Việc lưu trữ số dư (balance) của một account tiết kiệm bộ nhớ hơn so với việc lưu trữ một vài UTxOs là tổng số dư của user. Transaction ở account model cũng có kích thước nhỏ hơn vì chúng chỉ xác định người gửi, người nhận, số lượng gửi đi và chữ ký. Hơn nữa, bỏ qua change outputs (tiền thừa), một lượng lớn dữ liệu có thể được tiết kiệm hơn trong account model.

Ở cấp độ khái niệm, điều này là trực quan. Khi một UTxO transaction xác định state sau mỗi transaction (the newly generated transaction outputs), nó cần bao gồm nhiều dữ liệu hơn account transaction. Nó cũng có thể sử dụng một vài UTxO làm inputs, nhưng trái lại account transaction chỉ xác định balance của account nào để khấu trừ một số tiền. To give you an idea, ETH's account model mất khoảng 100 bytes, trong khi UTxO transaction ở Horizen mất khoảng 200-300 bytes.

Điều đó cũng có nghĩa là sẽ nhanh hơn trong việc đưa các node mới trực tuyến (online) trong hệ thống sử dụng account model vì cần ít dữ liệu để đồng bộ. Số lượng account thông thường sẽ nhỏ hơn nhiều so với tổng UTxO được đặt trong hệ thống có quy mô tương đối.

Cấu trúc State và kênh thanh toán
Hiện tại, cấu trúc kênh thanh toán tiên tiến nhất là `Lightning Network` ở Bitcoin. Nó sử dụng cơ chế gửi và xác minh bằng chứng (proof submission and verification mechanism) khi tài sản di chuyển vào và ra lớp thứ hai. Như đã đề cập ở trên, UTxO model cơ bản là verification model, trong khi account model là computational model. Do đó, UTxO phù hợp cho cách tiếp cận khả năng mở rộng.

Sharding
Phân chia blockchain thành các vùng nhỏ hoặc sidechains cũng dễ hơn so với sử dụng UTxO model. Tổng hợp các spendable transaction outputs và khởi tạo ouput xảy ra ở client-side, giảm bớt áp lực cho hệ thống tổng thể. Trong account model, tất cả các node phải khoanh vùng account của người gửi và người nhận trên các shards khác nhau và chỉnh sửa cả hai.

Tất nhiên,

0367839036
