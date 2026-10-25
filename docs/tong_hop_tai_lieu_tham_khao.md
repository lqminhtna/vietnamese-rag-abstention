# TỔNG HỢP KHẢO SÁT TÀI LIỆU THAM KHẢO (LITERATURE SURVEY)
**Đề tài:** Nghiên cứu cơ chế từ chối trả lời khi hệ thống hỏi đáp tài liệu không có đủ bằng chứng  
**Sinh viên:** Lê Quang Minh | **GVHD:** ThS. Nguyễn Hữu Trung  
Bảng tóm tắt các công trình nghiên cứu nền tảng và vai trò đóng góp trực tiếp cho đề tài:
| STT | Tài liệu tham khảo | Tác giả & Năm | Đóng góp / Ý nghĩa đối với đề tài |
|:---:|:---|:---:|:---|
| [1] | **RAG gốc**: *Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks* | Lewis et al. (NeurIPS 2020) | Đặt nền tảng kiến trúc pipeline kết hợp giữa bộ truy hồi và bộ sinh câu trả lời bằng LLM. |
| [2] | **Khảo sát ảo giác**: *Survey of Hallucination in Natural Language Generation* | Ji et al. (ACM Comput. Surv. 2023) | Phân loại các dạng ảo giác (factuality vs. faithfulness) và nguyên nhân LLM tự bịa câu trả lời. |
| [3] | **RGB Benchmark**: *Benchmarking Large Language Models in RAG* | Chen et al. (AAAI 2024) | Chỉ ra điểm yếu chí mạng của LLM ở năng lực từ chối (negative rejection) khi tài liệu không chứa câu trả lời. |
| [4] | **Ảo giác RAG pháp lý**: *Hallucination-Free? Assessing Reliability of AI Legal Tools* | Magesh et al. (JELS 2025) | Minh chứng thực tế: RAG thương mại vẫn ảo giác 17–33%, câu trả lời sai tự tin gây hại hơn việc từ chối. |
| [5] | **Self-RAG**: *Learning to Retrieve, Generate, and Critique* | Asai et al. (ICLR 2024) | Đưa các token tự phản biện (critique) để kiểm tra mức độ liên quan và tính trung thực của đoạn văn. |
| [6] | **CRAG**: *Corrective Retrieval Augmented Generation* | Yan et al. (arXiv 2024) | Cơ chế dùng bộ đánh giá ngoài (Retrieval Evaluator) với 3 ngưỡng để quyết định lọc, bổ sung hoặc từ chối context. |
| [7] | **Selective Classification**: *Selective Classification for Deep Neural Networks* | Geifman & El-Yaniv (NeurIPS 2017) | Nền tảng lý thuyết dự đoán có lựa chọn, định nghĩa độ bao phủ (coverage) và rủi ro (risk). |
| [8] | **Selective QA**: *Selective Question Answering under Domain Shift* | Kamath et al. (ACL 2020) | Ứng dụng selective prediction vào bài toán hỏi đáp, vẽ đường cong risk–coverage và chỉ số AURC. |
| [9] | **Khảo sát từ chối LLM**: *Know Your Limits: A Survey of Abstention in LLMs* | Wen et al. (TACL 2025) | Tổng quan toàn diện các kỹ thuật từ chối trả lời: prompt-based, threshold-based, external verifier. |
| [10] | **Dữ liệu tiếng Việt**: *VLSP 2021 – ViMRC Challenge (UIT-ViQuAD 2.0)* | Nguyen et al. (VNU J. Sci. 2022) | Bộ dữ liệu đọc hiểu tiếng Việt có nhãn câu hỏi không thể trả lời ở mức đoạn văn (dùng làm đối chứng). |
| [11] | **Nested Learning**: *The Illusion of Deep Learning Architecture* | Behrouz et al. (NeurIPS 2025) | Cơ sở lý thuyết giải thích LLM nhầm lẫn giữa bộ nhớ dài hạn (tham số) và ngắn hạn (context) dẫn đến ảo giác. |
| [12] | **TRUE Benchmark**: *Re-evaluating Factual Consistency Evaluation* | Honovich et al. (NAACL 2022) | Đánh giá tính trung thực dựa trên suy diễn ngôn ngữ tự nhiên (NLI / Entailment) để kiểm tra bằng chứng (M2). |
| [13] | **BM25**: *The Probabilistic Relevance Framework: BM25 and Beyond* | Robertson & Zaragoza (FTIR 2009) | Thuật toán truy hồi từ khóa truyền thống (sparse retrieval), thành phần của truy hồi lai. |
| [14] | **BGE-M3**: *Multi-Lingual Text Embeddings Through Self-Knowledge Distillation* | Chen et al. (arXiv 2024) | Mô hình embedding và reranker đa ngôn ngữ mạnh mẽ cho tiếng Việt, dùng cho Cổng 1 (M1). |
| [15] | **Semantic Entropy**: *Detecting Hallucinations in LLMs Using Semantic Entropy* | Farquhar et al. (Nature 2024) | Phương pháp đo độ bất định ngữ nghĩa từ các câu trả lời lấy mẫu, dùng để phát hiện ảo giác. 
