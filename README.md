Đây là file hướng dẫn chạy mô hình CRNN+CTC loss:

Bộ dữ liệu BKAI:
- Như mô tả trong báo cáo, dữ liệu sử dụng nằm trong thư mục ./training_data/new_train chứa 103000 ảnh và nhãn tương ứng lưu trong file train_gt.txt.
- Ta thực hiện tải bộ dataset lên Kaggle, hoặc có thể sử dụng bộ dữ liệu này: https://www.kaggle.com/datasets/vanthonguyen123/viet-ocr

Hướng dẫn thực thi:
Các file trong mã nguồn đều viết dưới dạng Jupyter Notebooks, để thực thi chỉ cần import notebook và chạy trên môi trường Kaggle với GPU là P100.
Lưu ý cần kiểm tra bộ dữ liệu đã được thêm vào notebook hay chưa, nếu chưa thì có thể tự tải lên hoặc truy cập: https://www.kaggle.com/datasets/vanthonguyen123/viet-ocr.

- Với mô hình CRNN sử dụng VGG-16+BiLSTM+drop-out 0.3: Chạy file CRNN-dropout3.ipynb 

- Với mô hình CRNN sử dụng VGG-16+BiLSTM, không sử dụng drop-out: Chạy file CRNN-nodropout.ipynb 

- Đánh giá hiệu năng trên tập validation set và kiểm tra trên tập test set trên mô hình VGG-16+BiLSTM+drop-out: Chạy file testcer-wer-dropout.ipynb, sử dụng file model.20-1.90.h5 (bộ trọng số tốt nhất của mô hình mà chúng em huấn luyện được)

- Đánh giá hiệu năng trên tập validation set và kiểm tra trên tập test set trên mô hình VGG-16+BiLSTM, không sử dụng drop-out: Chạy file testcer-wer-nodropout.ipynb và sử dụng file model.17-1.95.h5 (bộ trọng số tốt nhất của mô hình mà chúng em huấn luyện được)


Để có thể thực thi trên Kaggle, cần:
- Có tài khoản Kaggle đã được xác minh.
- Nếu cần sử dụng GPU (như trong mô hình này sử dụng GPU P100), thì ta lựa chọn GPU là GPU P100 trước khi bật kernel. 
Lưu ý GPU P100 chỉ có 30 tiếng sử dụng miễn phí trong 7 ngày, reset vào 7g00 sáng ngày thứ 7 hằng tuần.

