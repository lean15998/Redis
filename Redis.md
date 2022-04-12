# 1. Khái niệm
- Redis là tên viết tắt của Remote Dictionary Server (Máy chủ từ điển từ xa), là kho dữ liệu key-value, trong bộ nhớ, mã nguồn mở và có tốc độ truy cập nhanh để dùng làm cơ sở dữ liệu, cache, message broker và queue. Redis có thể được sử dụng như một database được lưu trữ trong ram để tăng tốc độ xử lí.

- Redis hiện cung cấp thời gian phản hồi ở tốc độ chưa đến một mili giây, vì Redis cho phép bạn lưu trữ trên RAM của mình nhanh hơn so với khi lưu trữ trên các ổ cứng, khoảng 150.000 lần so với truy cập ổ HDD và nhanh hơn 500 lần so với truy cập SSD.
- Một số đặc điểm chính:

<ul>
<ul>
<li> Dữ liệu được lưu trữ trên bộ nhớ trong (RAM), và chỉ sử dụng bộ nhớ ngoài cho việc sao lưu phục hồi dữ liệu
<li> Dữ liệu lưu trữ trong Redis có thể đặt thời gian hết hạn (expire).
<li> Truy cập dữ liệu rất nhanh
<li> Lưu trữ dữ liệu theo kiểu key/value. Rất thuận lợi cho việc đọc và ghi dữ liệu
<li>
</ul>
</ul>
# 2. Lợi ích của redis
- **In-Memory Data Store**: Toàn bộ dữ liệu Redis nằm trong bộ nhớ chính của máy chủ, khác với các cơ sở dữ liệu thường lưu phần lớn dữ liệu trên ổ đĩa hoặc ổ SSD. So với cơ sở dữ liệu trên ổ đĩa truyền thống trong đó phần lớn các tác vụ đều yêu cầu truy cập lặp lại tới ổ đĩa, còn Redis thì chỉ việc lấy ra kết quả đã tính toán. Do đó hiệu suất nhanh thấy rõ rệt với các tác vụ đọc hoặc ghi thông thường mất chưa đầy một mili giây và hỗ trợ hàng triệu tác vụ mỗi giây.
- **Cấu trúc dữ liệu linh hoạt**: Khác với những kho dữ liệu key-value đơn giản có cấu trúc dữ liệu giới hạn, Redis có nhiều cấu trúc dữ liệu khác nhau nên đáp ứng được nhu cầu ứng dụng của bạn. Kiểu dữ liệu Redis gồm có:

<ul>
<ul>
<li> String – văn bản hoặc dữ liệu nhị phân có kích thước lên tới 512MB
<li> List – một tập hợp các chuỗi được sắp xếp theo thứ tự như khi được thêm vào
<li> Set – một tập hợp chưa được sắp xếp các chuỗi, có khả năng giao cắt, liên kết và khác với các kiểu tập khác
<li> Sorted Set – Tập được sắp xếp theo giá trị
<li> Hash – một cấu trúc dữ liệu dùng để lưu trữ danh sách các trường và giá trị
<li> Bitmap – một kiểu dữ liệu cho phép thực hiện các tác vụ quy mô bit
<li> HyperLogLogs – một cấu trúc dữ liệu xác suất để ước tính các thành phần duy nhất trong một tập dữ liệu
</ul> 
</ul>

# 3. Ứng dụng của redis

- **CACHING**: Redis là một lựa chọn tuyệt vời để triển khai in-memory cache để giảm độ trễ truy cập dữ liệu, tăng thông lượng và giảm tải khỏi cơ sở dữ liệu quan hệ hoặc NoSQL trong ứng dụng của bạn. Redis có thể phục vụ các dữ liệu được yêu cầu thường xuyên ở thời gian phản hồi dưới một mili giây. Và cho phép bạn dễ dàng mở rộng quy mô cho các tải cao hơn mà không cần tăng phụ trợ tốn kém. Persistent session caching, web page caching và caching của các đối tượng được sử dụng thường xuyên như hình ảnh, tệp và siêu dữ liệu là các ví dụ phổ biến về caching với Redis.
- **SESSION STORE**: Redis như một kho lưu trữ dữ liệu trong bộ nhớ với tính sẵn sàng cao và bền bỉ là lựa chọn phổ biến của các nhà phát triển ứng dụng để lưu trữ và quản lý dữ liệu session cho các ứng dụng của mình. Redis cung cấp độ trễ dưới một phần nghìn giây và khả năng phục hồi cần thiết để quản lý dữ liệu session như hồ sơ người dùng, thông tin đăng nhập, trạng thái phiên và cá nhân hóa cụ thể của người dùng.


# 4. Caching

- Caching là một kỹ thuật tăng độ truy xuất dữ liệu và giảm tải cho hệ thống. Cache là nơi lưu tập hợp các dữ liệu, thường có tính chất nhất thời, cho phép sử dụng lại dữ liệu đã lấy hoặc tính toán trước đó, nên sẽ giúp tăng tốc cho việc truy xuất dữ liệu ở những lần sau.
- **Caching hoạt động**: Dữ liệu trong cache (bộ đệm) thường được lưu trữ trong RAM (Random-access memory). Mục đích chính của cache là tăng hiệu suất truy xuất dữ liệu. Cache thường lưu trữ một tập hợp con dữ liệu tạm thời.
- Lợi ích:

<ul>
<ul>
<li> Cải thiện hiệu suất của ứng dụng
<li>
<li>
<li>
</ul>
</ul>
