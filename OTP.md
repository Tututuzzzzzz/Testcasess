# Nền Tảng Machine Learning / Deep Learning + Vector Hóa

## Mục lục
1. [Supervised Learning - Học Có Giám Sát](#1-supervised-learning---học-có-giám-sát)
2. [Vector Hóa Dữ Liệu](#2-vector-hóa-dữ-liệu)
3. [Mạng Nơ-Ron Cơ Bản](#3-mạng-nơ-ron-cơ-bản)
4. [Loss Function](#4-loss-function)
5. [Optimizer](#5-optimizer)
6. [Quy Trình Huấn Luyện Mô Hình](#6-quy-trình-huấn-luyện-mô-hình-deep-learning)

---

## 1. Supervised Learning - Học Có Giám Sát

### Khái niệm
Học có giám sát là phương pháp huấn luyện mô hình từ dữ liệu **có nhãn** (input → output đúng).

- **Phân loại (Classification)**: Dự đoán lớp (ví dụ: spam / không spam).
- **Hồi quy (Regression)**: Dự đoán giá trị liên tục (ví dụ: giá nhà).

---

### Quy trình huấn luyện

1. **Thu thập dữ liệu**: Cặp \((x, y)\).
2. **Chia dữ liệu**:
   - Training set: 70–80%
   - Validation set: 10–15%
   - Test set: 10–15%
3. **Huấn luyện mô hình**: Học ánh xạ \( f: X \to Y \).
4. **Đánh giá mô hình**: Sử dụng các chỉ số đo lường.

---

### Các chỉ số đánh giá

- **Accuracy**  
  Accuracy = (Số dự đoán đúng) / (Tổng số mẫu)

- **Precision**  
  Precision = TP / (TP + FP)

- **Recall**  
  Recall = TP / (TP + FN)

- **F1-Score**  
  F1 = 2 × (Precision × Recall) / (Precision + Recall)

- **Mean Squared Error (MSE)**  
  MSE = (1 / n) × Σ(yᵢ − ŷᵢ)²


---

## 2. Vector Hóa Dữ Liệu

Máy tính chỉ xử lý dữ liệu số → cần chuyển dữ liệu thô thành vector.

### One-Hot Encoding
Ví dụ:

| Lớp | One-hot vector |
|-----|---------------|
| cat | [1, 0, 0]     |
| dog | [0, 1, 0]     |
| car | [0, 0, 1]     |

---

### Embedding
Biểu diễn dạng dense vector, giữ ngữ nghĩa:
- `"cat"` → \([0.12, -0.23, 0.55, \dots]\)
- `"dog"` → \([0.15, -0.20, 0.50, \dots]\)

**Cosine similarity**:
\[
\cos(\theta) = \frac{\mathbf{A} \cdot \mathbf{B}}{\|\mathbf{A}\| \times \|\mathbf{B}\|}
\]

---

## 3. Mạng Nơ-Ron Cơ Bản

### Công thức Neuron
\[
z = \sum_{i=1}^{n} w_i x_i + b
\]
\[
a = f(z)
\]
- \( w_i \): trọng số  
- \( b \): bias  
- \( f \): activation function

---

### Activation Functions

- **ReLU**:
\[
f(x) = \max(0, x)
\]
- **Sigmoid**:
\[
f(x) = \frac{1}{1 + e^{-x}}
\]
- **Tanh**:
\[
f(x) = \frac{e^{x} - e^{-x}}{e^{x} + e^{-x}}
\]
- **Softmax**:
\[
f(x_i) = \frac{e^{x_i}}{\sum_{j=1}^{K} e^{x_j}}
\]

---

### Forward Pass
Dữ liệu đi từ input → hidden layers → output.

---

### Backpropagation
- Tính gradient bằng **chain rule**.
- Cập nhật trọng số:
\[
w_{\text{new}} = w_{\text{old}} - \eta \cdot \frac{\partial L}{\partial w}
\]
- \(\eta\): learning rate.

---

## 4. Loss Function

- **Cross-Entropy Loss**:
\[
L = -\sum_{i=1}^{C} y_i \log(\hat{y}_i)
\]

- **Binary Cross-Entropy**:
\[
L = - \left[ y \log(\hat{y}) + (1-y) \log(1 - \hat{y}) \right]
\]

- **Mean Squared Error (MSE)**:
\[
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
\]

---

## 5. Optimizer

### SGD
\[
w_{\text{new}} = w_{\text{old}} - \eta \cdot \nabla L
\]
- \(\eta\): learning rate  
- \(\nabla L\): gradient

---

### Adam
Adam sử dụng **momentum** và **adaptive learning rate**:

\[
m_t = \beta_1 m_{t-1} + (1-\beta_1)g_t
\]
\[
v_t = \beta_2 v_{t-1} + (1-\beta_2)g_t^2
\]
\[
\hat{m}_t = \frac{m_t}{1 - \beta_1^t}, \quad \hat{v}_t = \frac{v_t}{1 - \beta_2^t}
\]
\[
\theta_{t+1} = \theta_t - \eta \frac{\hat{m}_t}{\sqrt{\hat{v}_t} + \epsilon}
\]

---

## 6. Quy Trình Huấn Luyện Mô Hình Deep Learning

1. **Chuẩn bị dữ liệu** → vector hóa (One-hot / Embedding / CNN features).
2. **Xây dựng mô hình** → layers + activation.
3. **Forward pass** → tính output.
4. **Tính loss** → so sánh với ground truth.
5. **Backward pass** → tính gradient.
6. **Tối ưu hóa** → SGD / Adam.
7. **Lặp qua nhiều epoch** → theo dõi loss & accuracy.
8. **Đánh giá trên test set** → deploy.

---

