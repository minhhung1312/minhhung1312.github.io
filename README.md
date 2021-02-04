# minhhung1312.github.io
Mocktest3

<!DOCTYPE html>
<html>
	<head>
		<title>Mocktest3</title>
		<meta charset="utf-8" />
		<meta name="desciption" content="Tìm Hiểu về K-means" />
		<link rel="stylesheet" href="normalize.css" /><!--resetcss-->
		<link rel="stylesheet" href="index.css" /><!--Css cho web-->
	</head>
	<body>
		<div id="logo">
			<div id="huge">
				<div id="big">
					<p>Đại học Quốc Gia Thành phố Hồ Chí Minh</p>
				</div>
				<div id="small">
					<p>Trường Đại Học Bách Khoa</p>
				</div>
			</div>
			<img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/cd/Logo-hcmut.svg/1200px-Logo-hcmut.svg.png" />
		</div>
		<div class="header">
			<h1>BÁO CÁO BÀI TẬP LỚN</h1>
			<h2>NHẬP MÔN ĐIỆN TOÁN</h2>
		</div>
		<div id="member">
			<div id="ds">
				<p>I. Danh sách thành viên</p>
			</div>
			<ul>
				<li>Mai Đình Quốc Anh - MSSV: 2012595</li>
				<li>Ngô Văn Khải Hoàn - MSSV: 2013212</li>
				<li>Lê Tấn Đạt - MSSV: 2012920</li>
				<li>Đinh Tiến Khởi - MSSV: 2013537</li>
			</ul>
		</div>
		<div id="work">
			<div id="work1">
				<p>II.Yêu cầu bài tập</p>
			</div>
			<div id="work2">
				<p>Đề 36: Ngày nay, các mô hình toán học được ứng dụng rất nhiều trong lĩnh vực khoa học máy tính. Hãy tìm hiểu mô hình K-means và xây dựng một minh họa cụ thể.
				</p>
			</div>
		</div>
		<div id="text">
			<p>1. Đặt vấn đề</p>
			<div id="doan1">
				<p>1.1 Tình Huống</p>
				<p>Trong các mô hình kinh doanh, doanh nghiệp sẽ chia nhỏ tệp khách hàng ra thành những nhóm đối tượng khác nhau để có thể áp dụng những chiến lược kinh doanh cụ thể cho từng nhóm đối tượng. Điều này giúp cho khách hàng được tiếp cận với các sản phẩm thật sự phù hợp với bản thân họ. Sự phù hợp đó sẽ kéo doanh số của chúng ta tăng lên. Vấn đề đặt ra là làm sao có thể chia nhỏ tệp khách hàng đó ra khi mà số lượng hóa đơn là rất lớn và chúng ta không thể ngồi để phân tích từng vị khách.
				</p>
			</div>
			<div id="doan2">
				<p>1.2 Giới thiệu chung</p>
				<p>Khi chúng ta làm việc với một lượng lớn dữ liệu, sẽ dễ dàng hơn khi phân vùng những dữ liệu đó thành các nhóm rồi sau đó mới tiến hành phân tích dữ liệu. Phân cụm (Clustering) là một trong những cách để chia nhóm các dữ liệu với sự hỗ trợ của nhiều thuật toán.
				Phân cụm (Clustering) là một thuật toán học không giám sát (unsupervised machine learning algorithm) thường được sử dụng nhất cho được phân lớp (partitioning) các quan sát của bộ dữ liệu thành k nhóm khác nhau được lựa chọn trước. Vì lý do này, phân cụm còn có tên đầy đủ là K-means clustering - tạm dịch là phân cụm k nhóm theo trung bình.
				</p>
			</div>
			<p>2. Thuật Toán</p>
			<div id="yt">
				<p>2.1 Ý tưởng</p>
				<p>Dựa trên mô hình lượng tử hóa <a href="https://vi.wikipedia.org/wiki/Vect%C6%A1" target="_blank">vecto</a>, các dữ liệu sẽ được biểu diễn thành điểm.
				</p>
			</div>
			<div id="vecto">
				<div id="vecto1">
					<img src="Media\1.PNG" />
					<p>Chọn K điểm làm Tâm cụm:</p>
					<img src="Media\2.PNG" />
					<p>Gán các điểm dữ liệu đến tâm dữ liệu gần nhất:</p>
					<img src="Media\3.PNG" />
				</div>
				<div id="yt1">
					<p>Di chuyển các tâm dữ liệu đến tọa độ trung bình của các điểm dữ liệu gán vào nó</p>
					<p>Tiếp tục lặp lại cho đến khi tâm dữ liệu không thay đổi (đáng kể) nữa.</p>
				</div>
			</div>
			<div id="problem">
				<p>2.2 Các vấn đề của thuật toán k-means</p>
				<p>2.2.1 Vấn đề chọn điểm K</p>
				<p>Chỉ việc lựa chọn số cụm k đã có thể tách thành 1 bài toán riêng. Không có 1 con số k nào là hợp lý cho tất cả các bài toán.Ta có thể đọc hiểu tập dữ liệu của mình để xác định xem trong đó có thể có bao nhiêu cụm? Nhưng không phải lúc nào cũng có thể làm thế. 
				Cách làm duy nhất là phải thử với từng giá trị k=1,2,3,4,5,… để xem kết quả phân cụm thay đổi như thế nào. Một số nghiên cứu cho thấy việc thay đổi k sẽ có hiệu quả nhưng tới một điểm nào đó, sẽ không hợp lý. Với k quá nhỏ thì làm giảm hiệu quả của sự phân cụm, còn với k quá lớn thì sẽ làm mất dần ý nghĩa của việc phân cụm. Vậy nên, để lựa chọn số k, không chỉ dừng lại ở phạm trù kỹ thuật, mà còn chạm tới phạm trù nghệ thuật.</p>
				<p>2.2.2 Vấn đề khởi tạo vị trí của k điểm</p>
				<p>Tương tự, việc khởi tạo vị trí của k điểm cũng quan trọng không kém. Hai vị trí khởi tạo khác nhau của k điểm có thể cho ra 2 kết quả hoàn toàn khác nhau.</p>
				<div class="img1">
					<img src="Media\7.PNG" />
				</div>
				<p>Nhìn vào sự biểu diễn điểm dữ liệu phía trên, con người có thể tính toán ra ngay được k=3, và 3 tâm cụm nằm trong ba vùng dữ liệu được định sẵn khá “rõ ràng”.</p>
				<div class="img1">
					<img src="Media\8.PNG" />
				</div>
				<p>Tuy nhiên, khi khởi tạo không chính xác, máy tính sẽ cho ra những kết quả không mong muốn. Hơn nữa, không phải lúc nào chúng ta cũng có thể nhìn ra chính xác được những điểm khởi tạo hợp lí.</p>
				<p>2.3 Giải quyết vấn đề bằng thuật toán:</p>
				<p>Dưới đây sẽ là một số cách cơ bản để xử lí các vấn đề trên. Lưu ý, không áp dụng được tất cả mọi trường hợp. Việc chạy ra kết quả tốt hay không phụ thuộc nhiều vào  khả năng và trình độ của người sử dụng.</p>
				<p>2.3.1 Chọn số điểm k</p>
				<div id="elbow">
					<p>Phương pháp Elbow</p>
				</div>
				<p>Ý tưởng của thuật toán này như sau. Bộ dữ liệu ban đầu sẽ được phân thành k nhóm. Với mỗi nhóm sẽ tính cái gọi là centroid (tâm ngẫu nhiên) tương ứng rồi tính tổng khoảng cách của tất cả các quan sát thuộc nhóm này đến centroid ở trên và tổng này gọi là WSS</p>
				<p>Vì mục tiêu của thuật toán phân cụm là phân chia toàn bộ các quan sát của bộ dữ liệu ban đầu thành k cụm khác nhau sao cho các quan sát thuộc cùng một cụm là tương đồng nhất với nhau có thể, hay TWSS nhỏ nhất có thể, và số điểm k không quá lớn, nên ta có thể dùng biểu diễn đồ thị của WSS phụ thuộc vào số điểm k. Dựa vào độ dốc của đồ thị và chọn điểm k thích hợp.</p>
				<div class="img1">
					<img src="Media\5.PNG" />
				</div>
				<p>Với minh họa bên trên, ta có thể thấy, khi k>3 thì  WSS của hệ giảm không đáng kể, nên ta sẽ chọn k=3 cho trường hợp này.</p>
				<p>Tuy nhiên, trong nhiều trường hợp, số k phù hợp nhất không thể được xác định rõ ràng bằng phương pháp Elbow, cho nên ta tới với một phương pháp khác, phương pháp Silhouette.</p>
				<p><b>Phương pháp Silhouette</b></p>
				<p>Phương pháp Silhouette tính toán sự tương đồng của các điểm trong cùng một cụm, biểu thị qua một giá trị gọi là Điểm Silhouette, biến thiên từ -1 tới 1, được tính toán theo công thức như sau.</p>
				<p>a(i) là giá trị trung bình khoảng cách của một điểm i tới các điểm còn lại trong cùng một cụm.</p>
				<img src="Media\16.PNG" />
				<div id="bi">
					<p>b(i) là khoảng cách trung bình nhỏ nhất tới các cụm khác.</p>
				</div>
				<img src="Media\17.PNG" />
				<p>Điểm Silhouette sẽ tính bằng S(i) theo công thức: </p>
				<img src="Media\18.PNG" />
				<p>Với k từ 1 tới 10 ta có đồ thị biểu diễn giá trị điểm Silhouette theo k như sau:</p>
				<img src="Media\6.PNG" />
				<p>2.3.2 Khởi tạo điểm k:</p>
				<p>Ta dùng phương pháp k-means++</p>
				<p>Ý tưởng của phương pháp này là chọn 1 điểm khởi tạo tâm cụm ban đầu ngẫu nhiên tại một điểm dữ liệu, sau đó k-1 điểm dữ liệu tiếp theo khởi tạo tại điểm có khoảng cách lớn nhất so với các tâm cụm còn lại.</p>
				<p>Tuy nhiên, phương pháp này rất nhạy cảm với các điểm outliers(nằm rất xa so với các điểm khác) cho nên cần tiền xử lý dữ liệu trước khi sử dụng phương pháp này.</p>
				<p>Ví dụ:</p>
				<p>Cohn 1 tâm cụm ngẫu nhiên.</p>
				<p>(Giả sử ta muốn khởi tạo k=3)</p>
				<div class="img1">
					<img src="Media\11.PNG" />
				</div>
				<p>Tính toán khoảng cách từ tâm tới cái điểm dữ liệu</p>
				<div class="img1">
					<img src="Media\12.PNG" />
				</div>
				<p>Chọn điểm cách xa nhất của tâm cụm tiếp theo</p>
				<div class="img1">
					<img src="Media\13.PNG" />
				</div>
				<p>Tiếp tục tính khoảng cách từ tâm cụm tới các điểm dữ liệu gán vào nó</p>
				<div class="img1">
					<img src="Media\14.PNG" /> 
				</div>
				<p>Chọn được điểm khởi tạo cuối cùng theo quy tắc trên và bắt đầu quá trình k-means clutstering</p>
				<div class="img1">
					<img src="Media\15.PNG" />
				</div>
				<p>3. Ví dụ minh họa</p>
				<p>Source: Vui lòng bấm vào <a href="https://rstudio-pubs-static.s3.amazonaws.com/323353_31f9a891bbf24fc0b42ff835344c2d1f.html" target="_blank">đây</a></p>
			</div><!--problem-->
		</div><!--#text-->
		<div id="footer">
			<p>Copyright &copy: 2021 Hoàn/Đạt/Q.Anh/Khởi</p>
		</div>
	</body>
</html>
