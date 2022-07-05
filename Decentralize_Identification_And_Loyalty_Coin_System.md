Source: https://iohk.io/en/blog/posts/2022/06/07/dish-launches-decentralized-identification-and-loyalty-coin-system-built-on-input-output-global-iog-technology/

DISH Network Corporation đã tiến đến bước đầu tiên để ra mắt hệ thống nhận diện phân tán và loyalty coin trên IOG (Input Output Global) được thiết kế và phát triển trên công nghệ blockchain. Bước này cho phép khả năng blockchain ở cơ sở hạ tầng của DISH thông qua các dịch vụ nhận dạng của PRISM và tính năng native asset của Cardano

Đối tượng cuối cùng của sự hợp tác này là tạo ra một kỹ thuật số mạnh mẽ, nhận diện phân tán và loyalty framework được xây dựng đầu tiên trên Cardano blockchain.

MVP này là một phần của dự án CRONUS, một sự hợp tác lâu dài và sáng tạo giữa IOG và DISH để làm cho blockchain trở thành một phần chính của hệ sinh thái DISH và phát triển chiến lược trong tương lai.

How does the CRONUS MVP work?
MVP là bước đầu để backend dựa trên hệ thống loyalty token hỗ trợ bởi công nghệ blockchain. Bước này cho phép minting loyalty token trên Cardano blockchain để nhân đôi loyalty coin blance trên chương trình DISH's BoostOne loyalty.

Cardano truy vết balance của loyalty coin hoặc Boostcoin được tích lũy bởi khách hàng, và mint hoặc burn loyalty token phù hợp. Balance của loyalty token được điều chỉnh thường xuyên sử dụng ví được kiểm soát bởi DISH. IOG sẽ không truy cập vào ví này. Để tránh đưa vào thông tinh cá nhân của khách hàng, MVP sử dụng thư viện Atala SDK để tạo mã nhận dạng phi tập trung DID (unpublished decentralized identifier)

Core MVP capabilities:
Khi khởi chạy, MVP sẽ cung cấp các khả năng sau:

- Cơ sở dữ liệu sổ cái loyalty (loyalty ledger database) sẽ theo dõi Boostcoin và cho biết có bao nhiêu loyalty token cần được mint hoặc burn để balance token khớp với balance loyalty coin
- API để mint và điều khiển token trên Cardano mainnet
- Cardano mainnet nơi mà loyalty token được mint hoặc burn theo dữ liệu được cung cấp bởi cơ sở dữ liệu sổ cái loyalty.
- Ví DISH sẽ giữ Boostcoin. Ví này sẽ thực thi việc mint và burn transaction trong khi cập nhật hàng loạt.
- Tạo DID cho mỗi khách hàng. Mã DID này sẽ được map với khách hàng master, nằm bên ngoài MVP. DID được tạo bởi thư viện Atala SDK nhưng sẽ không tự publish trên Cardano blockchain.

MVP bao gồm 2 API:

1. API để mint và kiểm soát token trên Cardano blockchain mainnet:

- Mint/burn loyalty token
- Truy vấn tổng số token đang lưu hành.

2. API cho loyalty ledger database:

- Thêm loyalty coin cho tài khoản khách hàng.
- Khấu trừ loyalty coin từ tài khoản khách hàng.
- Truy vấn balance loyalty coin và transaction của mỗi khách hàng.

MVP này là bước đầu tiên trong hành trình áp dụng blockchain. This first step is about `blockchain enablement`. DISH sẽ trở thành người tham gia vào hệ sinh thái Cardano bằng việc chạy các node khách nhau, phát hành DID, mint và burn native assets. Giai đoạn tiếp theo là liên quan đến `blockchain adoption`, nơi người dùng DISH sẽ được giới thiệu về những khía cạnh khác nhau của hệ sinh thái blockchain. Bao gồm nhưng không giới hạn khi có ví.

MVP: user stories
CRONUS MVP mở ra cơ hội cho DISH và đối tác phát triển của họ, IOG. Nhưng cuối cùng, khách hàng DISH sẽ có được nhiều lợi ích tốt nhất. Ví dụ: MVP cho phép người dùng sử dụng BoostOne xem được balance loyalty coin và transaction.
MVP cũng cho phép kiểm soát tốt hơn cho các quản trị viên backend BoostOne, vì họ có thể:

- Thêm hoặc xóa loyalty coin từ tài khoản người dùng BoostOne nếu cần.
- Mint hoặc burn token trên Cardano mainnet nếu cần để cung cấp loyalty token mà khách hàng BoostOne kiếm được
- Có quyền kiểm soát ví Dish loyalty token nên khách hàng không thể tương tác trực tiếp với loyalty token.
- Tham chiếu DID để xác định khách hàng được liên kết với tài khoản loyalty coin.
