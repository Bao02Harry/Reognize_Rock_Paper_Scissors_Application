# Recognize_Rock_Paper_Scissors_Application
## Ý tưởng nhận diện hình ảnh 
<blockquote>Trong mạng nơ-ron, mạng nơ-ron tích chập (<b>Convolutional Neural Network</b>)là một trong những phương pháp chính để thực hiện nhận dạng hình ảnh, phân loại hình ảnh. CNN được sử dụng rộng rãi trong một số lĩnh vực như phát hiện đối tượng, nhận dạng khuôn mặt, ...
<br>Ý tưởng đằng sau mạng nơ ron tích chập là chúng ta sẽ áp dụng các bộ lọc lên ảnh trước khi huấn luyện mạng nơron sau khi cho các tấm ảnh đi qua bộ lọc những đặc trưng của tấm ảnh sẽ trở nên nổi bật và chúng ta sẽ có thể dùng chúng để nhận diện hình ảnh.</blockquote>

<hr>
<ol>
<li>Convolutional Neural Network</li>
    <ul>
    <li>CNN phân loại hình ảnh bằng cách lấy 1 hình ảnh đầu vào, xử lý và phân loại nó theo các hạng mục nhất định.</li>
        <li>Các layer liên kết được với nhau thông qua cơ chế convolution.</li>
<li>Layer tiếp theo là kết quả convolution từ layer trước đó, nhờ vậy mà ta có được các kết nối cục bộ. Như vậy mỗi neuron ở lớp kế tiếp sinh ra từ kết quả của filter áp đặt lên một vùng ảnh cục bộ của neuron trước đó.</li>
<li>Mỗi một lớp được sử dụng các filter khác nhau thông thường có hàng trăm hàng nghìn filter như vậy và kết hợp kết quả của chúng lại.</li> 
<li>Đó là lý do tại sao CNNs cho ra mô hình với độ chính xác rất cao. Cũng giống như cách con người nhận biết các vật thể trong tự nhiên.</li>
    </ul>
    <blockquote>CNN bao gồm tập hợp các lớp cơ bản bao gồm: convolutional layer + nonlinear layer, pooling layer, fully connected layer. Các lớp này liên kết với nhau theo một thứ tự nhất định. </blockquote>
    <img src="https://drive.google.com/uc?id=1_7HoawTQ6CjAYLdbF4ikadkoE33CHZqe" style="witdth:450px;height:400px">
<li>Convolutional Layer</li>
    <ul>
        <li>Convolution layer là lớp quan trọng nhất và cũng là lớp đầu tiên của của mô hình CNN. Lớp này có chức năng chính là phát hiện các đặc trưng có tính không gian hiệu quả. Những đặc trưng này bao gồm đặc trưng cơ bản là góc,cạnh, màu sắc, hoặc đặc trưng phức tạp hơn như texture của ảnh. Vì bộ filter quét qua toàn bộ bức ảnh, nên những đặc trưng này có thể nằm ở vị trí bất kì trong bức ảnh, cho dù ảnh bị xoáy trái/phải thì những đặc trưng này vẫn bị phát hiện.</li>
    </ul>
<li>Nonlinear Layer</li>
    <ul>
        <li>ReLU (Rectified Linear Units, f = max(0, x)) là hàm kích hoạt phổ biến nhất cho CNN tại thời điểm của bài viết. Trước khi hàm ReLU được áp dụng thì những hàm như sigmoid hay tanh mới là những hàm được sử dụng phổ biến. Hàm ReLU được ưa chuộng vì tính toán đơn giản, giúp hạn chế tình trạng vanishing gradient, và cũng cho kết quả tốt hơn. ReLU cũng như những hàm kích hoạt khác, được đặt ngay sau tầng convolution, ReLU sẽ gán những giá trị âm bằng 0 và giữ nguyên giá trị của đầu vào khi lớn hơn 0.</li>
    </ul>
    <li>Pooling Layer</li>
    <ul>
        <li>Lớp gộp (pooling) chịu trách nhiệm để là giảm chiều kết quả tích chập. Để trích xuất các đặc trưng cốt lõi, cái thường bất biến trước các phép xoay và phép trượt, do đó làm cho quá trình huấn luyện mô hình hiệu quả hơn. </li>
        <li>Có hai loại phép gộp:Gộp cực đại (Max Pooling) và Gộp trung bình (Average Pooling)  </li>
        <img src="https://drive.google.com/uc?id=1hsh5if1FQeb00e7OmpUvNPxOj71rPOWs">
    </ul>
    <li>Fully Connected Layer</li>
    <ul>
    <li>Sau khi ảnh được truyền qua nhiều convolutional layer và pooling layer thì model đã học được tương đối các đặc điểm của ảnh thì tensor của output của layer cuối cùng sẽ được là phẳng thành vector và đưa vào một lớp được kết nối như một mạng nơ-ron. Với FC layer được kết hợp với các tính năng lại với nhau để tạo ra một mô hình. Cuối cùng sử dụng softmax để phân loại đầu ra.</li>
        <img src="https://drive.google.com/uc?id=1Wonq5mcTQqZ_y8FtrAkLqr8pm62hLvoT" >
    </ul>
</ol>
