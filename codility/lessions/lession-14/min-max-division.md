- [Min Max Division](#sec-1)
- [Input:](#sec-2)
  - [Assume that:](#sec-2-1)
  - [Complexity:](#sec-2-2)
- [Phân tích](#sec-3)
  - [Yêu cầu bài toán:](#sec-3-1)
  - [Phân tích bài toán:](#sec-3-2)
  - [Ý tưởng](#sec-3-3)
  - [Phân tích ý tưởng](#sec-3-4)
  - [Triển khai](#sec-3-5)

# Min Max Division<a id="sec-1"></a>

Divide array A into K blocks and minimize the largest sum of any block.

# Input:<a id="sec-2"></a>

## Assume that:<a id="sec-2-1"></a>

N and K are integers within the range [1..100,000]; M is an integer within the range [0..10,000]; each element of array A is an integer within the range [0..M].

## Complexity:<a id="sec-2-2"></a>

expected worst-case time complexity is O(N\*log(N+M)); expected worst-case space complexity is O(1) (not counting the storage required for input arguments).

# Phân tích<a id="sec-3"></a>

## Yêu cầu bài toán:<a id="sec-3-1"></a>

## Phân tích bài toán:<a id="sec-3-2"></a>

Cho 1 array A với N phần tử, chia A thành K phần liên tiếp sao cho tổng của mỗi block là nhỏ nhất có thể Q: Như nào tính là block ? A: bất cứ sub-array nào cũng tính là block của A ví dụ A: [1, 2, 3] => block có thể là [], [1], [2] hoặc [2, 3] Q: tổng của block là ? A: tổng của sub-array => [] có tổng là 0 [1] => tổng là 1

## Ý tưởng<a id="sec-3-3"></a>

Q: cho Array A với N phần tử mỗi phần tử tử [0..10e3] (không có số nào âm), tổng của block sẽ tăng khi có thêm nhiều phần tử đúng không ? A: Đúng vậy vì càng thêm sẽ càng tăng Q: Nếu chia array A thành K block vậy mỗi block sẽ có bao nhiêu phần tử ? A: Có thể N/K phần tử mỗi block nếu như N chia hết cho K, nếu không thì phần còn lại sẽ là dư của N/K ak N % K phần tử? Q: vậy sum mininum của mỗi block sẽ bao nhiêu ? A: Mỗi block có N/K hoặc N%K phần tử vậy tổng sẽ >= N/K \* Min(Array) hoặc N%K \* Min(Array), ta tìm được cận dưới của giá trị cần tìm Q: vậy trên là bao nhiều ? A: tương tự sẽ là N/K \* Max(Array) hoặc N%K \* Max(Array) Q: gọi X là giá trị cần tìm thì Min <= X <= Max ? ta cần làm sao ? A: Ta có thể loop Min => Max nếu tìm block thảo mãn đk thì trả về giá trị nếu không tăng gái trị và next looop Q: có cách nào improve không ? A: có thể sử dụng binary search Q: điều kiệu để tăng biến lặp khi sử dụng tìm kiếm nhị phân là gì ? A: check(array, mid) => check có thể tạo được K block và mỗi block có tổng là m không

## Phân tích ý tưởng<a id="sec-3-4"></a>

Q: độ hiệu năng là bao nhiều ? A: Binary search sẽ là log(M) vì M là max giá trí có thể có, đoạn code check cần lặp lại cả array `> N * log(M) Q: áp dụng ý tưởng cho // K` 3, M = 5, A = [2, 1, 5, 1, 2, 2, 2] Q: Min của A, Max của A ? A: MinA = 1, MaxA = 5 Q: Cận dưới là ? A: Cận dưới là Min(N/K \* MinA, (N/K + N%K) \* MinA) = Min(7/3 \* 1, (7/3 + 7%3) \* 1) = Min(2, 3) = 2 Q: cận trên là bao nhiều ? A: Max(N/K \* MaxA, (N/K + N%K) \* MaxA) = Max(7/3 \* 5, (7/3 + 7%3) \* 5) = Max(10, 15) = 15 Q: tiếp làm gì ? A: binary search 2 => 15 Q: mid là bao nhiều ? A: (2 + 15) / 2 = 8 Q: tạo được 3 block nào mà sum < 8 không ? A: check it loop A từ 0 => N - 1, tìm đc [0, 2] => sum(8) return true ok next Q: tiếp theo là gì ? A: giảm end => end = middle - 1 = 7 Q: middle mới là ? A: (2 + 7) / 2 = 4 Q: tạo được block sum <= 4 không ? A: 4 < MaxA => không thể tạo được block return false Q: neeus false thì sao ? A: thì tăng start lên => start = middle + 1 = 5 Q: mid mới là bn ? A: (5 + 7) / 2 = 6 Q: có thể tạo đc block 6 không ? A: check nào => [0, 1], [2, 3], [4, 6] OK Q: ok làm gì tiếp ? A: giảm end => end = middle - 1 = 6 - 1 = 5 Q: tiếp theo ? A: vì 5 <= 5 lên check tiếp với sum = 5 Q: tạo được block với tổng là 5 không ? A: check it ? sum = 5 => [0, 1], [2], [3, 5] => dư phân tử cuối suy ra không tao được Q: làm gì khi không tạo đưuoc ? A: tăng start lên start = middle + 1 = 5 + 1 = 6 Q: tiếp tục không ? A: không vì start > end Q: trả về kêt quả A: trả về 6 done

## Triển khai<a id="sec-3-5"></a>

Code thôi
