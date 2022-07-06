UTxO:

- Allows for the simpler parallelization of transactions in smart contract.
- Cần truy vấn thông tin từ các block khác
- Có thể ghi các transaction của cùng một account vào block
- Size of blockchain: specifies the state after the transition, the newly generated transaction outputs, include more data than Account transaction

Account-base model:

- Transaction affecting the same account should be executed sequentially
- Chỉ cần quan tâm input của transaction
- UTxO chỉ được tạo ra khi block kết thúc -> không thể ghi các transaction của cùng một account trên một block
- Size of blockchain: more efficient memory usage. Lưu balance của account tiết kiệm bộ nhớ hơn so với lưu trữ nhiều UTxO bao gồm tổng balance của account. Transaction cũng nhỏ hơn vì chỉ xác định sender, receiver, transfer amount và chữ ký.

##### Coin Selection Algorithm

Thuật toán Coin Selection của UTxO: https://bitcoin.stackexchange.com/questions/1077/what-is-the-coin-selection-algorithm

The **Coin Selection Algorithm** logic to transfer Target amount

1. If any of your _UTXO²_ matches the _Target¹_ it will be used.
2. If the "sum of all your UTXO smaller than the _Target_" happens to match the Target, they will be used. (This is the case if you sweep a complete wallet.)
3. If the "sum of all your UTXO smaller than the _Target_" doesn't surpass the target, the smallest UTXO greater than your Target will be used.
4. Else Bitcoin Core does 1000 rounds of randomly combining unspent transaction outputs until their sum is greater than or equal to the Target. If it happens to find an exact match, it stops early and uses that. Otherwise it finally settles for the minimum of

- the smallest UTXO greater than the Target
- the smallest combination of UTXO it discovered in Step 4.

As David mentioned, the subset problem will first restrict to UTXO that have at least one confirmation if sent by yourself, or six confirmations if received from another wallet, then later relaxes these requirements in two further passes if no suitable set of UTXO could be discovered.

Some examples
Alice has four UTXO:

- UTXO_A 0.1BTC
- UTXO_B 0.3BTC
- UTXO_C 0.5BTC
- UTXO_D 1BTC

I will be ignoring transaction fees for simplicity's sake.

###### Example 1:

Alice wants to send 0.3BTC.
Bitcoin Core discovers that `UTXO_B` matches the _Target_, and it only uses `UTXO_B` as input.

###### Example 2:

Alice wants to send 0.4BTC.
Bitcoin Core finds that `UTXO_C` is the smallest UTXO greater than the _Target_, and that the sum of all UTXO smaller than the target (i.e. `UTXO_A + UTXO_B = 0.1 + 0.3 = 0.4`) matches the _Target_ here. Both `UTXO_A` and `UTXO_B` are used as inputs.

###### Example 3:

Alice wants to send 0.45BTC.
Bitcoin Core finds that `UTXO_C` is the smallest UTXO greater than the _Target_, and that the sum of all UTXO smaller than the target (i.e. `UTXO_A + UTXO_B = 0.1 + 0.3 = 0.4`) does not surpass the _Target_. `UTXO_C` is used as the sole input, being the next smallest input greater than the _Target_.

###### Example 4:

Alice wants to send 0.35BTC.
Bitcoin Core finds that `UTXO_C` is the smallest UTXO greater than the _Target_, and that the sum of all UTXO smaller than the target (i.e. `UTXO_A + UTXO_B = 0.1 + 0.3 = 0.4`) does not match the _Target_. It adds up randomly selected UTXO 1000 times until they surpass the _Target_, remembering the smallest sufficient combination. The smallest sufficient combination is then compared with the smallest single input greater than the target. Assuming that it does find the best combination here which would be `UTXO_A + UTXO_B`, it finds that `Target < UTXO_A + UTXO_B < UTXO_C` and uses `UTXO_A` and `UTXO_B` as inputs.

###### Example 5:

Alice wants to send 0.6BTC.
Bitcoin Core finds that `UTXO_D` is the smallest UTXO greater than the _Target_, and that the sum of all UTXO smaller than the target (i.e. `UTXO_A + UTXO_B + UTXO_C = 0.1 + 0.3 + 0.5 = 0.9`) does not match the _Target_. It starts trying random combinations as before, and in this situation would probably discover that `UTXO_A + UTXO_C = Target`. As it finds a combination that matches the _Target_, it breaks and immediately goes with that combination. `UTXO_A` and `UTXO_C` are used as inputs.
