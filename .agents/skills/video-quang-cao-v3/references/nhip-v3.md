# Nhịp V3 đã được người dùng chấp nhận

Đọc cùng `haruco-v3-approved.txt`. Mười prompt đó được người dùng xác nhận tạo ra video họ rất ưng. Giữ cách tổ chức chuyển động của chúng; thay nội dung theo sản phẩm mới. Không cần tìm lại video gốc hoặc truy cập đường dẫn tạm của cuộc trò chuyện cũ.

## Công thức hình

Mỗi cảnh có một ý chính, diễn ra qua 2–3 nhịp. Nhân vật thực sự cử động khớp tay, vai, hông, chân hoặc thao tác vật thể. Zoom phục vụ việc quan sát hành động/chi tiết. Cảnh kết vẫn có cử động nhẹ.

Mắt linh hoạt theo kịch bản: có thể mở, chớp, nheo hoặc nhắm để thể hiện hành động và cảm xúc. Khi mở, mắt trắng không đồng tử; khi nhắm, thể hiện bằng nét mí đen. Giữ nhận diện nhân vật, mũi và phong cách nét vẽ, đồng thời cho phép biểu cảm mắt thay đổi. Ví dụ: đang chú ý vào chi tiết thì mở mắt, thả lỏng thì có thể nhắm nhẹ rồi mở lại nếu phù hợp với câu chuyện.

Mười prompt gốc trong `haruco-v3-approved.txt` được giữ nguyên để đối chiếu nhịp dựng. Cụm 'mắt trắng mở' và 'không đổi mặt' trong mẫu cũ không khóa trạng thái mắt ở prompt mới: hiểu là giữ nhận diện, còn mắt diễn theo từng cảnh. Có thể viết phần nhận diện ngắn là 'mắt trắng khi mở, biểu cảm theo hành động'.

Chọn thủ pháp theo lời kể:

| Lời đang nói | Tiến triển hình phù hợp |
|---|---|
| Một tình huống đời thường | Cận thao tác → zoom ra thấy người → theo tay đến điểm cần chú ý |
| Giới thiệu sản phẩm | Cận sản phẩm → thấy người giới thiệu → người nhỏ sang bên, sản phẩm lớn ở phía còn lại |
| Một bộ phận hoặc công dụng có thể quan sát | Tay chỉ/chạm → zoom theo tay → ô tròn trắng phóng đại đúng bộ phận, người tiếp tục thao tác |
| Hai chi tiết liên quan | Thấy vật đầy đủ → cận chi tiết thứ nhất → khung nhìn theo tay sang chi tiết thứ hai |
| Chuyển sang hoàn cảnh sử dụng | Sản phẩm thu nhỏ thành lớp phụ → lớp tình huống trượt vào → nhân vật thực hiện thao tác |
| Chọn cỡ/điều chỉnh | Dụng cụ thích hợp → thao tác thật → phóng đại vị trí đang điều chỉnh |
| Di chuyển | Đứng dậy/nhấc vật → zoom ra đủ cơ thể → khung nhìn theo bước đi |
| Các mục người xem có thể tìm hiểu | Vật dẫn chuyện → tương tác → 2–3 biểu tượng trắng xuất hiện đúng thứ tự được nhắc |
| Kết | Cận sản phẩm → thấy người → sản phẩm thành điểm nhìn chính, chuyển động dịu lại |

Đây là các lựa chọn, không phải danh sách phải dùng đủ. Với khoảng 8–10 cảnh, chọn ít nhất bốn kiểu bố cục phù hợp và một cảnh phóng đại chi tiết có ý nghĩa; với 3–5 cảnh chọn hai hoặc ba kiểu. Tránh nhiều cảnh liên tiếp chỉ cầm sản phẩm và đổi góc quay. Không ép ô phóng đại vào cảnh không có chi tiết cần giải thích.

Biến đổi hợp lệ là đổi kích thước/vị trí của lớp hình, đưa đồ họa vào, hoặc thay khung nhìn. Khi zoom vào quai bình, quai vẫn cùng hình dạng; khi minh họa hỗ trợ lưng, không làm cột sống tự biến thành một hình dạng 'đã chữa khỏi'. Giữ người và sản phẩm tự nhiên.

## Thời lượng tự chọn

T là độ dài bản dựng; L là độ dài mỗi clip AI nguồn. Mốc trong prompt là thời gian tính từ đầu clip nguồn, không phải timeline toàn phim. L mặc định 6 giây từ bộ đã được chấp nhận, không phải giới hạn cố định của Gemini hay mọi công cụ.

N = làm tròn T/L lên. Lập N khoảng dựng không chồng lấn, tổng đúng T. Chia đều T/N là điểm bắt đầu, sau đó chuyển phần giây giữa các cảnh theo lượng lời; mỗi cảnh vẫn không vượt L. Khi làm tròn đến mili giây, cho cảnh cuối nhận phần chênh lệch. Nếu dùng crossfade chồng hình, phải bù phần thời gian chồng; mặc định nối cắt thẳng theo động tác để dễ giữ tổng.

| T bản dựng | L nguồn | N prompt | Phân bổ ban đầu |
|---:|---:|---:|---|
| 15s | 6s | 3 | 5s mỗi cảnh |
| 30s | 6s | 5 | 6s mỗi cảnh |
| 45s | 6s | 8 | 5,625s mỗi cảnh |
| 55s | 6s | 10 | 5,5s mỗi cảnh |
| 60s | 6s | 10 | 6s mỗi cảnh |
| 90s | 6s | 15 | 6s mỗi cảnh |
| 120s | 6s | 20 | 6s mỗi cảnh |
| 45s | 8s | 6 | 7,5s mỗi cảnh |

Với T <= L, dùng một prompt, thu gọn câu chuyện thành tình huống → sản phẩm → kết ngay trong clip; hoàn thành ý trong T. Nếu T rất ngắn, giảm số nhịp và số chữ. Khi người dùng đưa cả N lẫn T mâu thuẫn với L, giải thích phép tính và hỏi họ ưu tiên thông số nào; không giả vờ đáp ứng cả ba.

Ví dụ với cảnh dự kiến lấy 5,625s: nhịp 0–1,2s → 1,2–3s → 3–5,1s; phần còn lại tiếp tục cử động nhẹ. Không để chi tiết chính chỉ xuất hiện ở 5,8s rồi hướng dẫn cắt tại 5,625s. Mốc AI có thể lệch, cần kiểm tra clip thực tế.

## Lời kể

Viết cả câu chuyện liền mạch trước, rồi chia theo cảnh. Lời đọc phải nghe như một người đang kể chuyện trực tiếp với người xem: câu ngắn xen câu dài vừa phải, có chỗ ngập ngừng hoặc nhấn nhẹ khi ý nghĩa cần. Tránh lặp 'sản phẩm giúp...', đọc danh sách tính năng hoặc hô bán hàng ở mọi câu. Không bịa trải nghiệm 'tôi dùng rồi' hay kết quả của khách hàng.

### Làm câu chuyện đáng xem

1. **Chọn một chuyện cụ thể.** Xác định người xem đang gặp tình huống nào và chi tiết nào của sản phẩm liên quan trực tiếp. Không dồn mọi công dụng vào một phim ngắn. Nếu chưa có chân dung khách hàng, suy ra tình huống hợp lý từ sản phẩm và nêu ngắn gọn giả định ngoài file prompt.
2. **Mở bằng việc đang xảy ra.** Trong khoảng 1–3 giây đầu của phim thông thường, cho người xem thấy một hành động chưa xong, một câu hỏi gần gũi hoặc một chi tiết đáng chú ý có căn cứ. Với phim cực ngắn, nêu ý ngay nhịp đầu. Tự viết thử ba góc mở khác nhau rồi chọn một; không xuất cả ba làm người dùng phải duyệt. Lời mở và hình mở cùng đặt ra một điều người xem muốn biết, thay vì chào hỏi hoặc giới thiệu tên sản phẩm dài dòng.
3. **Đưa ra lời giải đúng lúc.** Câu hỏi ở đầu phải được trả lời bằng hình hoặc thông tin cụ thể trong phim. Cho sản phẩm xuất hiện tại lúc nó có vai trò trong câu chuyện; phần còn lại chứng minh qua thao tác và chi tiết. Tránh câu câu giờ như 'xem đến cuối sẽ biết' khi có thể cho thấy ngay điều hữu ích.
4. **Mỗi cảnh tiến thêm một bước.** Chọn nhịp vì nó có thông tin mới: bất tiện được nhận ra → tay thử thao tác → chi tiết được phóng đại → cách dùng trở nên rõ. Đổi cỡ hình, chuyển lớp và biểu cảm mắt theo điểm chuyển ý. Zoom nhiều tự nó không làm lời kể hấp dẫn. Có thể gài một câu hỏi nhỏ rồi trả lời ở cảnh kế; không tạo chuỗi bí ẩn kéo dài vô cớ.
5. **Kết nối lại câu chuyện.** Cảnh cuối có thể trở lại hành động mở đầu để cho thấy câu chuyện đã đi đến đâu, rồi đưa một lời kêu gọi phù hợp như xem chi tiết hoặc chọn cỡ. Chỉ nêu ưu đãi, giá, lời hứa tư vấn hay khan hiếm khi người dùng đã cung cấp thông tin đó.

Ví dụ về lối kể cho bình có quai xách, không thêm tính năng mới:

- Mở: 'Cửa đã mở… còn bình nước vẫn trên bàn.' Hình: nhân vật bước đi, quay đầu nhìn lại; khung nhìn theo ánh mắt tới bình.
- Diễn biến: 'Quay lại một nhịp. Nắm quai, nhấc bình, rồi đi tiếp.' Hình: tay thực hiện thao tác, phóng đại đúng quai rồi mở rộng khung theo bước chân.
- Đưa đúng tên và chi tiết sản phẩm vào mạch kể khi người xem đang nhìn thấy chúng; kết theo mục tiêu của quảng cáo. Đây là cách nối tình huống với thao tác, không phải kịch bản cố định dùng lại cho mọi sản phẩm.

Trước khi xuất, tự rà năm câu hỏi: mở đầu có gắn với sản phẩm và người xem không; mỗi cảnh có điều mới không; điều gây tò mò đã được giải đáp chưa; đọc liền mạch có tự nhiên không; lời kết có hợp với chuyện vừa kể không. Nếu bỏ một câu mà câu chuyện không mất ý hoặc cảm xúc, cân nhắc cắt câu đó. Nếu đổi tên sản phẩm bất kỳ mà cả bài vẫn giữ nguyên được, viết lại bằng chi tiết riêng của sản phẩm.

Tạo sự hấp dẫn bằng quan sát, tình huống, nhịp kể và hình ảnh. Không dùng số liệu bịa, kết quả sức khỏe phóng đại, lời chứng thực giả hoặc nỗi sợ làm mồi câu. Không cam kết kịch bản chắc chắn viral hay đạt tỷ lệ giữ chân cụ thể khi chưa có dữ liệu thử thực tế.

Ước lượng ban đầu khoảng 3,3–4,2 tiếng Việt tách bằng khoảng trắng mỗi giây, có khoảng nghỉ; đó là ngân sách nháp, không phải cam kết thời gian TTS. Cảnh 6 giây thường bắt đầu khoảng 18–23 tiếng rồi thử đọc. Chỉnh theo giọng thực tế, đừng nhồi số chữ để đủ thời lượng. Giữ trật tự câu trong bản đọc liền mạch trùng thứ tự cảnh.

Phần minh họa phải theo đúng đối tượng trong câu: nhắc quai xách → thấy tay dùng quai; nhắc khe khung → phóng khe; nhắc mức dung tích → minh họa bình và để số đo cho chữ hậu kỳ. Không tự thêm vạch chia hay biến chai nhỏ thành chai lớn để diễn tả dung tích.

Nếu người dùng chỉ đưa công dụng, yêu cầu/đọc thông tin đúng mẫu khi cần cho tuyên bố nhạy cảm. Khi chưa có bằng chứng định lượng, ưu tiên đặc điểm nhìn được và cách lựa chọn phù hợp. Ví dụ bình có quai không suy ra chống rò hay giữ lạnh; đai đỏ đen không suy ra có điện, rung hay sưởi.

## Ảnh và ghép cảnh

`../assets/nhan-vat-v3.png` là ảnh nhân vật đã dùng. Sản phẩm mỗi lần phải lấy từ ảnh mới. Nếu công cụ chỉ nhận một ảnh, chuẩn bị ảnh tham chiếu có nhân vật và sản phẩm mới bằng công cụ tạo/chỉnh ảnh khi được yêu cầu; không lấy ảnh đai HARUCO làm tham chiếu cho món hàng khác.

Một ảnh chung không bảo đảm các clip nối liền chuyển động. Mỗi prompt nêu trạng thái mở đầu riêng. Trong bảng dựng, chọn điểm nối theo hướng chuyển động, đồ vật hoặc kích cỡ khung. Nếu công cụ có chế độ ảnh tham chiếu và ảnh đầu, chọn theo cấu hình người dùng; không khẳng định mọi công cụ đều có tùy chọn này.

Giữ mọi mô tả background ngoài các prompt dán hàng loạt vì công cụ của người dùng đã cài sẵn. Nếu người dùng đổi yêu cầu này, theo yêu cầu mới.
