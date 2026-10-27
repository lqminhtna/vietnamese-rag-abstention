# BÁO CÁO THỐNG KÊ CHI TIẾT BỘ DỮ LIỆU CÂU HỎI (DATASET V1)
**Tập tin:** `du_lieu/bo_du_lieu_cau_hoi.jsonl`  
**Quy mô:** 400 câu hỏi | **Định dạng:** JSON Lines (JSONL)  

---

## 1. Phân bổ theo nhãn chính (Label Distribution)
| Nhãn | Số lượng câu | Tỷ lệ | Định nghĩa & Xử lý của hệ thống |
|:---|:---:|:---:|:---|
| **`DU_BANG_CHUNG`** (Sufficient) | 200 | 50.0% | Hệ thống bắt buộc phải **trả lời** kèm trích dẫn đoạn bằng chứng (`ma_doan_bang_chung`). |
| **`KHONG_DU_BANG_CHUNG`** (Insufficient) | 200 | 50.0% | Hệ thống bắt buộc phải **từ chối trả lời** (Abstention). Nếu trả lời sẽ bị tính là ảo giác (hallucination). |
| **TỔNG CỘNG** | **400** | **100%** | **Cân bằng tuyệt đối 50/50** |

---

## 2. Phân loại chi tiết 4 dạng câu hỏi không đủ bằng chứng
| Phân loại con (`loai_tu_choi`) | Số lượng | Tỷ lệ trong nhóm từ chối | Mục đích nghiên cứu |
|:---|:---:|:---:|:---|
| **`ngoai_pham_vi`** (Out-of-scope) | 50 | 25.0% | Đánh giá năng lực nhận diện câu hỏi ngoài phạm vi trường/miền học vụ. |
| **`thieu_chi_tiet`** (Missing details) | 50 | 25.0% | Đánh giá việc mô hình có tự 'bịa' số liệu (tiền thưởng, cấu hình máy) hay không. |
| **`tien_de_sai`** (False premise) | 50 | 25.0% | Kiểm tra khả năng phát hiện câu hỏi gài bẫy, giả định trái quy chế học vụ. |
| **`bang_chung_mot_phan`** (Partial evidence) | 50 | 25.0% | Kiểm tra năng lực phát hiện câu hỏi hỏi gộp 2 ý mà chỉ có 1 ý được chứng minh. |

---

## 3. Phân chia tập huấn luyện/dò ngưỡng và kiểm tra (Dev / Test Split)
Bộ dữ liệu áp dụng phân tầng ngẫu nhiên (Stratified Sampling) giữ nguyên tỷ lệ 50/50 ở cả 2 tập:
- **Tập phát triển (`phat_trien_dev`):** **120 câu** (30.0%) – Dùng quét ngưỡng tau1 (retrieval score) và tau2 (NLI/verifier score) ở Tuần 4 và Tuần 5.
- **Tập kiểm tra (`kiem_tra_test`):** **280 câu** (70.0%) – Dùng độc lập để đo chỉ số rủi ro, độ bao phủ và AURC ở Tuần 6.

---

## 4. Cấu trúc trường thông tin của mỗi bản ghi
Mỗi câu hỏi được lưu dưới dạng một đối tượng JSON chuẩn:
```json
{
  "ma_cau_hoi": "CH_0001",
  "cau_hoi": "Sinh viên theo học ngành Dược cần đáp ứng các điều kiện gì theo chuẩn chương trình đào tạo khóa 2026?",
  "nhan": "DU_BANG_CHUNG",
  "loai_tu_choi": null,
  "ma_doan_bang_chung": "doan_0001",
  "cau_tra_loi_mau": "Văn bản 100310ctdt_duoc_2026 quy định rõ các chuẩn năng lực...",
  "tap_du_lieu": "kiem_tra_test"
}
```
