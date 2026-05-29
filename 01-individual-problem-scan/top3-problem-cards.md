# 01 — Top 3 Problem Cards & Draft Workflows

Dưới đây là bảng xếp hạng Top 3 vấn đề cá nhân mới được lựa chọn (sau khi thay đổi lựa chọn đề tài) để chuẩn bị thảo luận (pitch) với nhóm, kèm theo chi tiết từng Problem Card và bản phác thảo quy trình (workflow) trước và sau khi áp dụng AI.

## Xếp hạng Top 3 Vấn đề lựa chọn mới

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | **Gán nhãn dữ liệu ảnh cho bài toán Object Detection** (Problem 1) | Quy trình (workflow) cực kỳ rõ ràng, tính lặp lại cực cao. Điểm nghẽn vẽ hộp (bounding box) thủ công có thể cải thiện mạnh mẽ bằng AI auto-labeling (như SAM, YOLO) kết hợp người kiểm duyệt. | Chất lượng nhãn tự động từ AI đối với các vật thể quá nhỏ hoặc bị che khuất một phần. |
| 2 | **Điều phối luồng giao thông tại nút giao bằng mô phỏng** (Problem 2) | Giải quyết một vấn đề thực tế vô cùng phức tạp và ảnh hưởng lớn đến xã hội. AI (Computer Vision) có thể đếm xe tự động và học máy tối ưu (RL/generative simulation) có thể chạy hàng ngàn kịch bản thử nghiệm ảo để thay thế thử nghiệm thực địa gây kẹt xe. | Mức độ tương thích giữa mô phỏng ảo và hành vi thực tế của người tham gia giao thông. |
| 3 | **Viết CV ứng tuyển chuẩn kỹ thuật cho sinh viên** (Problem 3) | Học viên kỹ thuật thường viết CV thiếu chuyên nghiệp, không tối ưu cho ATS (hệ thống lọc hồ sơ). AI có thể đóng vai tuyển dụng để gợi ý chỉnh sửa cụ thể. | Làm sao để sinh viên điền thông tin trung thực và không lạm dụng AI tự bịa kinh nghiệm (boundary). |

---

## PROBLEM CARD #1 — Gán nhãn dữ liệu ảnh Object Detection

**Problem 1 câu:**  
Kỹ sư AI hoặc cộng tác viên gán nhãn dữ liệu mất 2-3 tiếng mỗi ngày để vẽ bounding box và phân loại class thủ công cho hàng trăm bức ảnh, quy trình lặp đi lặp lại và dễ mỏi mắt, sai sót.

**Actor:**  
Kỹ sư AI / Computer Vision, nhân viên gán nhãn dữ liệu (Data Labeler).

**Thời điểm / bối cảnh:**  
Giai đoạn thu thập và chuẩn bị dữ liệu (Data Preparation) trước khi huấn luyện mô hình Object Detection (ví dụ: YOLO, Faster R-CNN) cho các dự án AI.

**Current workflow:**
1. Thu thập ảnh raw từ camera hoặc internet và lưu vào thư mục dự án.
2. Mở công cụ gán nhãn chuyên dụng (như CVAT, LabelImg, Roboflow).
3. Chọn từng ảnh một từ danh sách dữ liệu.
4. Dùng chuột kéo thả để vẽ bounding box (khung chữ nhật) bao quanh vật thể cần phát hiện một cách chính xác.
5. Chọn nhãn (class name) phù hợp từ danh sách class có sẵn cho khung vừa vẽ.
6. Lặp lại bước 4 và 5 cho tất cả vật thể trong ảnh hiện tại.
7. Nhấn lưu và chuyển sang ảnh tiếp theo.
8. Export tập dữ liệu nhãn dưới định dạng chuẩn (YOLO, Pascal VOC, COCO).

**Bottleneck:**  
Bước 4 và 5 (vẽ bounding box và gán nhãn class thủ công) chiếm 80% thời gian (trung bình 1-2 phút/ảnh tùy độ phức tạp của ảnh), gây mỏi mắt, giảm độ chính xác sau 1-2 giờ làm việc liên tục.

**Impact:**  
Mất 120 - 180 phút mỗi ngày cho một người gán nhãn 100 ảnh phức tạp. Đối với dự án cần 10,000 ảnh, tổng công sức là cực kỳ lớn và dễ làm chậm tiến độ dự án AI.

**Success metric:**  
Giảm tổng thời gian gán nhãn cho 100 ảnh từ 120 phút xuống dưới 25 phút (giảm ~80% thời gian), trong khi chất lượng nhãn (độ khớp của box - IoU và độ chính xác của class) được bảo toàn sau bước người kiểm duyệt duyệt lại.

**Non-AI alternative:**  
Sử dụng phím tắt (hotkeys) tối ưu trong tool hoặc thuê ngoài (outsource) quy trình gán nhãn cho các bên dịch vụ dữ liệu (nhưng tốn chi phí lớn và khó bảo mật dữ liệu nội bộ).

**AI hypothesis:**  
Sử dụng mô hình AI pre-trained lớn (như Segment Anything Model - SAM hoặc một mô hình Object Detection pre-trained) để tự động phát hiện vật thể, vẽ bounding box và đề xuất class. Người gán nhãn chỉ đóng vai trò kiểm duyệt, điều chỉnh (fine-tune) lại các hộp vẽ lệch hoặc sửa các nhãn sai sót (semi-automatic labeling).

**Quick gut:**  
`[x]` Workflow  
(Quy trình tuyến tính rõ ràng, các bước nối tiếp cố định, AI đóng vai trò hỗ trợ một bước cụ thể dưới sự giám sát của con người).

### Draft current workflow
```text
CURRENT STATE — 120 phút / 100 ảnh

[1. Tải ảnh & tạo project trong tool: 10']
→ [2. Vẽ bounding box thủ công từng vật thể: 90']  <-- BOTTLENECK (Nhàm chán, mỏi mắt)
→ [3. Chọn nhãn (class) cho từng box: 15']
→ [4. Export dữ liệu nhãn (YOLO/VOC/COCO): 5']
```

### Draft future workflow
```text
FUTURE STATE — 20 phút / 100 ảnh

[1. Tải ảnh vào tool tích hợp AI: 5']
→ [2. AI tự động vẽ box và dự đoán class (Auto-label): 2']
→ [3. Kỹ sư AI kiểm duyệt, điều chỉnh box lệch & sửa class sai: 10']  <-- HUMAN BOUNDARY (Kiểm soát chất lượng)
→ [4. Export dữ liệu nhãn đã chuẩn hóa: 3']

Fallback: Nếu AI dự đoán sai/lệch quá nhiều ở các class hiếm, kỹ sư bỏ qua dự đoán AI và tự vẽ tay thủ công.
```

---

## PROBLEM CARD #2 — Điều phối luồng giao thông tại nút giao bằng mô phỏng

**Problem 1 câu:**  
Đội ngũ công an giao thông và chuyên viên quy hoạch phải thử nghiệm phân làn thực tế trực tiếp tại các nút giao để điều phối giao thông, gây ùn tắc giao thông nghiêm trọng và tốn nhân lực đếm lưu lượng xe thủ công.

**Actor:**  
Cán bộ công an giao thông (Traffic police officer), chuyên viên quy hoạch/phân luồng giao thông đô thị.

**Thời điểm / bối cảnh:**  
Khi có đề xuất thay đổi phân làn giao thông (ví dụ: cấm rẽ trái vào giờ cao điểm, chia lại vạch đường, cắm biển phụ) tại một nút giao thường xuyên xảy ra ùn tắc giao thông nặng nề.

**Current workflow:**
1. Đề xuất các phương án phân làn, điều phối mới trên bản vẽ giấy.
2. Triển khai phân làn thực địa tạm thời bằng dải phân cách di động và biển báo tạm tại nút giao.
3. Cử 2-3 chiến sĩ công an túc trực vào giờ cao điểm để đếm lưu lượng xe qua từng hướng và ghi chép thủ công (hoặc xem qua camera ghi lại để đếm).
4. Duy trì thử nghiệm tại thực địa từ 1-2 tuần để thu thập đủ số liệu đánh giá.
5. Tổng hợp dữ liệu đếm xe thủ công từ giấy/excel, viết báo cáo phân tích hiệu quả điều phối.
6. Stakeholder họp bàn quyết định giữ phương án phân làn mới, điều chỉnh tiếp, hoặc hủy bỏ.

**Bottleneck:**  
Bước 2 và 3 (thử nghiệm phân làn thực tế tại thực địa gây ùn tắc trực tiếp, tốn nhân lực đếm xe giờ cao điểm bằng tay) là điểm nghẽn nguy hiểm và mệt mỏi nhất, dễ gây ra các sự cố kẹt xe dây chuyền diện rộng trong đô thị.

**Impact:**  
Mỗi đợt thử nghiệm thực tế kéo dài từ 7-14 ngày khiến người tham gia giao thông chịu ùn ứ kéo dài, tốn chi phí nhiên liệu và sức khỏe. Cần nhiều cán bộ túc trực thường xuyên dưới thời tiết nắng nóng để đo số liệu.

**Success metric:**  
Chuyển đổi quy trình thử nghiệm thực địa ban đầu sang mô phỏng ảo số hóa, giảm thời gian thử nghiệm và ra quyết định từ 2 tuần xuống dưới 2 ngày (giảm 85% thời gian); loại bỏ hoàn toàn việc đếm xe thủ công; hạn chế tối đa nguy cơ ùn tắc thực tế do áp dụng thử nghiệm sai phương án.

**Non-AI alternative:**  
Sử dụng các phần mềm mô phỏng giao thông truyền thống (như PTV Vissim) đòi hỏi bản quyền đắt đỏ, kỹ sư chuyên môn rất sâu và tốn hàng tuần để thiết kế mạng lưới nút giao, nhập số liệu thủ công.

**AI hypothesis:**  
Sử dụng AI (Computer Vision) để tự động đếm và phân loại phương tiện (xe máy, ô tô, xe buýt) từ dữ liệu camera giám sát tại nút giao để lấy lưu lượng thực tế. Dùng dữ liệu này đưa vào một mô hình học máy mô phỏng/tối ưu hóa (như Reinforcement Learning hoặc Generative Traffic Simulation) để chạy thử nghiệm tự động hàng ngàn kịch bản phân làn ảo trong môi trường ảo, tìm ra phương án tối ưu nhất.

**Quick gut:**  
`[x]` Workflow  
(Quy trình phối hợp nhiều công cụ: AI CV đếm lưu lượng -> Mô hình mô phỏng ảo chạy kịch bản tự động -> Chuyên gia duyệt và ra quyết định thực địa).

### Draft current workflow
```text
CURRENT STATE — 14 ngày (thử nghiệm thực địa)

[1. Lên phương án phân làn sơ bộ: 1 ngày]
→ [2. Đặt dải phân cách tạm thời tại nút giao thực tế: 1 buổi]
→ [3. Phân công người đứng đếm xe giờ cao điểm (thủ công): 7-10 ngày]  <-- BOTTLENECK (Tốn nhân lực, kẹt xe thực tế)
→ [4. Nhập dữ liệu & viết báo cáo thống kê: 2 ngày]
→ [5. Stakeholder phê duyệt phương án: 2 ngày]
```

### Draft future workflow
```text
FUTURE STATE — 2 ngày (mô phỏng số + AI)

[1. AI tự động đếm & thống kê lưu lượng xe qua camera hiện trạng: 1 ngày]
→ [2. Nhập dữ liệu vào môi trường mô phỏng (sinh ngẫu nhiên xe theo lưu lượng): 2 giờ]
→ [3. Chạy thuật toán AI tối ưu (Generative/RL) đề xuất phương án phân làn tối ưu: 1 giờ]  <-- AI Intervention
→ [4. Chuyên gia duyệt kết quả mô phỏng tối ưu nhất: 4 giờ]  <-- HUMAN BOUNDARY (Kiểm duyệt và chốt phương án)
→ [5. Áp dụng phương án tối ưu nhất ra thực địa: 1 buổi]
```

---

## PROBLEM CARD #3 — Viết CV ứng tuyển chuẩn kỹ thuật cho sinh viên

**Problem 1 câu:**  
Sinh viên kỹ thuật mất 3-4 tiếng để viết và định dạng một CV từ đầu nhưng nội dung thường mơ hồ, thiếu từ khóa chuyên môn kỹ thuật, không tối ưu cho hệ thống lọc hồ sơ (ATS), dẫn đến tỷ lệ bị loại từ vòng gửi xe cao.

**Actor:**  
Sinh viên ngành kỹ thuật (CNTT, Điện tử, Cơ khí...) ứng tuyển thực tập hoặc việc làm đầu ra.

**Thời điểm / bối cảnh:**  
Khi sinh viên bắt đầu tìm kiếm cơ hội thực tập (năm 3, năm 4) hoặc chuẩn bị tốt nghiệp ra trường.

**Current workflow:**
1. Tìm kiếm và tải các mẫu CV (template) trên Canva, TopCV hoặc Word.
2. Liệt kê các thông tin cá nhân, học vấn và các dự án môn học đã làm.
3. Viết mô tả chi tiết cho từng dự án (mô tả công nghệ dùng, vai trò của bản thân, kết quả đạt được).
4. Tự dịch thuật ngữ công nghệ sang tiếng Anh hoặc tiếng Việt chuẩn.
5. Định dạng (format) căn chỉnh lề, font chữ, độ dài CV vừa vặn trong 1-2 trang.
6. Gửi CV nhờ anh chị đi trước (mentor) hoặc bạn bè xem và sửa giúp (nếu có).

**Bottleneck:**  
Bước 3 và 5 (viết mô tả dự án kỹ thuật sao cho chuyên nghiệp, nổi bật và format CV chuẩn ATS) là khó khăn nhất. Sinh viên thường viết kiểu liệt kê chung chung ("Làm web bán hàng dùng React") thay vì viết theo mô hình STAR (Situation, Task, Action, Result) và tối ưu từ khóa ngành.

**Impact:**  
Mất 3-4 tiếng để viết một bản CV nhưng chất lượng thấp, gửi đi 10-20 nơi không có phản hồi, làm sinh viên hoang mang, mất tự tin.

**Success metric:**  
Thời gian hoàn thiện CV giảm từ 4 tiếng xuống còn 45 phút; CV sau chỉnh sửa có đầy đủ từ khóa chuyên môn đạt điểm đánh giá ATS cao hơn (>80 điểm trên các công cụ chấm CV tự động); tăng tỷ lệ nhận phản hồi phỏng vấn từ nhà tuyển dụng.

**Non-AI alternative:**  
Sử dụng các CV Builder có sẵn form mẫu điền thông tin (chỉ giải quyết được phần format, không giải quyết được chất lượng viết nội dung mô tả kỹ thuật của sinh viên).

**AI hypothesis:**  
AI hỗ trợ chuyển đổi các mô tả dự án sơ sài của sinh viên thành các gạch đầu dòng chuyên nghiệp theo chuẩn STAR và tối ưu từ khóa kỹ thuật khớp với JD (Job Description) cụ thể, đồng thời tự động kiểm tra lỗi logic/cú pháp.

**Quick gut:**  
`[x]` Workflow  
(Quy trình tương tác qua lại: Nhập liệu -> AI gợi ý tối ưu -> Người dùng chỉnh sửa và duyệt).

### Draft current workflow
```text
CURRENT STATE — 240 phút (4 tiếng)

[1. Chọn & căn chỉnh template thiết kế: 30']
→ [2. Liệt kê thông tin học vấn & dự án môn học: 30']
→ [3. Tự viết mô tả chi tiết dự án (tech stack, vai trò, kết quả): 120']  <-- BOTTLENECK (Mơ hồ, thiếu chuẩn)
→ [4. Tự chỉnh sửa lỗi chính tả, dịch thuật ngữ kỹ thuật: 30']
→ [5. Định dạng căn chỉnh lề vừa trang: 30']
```

### Draft future workflow
```text
FUTURE STATE — 45 phút

[1. Nhập thông tin thô (nháp) vào CV Builder: 15']
→ [2. AI đề xuất viết lại mô tả dự án theo chuẩn STAR & tối ưu keyword: 3']
→ [3. AI tự động kiểm tra lỗi format và chính tả: 2']
→ [4. Sinh viên review nội dung, đối chiếu JD thực tế để tinh chỉnh: 20']  <-- HUMAN BOUNDARY (Kiểm duyệt tính trung thực)
→ [5. Xuất file PDF CV chuẩn ATS: 5']
```

---

## Lựa chọn Card muốn Pitch nhất với Nhóm

### Card tôi muốn pitch nhất:
**PROBLEM CARD #1 — Gán nhãn dữ liệu ảnh Object Detection**

### Vì sao:
- **Tần suất và mức độ lặp lại rất cao:** Đây là công việc cổ điển nhưng luôn gây nhức nhối trong phát triển phần mềm AI. Quy trình vẽ bounding box lặp lại hàng nghìn lần vô cùng nhàm chán và tốn thời gian của các AI Engineer.
- **Workflow rõ ràng bậc nhất:** Bản chất của việc gán nhãn là tuyến tính, các bước thao tác trên tool cực kỳ dễ chuẩn hóa.
- **Có giải pháp công nghệ khả thi và sẵn có:** Hiện tại đã có các mô hình như SAM (Segment Anything Model) từ Meta hoặc YOLO Auto-labeling, việc tích hợp vào workflow gán nhãn thực tế là hoàn toàn khả thi và đem lại hiệu quả tức thì.
- **Metric đo lường cực kỳ cụ thể:** Có thể đo lường trực tiếp bằng thời gian hoàn thành (phút/ảnh) và so sánh chênh lệch rõ ràng trước/sau.

### Câu hỏi tôi muốn nhóm challenge:
- *"Làm thế nào để đo lường độ chính xác của nhãn do AI vẽ tự động (IoU, Class classification) một cách nhanh chóng mà không làm tăng thời gian kiểm duyệt của Kỹ sư AI quá mức?"*
- *"Với các lớp đối tượng mới chưa có mô hình pre-trained tốt, liệu workflow này có thực sự mang lại hiệu quả vượt trội so với gán nhãn thủ công ngay từ đầu không?"*
