# Nghiên cứu cơ chế từ chối trả lời khi hệ thống RAG hỏi đáp tài liệu không có đủ bằng chứng
*(Abstention Mechanisms for Retrieval-Augmented Document Question Answering under Insufficient Evidence)*

## 1. Thông tin chung
- **Đề tài:** Nghiên cứu cơ chế từ chối trả lời khi hệ thống RAG hỏi đáp tài liệu không có đủ bằng chứng
- **Giảng viên hướng dẫn:** ThS. Nguyễn Hữu Trung
- **Chủ nhiệm đề tài:** Lê Quang Minh
  - MSSV: `2380601342`
  - Lớp: `23DTHB4`
  - Số điện thoại: `0764737823`
  - Email: `lqminhtna@gmail.com`
- **Đơn vị:** Khoa Công nghệ Thông tin – Trường Đại học Công nghệ TP.HCM (HUTECH)

---

## 2. Tính cấp thiết của đề tài
Retrieval-Augmented Generation (RAG) là phương pháp kết hợp mô hình ngôn ngữ với cơ chế truy xuất thông tin từ nguồn dữ liệu bên ngoài, giúp hệ thống có thể sử dụng các tài liệu liên quan để hỗ trợ tạo câu trả lời. Nghiên cứu của Lewis và cộng sự cho thấy RAG có khả năng cải thiện chất lượng và tính chính xác của việc sinh văn bản trong các bài toán yêu cầu khai thác kiến thức từ nguồn tài liệu. Tuy nhiên, việc truy xuất tài liệu không đồng nghĩa với việc hệ thống luôn có đủ thông tin để trả lời một câu hỏi.

Một vấn đề quan trọng của hệ thống hỏi đáp là xử lý những câu hỏi mà dữ liệu cung cấp không chứa đủ bằng chứng. Trong trường hợp này, nếu hệ thống vẫn cố gắng đưa ra câu trả lời, kết quả có thể không phù hợp với thông tin trong tài liệu. Các nghiên cứu về *selective question answering* cho thấy khả năng chủ động từ chối trả lời khi không đủ cơ sở là một yếu tố quan trọng để duy trì độ chính xác của hệ thống. Kamath và cộng sự chỉ ra rằng hệ thống cần cân bằng giữa việc trả lời được nhiều câu hỏi và duy trì độ chính xác, thay vì luôn cố gắng trả lời mọi câu hỏi.

Bên cạnh đó, nghiên cứu về *selective answering* cũng cho thấy việc xác định thời điểm nên trả lời hoặc từ chối trả lời vẫn là một vấn đề cần được nghiên cứu, đặc biệt khi câu hỏi có mức độ không chắc chắn cao. Nghiên cứu gần đây của Madhusudhan và cộng sự cũng cho thấy ngay cả các mô hình ngôn ngữ lớn vẫn gặp khó khăn trong việc nhận biết khi nào cần từ chối trả lời, qua đó cho thấy nhu cầu về các phương pháp đánh giá và kiểm soát khả năng này.

Vì vậy, đề tài tập trung nghiên cứu cơ chế giúp hệ thống RAG nhận biết khi tài liệu truy xuất không cung cấp đủ bằng chứng và chủ động từ chối trả lời. Đề tài sẽ xây dựng hệ thống RAG cơ bản làm mô hình đối chứng, sau đó bổ sung cơ chế kiểm tra bằng chứng và ngưỡng từ chối. Kết quả được đánh giá thông qua độ chính xác, tỷ lệ câu hỏi được trả lời, tỷ lệ từ chối đúng và tỷ lệ từ chối nhầm. Về mặt khoa học, đề tài góp phần khảo sát bài toán selective answering trong bối cảnh RAG; về mặt ứng dụng, kết quả có thể làm cơ sở cho việc xây dựng các hệ thống hỏi đáp tài liệu có độ tin cậy cao hơn.

---

## 3. Mục tiêu đề tài
### 3.1. Mục tiêu tổng quát
Xây dựng cơ chế từ chối trả lời cho hệ thống RAG khi không đủ bằng chứng.

### 3.2. Mục tiêu cụ thể
1. Xây dựng kho tài liệu và bộ câu hỏi thử nghiệm tiếng Việt.
2. Xây dựng hệ thống RAG làm baseline (đối chứng).
3. Xây dựng cơ chế kiểm tra mức độ đầy đủ của bằng chứng.
4. So sánh RAG thông thường với RAG có cơ chế từ chối.
5. Đánh giá độ chính xác và tỷ lệ từ chối nhầm.

---

## 4. Đối tượng, phạm vi và phương pháp nghiên cứu
- **Đối tượng nghiên cứu:** Hệ thống RAG hỏi đáp tài liệu và cơ chế từ chối trả lời khi thiếu bằng chứng.
- **Phạm vi nghiên cứu:** Kho tài liệu tiếng Việt quy mô nhỏ; tập trung vào các câu hỏi có đủ và không đủ bằng chứng trong tài liệu.
- **Cách tiếp cận:** Xây dựng RAG baseline, sau đó bổ sung cơ chế kiểm tra bằng chứng và ngưỡng từ chối.
- **Phương pháp nghiên cứu:** Khảo sát tài liệu, thực nghiệm, so sánh và đánh giá kết quả dựa trên độ chính xác, tỷ lệ từ chối đúng và tỷ lệ từ chối nhầm.

---

## 5. Kế hoạch và nội dung nghiên cứu (12 tuần)
| STT | Nội dung công việc thực hiện chủ yếu | Sản phẩm phải đạt | Thời gian | Người thực hiện |
|:---:|:---|:---|:---:|:---:|
| 1 | Khảo sát RAG và các phương pháp selective answering/abstention; xác định tiêu chí nhận biết câu hỏi đủ và không đủ bằng chứng | Tài liệu tổng quan và cơ sở lý thuyết | Tuần 1-2 | Lê Quang Minh |
| 2 | Thu thập và chuẩn hóa kho tài liệu tiếng Việt; xây dựng bộ câu hỏi gồm nhóm đủ bằng chứng và không đủ bằng chứng; gán nhãn và kiểm chứng thủ công | Kho tài liệu và bộ dữ liệu có 2 nhãn "đủ/không đủ bằng chứng" | Tuần 3-4 | Lê Quang Minh |
| 3 | Xây dựng pipeline RAG baseline gồm chia nhỏ tài liệu, tạo biểu diễn tài liệu, truy xuất các đoạn liên quan và sinh câu trả lời | Hệ thống RAG baseline có khả năng hỏi đáp trên kho tài liệu | Tuần 5-6 | Lê Quang Minh |
| 4 | Thiết lập ngưỡng truy hồi và xây dựng bước kiểm tra mức độ đầy đủ của bằng chứng trước khi sinh câu trả lời | Cơ chế kiểm tra bằng chứng và quyết định "trả lời/từ chối" | Tuần 7–8 | Lê Quang Minh |
| 5 | Thực nghiệm trên bộ câu hỏi; so sánh RAG baseline với RAG có cơ chế từ chối theo các tiêu chí tỷ lệ sai, tỷ lệ câu được trả lời và tỷ lệ từ chối nhầm | Bảng kết quả thực nghiệm và số liệu đánh giá | Tuần 9–10 | Lê Quang Minh |
| 6 | Phân tích sự đánh đổi giữa độ tin cậy và độ bao phủ; điều chỉnh ngưỡng từ chối; xây dựng giao diện demo và hoàn thiện báo cáo | Demo hệ thống và báo cáo nghiên cứu | Tuần 11-12 | Lê Quang Minh |

---

## 6. Cấu trúc thư mục kho lưu trữ
```text
vietnamese-rag-abstention/
├── docs/
│   ├── guidelines/
│   │   └── Huong_dan_gan_nhan_v1.md         <- Hướng dẫn chi tiết phân loại nhãn và quy chuẩn đánh giá
│   ├── danh_sach_tai_lieu.md                <- Danh mục 81 văn bản học vụ thu thập được
│   ├── tong_hop_tai_lieu_tham_khao.md       <- Khảo sát 15 bài báo khoa học nền tảng (Literature Survey)
│   └── bien_ban_kiem_tra_cheo_kappa.md      <- Biên bản đánh giá độc lập kép (Cohen's Kappa = 0.875)
├── du_lieu/
│   ├── kho_doan_van_ban.jsonl               <- 444 đoạn văn bản chuẩn 300-350 từ trích xuất từ 81 văn bản
│   └── bo_du_lieu_cau_hoi.jsonl             <- 400 câu hỏi có gán nhãn (200 đủ bằng chứng, 200 từ chối chia 4 loại)
└── README.md
```

---

## 7. Sản phẩm dự kiến
- **Ứng dụng RAG:** Hệ thống hỏi đáp tài liệu tiếng Việt tích hợp cơ chế từ chối trả lời khi không đủ bằng chứng.
- **Báo cáo nghiên cứu khoa học:** Đầy đủ số liệu thực nghiệm, phân tích đánh đổi độ tin cậy và độ bao phủ (*Risk-Coverage Tradeoff*).
- **Bộ dữ liệu công bố:** Kho văn bản học vụ và bộ câu hỏi đánh giá có gán nhãn chuẩn hóa.
