# 02 — Group Problem Statement: Vibe code chuẩn - Socratic Coding Tutor (Workflow Edition)

Tài liệu này tổng hợp kết quả làm việc nhóm nhằm phân tích, xác định và thiết kế đề xuất ứng dụng AI (Multi-turn Workflow) vào bài toán "Giải thích logic & Debug" dành cho sinh viên học lập trình, với phương pháp tiếp cận Socratic (gợi mở thay vì đưa đáp án).

---

## 1. Nhật ký hội tụ nhóm (Group Convergence)

Nhóm gồm 4 thành viên (Trần Duy Anh, Đỗ Nhật Minh, Nguyễn Tuấn Phong, Nguyễn Hữu Đức) đã trình bày tổng cộng 12 candidate problems từ trải nghiệm thực tế:

### 1.1. Danh sách 12 Candidate Problems
| # | Người đề xuất | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh |
| :---- | :---- | :---- | :---- | :---- | :---- |
| 1 | Trần Duy Anh | Viết CV ứng tuyển chuẩn kỹ thuật cho sinh viên | Sinh viên ngành kỹ thuật | Tự viết mô tả chi tiết dự án (chuẩn STAR) và căn chỉnh format | Workflow |
| 2 | Trần Duy Anh | Điều phối luồng giao thông tại nút giao | Cán bộ CSGT, chuyên viên quy hoạch | Thử nghiệm thực địa gây ùn tắc, đứng đếm xe thủ công | Workflow |
| 3 | Trần Duy Anh | Gán nhãn dữ liệu ảnh Object Detection | Kỹ sư AI, Data Labeler | Vẽ bounding box và gán nhãn thủ công gây mỏi mắt, sai sót | Workflow |
| 4 | Đỗ Nhật Minh | Chấm và cộng điểm tương tác tự động | Trợ giảng (TA) và Học viên | Đọc dò tay từng dòng log chat và đối chiếu tên hiển thị | Workflow |
| 5 | Đỗ Nhật Minh | Hỗ trợ cài đặt môi trường và sửa lỗi Lab | Học viên mới và Trợ giảng (TA) | Chờ TA rảnh để đọc tin và ping-pong lấy bối cảnh máy | Workflow |
| 6 | Đỗ Nhật Minh | Giải đáp tự động quy định khóa học | Học viên, TA, BTC | TA lặp lại việc lục tìm link và gõ lại câu trả lời cũ | Workflow |
| 7 | Nguyễn Tuấn Phong | Giải thích logic & Debug (Vibe code chuẩn) | Học viên (đặc biệt là non-tech) | Bế tắc tự sửa và chọn cách copy code AI/bạn bè | Workflow |
| 8 | Nguyễn Tuấn Phong | Xử lý FAQ & Giảm tải cho Trợ giảng | Học viên & Lab Coach | Học viên chờ lâu, TA lặp lại công việc tay chân rep tin | Workflow |
| 9 | Nguyễn Tuấn Phong | Tổng hợp thông tin & Link phân tán | Học viên | Cuộn tìm Discord và lục lọi Outlook Mail mất thời gian | Workflow |
| 10 | Nguyễn Hữu Đức | Khó truy cập học liệu | Sinh viên mới nhập học | Thao tác tìm kiếm đúng tài liệu đa nền tảng dễ nhầm lẫn | Workflow |
| 11 | Nguyễn Hữu Đức | Thiếu trợ giảng hỗ trợ không kịp | Sinh viên trong giờ lab/assignment | Coach không đủ, thời gian chờ hỗ trợ quá lâu | Agent |
| 12 | Nguyễn Hữu Đức | Nhắc nhở deadline chưa hiệu quả | Sinh viên nhiều lớp/deadline | Không có hệ thống nhắc việc, lỡ/trôi thông báo | Workflow |

### 1.2. Phân nhóm (Clustering)
| Cluster | Candidates included | Pattern chung | Ghi chú |
| :---- | :---- | :---- | :---- |
| A. Hỗ trợ gỡ lỗi & Lab | 5, 7, 11 | Học viên kẹt kỹ thuật nhưng TA phản hồi chậm, dẫn đến mất gốc/nản chí. | Gom chung vì đều xoay quanh trải nghiệm thực hành Lab và thiếu hụt TA. |
| B. Quản lý thông tin & Hỏi đáp | 6, 8, 9, 10, 12 | Học viên hỏi đi hỏi lại hoặc miss thông tin phân tán; TA quá tải đóng vai "tổng đài viên". | Cùng giải bài toán truy xuất thông tin (RAG/FAQ) và cảnh báo. |
| C. Tối ưu tác vụ thủ công lặp lại | 3, 4 | Dùng mắt và tay thao tác hàng trăm lần (dò điểm, vẽ khung ảnh) dễ sai sót. | Rõ ràng về metric thời gian nhưng mức độ tư duy (reasoning) của AI thấp. |
| D. Tác vụ chuyên môn sâu | 1, 2 | Cần chuyên môn ngành hẹp (đánh giá CV chuẩn ATS, mô phỏng giao thông). | Scope khá lớn so với một bài thực hành Lab ngắn hạn. |

### 1.3. Đánh giá và Chấm điểm đồng thuận
Nhóm tiến hành chấm điểm 3 candidates đại diện các cluster (thang điểm 1-5):

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **Giải thích logic & Debug** | 5 | 5 | 5 | 5 | 5 | 5 | 5 | **35** |
| Chấm điểm tương tác | 5 | 5 | 4 | 5 | 4 | 5 | 4 | 32 |
| Viết CV kỹ thuật | 4 | 4 | 3 | 4 | 4 | 4 | 4 | 27 |

* **Lựa chọn cuối cùng:** **Giải thích logic & Debug (Vibe code chuẩn)** của Nguyễn Tuấn Phong.
* **Lý do chọn:** Vấn đề cực kỳ sát sườn với giáo dục: Học viên nộp bài chạy được nhờ copy AI nhưng rỗng kiến thức. Thiết kế workflow có "Human boundary" rất chuẩn (AI chỉ gợi ý lỗi, học viên phải tự sửa). Rất dễ build prototype bằng một Workflow AI (Socratic Prompt) ngay trong buổi Lab để kiểm chứng.

---

## 2. Kiểm chứng nhanh (Validation) & Research giải pháp

### 2.1. Kết quả kiểm chứng nhanh (Quick Validation)
* **Khảo sát nhanh (Discord Poll - 10 người):** 90% học viên xác nhận phải dùng ChatGPT giải hộ vì áp lực thời gian nộp Lab, dẫn tới hổng kiến thức nghiêm trọng.
* **Phỏng vấn sâu (2 Học viên, 1 TA):**
  - Học viên thừa nhận việc copy code AI là do "sợ trễ deadline" và "TA phản hồi quá chậm". Học viên muốn có tool chỉ lỗi thay vì cho sẵn đáp án.
  - TA xác nhận thời gian kẹt lỗi kéo dài 20-30 phút/case gây quá tải.
* **Quyết định định hình AI:** AI phải giải thích cực kỳ ngắn gọn, khoanh vùng lỗi, tuyệt đối không sinh code. Thêm fallback tag TA nếu hỏi 3 lần vẫn sai.

### 2.2. Research giải pháp đã có
| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
| :---- | :---- | :---- | :---- | :---- | :---- |
| **CS50 Duck (Harvard CS50)** | [CS50's Duck Debugger](https://cs50.harvard.edu/x/2023/honesty/) | Nhận mã lỗi và giải thích khái niệm. | Thiết kế System Prompt tuyệt đối không viết code thay sinh viên. | Context bị giới hạn trong phạm vi khóa CS50. | Cần thiết lập Hard-rule để cấm cung cấp code trực tiếp. |
| **Khanmigo (Khan Academy)** | [Khanmigo Socratic AI](https://www.khanacademy.org/khan-labs) | Hỗ trợ giải bài tập qua phương pháp hỏi ngược lại. | Buộc người học phải tự động não. | Đôi khi quá dài dòng gây ức chế khi học viên kẹt deadline. | Không lạm dụng hỏi ngược quá nhiều, chỉ gợi ý 1-2 vòng rồi fallback. |
| **GitHub Copilot / Cursor** | [GitHub Copilot Chat](https://github.com/features/copilot) | Phát hiện lỗi và sinh code tự động. | Context-aware cực mạnh. | **Anti-pattern:** Nhả code quá nhanh, cổ xúy thói quen "Vibe code" mù quáng. | Cấm tích hợp AI trực tiếp vào IDE sinh code. |

---

## 3. Bản đồ quy trình (Workflow) trước và sau tối ưu

### 3.1. Quy trình hiện tại (Current State)
Quy trình độc hại khi sinh viên phụ thuộc LLM.

```text
[Sinh viên] Viết code --> Bị lỗi --> [Sinh viên] Đọc log lỗi đỏ (không hiểu) --> [Sinh viên] Paste đề + lỗi vào ChatGPT --> [ChatGPT] Trả đoạn code fix sẵn --> [Sinh viên] Copy & Paste đè lên code cũ --> Pass testcase nhưng rỗng kiến thức.
```
**Bottleneck:** Cầu cứu AI và nhận code giải sẵn là "điểm gãy". Sinh viên hoàn thành "nghĩa vụ nộp bài" nhưng thất bại ở "mục tiêu hiểu logic".

### 3.2. Quy trình tương lai (Future State) - Multi-turn Workflow
Hệ thống ép sinh viên phải tự suy nghĩ thông qua Hint.

```text
[Sinh viên viết code lỗi] --> [Nạp code vào Socratic Tutor AI] --> [AI phân tích lỗi] --> (Rule: Cấm xuất code) --> [Đưa ra Hint 1: Khoanh vùng lỗi + Hỏi gợi mở] --> [Sinh viên suy nghĩ & tự sửa] 
Nếu vẫn sai --> [Đưa ra Hint 2: Giải thích logic] --> [Sinh viên tự sửa đúng & Hiểu bài]
Nếu sai >3 lần --> [Tag TA vào hỗ trợ 1-1]
```

---

## 4. Problem Statement (v1)

* **Actor:** Sinh viên năm nhất (non-tech) học môn lập trình cơ sở, chưa có nền tảng tư duy thuật toán và yếu kỹ năng đọc log lỗi.
* **Workflow:** Viết code bị lỗi → Gửi code/log cho Socratic Tutor (AI) → AI phân tích và đặt câu hỏi gợi mở → SV phản hồi/tự sửa code → Lặp lại đến khi hiểu bản chất.
* **Bottleneck:** Sự cám dỗ của việc có đáp án ngay lập tức từ các tool AI bên ngoài làm thui chột năng lực tự gỡ rối (debug) của sinh viên.
* **Impact:** Cải thiện triệt để kỹ năng giải quyết vấn đề tự lực (problem-solving), triệt tiêu thói quen học vẹt, copy mù quáng.
* **Success Metric:** 
  - Thời gian trung bình để tự gỡ lỗi thành công giảm từ 20 phút xuống < 5 phút.
  - Tỷ lệ sinh viên nộp bài thành công sau tối đa 3-4 lượt tương tác gợi ý (turns) từ bot đạt > 80%.
* **Boundary:** 
  - Tuyệt đối KHÔNG xuất ra mã nguồn hoàn chỉnh.
  - Mã giả (pseudocode) bị giới hạn: Không dùng cú pháp cấu trúc (if/for/while).
  - Tích hợp System Prompt chống Prompt Injection (từ chối mọi yêu cầu in code).
* **Mức chọn:** Workflow (Multi-turn chat).

---

## 5. Phân tích giải pháp: Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Dùng regex chặn từ khóa "code" trong prompt hoặc output để cấm chatbot sinh mã. | Nếu chỉ muốn cấm bot một cách cứng nhắc. | Không giúp gì cho sinh viên khi bị kẹt logic, sinh viên sẽ nản và bỏ đi tìm tool khác. | Không |
| **Workflow** | AI đóng vai trò Socratic Tutor trong 1 phiên chat (multi-turn). Cố định luồng: SV nhập lỗi → AI dựa trên System Prompt phân tích và đặt câu hỏi gợi mở → SV trả lời/sửa → Lặp lại. | Hỗ trợ tương tác tuyến tính qua lại. AI xử lý tốt ngôn ngữ tự nhiên và giữ bối cảnh trong một phiên chat. | Sinh viên dùng thủ thuật ép bot nhả code. Cần System Prompt chặt chẽ. | **Chọn** |
| **Agent** | AI tự động truy cập vào môi trường code của SV, tự chạy test, tự phân tích lỗi và lập kế hoạch mớm bài học theo lịch sử năng lực. | Khi cần một hệ thống AI hoàn toàn tự trị. | Over-engineering. Tốn kém tài nguyên và vượt quá phạm vi của một buổi lab. | Không |

* **Quyết định:** Chọn **Workflow**. Việc AI đóng vai trò Tutor hỏi - đáp bản chất là một quy trình tương tác đa lượt (multi-turn), không yêu cầu AI tự gọi các công cụ bên ngoài hay tự lên kế hoạch phức tạp. Mức Workflow đáp ứng hoàn hảo tính linh hoạt, đồng thời dễ kiểm soát rủi ro hơn Agent.

---

## 6. Quyết định cuối cùng (Final Decision)

* **Decision:** **Go**
* **Lý do:** Bài toán giải quyết trúng "nỗi đau" lớn nhất của giáo dục lập trình hiện đại. Workflow rõ ràng, rủi ro được cô lập tốt bằng Boundary cứng (chặn code), dễ tạo dữ liệu test và chứng minh được giá trị tư duy logic của AI.
* **Pilot nhỏ nhất:** Xây dựng một chatbot nhỏ trên nền tảng nội bộ. Nhập input là 1 bài tập kinh điển và 1 đoạn code có lỗi logic phổ biến. Mời 5 sinh viên yếu kỹ năng debug dùng thử Socratic Tutor để sửa lỗi. Đo lường thời gian hoàn thành và phỏng vấn nhanh cảm nhận của họ.
