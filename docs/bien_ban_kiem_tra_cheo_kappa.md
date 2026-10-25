# BIÊN BẢN KIỂM TRA CHÉO VÀ ĐỘ ĐỒNG THUẬN GÁN NHÃN (COHEN\'S KAPPA)
**Đề tài:** Nghiên cứu cơ chế từ chối trả lời khi hệ thống hỏi đáp tài liệu không có đủ bằng chứng  
**Người gán nhãn 1:** Lê Quang Minh (Sinh viên chủ nhiệm đề tài)  
**Người gán nhãn 2:** ThS. Nguyễn Hữu Trung (Cán bộ hướng dẫn khoa học)  

---

## 1. THÔNG TIN MẪU KIỂM TRA CHÉO
- Tổng số câu hỏi trong bộ dữ liệu: 400 câu
- Số lượng mẫu rút ngẫu nhiên để đánh giá độc lập: 80 câu (chiếm 20.0% tổng số mẫu)
- Phương pháp gán nhãn: Độc lập kép (Double-blind annotation trên cùng kho tài liệu)

---

## 2. KẾT QUẢ ĐỒNG THUẬN VÀ CHỈ SỐ COHEN\'S KAPPA
- Tỷ lệ đồng thuận quan sát (Observed Agreement - $): **93.75%** (75/80 câu thống nhất)
- Tỷ lệ đồng thuận kỳ vọng ngẫu nhiên (Expected Agreement - $): **50.00%**
- **Hệ số Cohen\'s Kappa ($\kappa$): 0.8750**
- **Đánh giá:** $\kappa = 0.8750 \ge 0.70$, đạt mức **Đồng thuận rất cao (Almost Perfect Agreement)** theo thang đo Landis & Koch (1977). Đủ điều kiện nghiệm thu bộ dữ liệu theo quy định thuyết minh.

---

## 3. THỐNG KÊ CHI TIẾT CÁC TRƯỜNG HỢP BẤT ĐỒNG VÀ BIỆN PHÁP XỬ LÝ
Các trường hợp bất đồng nhãn chủ yếu phát sinh ở nhóm câu hỏi \'bằng chứng một phần\' (partial evidence) khi câu hỏi có 1 vế tìm thấy trong tài liệu và 1 vế nằm ngoài văn bản:
- **Biện pháp xử lý thống nhất:** Tuân thủ triệt để nguyên tắc thận trọng (conservative principle): Nếu câu hỏi có bất kỳ phần nào không được văn bản hỗ trợ thì bắt buộc gán nhãn KHONG_DU_BANG_CHUNG nhằm triệt tiêu tối đa rủi ro ảo giác của hệ thống.
