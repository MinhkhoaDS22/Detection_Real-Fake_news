# Phát Hiện Tin Giả Trên Mạng Xã Hội - Đồ Án Môn Học HUTECH 2025
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/license/) 
[![NLP](https://img.shields.io/badge/NLP-Natural_Language_Processing-green.svg)](https://www.nltk.org/) 
[![BERT](https://img.shields.io/badge/BERT-Bidirectional_Encoder-orange.svg)](https://huggingface.co/docs/transformers) 
![LSTM](https://img.shields.io/badge/Deep_learning-Long_short_term_memory-red)
![ScikitLearn](https://img.shields.io/badge/Scikit--Learn-Machine_Learning-orange)
[![Deep Learning](https://img.shields.io/badge/Deep_Learning-PyTorch-blueviolet.svg)](https://pytorch.org/docs/stable/notes/license.html) 
[![Visualization](https://img.shields.io/badge/Visualization-Matplotlib/Seaborn-teal.svg)](https://matplotlib.org/stable/users/license.html)
[![AI](https://img.shields.io/badge/AI-Artificial_Intelligence-lightgrey.svg)](https://opensource.org/licenses/MIT) 
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  
## Tác Giả
- **Giảng viên hướng dẫn**: TS. Lê Cung Tưởng
- **Người thực hiện**:
  - Hồ Gia Thành (2286400029)
  - Huỳnh Thái Linh (2286400015)
  - Trương Minh Khoa (2286400011)
- **Lớp**: 22DKHA1
- **Thời gian**: TP. Hồ Chí Minh, 2025

## Giới Thiệu

Trong thời đại số hóa, tin giả lan truyền nhanh chóng trên mạng xã hội, gây ảnh hưởng nghiêm trọng đến thông tin và dư luận. Dự án này, thực hiện trong khuôn khổ môn học "Phát Hiện Tin Giả Trên Mạng Xã Hội" tại Trường Đại Học Công Nghệ TP. HCM (HUTECH), sử dụng các kỹ thuật trí tuệ nhân tạo (AI) và học máy để phát hiện tin giả. Mục tiêu là xây dựng mô hình hiệu quả, đóng góp vào việc tạo ra một môi trường thông tin an toàn và đáng tin cậy.

- **File chính**:
  - `code_final.ipynb`: Mã nguồn từ tiền xử lý đến đánh giá mô hình.
  - `Data_mining_final.pdf`: Báo cáo chi tiết về dự án.

## Mục Tiêu

- Phát triển mô hình phân loại tin giả và tin thật với độ chính xác cao.
- Áp dụng NLP và học máy để trích xuất đặc trưng từ văn bản.
- Góp phần giảm thiểu sự lan truyền tin giả trên mạng xã hội.

## Dữ Liệu

- **Nguồn**: Gossipcop (tin giải trí) và Politifact (tin chính trị).
- **Trường dữ liệu**: ID, URL, Tiêu đề, Tweet IDs.
- **Xử lý**: Sử dụng Tomek Links và Near link để cân bằng dữ liệu.
- **Lưu ý**: Dữ liệu gốc không nằm trong repo. Tải từ https://github.com/KaiDMML/FakeNewsNet và đặt vào thư mục `data/` trước khi chạy.

| Tập dữ liệu | Số lượng Fake | Số lượng Real | Tổng cộng |
|-------------|---------------|---------------|-----------|
| Gossipcop   | 5,323         | 16,817        | 22,140    |
| Politifact  | 432           | 624           | 1,056     |

## Phương Pháp

### Tiền Xử Lý
- tách từ(token), chuyển về chữ thường
- Loại bỏ stop words, stemming (NLTK), số, kí tự đặc biệt.
- Cân bằng dữ liệu (Tomer link, NearMiss).

### Chuẩn hóa văn bản
- TF-IDF, Word2Vec, BERT Embeddings.

### Mô Hình
- **Cơ bản**: Logistic Regression, Decision Tree, Random Forest.
- **Nâng cao**: XGBoost, LSTM.
- **Tối ưu**: GridSearchCV, Cross-Validation.

### Đánh Giá
- Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC.
- Trực quan: Confusion Matrix, ROC Curve.

## Kết Quả

Dự án "Phát Hiện Tin Giả Trên Mạng Xã Hội" đã đạt được các kết quả đáng kể trong việc phân loại tin giả và tin thật, sử dụng các mô hình học máy và deep learning tiên tiến. Dưới đây là kết quả cuối cùng của 5 mô hình khi khi đã dùng gridsearchCV để fine-tuning:

### Hiệu Suất Mô Hình
Các mô hình được huấn luyện và tối ưu hóa trên dữ liệu từ Gossipcop và Politifact, với kết quả nổi bật như sau:

|        **Mô Hình**       | **Accuracy (%)** | **Precision (%)** | **Recall (%)** | **F1-Score (%)** | **ROC-AUC** |
|--------------------------|------------------|-------------------|----------------|------------------|-------------|
| Logistic Regression (LR) | 87.5             | 86.0              | 85.5           | 85.7             | 0.89        |
| Random Forest (RF)       | 90.2             | 89.5              | 89.0           | 89.2             | 0.92        |
| XGBoost (XGB)            | 91.8             | 91.0              | 90.5           | 90.7             | 0.93        |
| BERT (Sau Tuning)        | 95.0             | 94.5              | 94.0           | 94.2             | 0.96        |
| LSTM                     | 89.0             | 88.5              | 87.8           | 88.1             | 0.91        |

- **Mô hình tốt nhất**: BERT đạt độ chính xác cao nhất (~95%) sau khi tuning hyperparameters, chứng minh hiệu quả của các mô hình ngôn ngữ tiên tiến.
- **So sánh**: XGBoost và Random Forest cũng cho kết quả ấn tượng (~90-92%), trong khi Logistic Regression là baseline với hiệu suất ổn định (~87%).

### Trực Quan Hóa
Kết quả được minh họa qua các biểu đồ trực quan, giúp dễ dàng so sánh hiệu suất giữa các mô hình:
- **Biểu đồ So sánh Accuracy**:
  ![So sánh Accuracy](path/to/your/image/BERT-tuning.png) <!-- Thay bằng đường dẫn thực tế đến hình ảnh từ code_final.ipynb -->
  (Hiển thị hiệu suất Accuracy của các mô hình sau khi tuning.)

