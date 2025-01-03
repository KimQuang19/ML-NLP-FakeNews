# Sử dụng mô hình SVM trong việc phát hiện tin giả trên mạng xã hội
> Dự án: Phát hiện tin giả trên mạng xã hội bằng mô hình SVM

> Mô hình SVM (Support Vector Machine) được áp dụng để phân loại các bài đăng trên mạng xã hội thành các loại: tin thật và tin giả, giúp cải thiện chất lượng thông tin và giảm thiểu nguy cơ từ việc lan truyền thông tin sai lệch.
## Nội dung
+ Giới thiệu
+ Các tính năng chính
+ Công nghệ sử dụng
+ Kết quả
+ Tham gia dự án
+ Giấy phép
## Giới thiệu
Dự án này sử dụng mô hình học máy SVM (Support Vector Machine) để phát hiện tin giả trên các nền tảng mạng xã hội. Bằng cách phân tích các bài viết và dữ liệu từ các mạng xã hội như Facebook, Twitter, và Instagram, mô hình sẽ phân loại nội dung thành các bài viết “thật” hoặc “giả”. Mục tiêu là giúp người dùng và các tổ chức phát hiện nhanh chóng thông tin sai lệch, bảo vệ cộng đồng khỏi những nguy cơ của tin giả.
## Các tính năng chính
+ Thu thập dữ liệu: Sử dụng bộ dữ liệu chuẩn trên Kaggle với kích thước 94.14 MB, 20800 tin. Dữ liệu được chia thành các cột id, tiêu đề, tác giả, văn bản và nhãn
+ Tiền xử lý dữ liệu: Tiến hành tiền xử lý văn bản bao gồm việc loại bỏ từ ngừng, chuẩn hóa văn bản, phân tách từ (tokenization) và chuyển đổi văn bản thành vector đặc trưng.
+ Phân loại bằng SVM: Sử dụng mô hình SVM để phân loại bài viết thành "tin thật" và "tin giả". Mô hình được huấn luyện trên tập dữ liệu đã gán nhãn.
+ Đánh giá mô hình: Đánh giá hiệu quả mô hình thông qua các chỉ số như Accuracy, Precision, Recall, F1-Score.
Công nghệ sử dụng
+ Ngôn ngữ lập trình: Python
+ Thư viện học máy: scikit-learn (SVM), pandas, numpy
+ Tiền xử lý văn bản: nltk
+ Công cụ phân tích dữ liệu: matplotlib
## Kết quả 
### Tiền xử lý dữ liệu
Với dữ liệu file CSV ban đầu kích thước 94.14MB và 20800 tin , sau khi loại bỏ các thuộc tính và dữ liệu kém giá trị thì ta còn bộ dữ liệu đầu vào với kích thước 29.7 MB và 5200 tin
![](image_dir/DuLieuThuNghiem.jpg)
