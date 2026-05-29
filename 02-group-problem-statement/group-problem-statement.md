# 02 — Group Problem Statement: Viết CV ứng tuyển chuẩn kỹ thuật cho sinh viên

Tài liệu này tổng hợp kết quả làm việc nhóm nhằm phân tích, xác định và xây dựng đề xuất ứng dụng AI vào bài toán viết CV ứng tuyển dành cho sinh viên khối ngành kỹ thuật.

---

## 1. Nhật ký hội tụ nhóm (Group Convergence)

Nhóm gồm 4 thành viên (Duy Anh, Nam, Lan, Minh) đã trình bày 4 candidate problems được trích xuất từ trải nghiệm thực tế:

### 1.1. Danh sách Candidate Problems
| # | Người đề xuất | Candidate problem | Actor | Điểm nghẽn | Cảm nhận nhanh |
|---|---|---|---|---|---|
| 1 | Duy Anh | Viết CV ứng tuyển chuẩn kỹ thuật | Sinh viên năm cuối | Viết mô tả dự án chuẩn STAR & chèn từ khóa JD | Rất nhức nhối, thiết thực |
| 2 | Nam | Tóm tắt bài báo khoa học | Sinh viên nghiên cứu | Đọc hiểu và chắt lọc nội dung cốt lõi | Hay nhưng đã có nhiều tool miễn phí |
| 3 | Lan | Sắp xếp lịch trình tránh burnout | Sinh viên đi làm thêm | Phân bổ thời gian khi có việc đột xuất | Hơi nghiêng về quản lý cá nhân |
| 4 | Minh | Gán nhãn dữ liệu Object Detection | Kỹ sư AI / Labeler | Vẽ bounding box thủ công | Rõ ràng nhưng tích hợp phức tạp |

### 1.2. Phân nhóm (Clustering)
* **Cluster A (Hỗ trợ chuẩn bị hồ sơ ứng tuyển):** Viết CV (Duy Anh), Tối ưu LinkedIn profile.
* **Cluster B (Tóm tắt & Xử lý tài liệu):** Tóm tắt bài báo khoa học (Nam), Soạn tài liệu học tập.
* **Cluster C (Tối ưu hóa quy trình kỹ thuật):** Gán nhãn dữ liệu Object Detection (Minh), Auto-build test.
* **Cluster D (Quản lý cá nhân):** Sắp xếp lịch trình tránh burnout (Lan).

### 1.3. Đánh giá và Chấm điểm đồng thuận
Nhóm tiến hành chấm điểm các shortlist candidates dựa trên thang điểm từ 1 đến 5 cho các tiêu chí:

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Viết CV chuẩn kỹ thuật** | **5** | **5** | **5** | **5** | **5** | **5** | **5** | **35** |
| Gán nhãn dữ liệu ảnh | 4 | 5 | 4 | 4 | 3 | 4 | 4 | 28 |
| Tóm tắt bài báo khoa học | 4 | 4 | 4 | 4 | 4 | 4 | 4 | 28 |

* **Lựa chọn cuối cùng:** **Viết CV ứng tuyển chuẩn kỹ thuật cho sinh viên**.
* **Lý do chọn:** Vấn đề có nỗi đau lớn, ảnh hưởng trực tiếp đến việc làm của sinh viên mới ra trường. Quy trình tuyến tính rõ ràng, dễ đo lường bằng thời gian và chất lượng đầu ra.
* **Lý do loại các bài khác:** Gán nhãn ảnh đòi hỏi việc tích hợp hạ tầng công nghệ phức tạp và chi phí GPU lớn. Tóm tắt bài báo khoa học có giá trị gia tăng thấp vì thị trường đã có quá nhiều công cụ miễn phí.

---

## 2. Kiểm chứng nhanh (Validation) & Research giải pháp

### 2.1. Kết quả kiểm chứng nhanh (Quick Validation)
* **Phỏng vấn nhanh (3 SV CNTT):** Đều xác nhận việc mô tả dự án theo cấu trúc STAR và chọn từ khóa công nghệ khớp JD là bước mất thời gian nhất (thường tốn hơn 2 tiếng).
* **Khảo sát (8 SV trong lớp):** 7/8 bạn mất từ 2-4 tiếng để hoàn thành 1 bản CV hoàn chỉnh và cảm thấy thiếu tự tin về các từ khóa kỹ thuật.
* **Review CV mẫu (15 bản):** 90% lỗi CV của sinh viên là viết chung chung (ví dụ: "Làm trang web", "Tham gia dự án"), thiếu các con số định lượng kết quả và cấu trúc STAR rõ ràng.

### 2.2. Research giải pháp đã có
* **Kickresume / Resume.io:** Hỗ trợ sinh mô tả tự động theo chức danh. *Điểm yếu:* Nội dung rập khuôn, thiếu chiều sâu kỹ thuật thực tế của dự án, dễ bị trùng lặp.
* **Jobscan ATS Checker:** Quét CV đối chiếu với JD để chấm điểm từ khóa. *Điểm yếu:* Chỉ chỉ ra từ khóa thiếu, không hỗ trợ viết lại câu mô tả theo chuẩn STAR.
* **ChatGPT/Claude với prompt tự chế:** Viết lại câu từ rất tốt. *Điểm yếu:* Sinh viên không biết viết prompt chuẩn, dễ dẫn đến việc AI tự bịa đặt thông tin (hallucinate).
* **Bài học rút ra:** AI cần hỗ trợ viết lại dựa trên dữ liệu thô chi tiết do chính người dùng cung cấp (form-based) và tự động so sánh, chèn từ khóa từ JD mục tiêu, chứ không sinh nội dung tự do từ số không.

---

## 3. Bản đồ quy trình (Workflow) trước và sau tối ưu

### 3.1. Quy trình hiện tại (Current State) — 240 phút
Quy trình thủ công hoàn toàn, tốn thời gian viết và hiệu chỉnh nội dung.

```text
           +---------------------------------------------+
           | 1. Tìm & tải mẫu CV trên mạng (Canva/Word)   | (30 phút)
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 2. Liệt kê thông tin học vấn & dự án thô    | (30 phút)
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 3. Tự viết chi tiết dự án (không chuẩn STAR)| (120 phút) <--- [BOTTLENECK]
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 4. Tự dịch thuật ngữ & căn chỉnh định dạng  | (30 phút)
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 5. Nhờ mentor/bạn bè xem và sửa lại         | (Chờ 1-2 ngày)
           +---------------------------------------------+
```

### 3.2. Quy trình tương lai hỗ trợ bởi AI (Future State) — 45 phút
AI tự động hóa khâu viết mô tả chuẩn STAR và kiểm tra lỗi, con người giữ vai trò kiểm duyệt tính trung thực.

```text
           +---------------------------------------------+
           | 1. Nhập thông tin thô vào CV Builder        | (15 phút)
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 2. AI đề xuất viết lại theo STAR & key JD   | (3 phút) <--- [AI INTERVENTION]
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 3. AI tự động kiểm tra format & chính tả    | (2 phút)
           +---------------------+-----------------------+
                                 |
                                 v
           +---------------------+-----------------------+
           | 4. Sinh viên review, chỉnh sửa tính trung thực| (20 phút) <--- [HUMAN BOUNDARY]
           +-------+-----------------------------+-------+
                   |                             |
     (Nội dung đúng|                             | (AI bịa đặt/mơ hồ - Fallback)
      sự thật & JD)|                             v
                   |                    +--------+----------------------------+
                   |                    | Nhập lại thông tin thô chính xác    |
                   |                    +--------+----------------------------+
                   v                             |
           +-------+-----------------------------+-------+
           | 5. Xuất file PDF CV chuẩn ATS               | (5 phút)
           +---------------------------------------------+
```

---

## 4. Problem Statement v0 & v1

### 4.1. Problem Statement v0
* **Actor:** Sinh viên ngành kỹ thuật (đặc biệt là CNTT) chuẩn bị ra trường ứng tuyển.
* **Workflow:** Tìm mẫu -> Nhập thông tin thô -> Tự viết mô tả chi tiết -> Căn chỉnh format -> Nhờ người khác review.
* **Bottleneck:** Bước viết mô tả chi tiết dự án theo chuẩn STAR và khớp từ khóa JD mất 120 phút nhưng chất lượng kém.
* **Impact:** Mất 4 tiếng viết CV nhưng tỷ lệ trượt vòng lọc ATS rất cao, sinh viên mất tự tin và trễ hạn nộp CV.
* **Success Metric:** Tổng thời gian giảm từ 4 tiếng xuống dưới 45 phút; CV đạt điểm ATS >80; tăng tỷ lệ vượt qua vòng lọc hồ sơ.
* **Boundary:** AI không tự nộp hồ sơ; không tự động bịa đặt kinh nghiệm; ứng viên chịu trách nhiệm 100% tính xác thực.

### 4.2. Problem Statement v1
* **Actor:** Sinh viên năm cuối ngành CNTT chuẩn bị ra trường đi xin việc.
* **Workflow:** Nhập thông tin thô -> AI đề xuất viết lại theo STAR khớp JD -> SV review chỉnh sửa -> Kiểm tra lỗi chính tả -> Xuất PDF CV chuẩn ATS.
* **Bottleneck:** Viết mô tả dự án theo STAR và khớp từ khóa của JD mất 120 phút và chất lượng kém.
* **Impact:** CV bị loại ở vòng lọc ATS vì thiếu từ khóa công nghệ, sinh viên trễ hạn apply và mất tự tin.
* **Success Metric:** Giảm thời gian viết CV từ 4 tiếng xuống dưới 45 phút; CV đạt điểm ATS >80; tỷ lệ phản hồi phỏng vấn tăng từ <10% lên >25%.
* **Boundary:** AI không tự bịa kinh nghiệm; không tự động gửi CV; chỉ là công cụ gợi ý; ứng viên chịu trách nhiệm 100% về tính trung thực.
* **AI intervention point:** AI nhảy vào viết lại phần mô tả dự án từ bản nháp thô của sinh viên và từ khóa từ JD.
* **Mức chọn:** Workflow
* **Rủi ro & người thật kiểm tra:** Rủi ro AI bịa đặt kinh nghiệm (hallucinate). Người kiểm tra: SV bắt buộc phải tự đối chiếu bản AI viết với năng lực thực tế, chỉnh sửa lại các công nghệ chưa biết trước khi xuất file.

---

## 5. Phân tích giải pháp: Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Định dạng CV chuẩn ATS từ form điền thông tin có sẵn. | Đủ nếu người dùng đã tự viết nội dung rất tốt. | Không giải quyết được bottleneck diễn đạt và tối ưu từ khóa. | Không làm chính |
| **Workflow** | Điền thông tin nháp -> AI đề xuất mô tả STAR khớp JD -> Người dùng chỉnh sửa -> Xuất PDF. | Đủ vì quy trình tuyến tính, AI tập trung vào một bước ngôn ngữ có con người kiểm soát. | AI có thể viết quá đà hoặc bịa đặt (hallucination). | **Chọn** |
| **Agent** | Agent tự động thu thập LinkedIn/Github, tự tìm JD, tự viết CV và tự động nộp hồ sơ. | Cần thiết khi quy trình tuyển dụng tự động hoàn toàn ở cả hai phía. | Mất kiểm soát tính trung thực, rủi ro bảo mật thông tin cá nhân cực kỳ cao. | Không |

* **Quyết định:** Chọn **Workflow**. Quy trình viết CV của sinh viên là tuyến tính, cố định. Sự tham gia của con người ở bước review (human-in-the-loop) là bắt buộc để đảm bảo tính trung thực và ngăn chặn AI bịa đặt kinh nghiệm. Do đó, mô hình Workflow là tối ưu nhất.

---

## 6. Quyết định cuối cùng (Final Decision)

* **Decision:** **Go**
* **Lý do:** Nỗi đau của sinh viên lớn và thực tế, workflow tuyến tính rõ ràng, rủi ro thấp vì có con người kiểm duyệt chặn lỗi của AI trước khi gửi đi.
* **Pilot nhỏ nhất:** Chạy thử nghiệm bán thủ công: Gom 5 bản CV thô của sinh viên CNTT và JD tương ứng, sử dụng prompt hệ thống đã thiết kế trên ChatGPT để AI tối ưu hóa các dòng mô tả dự án theo chuẩn STAR. Đo lường thời gian sinh viên cần để chỉnh sửa lại và đánh giá độ hài lòng.
