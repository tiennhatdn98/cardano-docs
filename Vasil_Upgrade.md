Hard fork (hardfork): làm cho cái khối và giao dịch không hợp lệ trước đây trở nên hợp lệ hoặc ngược lại. Một đợt hardfork yêu cầu tất cả các node hoặc người dùng nâng cấp lên phiên bản mới nhất của giao thức.

Source: https://iohk.io/jp/blog/posts/2022/07/04/cardano-s-approaching-vasil-upgrade-what-to-expect/

Vasil upgrade sẽ giúp tăng cường chức năng, hiệu suất, khả năng mở rộng và khả năng tương tác cho Cardano thông qua các tính năng và cải tiến mới.

Vasil upgrade sẽ mang đến một hiệu suất đáng kể và nâng cao khả năng mở rộng cho Cardano. Network đã có những cải tiến nhất quán trong vài năm qua và có sự ra mắt của NFT, multi-asset và khả năng smart contract vào năm 2021 - nhưng đơn giản hơn, Vasil là một network upgrade đáng kể khi triển khai staking thông qua Shelley.

All about Vasil
Cũng như mang lại những cải tiến cho smart contract, việc nâng cấp là một phần của giai đoạn Basho của lộ trình Cardano, tập trung vào việc mở rộng quy mô, tối ưu hóa mạng và sổ cái, Vasil sẽ được triển khai ở tầng giao thức sử dụng Cardano's hard-fork combinator (HFC) - công nghệ sáng tạo cho phép chuyển đổi giao thức liền mạng và nâng cấp sổ cái để giảm thiếu sự gián đoạn cho end-users.

Sự nâng cấp - được đặt tên để vinh danh Vasil St.Dabov, một đại sứ của Cardano, người đã qua đời vào năm 2021 - sẽ triển khai các tính năng được nhiều người mong đợi như kết nối khuếch tán (diffusion pipelining) và nâng cấp cho Plutus - Cardano's core smart contract language. Nhiều sự cải tiến đã được nhắm đến và phát triển với sự hỗ trợ của cộng đồng phát triển rộng lớn và xuất phát từ Cardano Improvement Proposals (CIPs). Hơn nữa, một số cryptographic primitives mới sẽ được cung cấp và các quy trình script validation sẽ tiếp tục chứng kiến các điều chỉnh và tối ưu hóa góp phần vào tính nhất quán trong thời gian truyền khối (block propagation times) và tốc độ xử lý giao dịch cao hơn.

How we arrived here
Kể từ khi khởi động lại Byron năm 202, Cardano đã nâng cấp, cho phép một cộng đồng hơn 3000 SPO tạo và hỗ trợ mạng lưới chứng minh proof-of-stake phi tập trung.

Kể từ khi Mary upgrade (đầu năm 2021), người dùng được phép tạo nhiều native assets để trao đổi trên sổ cái. Tháng 9 năm 2021, Alonzo giới thiệu hỗ trợ smart contract, và Cardano liên tục phát triển nền tảng smart contract functional, với một hệ sinh thái NFT phong phú và multiple native tokens.

Sự phát triển của Cardano tạo điều kiện thuận lợi cho việc ra mắt DApp, với hàng tá đang hoạt động trên mainnet, bao gồm nhiều sàn giao dịch phi tập trung (DEXs) và thị trường NFT. Nhưng đó chỉ mới bắt đầu - đội ngũ IOG đang theo dõi hơn 1000 dự án được xây dựng trên Cardano và có thể đánh giá thấp khối lượng công việc đang diễn ra.

Vasil upgrade sẽ cung cấp khả năng chính cho phép các dự án tiếp theo khởi chạy cũng như cung cấp con đường nâng cấp (mang lại tốc độ cao, khả năng giao dịch và script mạnh mẽ) cho các DApp hiện có. Với Vasil hard fork, tham số d cũng sẽ được loại bỏ khi việc tạo block là phi tập trung hoàn toàn, điều này sẽ ngăn được việc tái liên kết. Chúng ta sẽ cùng xem kỹ hơn những thay đổi của Vasil.

Diffusion pipelining
IOG đã và đang áp dụng một loạt các tối ưu hóa thông số cần thận, ổn định (chẳng hạn như kích thước khối và đơn vị script memory tăng lên) trong suốt năm 2020 để điều chỉnh và cải thiện hiệu suất mạng. Diffusion pipelining steps things up a gear, bằng cách cải thiện thời gian truyền khối, do đó cho phép thông lượng cao hơn.

Về bản chất, nó hợp lý hóa quá trình chia sẻ thông tin về việc tạo block mới giữa những người tham gia mạng bằng cách đảm bảo rằng các block được chia sẻ (truyền) trên mạng với 5 giây sau khi được tạo. Đối với điều này, diffusion pipelining truyền các khối trước khi chúng được xác thực, do đó, có sự chồng chéo (overlapping) về thời gian để khuếch tán với thời gian cần để xác thực.

Pipelining cũng đảm bảo rằng block header tham chiếu đến hash của block trước đó được truyền chính xác. Body của block được giữ lại cùng với metadata của block tiếp theo, cản được sự tấn công DDos không cần xác thực block hoàn toàn.

Cuối cùng, diffusion pipelining sẽ thêm khả năng mở rộng bằng cách cho phép kích thước block tăng lên và cải thiện Plutus script, vì IOG tiếp tục tối ưu hóa mạng xuyên suốt thời gian còn lại trong năm.

Plutus script enhancements
Vasil sẽ cải tiến nền tảng Plutus mạnh mẽ, cho phép nhà phát triển tạo DApp nhanh và hiệu quả. Tối ưu hóa smart contract cho phép tận dụng tốt hơn mô hình EUTxO của Cardano, bao gồm:

- Bổ sung các input tham chiếu (reference inputs) (CIP-31). Việc nâng cấp này cho phép chia sẻ dữ liệu on-chain. Trước đó, datum được chứa trong transaction outputs; chúng được lưu trữ và cung cấp khả năng truy cập đến thông tin trên blockchain. Tuy nhiên, để truy cập thông tin trên datum này, người dùng (one) phải spend cho output mà datum được đính kèm. Điều này yêu cầu việc tạo lại spent output. Việc bổ sung các đầu vào tham chiếu (reference inputs) cho phép các nhà phát triển tìm datum mà không cần trải qua nhiều bước. Điều này tạo điều kiện cho việc truy cập thông tin được lưu trữ trên blockchain mà không cần spending và tạo lại UTxOs. Nó sẽ hữu ích cho oracles, for example.
- Bổ sung inline datum (CIP-32): Transaction datum được đính kèm trước đó vào output dưới dạng hash. Với việc triển khai inline datum, các nhà phát triển có thể tạo script và gắn datums trực tiếp vào output tha vì sử dụng hash của chúng. Điều này làm đơn giản việc sử dụng datum - người dùng có thể xem dữ liệu của datum thực tế hơn là so sánh nó với hash được tạo trước.
- Triển khai reference scripts (CIP-33): Trong Alonzo, khi spending một ouput được khóa với Plutus script, người dùng cần phải đưa script vào spending transaction. Điều này làm tăng kích thước của script gây ra độ trễ nhất định trong quá trình xử lý. Reference script upgrade cho phép các nhà phát triển tham chiếu script mà không cần đưa nó vào mỗi transaction. Điều này làm giảm đáng kể kích thước, cài thiện thông lượng, và giảm chi phí thực thi script (khi script chỉ cần được trả một lần).

Các nhà phát triển cũng như DApp users đều đang háo hức mong đợi những cải tiến này của Plutus. Điều này quan trọng để thông báo rằng các nhà phát triển sẽ cần thời gian để sử dụng và triển khai Plutus cải tiến cho DApps của họ để tận dụng lợi thế và nhiều người cũng sẽ tìm kiếm một cuộc kiểm tra mới (fresh audit) sau khi có sự thay đổi đáng kể trong code của họ.

Plutus V2
Vasil upgrade cũng sẽ bao gồm các cải tiến về Cardano cryptographic (cho phép các tùy chọn khả năng tương tác cao hơn so với các blockchain khác), trình thông dịch Plutus được điều chỉnh và mô hình chi phí mới (new cost model), tất cả đều là một phần của Plutus V2 script.

- Cải thiện tốc độ của trình đánh giá Plutus (Plutus evalator speed improvements): Do cải tiến trình đánh giá Plutus, cả Plutus V1 và Plutus V2 script có thông số chi phí thấp hơn trước, dẫn đến cải thiện 20-30% việc sử dụng tài nguyên script.
- Thông số mô hình chi phí được cập nhật (Updated cost model parameters): mở rộng tập hợp các function built-in bằng cách thêm 3 built-in mới: `serialiseData`, `verifyEcdsaSecp256k1Signature`, and `verifySchnorrSecp256k1Signature`. Các built-ins sau này hỗ trợ ECDSA/SECP256K elliptic curve standard, cung cấp khả năng tương tác giữa Cardano với các blockchain khác như là Bitcoin, Ethereum chẳng hạn. `serialiseData` (CIP-42) function giảm thiểu bộ nhớ và chi phí CPU cho phép tối ưu hóa cách tuần tự hóa dữ liệu.
- Datums và redeemers: Theo Vasil upgrade, các nhà phát triển sẽ có thể xem redeemers ở tất cả inputs hơn là chỉ một được truyền qua script hiện đang thực thi.

Vì cần new cost model để kích hoạt (enable) Plutus V2, các khả năng của Plutus V2 sẽ khả dụng từ sau (epoch following) Vasil hard fork. Cũng cần lưu ý rằng Plutus V1 không thể sử dụng reference inputs, reference script và inline datums.

Other enhancements (Những cải tiến khác)
Script collateral adjustment (CIP-40) là một sự điều chỉnh khác cải tiến việc xác thực transaction. Trước đây, collateral amount là 150% của transaction fee, và không có tiền thừa được cung cấp ở collateral UTxO. Có nghĩa là nếu script thất bại ở xác thực phase-2, người dùng DApp sẽ mất tất cả tiền được lưu trữ ở UTxO được chọn cho collateral.

Sau khi Vasil, các nhà phát triển DApp sẽ có khả năng xác định địa chỉ thay đổi (change address?) của script collateral. Nếu script thất bại ở xác thực phase-2, chỉ collateral amount sẽ được lấy, và số tiền còn lại sẽ được chuyển cho địa chỉ thay đổi (change address?).

Cuối cùng, Vasil tối ưu hóa quá trình Ouroboros's Verifiable Random Function (VFR). Trước Vasil, việc xác thực block yêu cầu 2 VRF functions trong mỗi bước chuyển mạng (network hop). Vasil bỏ một trong những functions này, dẫn đến việc xác thực block và tổng thời gian đồng bộ mạng nhanh hơn. Người dùng sẽ trải nghiệm hiệu suất cao hơn mà không ảnh hưởng đến thiết lập bảo mật.
