# retail-sales-statistics
Phân tích thống kê dữ liệu bán lẻ

# BÀI TẬP THỐNG KÊ: PHÂN TÍCH DỮ LIỆU BÁN LẺ

## 1. Giới thiệu đề tài

Đề tài sử dụng bộ dữ liệu `retail_sales_dataset.csv` để phân tích đặc điểm khách hàng và hoạt động giao dịch bán lẻ. Thông qua các phương pháp thống kê mô tả, ước lượng điểm và khoảng tin cậy, nhóm tiến hành phân tích các biến liên quan đến khách hàng, danh mục sản phẩm và giá trị giao dịch. Kết quả giúp minh họa việc vận dụng kiến thức xác suất và thống kê vào phân tích dữ liệu thực tế.

## 2. Bối cảnh và ý nghĩa của dữ liệu

### 2.1. Bối cảnh dữ liệu

Tập dữ liệu `retail_sales_dataset.csv` bao gồm 1.000 bản ghi giao dịch bán lẻ, được ghi nhận trong khoảng thời gian từ ngày 01/01/2023 đến ngày 01/01/2024. Mỗi bản ghi thể hiện thông tin về một giao dịch, bao gồm mã giao dịch, ngày giao dịch, mã khách hàng, giới tính, độ tuổi, danh mục sản phẩm, số lượng sản phẩm, đơn giá và tổng số tiền thanh toán.

Dữ liệu phản ánh đặc điểm nhân khẩu học của khách hàng trong độ tuổi từ 18 đến 64, với hai nhóm giới tính Male và Female. Các giao dịch thuộc ba danh mục sản phẩm chính: Beauty, Clothing và Electronics. Ngoài ra, dữ liệu cung cấp thông tin về số lượng sản phẩm, đơn giá và tổng giá trị của từng giao dịch.

### 2.2. Ý nghĩa của dữ liệu

* **Phân tích hành vi người tiêu dùng:** Hỗ trợ tìm hiểu đặc điểm mua sắm và mức chi tiêu theo độ tuổi, giới tính và danh mục sản phẩm.
* **Đánh giá hoạt động kinh doanh:** Giúp thống kê số lượng giao dịch, mức chi tiêu và doanh thu ghi nhận theo từng danh mục sản phẩm.
* **Phân tích biến động theo thời gian:** Hỗ trợ quan sát sự thay đổi của hoạt động giao dịch trong giai đoạn nghiên cứu.
* **Ứng dụng các phương pháp thống kê:** Cung cấp dữ liệu để thực hành ước lượng kỳ vọng, phương sai, tỷ lệ tổng thể và hiệu kỳ vọng giữa hai nhóm.

Các kết quả phân tích được sử dụng để minh họa phương pháp thống kê trên bộ dữ liệu đã chọn, không mặc nhiên đại diện cho toàn bộ thị trường bán lẻ.

## 3. Mô tả và phân loại các biến

Bộ dữ liệu gồm 1.000 quan sát và 9 biến, được phân loại như sau:

### 3.1. Biến định tính 

| Tên biến         | Ý nghĩa           | Đặc điểm                                         |
| ---------------- | ----------------- | -------------------------------------------------|
| Transaction ID   | Mã giao dịch      | Biến định danh, dùng để phân biệt các giao dịch  |
| Customer ID      | Mã khách hàng     | Biến định danh, dùng để nhận diện khách hàng     |
| Gender           | Giới tính         | Biến phân loại, gồm Male và Female               |
| Product Category | Danh mục sản phẩm | Biến phân loại, gồm Beauty, Clothing và Electronics |

### 3.2. Biến định lượng 

| Tên biến       | Ý nghĩa                | Đặc điểm                                |
| -------------- | ---------------------- | --------------------------------------- |
| Age            | Độ tuổi khách hàng     | Định lượng rời rạc, từ 18 đến 64 tuổi   |
| Quantity       | Số lượng sản phẩm      | Định lượng rời rạc, từ 1 đến 4 sản phẩm |
| Price per Unit | Đơn giá sản phẩm       | Định lượng, thang đo tỷ lệ              |
| Total Amount   | Tổng số tiền giao dịch | Định lượng, thang đo tỷ lệ              |

### 3.3. Biến thời gian

| Biến | Ý nghĩa                  | Đặc điểm                                   |
| ---- | ------------------------ | ------------------------------------------ |
| Date | Ngày phát sinh giao dịch | Biến thời gian, dùng để phân tích hoạt động giao dịch theo ngày |

**Lưu ý:** Transaction ID và Customer ID là các mã định danh, không được sử dụng như đại lượng số để tính trung bình hoặc phương sai. Biến Date được xử lý dưới dạng ngày tháng khi cần phân tích theo thời gian.

## 4. Mục tiêu và phương pháp thống kê

Bài tập tập trung vào các nội dung sau:

### 4.1. Ước lượng kỳ vọng tổng thể

Sử dụng trung bình mẫu để ước lượng kỳ vọng tổng thể của một biến định lượng phù hợp, chẳng hạn Total Amount.

### 4.2. Ước lượng phương sai tổng thể

Sử dụng phương sai mẫu và phân phối Chi-bình phương để xây dựng khoảng tin cậy cho phương sai tổng thể, với điều kiện tổng thể có phân phối chuẩn.

### 4.3. Ước lượng tỷ lệ tổng thể

Ước lượng tỷ lệ giao dịch thuộc một danh mục sản phẩm cụ thể, chẳng hạn Electronics, trên tổng số giao dịch hợp lệ.

### 4.4. Ước lượng hiệu kỳ vọng giữa hai nhóm

So sánh số tiền thanh toán trung bình giữa hai nhóm khách hàng Male và Female, sử dụng khoảng tin cậy cho hiệu hai kỳ vọng của hai tổng thể độc lập.

### 4.5. Diễn giải kết quả

Giải thích các kết quả ước lượng theo bối cảnh dữ liệu, trình bày khoảng tin cậy và nêu ý nghĩa thống kê của các kết quả thu được.

## 5. Công cụ sử dụng

* **Python:** Ngôn ngữ lập trình để xử lý và phân tích dữ liệu.
* **GitHub:** Lưu trữ, quản lý và chia sẻ mã nguồn, dữ liệu và báo cáo.
* .....


## 6. Cấu trúc dự án

```text
retail-sales-statistics/
├── README.md
├── data/
│   └── retail_sales_dataset.csv
├── notebooks/
│   └── phan_tich_thong_ke.ipynb
└── reports/
    └── bao_cao.pdf
```

* `README.md`: Giới thiệu đề tài, dữ liệu, phương pháp và phân công công việc.
* `data/`: Chứa bộ dữ liệu gốc.
* `notebooks/`: Chứa mã Python, công thức, kết quả tính toán và nhận xét.
* `reports/`: Chứa báo cáo tổng hợp dưới dạng PDF.

## 7. Kết quả dự kiến

Thông qua bài tập, nhóm thực hành quy trình phân tích dữ liệu từ khâu chuẩn bị dữ liệu đến tính toán, diễn giải và trình bày kết quả. Sản phẩm cuối cùng bao gồm bộ dữ liệu, notebook Python và báo cáo PDF trình bày các phương pháp ước lượng điểm, khoảng tin cậy và nhận xét theo bối cảnh nghiên cứu.
