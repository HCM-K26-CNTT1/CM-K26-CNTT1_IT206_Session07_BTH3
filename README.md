# BÀI THỰC HÀNH 3: TÓM TẮT TÀI LIỆU QUY ĐỊNH NHÂN SỰ VƯỢT QUÁ CONTEXT WINDOW


## 1. Phân tích phương pháp thực hiện

Do tài liệu có dung lượng lớn, AI không thể xử lý toàn bộ nội dung trong một lần. Vì vậy, sử dụng phương pháp Chunking kết hợp MapReduce.

**Bước 1: Chunking – Chia nhỏ tài liệu**

Chia tài liệu thành 5 chương riêng biệt theo nội dung:

| Phần | Nội dung |
|---|---|
| Chunk 1 | Nội quy lao động |
| Chunk 2 | Quy định nghỉ phép |
| Chunk 3 | Chính sách làm thêm giờ |
| Chunk 4 | Quy định đánh giá nhân viên |
| Chunk 5 | Chính sách khen thưởng và kỷ luật |

**Bước 2: Map – Xử lý từng phần**

Đưa từng chương vào AI để phân tích và tóm tắt theo cùng một cấu trúc. Lưu lại kết quả sau mỗi lần xử lý.

**Bước 3: Reduce – Tổng hợp kết quả**

Kết hợp 5 bản tóm tắt thành một tài liệu hoàn chỉnh, tìm ra những quy định có liên quan giữa các chương.

**Bước 4: Kiểm tra**

Đối chiếu kết quả tổng hợp với tài liệu gốc để phát hiện thông tin bị thiếu, sai lệch hoặc chưa được đề cập.

## 3. Prompt xử lý từng phần tài liệu

Sử dụng prompt sau cho từng chương của tài liệu:

### PROMPT 1: TÓM TẮT TỪNG CHUNK

Bạn là chuyên viên phân tích tài liệu nhân sự. Hãy phân tích chương tài liệu tôi cung cấp và thực hiện các yêu cầu sau:

1. Tóm tắt nội dung chính, không bỏ qua quy định quan trọng.
2. Giữ nguyên tất cả con số, tỷ lệ, thời hạn và điều kiện áp dụng.
3. Liệt kê đầy đủ các trường hợp ngoại lệ.
4. Không tự suy đoán hoặc bổ sung thông tin không xuất hiện trong tài liệu.
5. Nếu tài liệu không đề cập đến một thông tin, hãy ghi rõ "Tài liệu không đề cập".
6. Ghi lại số trang hoặc vị trí chứa thông tin để thuận tiện đối chiếu.

**Trình bày kết quả theo cấu trúc:**

- Tên chương:
- Nội dung chính:
- Các quy định cụ thể:
- Điều kiện áp dụng:
- Các trường hợp ngoại lệ:
- Số liệu và thời hạn quan trọng:
- Những nội dung chưa được đề cập:
- Vị trí thông tin trong tài liệu:

Sau khi hoàn thành, hãy tạo một bản ghi nhớ (Summary Notes) ngắn gọn nhưng đầy đủ để sử dụng trong bước tổng hợp.

## 4. Kết quả xử lý từng phần

Sau khi sử dụng Prompt 1, lưu kết quả riêng cho từng chương.

### Chunk 1: Nội quy lao động

- Kết quả tóm tắt: [DÁN KẾT QUẢ AI]
- Thông tin quan trọng: [DÁN SUMMARY NOTES]
- Vị trí trong tài liệu: [SỐ TRANG]

### Chunk 2: Quy định nghỉ phép

- Kết quả tóm tắt: [DÁN KẾT QUẢ AI]
- Thông tin quan trọng: [DÁN SUMMARY NOTES]
- Vị trí trong tài liệu: [SỐ TRANG]

### Chunk 3: Chính sách làm thêm giờ

- Kết quả tóm tắt: [DÁN KẾT QUẢ AI]
- Thông tin quan trọng: [DÁN SUMMARY NOTES]
- Vị trí trong tài liệu: [SỐ TRANG]

### Chunk 4: Quy định đánh giá nhân viên

- Kết quả tóm tắt: [DÁN KẾT QUẢ AI]
- Thông tin quan trọng: [DÁN SUMMARY NOTES]
- Vị trí trong tài liệu: [SỐ TRANG]

### Chunk 5: Chính sách khen thưởng và kỷ luật

- Kết quả tóm tắt: [DÁN KẾT QUẢ AI]
- Thông tin quan trọng: [DÁN SUMMARY NOTES]
- Vị trí trong tài liệu: [SỐ TRANG]

## 5. Prompt tổng hợp các phần tài liệu

### PROMPT 2: TỔNG HỢP THEO PHƯƠNG PHÁP REDUCE

Bạn là chuyên viên nhân sự của Công ty ABC Technology.

Tôi sẽ cung cấp cho bạn 5 bản tóm tắt đã được xử lý riêng từ 5 chương của tài liệu quy định nhân sự.

Hãy tổng hợp chúng thành một tài liệu hoàn chỉnh theo các yêu cầu:

1. Kết hợp thông tin từ cả 5 chương, tránh lặp lại nội dung.
2. Giữ nguyên chính xác các con số, thời hạn, tỷ lệ và điều kiện.
3. Không được bỏ qua các trường hợp ngoại lệ.
4. Phát hiện những nội dung có liên quan giữa các chương và giải thích mối liên hệ dựa trên tài liệu.
5. Phân biệt rõ thông tin có trong tài liệu và thông tin chưa được đề cập.
6. Không tự suy đoán hoặc bổ sung quy định ngoài tài liệu gốc.
7. Nếu có thông tin mâu thuẫn giữa các chương, hãy chỉ ra vị trí và không tự ý kết luận.

**Yêu cầu đầu ra:**

- Bảng tổng hợp gồm: Chủ đề, Quy định chính, Điều kiện áp dụng, Ngoại lệ.
- Bản tóm tắt hoàn chỉnh dài khoảng 1.000–1.500 từ.
- Các nội dung liên quan giữa các chương.
- Những thông tin chưa được đề cập.
- Danh sách các nội dung cần kiểm tra lại với tài liệu gốc.

Dưới đây là 5 bản tóm tắt:

[DÁN KẾT QUẢ CHUNK 1]

[DÁN KẾT QUẢ CHUNK 2]

[DÁN KẾT QUẢ CHUNK 3]

[DÁN KẾT QUẢ CHUNK 4]

[DÁN KẾT QUẢ CHUNK 5]

## 6. Bảng tổng hợp quy định nhân sự

| Chủ đề | Quy định chính | Điều kiện áp dụng | Ngoại lệ |
|---|---|---|---|
| Nội quy lao động | [Trích xuất từ tài liệu] | [Điều kiện] | [Ngoại lệ] |
| Nghỉ phép | [Trích xuất từ tài liệu] | [Điều kiện] | [Ngoại lệ] |
| Làm thêm giờ | [Trích xuất từ tài liệu] | [Điều kiện] | [Ngoại lệ] |
| Đánh giá nhân viên | [Trích xuất từ tài liệu] | [Điều kiện] | [Ngoại lệ] |
| Khen thưởng và kỷ luật | [Trích xuất từ tài liệu] | [Điều kiện] | [Ngoại lệ] |

## 7. Bản tóm tắt hoàn chỉnh (1.000–1.500 từ)

### 7.1. Nội quy lao động

[DÁN NỘI DUNG TÓM TẮT CHƯƠNG 1]

### 7.2. Quy định nghỉ phép

[DÁN NỘI DUNG TÓM TẮT CHƯƠNG 2]

### 7.3. Chính sách làm thêm giờ

[DÁN NỘI DUNG TÓM TẮT CHƯƠNG 3]

### 7.4. Quy định đánh giá nhân viên

[DÁN NỘI DUNG TÓM TẮT CHƯƠNG 4]

### 7.5. Chính sách khen thưởng và kỷ luật

[DÁN NỘI DUNG TÓM TẮT CHƯƠNG 5]

### 7.6. Mối liên hệ giữa các chương

[DÁN KẾT QUẢ AI PHÂN TÍCH MỐI LIÊN HỆ GIỮA CÁC CHƯƠNG]

## 8. Câu hỏi kiểm tra thông tin

Tạo ít nhất 5 câu hỏi dựa trên tài liệu gốc để kiểm tra độ chính xác của thông tin đã trích xuất.

| STT | Câu hỏi | Câu trả lời | Vị trí trong tài liệu |
|---|---|---|---|
| 1 | [Câu hỏi về nội quy lao động] | [Câu trả lời] | [Chương, trang] |
| 2 | [Câu hỏi về nghỉ phép] | [Câu trả lời] | [Chương, trang] |
| 3 | [Câu hỏi về làm thêm giờ] | [Câu trả lời] | [Chương, trang] |
| 4 | [Câu hỏi về đánh giá nhân viên] | [Câu trả lời] | [Chương, trang] |
| 5 | [Câu hỏi về khen thưởng và kỷ luật] | [Câu trả lời] | [Chương, trang] |

## 9. Kiểm tra và đánh giá kết quả

Sau khi AI tổng hợp, tiến hành đối chiếu với tài liệu gốc theo các tiêu chí:

| Tiêu chí | Nội dung kiểm tra | Kết quả |
|---|---|---|
| Độ chính xác | Các quy định có đúng với tài liệu gốc không? | [Đạt/Chưa đạt] |
| Số liệu | Có giữ nguyên con số, tỷ lệ và thời hạn không? | [Đạt/Chưa đạt] |
| Ngoại lệ | Có bỏ sót trường hợp ngoại lệ không? | [Đạt/Chưa đạt] |
| Tính đầy đủ | Đã xử lý đủ 5 chương chưa? | [Đạt/Chưa đạt] |
| Tính trung thực | Có xuất hiện thông tin AI tự suy đoán không? | [Đạt/Chưa đạt] |
| Vị trí trích dẫn | Có xác định được chương và trang của thông tin không? | [Đạt/Chưa đạt] |

