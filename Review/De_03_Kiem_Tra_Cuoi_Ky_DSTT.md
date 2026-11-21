# ĐỀ KIỂM TRA CUỐI KỲ MÔN ĐẠI SỐ TUYẾN TÍNH - ĐỀ SỐ 03
**Thời gian làm bài:** 90 phút  
**Hình thức:** 20 Câu Trắc Nghiệm (6.0 điểm) + 10 Câu Tự Luận (4.0 điểm)  
**Tài liệu tham khảo:** Học phần Đại số tuyến tính & Lập trình Python (SymPy, NumPy)  

---

### MA TRẬN ĐỘ KHÓ ĐỀ THI (CẤU TRÚC CHUẨN)
| Mức độ độ khó | Tỷ lệ % | Số câu Trắc nghiệm (20 câu) | Số câu Tự luận (10 câu) | Tổng số câu (30 câu) |
| :--- | :---: | :---: | :---: | :---: |
| **Dễ** | 30% | 6 câu (TN1 - TN6) | 3 câu (TL1 - TL3) | 9 câu |
| **Trung bình** | 30% | 6 câu (TN7 - TN12) | 3 câu (TL4 - TL6) | 9 câu |
| **Cần suy nghĩ / Vận dụng** | 20% | 4 câu (TN13 - TN16) | 2 câu (TL7 - TL8) | 6 câu |
| **Hơi khó** | 10% | 2 câu (TN17 - TN18) | 1 câu (TL9) | 3 câu |
| **Rất khó** | 10% | 2 câu (TN19 - TN20) | 1 câu (TL10) | 3 câu |


---

## PHẦN I: TRẮC NGHIỆM (20 CÂU - 6.0 ĐIỂM)

### A. LẬP TRÌNH PYTHON CHO ĐẠI SỐ TUYẾN TÍNH (10 CÂU)

**Câu 1 (Dễ):** Trong thư viện `sympy`, lệnh nào dưới đây dùng để khởi tạo ma trận $A = \begin{pmatrix} 3 & 2 \\ 1 & 4 \end{pmatrix}$?
* A. `A = sympy.Matrix([[3, 2], [1, 4]])`
* B. `A = sympy.array([[3, 2], [1, 4]])`
* C. `A = sympy.create_matrix(3, 2, 1, 4)`
* D. `A = sympy.mat(3, 2, 1, 4)`

**Câu 2 (Dễ):** Để tính định thức của ma trận `A` trong SymPy, hàm nào sau đây là đúng?
* A. `A.det()`
* B. `A.determinant()`
* C. `sympy.det(A)`
* D. Cả A và C đều đúng.

**Câu 3 (Dễ):** Trong NumPy, để thực hiện phép nhân ma trận $A \times B$ (không phải nhân từng phần tử), câu lệnh nào chính xác?
* A. `A * B`
* B. `A @ B` hoặc `np.matmul(A, B)`
* C. `A.multiply(B)`
* D. `np.dot_product(A, B)`

**Câu 4 (Dễ):** Hàm `np.linalg.inv(A)` trong thư viện NumPy dùng để làm gì?
* A. Tính ma trận chuyển vị của $A$.
* B. Tính ma trận nghịch đảo của $A$ nếu $A$ khả nghịch.
* C. Tính định thức của $A$.
* D. Tính vết (trace) của ma trận $A$.

**Câu 5 (Dễ/TB):** Phương thức `A.rref()` trong SymPy trả về kết quả gồm những thành phần nào?
* A. Ma trận dạng bậc thang dòng thu gọn và danh sách chỉ số các cột cơ sở (pivot columns).
* B. Chỉ trả về ma trận nghịch đảo $A^{-1}$.
* C. Trả về định thức và hạng của ma trận $A$.
* D. Trả về trị riêng và vector riêng của $A$.

**Câu 6 (Trung bình):** Đoạn mã SymPy nào dưới đây giải hệ phương trình tuyến tính $A x = b$ với $A = \begin{pmatrix} 1 & 3 \\ 2 & 3 \end{pmatrix}$ và $b = \begin{pmatrix} 5 \\ 8 \end{pmatrix}$?
* A. `x = A.LUsolve(b)`
* B. `x = A.solve(b)`
* C. `x = A.inv() * b`
* D. Tất cả các phương án A, B, C đều đúng.

**Câu 7 (Trung bình):** Để tìm các trị riêng (eigenvalues) và không gian riêng (eigenspaces) của ma trận `A` trong SymPy, ta dùng hàm nào?
* A. `A.eigenvals()` và `A.eigenvects()`
* B. `np.linalg.eig(A)`
* C. `A.get_eigen()`
* D. `A.diagonalize_values()`

**Câu 8 (Trung bình):** Cho vector $u = (3, 3, -1)$ và $v = (2, 0, 5)$. Để tính tích vô hướng $u \cdot v$ trong SymPy, cú pháp nào sau đây đúng?
* A. `u.dot(v)`
* B. `u * v`
* C. `u.cross(v)`
* D. `u.inner(v)`

**Câu 9 (Vận dụng):** Để chéo hóa ma trận `A` trong SymPy thành dạng $A = P D P^{-1}$, phương thức nào trả về cặp ma trận $(P, D)$?
* A. `P, D = A.diagonalize()`
* B. `P, D = A.decompose_diagonal()`
* C. `P, D = sympy.diag(A)`
* D. `P, D = A.jordan_form()`

**Câu 10 (Hơi khó):** Đoạn mã Python nào sau đây tính chính xác hạng (rank) của ma trận $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 3 & 6 & 9 \end{pmatrix}$ trong SymPy?
* A. `A.rank()`
* B. `np.linalg.matrix_rank(np.array([[1, 2, 3], [2, 4, 6], [3, 6, 9]]))`
* C. Cả A và B đều đúng.
* D. `A.dimension()`

---

### B. ĐẠI SỐ TUYẾN TÍNH CHO HỒI QUY TUYẾN TÍNH & BÌNH PHƯƠNG TỐI THIỂU (10 CÂU)

**Câu 11 (Dễ):** Trong bài toán hồi quy tuyến tính $y = X\beta + \epsilon$, nếu hệ $X\beta = y$ vô nghiệm (vô số điểm dữ liệu không cùng thuộc 1 đường thẳng), phương pháp bình phương tối thiểu (OLS) tìm $\hat{\beta}$ bằng cách tối thiểu hóa lượng nào?
* A. Tổng bình phương phần dư (Residual Sum of Squares - RSS): $\|y - X\beta\|^2$
* B. Tổng độ dài các vector $X\beta$
* C. Định thức của ma trận $X^T X$
* D. Vết của ma trận $X$

**Câu 12 (Dễ):** Phương trình chuẩn (Normal Equation) để xác định ước lượng OLS $\hat{\beta}$ là gì?
* A. $X^T X \hat{\beta} = X^T y$
* B. $X X^T \hat{\beta} = y$
* C. $X \hat{\beta} = y$
* D. $(X + X^T) \hat{\beta} = y$

**Câu 13 (Trung bình):** Khi ma trận thiết kế $X$ có các cột độc lập tuyến tính, ma trận $X^T X$ có tính chất gì?
* A. Đối xứng và khả nghịch (khác 0 định thức).
* B. Ma trận suy biến (định thức bằng 0).
* C. Ma trận đường chéo.
* D. Ma trận tam giác trên.

**Câu 14 (Trung bình):** Ước lượng OLS $\hat{\beta}$ có công thức nghiệm tường minh là:
* A. $\hat{\beta} = (X^T X)^{-1} X^T y$
* B. $\hat{\beta} = X^T (X X^T)^{-1} y$
* C. $\hat{\beta} = (X^T y)^{-1} X$
* D. $\hat{\beta} = X^-1 y$

**Câu 15 (Trung bình):** Ma trận mũ (Hat Matrix) $H = X (X^T X)^{-1} X^T$ có vai trò gì trong mô hình hồi quy?
* A. Biến đổi vector quan sát $y$ thành vector giá trị dự báo $\hat{y} = H y$.
* B. Biến đổi vector phần dư $e$ thành $y$.
* C. Tính định thức của mô hình hồi quy.
* D. Là ma trận nghịch đảo của $X$.

**Câu 16 (Vận dụng):** Tính chất quan trọng của Ma trận chiếu (Hat Matrix) $H$ là gì?
* A. Đối xứng ($H^T = H$) và Lũy đẳng ($H^2 = H$).
* B. $H^-1 = H^T$.
* C. Định thức $\det(H) = 0$ luôn đúng với mọi $H$.
* D. Ma trận $H$ có các trị riêng bằng 0 và 1. (A và D đều đúng).

**Câu 17 (Vận dụng):** Vector phần dư $e = y - \hat{y}$ trong phương pháp OLS có quan hệ hình học như thế nào với không gian cột $\text{Col}(X)$ của ma trận thiết kế?
* A. Vector $e$ vuông góc (trực giao) với mọi cột của ma trận $X$, nghĩa là $X^T e = 0$.
* B. Vector $e$ song song với cột của ma trận $X$.
* C. Vector $e$ nằm hoàn toàn trong không gian cột $\text{Col}(X)$.
* D. Độ dài $\|e\| = 0$.

**Câu 18 (Hơi khó):** Hiện tượng đa cộng tuyến hoàn hảo (perfect multicollinearity) xảy ra khi nào và ảnh hưởng gì đến bài toán OLS?
* A. Xảy ra khi các cột của $X$ phụ thuộc tuyến tính; làm ma trận $X^T X$ không khả nghịch, không thể tính $(X^T X)^{-1}$.
* B. Xảy ra khi $y = 0$; làm mô hình luôn đúng.
* C. Làm cho $R^2 = 1$.
* D. Làm cho RSS bằng 0.

**Câu 19 (Rất khó):** Trong kỹ thuật Hồi quy Ridge (L2 Regularization), để khắc phục hiện tượng ma trận $X^T X$ bị suy biến hoặc khó nghịch đảo, người ta thêm tham số $\lambda > 0$. Nghiệm $\hat{\beta}_{\text{Ridge}}$ là:
* A. $\hat{\beta}_{\text{Ridge}} = (X^T X + \lambda I)^{-1} X^T y$
* B. $\hat{\beta}_{\text{Ridge}} = (X^T X - \lambda I)^{-1} X^T y$
* C. $\hat{\beta}_{\text{Ridge}} = (X^T X)^-1 X^T y + \lambda$
* D. $\hat{\beta}_{\text{Ridge}} = \lambda (X^T X)^-1 y$

**Câu 20 (Rất khó):** Cho phân tích QR của ma trận thiết kế $X = Q R$, trong đó $Q$ có các cột trực chuẩn ($Q^T Q = I$) và $R$ là ma trận tam giác trên khả nghịch. Công thức OLS $\hat{\beta}$ qua $Q$ và $R$ là:
* A. $R \hat{\beta} = Q^T y \implies \hat{\beta} = R^{-1} Q^T y$
* B. $\hat{\beta} = Q R^T y$
* C. $\hat{\beta} = (Q^T R)^-1 y$
* D. $\hat{\beta} = R Q^T y$

---

## PHẦN II: TỰ LUẬN (10 CÂU - 4.0 ĐIỂM)

### A. LÝ THUYẾT VÀ TÍNH TOÁN ĐẠI SỐ TUYẾN TÍNH (8 CÂU)

**Bài 1 (Dễ):** Cho hai vector $u = (3, 2, 1)$ và $v = (1, -1, 3)$ trong không gian $\mathbb{R}^3$.
1. Tính tích vô hướng $u \cdot v$ và độ dài $\|u\|, \|v\|$.
2. Kiểm tra Bất đẳng thức Cauchy-Schwarz $|u \cdot v| \le \|u\| \|v\|$.

**Bài 2 (Dễ):** Cho ma trận $A = \begin{pmatrix} 4 & 5 \\ 2 & 6 \end{pmatrix}$.
1. Tính định thức $\det(A)$.
2. Tìm ma trận nghịch đảo $A^{-1}$ (nếu có). Viết mã Python SymPy để kiểm tra kết quả.

**Bài 3 (Trung bình):** Giải hệ phương trình tuyến tính sau bằng phương pháp khử Gauss-Jordan (biến đổi dòng sơ cấp):
$$\begin{cases} x_1 + 2x_2 + z = 5 \\ 2x_1 + 5x_2 + 3z = 13 \\ x_1 + 3x_2 + 4z = 11 \end{cases}$$

**Bài 4 (Trung bình):** Trong không gian $\mathbb{R}^3$, xét phép biến đổi tuyến tính $T: \mathbb{R}^3 \to \mathbb{R}^3$ xác định bởi:
$$T(x, y, z) = (x + 3y, 2y + z, x + y + z)$$
1. Tìm ma trận tiêu chuẩn $A$ của phép biến đổi tuyến tính $T$.
2. Tính $T(1, 2, 3)$.

**Bài 5 (Trung bình):** Cho tập hợp các vector $S = \left\{ v_1 = (1, 1, 0), v_2 = (0, 1, 1), v_3 = (3, 0, 1) \right\}
$.
1. Xét tính độc lập tuyến tính hoặc phụ thuộc tuyến tính của tập $S$.
2. Tập $S$ có tạo thành một cơ sở cho không gian $\mathbb{R}^3$ hay không? Vì sao?

**Bài 6 (Vận dụng):** Cho ma trận $A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 23 \\ 3 & 6 & 33 \end{pmatrix}$.
1. Tìm hạng $\text{rank}(A)$ và một cơ sở cho không gian cột $\text{Col}(A)$.
2. Tìm số chiều và một cơ sở cho không gian hạt nhân $\text{Null}(A)$. Kiểm tra Định lý Rank-Nullity.

**Bài 7 (Vận dụng):** Tìm các trị riêng (eigenvalues) và các vector riêng (eigenvectors) tương ứng của ma trận $B = \begin{pmatrix} 4 & 0 \\ 2 & 6 \end{pmatrix}$.

**Bài 8 (Hơi khó):** Chéo hóa ma trận $C = \begin{pmatrix} 3 & 0 \\ 1 & 2 \end{pmatrix}$ (tìm ma trận khả nghịch $P$ và ma trận đường chéo $D$ sao cho $C = P D P^{-1}$). Từ đó tính $C^5$.

---

### B. ỨNG DỤNG HỒI QUY TUYẾN TÍNH & BÌNH PHƯƠNG TỐI THIỂU (2 CÂU)

**Bài 9 (Hơi khó / Nâng cao):** Cho bảng dữ liệu thực nghiệm về mối liên hệ giữa thời gian học $x$ (giờ) và điểm số $y$ (điểm):
| $x$ (Giờ học) | 1 | 2 | 4 | 5 |
| :--- | :---: | :---: | :---: | :---: |
| $y$ (Điểm số) | 5 | 7 | 10 | 12 |

1. Thiết lập ma trận thiết kế $X$ và vector quan sát $y$ cho mô hình hồi quy tuyến tính đơn $y = \beta_0 + \beta_1 x$.
2. Lập phương trình chuẩn $X^T X \hat{\beta} = X^T y$ và tìm hệ số OLS $\hat{\beta} = (\beta_0, \beta_1)^T$.
3. Dự báo điểm số của sinh viên nếu học trong $x = 6$ giờ.

**Bài 10 (Rất khó / Chuyên sâu):** Cho ma trận thiết kế $X = \begin{pmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{pmatrix}$ và vector quan sát $y = \begin{pmatrix} 3 \\ 5 \\ 6 \end{pmatrix}$.
1. Tính ma trận Hat Matrix $H = X (X^T X)^{-1} X^T$.
2. Tính vector dự báo $\hat{y} = H y$ và vector phần dư $e = y - \hat{y}$.
3. Kiểm tra tính chất trực giao giữa vector phần dư $e$ và các cột của $X$ (chứng minh $X^T e = 0$).

---

## ĐÁP ÁN VÀ LỜI GIẢI CHI TIẾT

### HƯỚNG DẪN ĐÁP ÁN TRẮC NGHIỆM (20 CÂU)

| Câu | Đáp án | Câu | Đáp án |
| :---: | :---: | :---: | :---: |
| **1** | A | **11** | A |
| **2** | D | **12** | A |
| **3** | B | **13** | A |
| **4** | B | **14** | A |
| **5** | A | **15** | A |
| **6** | D | **16** | D |
| **7** | A | **17** | A |
| **8** | A | **18** | A |
| **9** | A | **19** | A |
| **10** | C | **20** | A |

---

### LỜI GIẢI CHI TIẾT PHẦN TRẮC NGHIỆM

* **Câu 1-4:** Các hàm cơ bản SymPy/NumPy: `sympy.Matrix`, `det()`, `@` hoặc `np.matmul`, `np.linalg.inv`.
* **Câu 5:** `rref()` trả về tuple `(ma_trận_rref, chỉ_số_cột_pivot)`.
* **Câu 6:** Hệ $Ax = b$ giải bằng `LUsolve`, `solve`, hoặc `inv() * b`.
* **Câu 7-10:** `eigenvals()/eigenvects()` cho trị riêng/vector riêng; `dot()` cho tích vô hướng; `diagonalize()` cho chéo hóa; `rank()` hoặc `matrix_rank()` cho hạng ma trận.
* **Câu 11-14:** OLS tối thiểu hóa $RSS = \|y - X\beta\|^2$, phương trình chuẩn $X^T X \hat{\beta} = X^T y$, nghiệm $\hat{\beta} = (X^T X)^{-1} X^T y$.
* **Câu 15-16:** Ma trận chiếu $H = X(X^T X)^{-1}X^T$ biến đổi $y \to \hat{y}$, có tính chất đối xứng $H^T = H$, lũy đẳng $H^2 = H$, trị riêng bằng 0 và 1.
* **Câu 17:** Phần dư $e = y - \hat{y}$ vuông góc với không gian cột $\text{Col}(X)$, tức $X^T e = 0$.
* **Câu 18:** Đa cộng tuyến làm $\det(X^T X) = 0$, không tính được nghịch đảo.
* **Câu 19:** Hồi quy Ridge thêm $\lambda I$ để đảm bảo nghịch đảo: $\hat{\beta}_{\text{Ridge}} = (X^T X + \lambda I)^{-1} X^T y$.
* **Câu 20:** Phân tích QR $X = QR \implies X^T X = R^T Q^T Q R = R^T R$, suy ra $R \hat{\beta} = Q^T y \implies \hat{\beta} = R^{-1} Q^T y$.

---

### LỜI GIẢI CHI TIẾT PHẦN TỰ LUẬN

#### **Bài 1:**
1. $u \cdot v = 3 \times 1 + 2 \times (-1) + 1 \times 3 = 4$.
   * $\|u\| = \sqrt{3^2 + 2^2 + 1^2} = \sqrt{14}$.
   * $\|v\| = \sqrt{1^2 + (-1)^2 + 3^2} = \sqrt{11}$.
2. $|u \cdot v| = |4|$. Ta có $\|u\| \|v\| = \sqrt{11(14)}$.
   * Thỏa mãn $|u \cdot v| \le \|u\| \|v\|$ theo Bất đẳng thức Cauchy-Schwarz.

#### **Bài 2:**
1. $\det(A) = (4)(6) - (5)(2) = 14$.
2. Vì $\det(A) = 14 \neq 0$, $A$ khả nghịch:
   $$A^{-1} = \frac{1}{14} \begin{pmatrix} 6 & -5 \\ -2 & 4 \end{pmatrix}$$
```python
import sympy as sp
A = sp.Matrix([[4, 5], [2, 6]])
print("A_inv =", A.inv())
```

#### **Bài 3:**
Ma trận bổ sung $[A|b] = \begin{pmatrix} 1 & 2 & 1 & 5 \\ 2 & 5 & 3 & 13 \\ 1 & 3 & 4 & 11 \end{pmatrix}$.
Biến đổi dòng:
* $d_2 \to d_2 - 2d_1: \begin{pmatrix} 1 & 2 & 1 & 5 \\ 0 & 1 & 1 & 3 \\ 1 & 3 & 4 & 11 \end{pmatrix}$
* $d_3 \to d_3 - d_1: \begin{pmatrix} 1 & 2 & 1 & 5 \\ 0 & 1 & 1 & 3 \\ 0 & 1 & 3 & 6 \end{pmatrix}$
* $d_3 \to d_3 - d_2: \begin{pmatrix} 1 & 2 & 1 & 5 \\ 0 & 1 & 1 & 3 \\ 0 & 0 & 2 & 3 \end{pmatrix} \implies z = 1.5, y = 1.5, x = 0.5$.

#### **Bài 4:**
1. Ma trận tiêu chuẩn $A = [T(e_1) | T(e_2) | T(e_3)] = \begin{pmatrix} 1 & 3 & 0 \\ 0 & 2 & 1 \\ 1 & 1 & 1 \end{pmatrix}$.
2. $T(1, 2, 3) = A \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} = \begin{pmatrix} 1 + 23 \\ 4 + 3 \\ 1 + 2 + 3 \end{pmatrix} = \begin{pmatrix} 7 \\ 7 \\ 6 \end{pmatrix}$.

#### **Bài 5:**
1. Xét $\det([v_1 | v_2 | v_3]) = \begin{vmatrix} 1 & 0 & 3 \\ 1 & 1 & 0 \\ 0 & 1 & 1 \end{vmatrix} = 1(1) + 3(1) = 4$.
   * Vì $4 \neq 0$ (với $k \ge 1$), tập $S$ độc lập tuyến tính.
2. Do $S$ gồm 3 vector độc lập tuyến tính trong không gian 3 chiều $\mathbb{R}^3$, $S$ là một cơ sở của $\mathbb{R}^3$.

#### **Bài 6:**
1. Nhận xét $c_2 = 2 c_1$ và $c_3 = 3 c_1$. Do đó $\text{rank}(A) = 1$. Cơ sở không gian cột $\text{Col}(A) = \left\{ (1, 2, 3)^T \right\}$.
2. Theo Định lý Rank-Nullity: $\dim(\text{Null}(A)) = 3 - \text{rank}(A) = 3 - 1 = 2$.
   * Phương trình $x_1 + 2x_2 + 3x_3 = 0 \implies x_1 = -2x_2 - 3x_3$.
   * Cơ sở $\text{Null}(A) = \left\{ (-2, 1, 0)^T, (-3, 0, 1)^T \right\}$.

#### **Bài 7:**
Ma trận tam giác dưới $B = \begin{pmatrix} 4 & 0 \\ 2 & 6 \end{pmatrix}$.
* Trị riêng là các phần tử trên đường chéo chính: $\lambda_1 = 4, \lambda_2 = 6$.
* Vector riêng ứng với $\lambda_1 = 4$: $(B - (4)I) v = 0 \implies \begin{pmatrix} 0 & 0 \\ 2 & 2 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = 0 \implies x + y = 0 \implies v_1 = (1, -1)^T$.
* Vector riêng ứng với $\lambda_2 = 6$: $(B - (6)I) v = 0 \implies \begin{pmatrix} -2 & 0 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = 0 \implies x = 0 \implies v_2 = (0, 1)^T$.

#### **Bài 8:**
Ma trận $C = \begin{pmatrix} 3 & 0 \\ 1 & 2 \end{pmatrix}$.
* Trị riêng $\lambda_1 = 3, \lambda_2 = 2$.
* Với $\lambda_1 = 3$: vector riêng $v_1 = (1, 1)^T$ (nếu $k \neq 2$). Với $\lambda_2 = 2$: $v_2 = (0, 1)^T$.
* Ma trận đường chéo $D = \begin{pmatrix} 3 & 0 \\ 0 & 2 \end{pmatrix}$, $P = \begin{pmatrix} 1 & 0 \\ 1 & 1 \end{pmatrix}$.
* $C^5 = P D^5 P^{-1} = P \begin{pmatrix} 3^5 & 0 \\ 0 & 32 \end{pmatrix} P^{-1}$.

#### **Bài 9:**
1. Ma trận thiết kế $X = \begin{pmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 4 \\ 1 & 5 \end{pmatrix}$, $y = \begin{pmatrix} 5 \\ 7 \\ 10 \\ 12 \end{pmatrix}$.
2. $X^T X = \begin{pmatrix} 4 & 12 \\ 12 & 46 \end{pmatrix}$, $X^T y = \begin{pmatrix} 34 \\ 109 \end{pmatrix}$.
   * Giải $(X^T X) \hat{\beta} = X^T y \implies \hat{\beta} = (X^T X)^{-1} X^T y$.
3. Thay $x = 6$ vào phương trình dự báo $\hat{y} = \beta_0 + \beta_1 (6)$.

#### **Bài 10:**
1. $X = \begin{pmatrix} 1 & 1 \\ 1 & 2 \\ 1 & 3 \end{pmatrix} \implies X^T X = \begin{pmatrix} 3 & 6 \\ 6 & 14 \end{pmatrix}$.
   * $(X^T X)^{-1} = \frac{1}{6} \begin{pmatrix} 14 & -6 \\ -6 & 3 \end{pmatrix}$.
   * $H = X (X^T X)^{-1} X^T = \frac{1}{6} \begin{pmatrix} 5 & 2 & -1 \\ 2 & 2 & 2 \\ -1 & 2 & 5 \end{pmatrix}$.
2. $\hat{y} = H y = \begin{pmatrix} 3.167 \\ 4.667 \\ 6.167 \end{pmatrix} \implies e = y - \hat{y}$.
3. Tính $X^T e = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 2 & 3 \end{pmatrix} e = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$, chứng minh vector phần dư trực giao với không gian cột của $X$.
