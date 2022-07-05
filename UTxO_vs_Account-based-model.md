UTxO:

- Allows for the simpler parallelization of transactions in smart contract.
- Cần truy vấn thông tin từ các block khác
- Có thể ghi các transaction của cùng một account vào block

Account-base model:

- Transaction affecting the same account should be executed sequentially
- Chỉ cần quan tâm input của transaction
- UTxO chỉ được tạo ra khi block kết thúc -> không thể ghi các transaction của cùng một account trên một block

Thuật toán Coin Selection của UTxO: https://bitcoin.stackexchange.com/questions/1077/what-is-the-coin-selection-algorithm
