# MAD101_Assignment_1-
Nguyễn Bá Tâm, Trần Ngọc Tùng, Lưu Đình Huy

<img width="712" height="507" alt="image" src="https://github.com/user-attachments/assets/a1459d69-de97-4370-af22-e846b1425750" />



### Câu 1.1: Tìm |B \ A|
- **Tập A**: gồm các số tự nhiên `n` sao cho `n^2 + 2n` chia hết cho 15.  
  → Điều kiện kiểm tra: `(n*n + 2*n) % 15 == 0`.  
- **Tập B**: gồm tất cả số từ 0 đến 10000.  
- **Ý tưởng**:  
  1. Sinh tập A bằng cách duyệt từ 0 → 10000 và giữ lại số thỏa mãn điều kiện.  
  2. Tập B có sẵn bằng `range(0, 10001)`.  
  3. Lấy hiệu `B \ A` bằng cách lọc các số thuộc B mà không thuộc A.  
  4. Đếm số phần tử.  

---

### Câu 1.2: Phần tử thứ 100 của A ∩ B theo thứ tự giảm dần
- **Ý tưởng**:  
  1. Giao của A và B chính là A (vì A đã được lọc từ B).  
  2. Sắp xếp A theo thứ tự giảm dần (`sorted(..., reverse=True)`).  
  3. Lấy phần tử thứ 100 (chỉ số 99 trong Python).  

---

### Câu 1.3: Tập C = { n | n = p * q, với p, q là 2 số nguyên tố phân biệt }
- **Ý tưởng**:  
  1. Viết hàm `is_prime(x)` để kiểm tra số nguyên tố.  
  2. Sinh danh sách tất cả số nguyên tố nhỏ hơn 5000 để dùng kiểm tra nhanh.  
     (5000 là đủ vì `p * q ≤ 10000`, nên `p` và `q` đều ≤ 5000).  
  3. Với mỗi số `n` từ 6 → 10000, kiểm tra xem có thể viết thành `p * q` với `p, q` nguyên tố và `p ≠ q`.  
  4. Tạo danh sách C.  
  5. Lấy phần tử thứ 100 theo thứ tự tăng dần.  

---

### Câu 1.4: Tìm |B ∩ C|
- **Ý tưởng**:  
  1. Vì cả C và B đều ≤ 10000, ta chỉ cần lọc lại những phần tử của C có trong B.  
  2. Đếm số phần tử đó.
  
<img width="675" height="182" alt="image" src="https://github.com/user-attachments/assets/64ee8cb0-47d3-4185-8179-2fc7882ceb8a" />
# Câu 3:


So sánh hai mệnh đề logic:

\[
(p \lor q) \rightarrow r \quad \text{và} \quad (p \oplus r) \land q
\]

---

## 💡 Hướng tư duy & cách làm

1. **Phân tích mệnh đề**  
   - \((p \lor q) \rightarrow r\) tương đương với:  
     \[
     \neg(p \lor q) \lor r
     \]  
   - \((p \oplus r) \land q\) giữ nguyên (⊕ là XOR).

2. **Chuyển sang Python**  
   - `not(p or q) or r`  
   - `(p ^ r) and q`

3. **Lập bảng chân trị bằng code**  
   - Cho `p, q, r` chạy lần lượt các giá trị `True/False`.  
   - Tính giá trị của cả 2 mệnh đề.  
   - So sánh chúng → nếu bằng nhau thì in ra.

4. **Ý nghĩa**  
   - Đây là cách kiểm tra xem hai mệnh đề có **tương đương logic** hay không.  
   - Việc dùng vòng lặp giúp duyệt nhanh toàn bộ 8 trường hợp của `p, q, r` thay vì lập bảng thủ công.



     
