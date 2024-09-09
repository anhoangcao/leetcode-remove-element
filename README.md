
# Bài toán: Loại bỏ phần tử khỏi mảng

## Mô tả bài toán

Cho một mảng số nguyên `nums` và một giá trị số nguyên `val`. Nhiệm vụ của bạn là loại bỏ tất cả các phần tử có giá trị bằng `val` trong mảng `nums`, thực hiện việc này trực tiếp (in-place). Thứ tự của các phần tử có thể thay đổi. Sau đó, trả về số lượng các phần tử không bằng `val`.

Số phần tử còn lại sau khi loại bỏ sẽ được lưu trong `k`. Bạn cần đảm bảo:
- Các phần tử từ `nums[0]` đến `nums[k-1]` chứa các giá trị khác `val`.
- Các phần tử còn lại không quan trọng.

## Cách mà trình kiểm thử sẽ đánh giá bài làm của bạn:

1. Trình kiểm thử sẽ tạo ra mảng `nums` và giá trị `val`.
2. Gọi hàm `removeElement(nums, val)` để thực thi thuật toán của bạn.
3. Sau đó sẽ kiểm tra số phần tử còn lại (`k`) và so sánh với số phần tử mong đợi.
4. Các phần tử trong mảng từ `nums[0]` đến `nums[k-1]` sẽ được sắp xếp để đối chiếu với kết quả mong đợi.

## Ví dụ

### Ví dụ 1:
```plaintext
Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Giải thích: Hàm của bạn nên trả về k = 2, với 2 phần tử đầu tiên của mảng là 2.
Các phần tử sau k không quan trọng.
```

### Ví dụ 2:
```plaintext
Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Giải thích: Hàm của bạn nên trả về k = 5, với 5 phần tử đầu tiên của mảng là [0, 1, 4, 0, 3].
Các phần tử sau k không quan trọng.
```

## Hướng dẫn

### Cách tiếp cận:

1. Sử dụng một biến con trỏ `k` để theo dõi vị trí cho các phần tử không bằng `val`.
2. Duyệt qua mảng:
   - Nếu phần tử hiện tại khác `val`, gán nó vào vị trí `k` và tăng `k`.
3. Sau khi duyệt xong, các phần tử từ `nums[0]` đến `nums[k-1]` sẽ là các phần tử khác `val`.
4. Trả về `k`.

### Mã nguồn

```java
public class Solution {
    public int removeElement(int[] nums, int val) {
        int k = 0; // Con trỏ theo dõi vị trí cho các phần tử không bằng val

        // Duyệt qua mảng nums
        for (int i = 0; i < nums.length; i++) {
            // Nếu phần tử khác val, gán nó vào vị trí k và tăng k
            if (nums[i] != val) {
                nums[k] = nums[i];
                k++;
            }
        }

        // Trả về k là số phần tử không bằng val
        return k;
    }
}
```

### Độ phức tạp

- **Độ phức tạp thời gian**: O(n), với `n` là số phần tử trong mảng `nums`. Chúng ta chỉ cần duyệt qua mảng một lần.
- **Độ phức tạp không gian**: O(1), vì chúng ta không sử dụng bộ nhớ bổ sung ngoài một số biến lưu trữ tạm thời.

## Liên hệ

Nếu bạn có bất kỳ câu hỏi nào về bài toán hoặc giải pháp, vui lòng liên hệ qua [email@example.com].
