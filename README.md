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
- **Trường:** Trường Đại học Công nghệ TP. Hồ Chí Minh — *Khoa Công Nghệ Thông Tin* - *Ngành khoa học dữ liệu*
- **Năm thực hiện:** 7/11/2025 

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

|        **Mô Hình**       | **Accuracy (%)** | **Precision (%)** | **Recall (%)** | **F1-Score (%)** |
|--------------------------|------------------|-------------------|----------------|------------------|
| Logistic Regression (LR) | 70.7             | 70.7              | 70.7           | 70.7             |
| Random Forest (RF)       | 69.7             | 69.9              | 69.7           | 69.6             |
| XGBoost (XGB)            | 71.8             | 71.8              | 71.8           | 71.7             |
| Decision Tree            | 63.9             | 63.9              | 63.9           | 63.9             |
| LSTM                     | 71.9             | 72.2              | 71.9           | 71.9             |

- **Mô hình tốt nhất**: LSTM đạt độ chính xác cao nhất (~72%) sau khi tuning hyperparameters, mô hình xử lý chưa tốt và còn cần cải thiện nhiều.


<p align="center">
  <a href="https://github.com/MinhkhoaDS22">
    <img src="https://github-readme-stats.vercel.app/api?username=MinhkhoaDS22&show_icons=true&theme=radical&cache_seconds=3600&hide_border=false" height="160px"/>
  </a>
  <a href="https://github-readme-stats.vercel.app/api/top-langs/?username=MinhkhoaDS22&layout=donut&theme=radical&hide_border=false&cache_seconds=3600">
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=MinhkhoaDS22&layout=donut&theme=radical&hide_border=flase&cache_seconds=3600" height="160px"/>
  </a>
</p>

