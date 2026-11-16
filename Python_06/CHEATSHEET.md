# Cheatsheet — Giải Đại Số Tuyến Tính bằng Python

> Dùng **SymPy** khi cần đáp án chính xác (`1/3`, `√5`, `λ²−4λ+3`) — tức là khi làm bài tập.
> Dùng **NumPy** khi cần số thập phân nhanh trên dữ liệu lớn.

```python
import sympy as sp, numpy as np
from sympy import Matrix, Rational, symbols, sqrt, pi, simplify, factor, eye, zeros
sp.init_printing(use_unicode=True)
lam = symbols('lamda'); x, y, z = symbols('x y z')

A = Matrix([[2, 1], [1, -1]])     # ma trận
u = Matrix([1, 2, 2])             # vector (cột)
```

---

## Lecture 02–03 · Vector, độ dài, góc, tích vô hướng

| Đề hỏi | Lệnh |
|---|---|
| `u + v`, `ku` | `u + v`, `k*u` |
| Tích vô hướng `u·v` | `u.dot(v)` |
| Độ dài `‖u‖` | `u.norm()` |
| Khoảng cách `d(u,v)` | `(u - v).norm()` |
| Vector đơn vị | `u / u.norm()` |
| Vuông góc? | `u.dot(v) == 0` |
| Góc (radian) | `sp.acos(u.dot(v)/(u.norm()*v.norm()))` |
| Góc (độ) | `sp.deg(...)` rồi `float(...)` |
| Hình chiếu `u` lên `v` | `(u.dot(v)/v.dot(v))*v` |
| Tích có hướng (R³) | `u.cross(v)` |

## Lecture 04 · Ma trận

| Đề hỏi | Lệnh |
|---|---|
| Cộng / nhân số | `A + B`, `3*A` |
| Nhân ma trận | `A*B` (nhớ: `A*B ≠ B*A`) |
| Chuyển vị | `A.T` |
| Lũy thừa | `A**2` |
| Vết | `A.trace()` |
| Kích thước | `A.shape` |
| Đối xứng? | `A == A.T` |

## Lecture 05 · Biến đổi tuyến tính

| Đề hỏi | Lệnh |
|---|---|
| Ma trận chuẩn từ `T(e₁), T(e₂)` | `Matrix.hstack(Te1, Te2)` |
| Ma trận từ công thức | `Matrix([x+2*y, 3*x-y]).jacobian([x, y])` |
| Ảnh `T(v)` | `A * v` |
| Hạch `ker(T)` | `A.nullspace()` |
| Ảnh `im(T)` | `A.columnspace()` |
| Đơn ánh? | `len(A.nullspace()) == 0` |
| Toàn ánh? | `A.rank() == A.rows` |
| Hợp `S∘T` | `A_S * A_T` (phải → trái) |
| Quay góc θ | `Matrix([[cos(θ),-sin(θ)],[sin(θ),cos(θ)]])` |
| Hình chiếu lên `span{v}` | `(v*v.T)/v.dot(v)` |

## Lecture 06 · Hệ phương trình

| Đề hỏi | Lệnh |
|---|---|
| RREF | `A.rref()` → `(ma trận, cột trụ)` |
| Ma trận mở rộng | `Matrix.hstack(A, b)` |
| Giải hệ | `sp.linsolve((A, b), [x, y, z])` |
| Nghiệm tổng quát có tham số | `A.gauss_jordan_solve(b)` |
| Hệ thuần nhất `Ax=0` | `A.nullspace()` |

**Biện luận:** `rank(A) < rank([A|b])` → vô nghiệm · `= n` → duy nhất · `< n` → vô số nghiệm.
`linsolve` trả `EmptySet` nghĩa là **vô nghiệm**; `tau0, tau1` là **tham số tự do**.

## Lecture 07 · Nghịch đảo

| Đề hỏi | Lệnh |
|---|---|
| Nghịch đảo | `A.inv()` |
| Qua `[A\|I]` | `Matrix.hstack(A, eye(n)).rref()[0]` |
| Bằng phụ hợp | `A.adjugate() / A.det()` |
| Khả nghịch? | `A.det() != 0` |
| Giải hệ bằng nghịch đảo | `A.inv() * b` |
| Ma trận sơ cấp | `E = eye(n)` rồi làm phép biến đổi hàng trên `E` |

## Lecture 08–09 · Không gian con, cơ sở, hạng

Xếp các vector thành **cột**: `A = Matrix.hstack(v1, v2, v3)`

| Đề hỏi | Lệnh |
|---|---|
| Độc lập tuyến tính? | `A.rank() == A.cols` |
| Quan hệ phụ thuộc | `A.nullspace()` |
| `b ∈ span`? | `sp.linsolve((A, b))` khác `EmptySet` |
| Cơ sở của span | `A.columnspace()` |
| `dim span` | `A.rank()` |
| Cơ sở không gian hàng | `A.rowspace()` |
| Hạng / số chiều hạch | `A.rank()` / `len(A.nullspace())` |
| Là cơ sở của Rⁿ? | độc lập **và** số vector `= n` |
| Toạ độ theo cơ sở B | `sp.linsolve((B, v))` |

**Định lý hạng:** `rank + nullity = số cột`

## Lecture 10 · Định thức

| Đề hỏi | Lệnh |
|---|---|
| Định thức | `A.det()` |
| Ma trận con (minor) | `A.minor_submatrix(i, j)` |
| Phần bù đại số | `A.cofactor(i, j)` / `A.cofactor_matrix()` |
| Ma trận phụ hợp | `A.adjugate()` |
| Cramer | `Ai = A.copy(); Ai[:, i] = b; Ai.det()/A.det()` |
| Tìm `k` để suy biến | `sp.solve(A.det(), k)` |

## Lecture 11–12 · Trị riêng, vector riêng, chéo hóa

| Đề hỏi | Lệnh |
|---|---|
| Đa thức đặc trưng | `A.charpoly(lam).as_expr()` |
| Phân tích nhân tử | `factor(...)` |
| Trị riêng + bội đại số | `A.eigenvals()` → `{λ: bội}` |
| Vector riêng | `A.eigenvects()` → `[(λ, bội, [vector])]` |
| Bội hình học | số vector trong `eigenvects()` của λ đó |
| Chéo hóa được? | `A.is_diagonalizable()` |
| Tìm `P, D` | `P, D = A.diagonalize()` |
| Kiểm tra | `simplify(P.inv()*A*P) == D` |
| `Aⁿ` nhanh | `P * D**n * P.inv()` |
| Số gần đúng | `np.linalg.eig(np.array(A, dtype=float))` |

**Kiểm tra nhanh:** tổng trị riêng `= tr(A)`, tích trị riêng `= det(A)`.

---

## Lỗi thường gặp

| Hiện tượng | Xử lý |
|---|---|
| Ra `0.333` thay vì `1/3` | Đừng nhập số thực; dùng số nguyên hoặc `Rational(1,3)` |
| Ra `1.4142` thay vì `sqrt(2)` | Đang dùng NumPy → chuyển sang SymPy |
| `ShapeError` | Số cột của A ≠ số hàng của B |
| `NonInvertibleMatrixError` | `det(A) = 0`, không có nghịch đảo |
| `EmptySet` | Hệ vô nghiệm (không phải lỗi) |
| `A.diagonalize()` lỗi | Kiểm tra `A.is_diagonalizable()` trước |
