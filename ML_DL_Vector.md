# Tìm Hiểu Về Nền Tảng Machine Learning/Deep Learning + Vector Hóa

Machine Learning (ML) và Deep Learning (DL) là các lĩnh vực cốt lõi trong trí tuệ nhân tạo (AI), tập trung vào việc xây dựng mô hình có khả năng học từ dữ liệu để đưa ra dự đoán hoặc quyết định. Deep Learning là một nhánh của Machine Learning sử dụng mạng nơ-ron nhân tạo với nhiều lớp để xử lý dữ liệu phức tạp như hình ảnh, văn bản hoặc âm thanh. Vector hóa là bước quan trọng để chuyển đổi dữ liệu thô thành dạng số mà máy tính có thể xử lý. Trong tài liệu này, chúng ta sẽ tập trung vào học có giám sát (Supervised Learning), các khái niệm cơ bản của mạng nơ-ron, và quy trình huấn luyện mô hình.

## Supervised Learning - Học Có Giám Sát

### Khái Niệm
Học có giám sát (Supervised Learning) là một phương pháp huấn luyện mô hình machine learning từ dữ liệu đã được gán nhãn đầy đủ. Dữ liệu bao gồm cặp input (đầu vào) và output (đầu ra) tương ứng, nơi output là "nhãn" đúng (ground truth). Mô hình học cách ánh xạ từ input sang output bằng cách tìm ra các mẫu (patterns) trong dữ liệu.

Mục tiêu chính là giảm thiểu sai số giữa dự đoán của mô hình và nhãn thực tế. Phương pháp này thường được sử dụng cho các bài toán phân loại (classification) hoặc hồi quy (regression):
- **Phân loại**: Dự đoán lớp (category), ví dụ: phân loại email là spam hay không spam.
- **Hồi quy**: Dự đoán giá trị liên tục, ví dụ: dự đoán giá nhà dựa trên diện tích và vị trí.

Ưu điểm: Độ chính xác cao nếu dữ liệu nhãn tốt. Nhược điểm: Cần nhiều dữ liệu nhãn, tốn kém để thu thập và gán nhãn.

### Quy Trình Huấn Luyện
Quy trình học có giám sát thường bao gồm các bước sau:

1. **Thu Thập Dữ Liệu Có Nhãn**: Thu thập dữ liệu đầu vào (features) và nhãn tương ứng. Ví dụ: Trong bài toán nhận diện chữ viết tay (OCR - Optical Character Recognition), input là ảnh chứa chữ, output là văn bản đúng (e.g., ảnh chữ "A" → nhãn "A").
   
2. **Chia Dữ Liệu**: Phân chia dữ liệu thành:
   - **Tập Huấn Luyện (Training Set)**: 70-80% dữ liệu, dùng để huấn luyện mô hình.
   - **Tập Kiểm Tra (Validation Set)**: 10-15%, dùng để điều chỉnh siêu tham số (hyperparameters) và tránh overfitting.
   - **Tập Thử Nghiệm (Test Set)**: 10-15%, dùng để đánh giá cuối cùng.

3. **Huấn Luyện Mô Hình Và Dự Đoán**: Sử dụng thuật toán (e.g., mạng nơ-ron) để học từ training set và đưa ra dự đoán trên validation/test set.

4. **Đánh Giá Kết Quả**: Sử dụng các chỉ số đo lường hiệu suất:
   - **Accuracy**: Tỷ lệ dự đoán đúng (suitable cho dữ liệu cân bằng).
   - **Precision, Recall, F1-Score**: Dùng cho dữ liệu không cân bằng, đặc biệt phân loại (e.g., F1 = 2 * (Precision * Recall) / (Precision + Recall)).
   - **Mean Squared Error (MSE)**: Cho hồi quy, công thức: MSE = (1/n) * Σ(y_i - ŷ_i)^2.
   - **Confusion Matrix**: Bảng hiển thị true positive, false positive, v.v.

### Ví Dụ
- **OCR Trong Dịch Ảnh**: Input: Ảnh chứa chữ (e.g., ảnh biển số xe). Output: Văn bản đúng (e.g., "ABC-123"). Mô hình học cách trích xuất và nhận diện ký tự.
- **Dự Đoán Bệnh Lý**: Input: Hình ảnh X-quang. Output: Nhãn "có bệnh" hoặc "không bệnh".
- **Dịch Máy**: Input: Câu tiếng Anh. Output: Câu tiếng Việt đúng.

## Vector Hóa Dữ Liệu

Máy tính chỉ xử lý dữ liệu số (numbers), nên cần chuyển đổi dữ liệu thô như text, ảnh, âm thanh thành dạng vector (mảng số). Vector hóa giúp mô hình học được các đặc trưng (features) và quan hệ giữa dữ liệu.

### Khái Niệm Và Phương Pháp
- **One-Hot Encoding**: Dùng cho dữ liệu rời rạc (categorical). Ví dụ: Các lớp "cat", "dog", "car" → [1,0,0], [0,1,0], [0,0,1]. Nhược điểm: Vector thưa (sparse), không giữ ngữ nghĩa.
- **Nhúng (Embedding)**: Biểu diễn dense vector (mảng số thực ngắn gọn) giữ được quan hệ ngữ nghĩa. Embedding học từ dữ liệu, nơi các vector gần nhau có nghĩa tương tự.
  - **Ưu Điểm**: Giảm chiều dữ liệu, giữ ngữ nghĩa (semantic similarity).
  - **Công Cụ**: Word2Vec (cho text), GloVe, BERT (advanced embedding cho NLP).

### Ví Dụ
- **Text Embedding**: 
  - "cat" = [0.12, -0.23, 0.55, ...] (vector 300 chiều).
  - "dog" = [0.15, -0.20, 0.50, ...] (gần "cat" hơn "car").
  - Khoảng cách: Sử dụng cosine similarity = (A · B) / (|A| |B|).

- **Ảnh Trong Bài Toán Dịch Ảnh**: Sử dụng Convolutional Neural Network (CNN) để trích xuất đặc trưng:
  - Input: Ảnh (ma trận pixel).
  - CNN: Áp dụng filter để tạo feature map (e.g., cạnh, hình dạng).
  - Flatten: Chuyển feature map thành vector 1D (e.g., [0.3, 0.7, -0.1, ...]).
  - Dùng cho OCR: Vector đại diện cho đặc trưng chữ cái.

- **Âm Thanh**: Spectrogram → Vector qua Mel-Frequency Cepstral Coefficients (MFCC).

## Mạng Nơ-Ron Cơ Bản

Mạng nơ-ron nhân tạo (Neural Network) mô phỏng não bộ, gồm nhiều lớp nơ-ron kết nối.

### Neuron - Thành Phần Cơ Bản
Mỗi neuron nhận input, tính toán: z = Σ(w_i * x_i) + b (w: trọng số, x: input, b: bias). Sau đó áp dụng hàm kích hoạt (activation function) để output: a = f(z).

### Activation Function
Hàm kích hoạt giới thiệu tính phi tuyến tính, giúp mô hình học các mẫu phức tạp.
- **ReLU (Rectified Linear Unit)**: f(x) = max(0, x). Ưu: Đơn giản, tránh vanishing gradient. Nhược: Dead neuron nếu x < 0. Thường dùng trong CNN.
- **Sigmoid**: f(x) = 1 / (1 + e^{-x}). Output: [0,1]. Dùng cho phân loại nhị phân. Nhược: Vanishing gradient ở cực trị.
- **Tanh**: f(x) = (e^x - e^{-x}) / (e^x + e^{-x}). Output: [-1,1]. Tương tự sigmoid nhưng cân bằng hơn.
- **Softmax**: f(x_i) = e^{x_i} / Σ e^{x_j}. Biến vector thành phân phối xác suất (sum=1). Thường dùng ở lớp output cho phân loại nhiều lớp.

### Forward Pass
Dữ liệu đi từ input layer qua hidden layers đến output layer:
- Input → Multiply weights + bias → Activation → Next layer.
- Dự đoán: Output cuối cùng (e.g., xác suất lớp).

### Backward Pass (Backpropagation)
- Tính gradient của loss theo từng trọng số bằng chain rule.
- Cập nhật trọng số: w_new = w_old - learning_rate * gradient.
- Mục tiêu: Giảm loss qua các epoch (lặp huấn luyện).

## Loss Function - Hàm Mất Mát

Loss function đo lường độ sai lệch giữa dự đoán và nhãn thực tế. Mô hình tối ưu để minimize loss.

- **Cross-Entropy Loss**: Dùng cho phân loại (categorical).
  - Công thức: L = -Σ y_i * log(ŷ_i), nơi y: one-hot vector nhãn thật, ŷ: xác suất dự đoán.
  - Ví dụ: OCR dự đoán ký tự (e.g., 26 lớp chữ cái); Dịch máy dự đoán từ tiếp theo trong từ điển.
  - Ưu: Phạt mạnh dự đoán sai tự tin cao.

- **Các Loss Khác**:
  - **Mean Squared Error (MSE)**: Cho hồi quy, L = (1/n) Σ (y_i - ŷ_i)^2.
  - **Binary Cross-Entropy**: Cho phân loại nhị phân.

## Optimizer - Tối Ưu Hóa

Optimizer cập nhật trọng số dựa trên gradient để minimize loss.

- **SGD (Stochastic Gradient Descent)**:
  - Cập nhật: w = w - η * ∇L (η: learning rate, ∇L: gradient).
  - Sử dụng batch nhỏ (mini-batch) để nhanh hơn GD đầy đủ. Nhược: Có thể kẹt local minima.

- **Adam (Adaptive Moment Estimation)**:
  - Cải tiến SGD: Kết hợp momentum (tích lũy gradient quá khứ) và adaptive learning rate (riêng cho từng tham số).
  - Công thức: Sử dụng m_t (first moment) và v_t (second moment) để cập nhật.
  - Ưu: Hội tụ nhanh, ít cần tune learning rate. Thường dùng mặc định.

- **Cách Hoạt Động Chung**:
  1. Tính loss từ forward pass.
  2. Backpropagation để lấy gradient.
  3. Optimizer cập nhật trọng số (e.g., Adam điều chỉnh dựa trên lịch sử gradient).

- **Các Optimizer Khác**: RMSProp (tương tự Adam nhưng không momentum), Adagrad (adaptive LR cho dữ liệu thưa).

## Quy Trình Tổng Quát Huấn Luyện Mô Hình

Dưới đây là quy trình tổng quát cho một mô hình Deep Learning trong học có giám sát:

1. **Chuẩn Bị Dữ Liệu**: Thu thập ảnh/text → Vector hóa (Embedding cho text, CNN feature extraction cho ảnh, hoặc One-hot).

2. **Xây Dựng Mô Hình**: Khởi tạo mạng nơ-ron với layers, activation functions.

3. **Forward Pass**: Dữ liệu vector qua mạng → Dự đoán output.

4. **Tính Loss**: So sánh dự đoán với nhãn thật (e.g., Cross-Entropy cho phân loại).

5. **Backward Pass**: Tính gradient qua backpropagation.

6. **Tối Ưu Hóa**: Cập nhật trọng số bằng optimizer (SGD/Adam). Lặp qua nhiều epoch (e.g., 10-100 epoch), theo dõi loss trên validation set để tránh overfitting (sử dụng regularization như dropout).

7. **Đánh Giá Và Triển Khai**: Test trên test set → Deploy mô hình nếu đạt yêu cầu.

Quy trình này lặp lại để mô hình "học" tốt hơn, giảm loss và tăng accuracy qua từng epoch. Trong thực tế, sử dụng framework như TensorFlow hoặc PyTorch để triển khai.
