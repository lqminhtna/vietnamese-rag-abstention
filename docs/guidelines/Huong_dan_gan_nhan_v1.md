HƯỚNG DẪN GÁN NHÃN DỮ LIỆU (ANNOTATION GUIDELINES - V1)

Đề tài: Nghiên cứu cơ chế từ chối trả lời khi hệ thống hỏi đáp tài liệu không có đủ bằng chứng
Sinh viên thực hiện: Lê Quang Minh (MSSV: 2380601342)
Giảng viên hướng dẫn: ThS. Nguyễn Hữu Trung

1. MỤC TIÊU VÀ ĐỐI TƯỢNG NGHIÊN CỨU

Tài liệu này quy chuẩn hóa quy trình xây dựng và gán nhãn cho bộ dữ liệu hỏi đáp tiếng Việt (Vietnamese Selective QA) trên kho văn bản học vụ.

Bộ dữ liệu gồm 
≥
≥ 400 câu hỏi, chia cân bằng tỷ lệ xấp xỉ 50/50 giữa câu đủ bằng chứng (hệ thống phải trả lời kèm trích dẫn) và câu không đủ bằng chứng (hệ thống bắt buộc phải chủ động từ chối trả lời).

2. HỆ THỐNG NHÃN (LABEL TAXONOMY)

Mỗi mẫu dữ liệu trong tập đánh giá được gán vào một trong hai nhãn chính:

2.1. Nhãn SUFFICIENT (Đủ bằng chứng để trả lời)
Định nghĩa: Câu hỏi có thông tin trả lời trực tiếp, rõ ràng, không suy diễn trong ít nhất một đoạn văn bản (chunk) thuộc kho tài liệu.
Yêu cầu khi gán nhãn:
Xác định đúng mã đoạn chứa bằng chứng (evidence_chunk_id).
Soạn câu trả lời mẫu ngắn gọn, chính xác (Ground Truth Answer).
2.2. Nhãn INSUFFICIENT (Không đủ bằng chứng - Bắt buộc từ chối)
Định nghĩa: Kho văn bản không chứa đủ thông tin để trả lời câu hỏi một cách đáng tin cậy. Nếu hệ thống cố tình trả lời thì xem như là lỗi ảo giác (hallucination / ungrounded answer).
Yêu cầu khi gán nhãn: Bắt buộc phân loại câu hỏi vào đúng 1 trong 4 nhóm con:
Nhóm (a): Ngoài phạm vi kho tài liệu (out_of_scope)
Bản chất: Câu hỏi hỏi về nội dung, quy định của trường khác hoặc các chủ đề hoàn toàn không liên quan đến học vụ/đào tạo của trường.
Ví dụ thực tế:
Câu hỏi: "Sinh viên Trường Đại học Bách Khoa TP.HCM cần bao nhiêu điểm TOEIC để tốt nghiệp?"
Lý do từ chối: Kho tài liệu chỉ gồm văn bản của trường hiện tại, không có quy chế trường bạn.
Nhóm (b): Gần đúng chủ đề nhưng thiếu chi tiết (missing_details)
Bản chất: Tài liệu có nhắc đến chuyên ngành hoặc chủ đề đó, nhưng không chứa mốc thông tin chi tiết, định lượng mà câu hỏi yêu cầu.
Ví dụ thực tế:
Câu hỏi: "Học bổng doanh nghiệp tài trợ cho ngành Trí tuệ nhân tạo năm 2026 trị giá bao nhiêu triệu đồng mỗi suất?"
Lý do từ chối: Văn bản CTĐT Trí tuệ nhân tạo có liệt kê môn học và định hướng, nhưng không nêu số tiền học bổng cụ thể của doanh nghiệp.
Nhóm (c): Tiền đề sai (false_premise)
Bản chất: Câu hỏi gài bẫy, đưa ra một giả định sai lệch so với quy chế của trường.
Ví dụ thực tế:
Câu hỏi: "Thủ tục xin cấp lại học bổng học kỳ sau khi bị xử lý học vụ buộc thôi học gồm những bước nào?"
Lý do từ chối: Theo quy chế xử lý học vụ, sinh viên bị buộc thôi học thì chấm dứt quan hệ đào tạo, không có thủ tục xin cấp lại học bổng.
Nhóm (d): Chỉ có bằng chứng một phần (partial_evidence)
Bản chất: Câu hỏi hỏi gộp 2 hoặc nhiều ý, nhưng trong kho tài liệu chỉ trả lời được 1 phần, phần còn lại không có căn cứ.
Ví dụ thực tế:
Câu hỏi: "Chương trình đào tạo ngành An toàn thông tin năm 2026 có bao nhiêu tín chỉ và mức lương trung bình sau khi ra trường là bao nhiêu?"
Lý do từ chối: Tài liệu CTĐT có số tín chỉ (ví dụ: 150 tín chỉ) nhưng không có số liệu cam kết mức lương.
3. CẤU TRÚC BẢN GHI DỮ LIỆU CHUẨN (JSONL)

Mỗi câu hỏi sau khi gán nhãn sẽ là 1 dòng JSON hoàn chỉnh:

json
{
  "id": "Q_001",
  "question": "Sinh viên ngành Công nghệ ô tô thông minh khóa 2026 phải tích lũy tối thiểu bao nhiêu tín chỉ để tốt nghiệp?",
  "label": "SUFFICIENT",
  "insufficient_type": null,
  "evidence_chunk_id": "chunk_ctdt_oto_01",
  "sample_answer": "Sinh viên cần tích lũy tối thiểu 152 tín chỉ theo đúng khung chương trình đào tạo."
}

Đối với mẫu câu không đủ bằng chứng:

json
{
  "id": "Q_002",
  "question": "Thời gian nộp đơn xin hoãn thi lần 3 của học kỳ 2 năm 2026 là ngày nào?",
  "label": "INSUFFICIENT",
  "insufficient_type": "false_premise",
  "evidence_chunk_id": null,
  "sample_answer": "Hệ thống từ chối trả lời: Quy chế thi không cho phép hoãn thi đến lần thứ 3 hoặc văn bản không quy định nội dung này."
}
4. QUY TRÌNH KIỂM CHÉO VÀ TÍNH ĐỘ ĐỒNG THUẬN (COHEN'S KAPPA)
Gán nhãn độc lập:
Người 1 (Sinh viên) gán nhãn toàn bộ 
≥
≥ 400 câu hỏi.
Người 2 (GVHD hoặc cộng tác viên) gán nhãn độc lập ngẫu nhiên tối thiểu 20% mẫu (tương đương 
≥
≥ 80 câu), chỉ dựa trên câu hỏi và kho văn bản, không xem trước nhãn của Người 1.
Tiêu chuẩn nghiệm thu:
Độ đồng thuận giữa 2 người phải đạt hệ số Cohen’s 
𝜅
≥
0,70
κ≥0,70 (mức Substantial Agreement).
Xử lý bất đồng:
Tất cả các trường hợp gán nhãn lệch nhau sẽ được tổng hợp vào bảng riêng để thảo luận, thống nhất định nghĩa và cập nhật lại hướng dẫn gán nhãn nếu cần.
