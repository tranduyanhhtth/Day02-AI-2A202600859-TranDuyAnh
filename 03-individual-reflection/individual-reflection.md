# 03 — Individual Reflection: Trần Duy Anh

Tài liệu này là bản báo cáo cá nhân (Reflection) của Trần Duy Anh về quá trình tham gia làm việc nhóm, đóng góp vào sản phẩm chung và cách sử dụng AI trong buổi Lab 2.

---

## 1. Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| **Scan cá nhân** | Lên 3 ideas (CV Builder, Traffic Sim, Object Det). | Góp phần làm đa dạng pool ý tưởng, giúp nhóm có cơ sở so sánh các domain khác nhau. |
| **Pitch Problem Card** | Pitch bài toán CV Builder. Trình bày quy trình làm CV hiện tại và pain point. | Nhóm nhận thấy bài toán này phổ biến nhưng thiếu tính "deep tech" và độ khó cho một Agent. |
| **Challenge bài của bạn khác** | Phản biện bạn Phong về việc "làm sao ngăn sinh viên bypass AI để lấy code?". | Giúp nhóm nhận ra rủi ro cốt lõi và bổ sung ngay phần Boundary / Guardrails cho Socratic Tutor. |
| **Gom trùng / cluster** | Gợi ý nhóm phân loại theo End-user (Sinh viên vs Developer). | Giúp dễ ra quyết định khi so sánh các bài toán cùng tệp người dùng. |
| **Chọn candidate problem** | Đồng ý lùi lại, ủng hộ ý tưởng Vibe Code Chuẩn của Phong. | Nhóm chốt được chủ đề nhanh chóng mà không bị kẹt vì cái tôi cá nhân. |
| **Validation / research** | Góp ý đưa ví dụ Khanmigo vào so sánh vì từng thấy mô hình này hoạt động tốt. | Thêm căn cứ vững chắc cho tính khả thi của giải pháp. |
| **Workflow nhóm** | Vẽ before/after workflow, đặc biệt tập trung vào việc mô tả sự bế tắc của sinh viên khi đọc Log lỗi. | Làm nổi bật pain point tại bước "đọc log không hiểu" dẫn đến "hành vi copy". |
| **Problem Statement** | Giúp nhóm chốt lại success metric thực tế (thời gian debug giảm xuống < 10 phút). | PS trở nên đo lường được thay vì nói chung chung "giúp SV học tốt hơn". |
| **Rule / Workflow / Agent** | Tham gia tranh luận nên dùng Workflow hay Agent. | Chốt được phương án dùng Workflow (Multi-turn chat) thay vì Agent để tránh over-engineering, kết hợp Rule chặn code. |
| **Decision** | Vote "Go". | Cùng nhóm thống nhất hành động triển khai ý tưởng Tutor. |

---

## 2. Bảng dùng AI trong quá trình làm Lab

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| **Scan** | Brainstorm ý tưởng | Gợi ý được nhiều pain point phổ biến. | Gợi ý đôi khi quá vĩ mô (vấn đề quy hoạch giao thông). | Lọc lại chọn các vấn đề gần gũi với sinh viên. |
| **Problem Card** | Định dạng nội dung. | Giúp chuẩn hóa các đầu mục (actor, workflow). | Không hiểu sâu về workflow sinh viên làm CV. | Tự bổ sung chi tiết về khó khăn ATS và việc format. |
| **Workflow** | Không dùng. | N/A | N/A | Tự thảo luận cùng nhóm để vẽ workflow sinh viên debug. |
| **Research** | Tìm kiếm tool tương tự. | Gợi ý ChatGPT và các tool AI cơ bản. | Không cung cấp được tool giáo dục chuyên biệt sâu. | Tự thêm Khanmigo từ kiến thức cá nhân. |
| **Problem Statement** | Kiểm tra xem PS đã đủ tiêu chuẩn chưa. | Báo lỗi thiếu Boundary. | Đưa ra success metric quá xa vời (tăng điểm số lên A+). | Tự định nghĩa lại metric về thời gian debug < 10 phút. |
| **Rule / Workflow / Agent**| Tra cứu định nghĩa Agent và Workflow. | Giải thích sự khác biệt giữa Workflow và Agent (Agent có tool use, tự trị). | N/A | Thuyết phục nhóm hạ từ Agent xuống Workflow vì việc hỏi đáp Socratic chỉ cần Multi-turn chat tĩnh. |
| **Decision** | Phản biện lại PS cuối cùng. | Đóng vai "devil's advocate" để tìm lỗ hổng. | Đôi khi hỏi lặp lại. | Tự chốt lại quyết định cuối cùng dựa trên bối cảnh thực tế. |

---

## 3. Reflection câu hỏi mở

**1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**
Tôi nhận ra rằng pain point càng hẹp, càng đặc thù của người trong ngành (như việc bị kẹt logic code hay phải đọc source code legacy) thì khi áp dụng AI lại càng tạo ra impact sâu sắc hơn là các bài toán mang tính chất tiện ích chung chung (như làm CV).

**2. Nhóm có lúc nào bị solution-first không?**
Có, lúc đầu khi Phong trình bày ý tưởng Socratic Tutor, cả nhóm ngay lập tức bàn xem dùng prompt nào, API của OpenAI hay Claude, mà quên mất việc vẽ workflow. Tôi đã kéo nhóm lại để tập trung vào việc mô tả nỗi đau của sinh viên khi không hiểu log lỗi trước khi bàn về công nghệ.

**3. Tôi có thay đổi ý kiến sau khi bị challenge không?**
Có. Ban đầu tôi bảo vệ bài CV Builder vì nghĩ nó rất thực tế và đông người dùng. Nhưng sau khi bị nhóm challenge rằng "chỉ cần 1 prompt là làm xong CV", tôi nhận ra nó không đáp ứng đủ yêu cầu chuyên sâu của môn học (thiết kế luồng hệ thống tương tác nhiều bước) và quyết định lùi lại, ủng hộ ý tưởng Socratic Tutor của Phong.

**4. Tôi đóng góp gì thật sự vào artifact cuối?**
Tôi trực tiếp thiết kế Before/After Workflow, nhấn mạnh sự thay đổi hành vi từ "Copy Code" sang "Tự suy nghĩ nhờ Hint", và thiết lập Boundary rõ ràng là "cấm AI xuất code trực tiếp". Tôi cũng điều chỉnh lại success metric để nhóm có thể đo lường dễ hơn (thời gian tự debug giảm xuống < 5 phút và pass bài dưới 3 lượt chat).

**5. Điều khó nhất khi viết Problem Statement là gì?**
Khó nhất là xác định Boundary. Khi thiết kế Tutor AI, ranh giới giữa việc "gợi ý" và "giải hộ bài" rất mong manh. Dễ bị sa đà vào việc biến AI Tutor thành một AI làm hộ bài, phá hỏng mục đích sư phạm ban đầu.

**6. Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?**
Tôi sẽ challenge nhóm nghĩ sâu hơn về cách đánh giá thế nào là "hiểu bài". Hiện tại metric "tự fix lỗi dưới 10 phút" vẫn có thể bị đánh lừa nếu sinh viên âm thầm mở tab khác tra Google thay vì dùng Tutor. Có lẽ cần thêm metric liên quan đến việc duy trì số vòng hội thoại liên tục với Tutor.

---

## 4. Tự kiểm cuối bài

- [x] **[12đ cá nhân]** Cá nhân có 5+ problems và top 3 Problem Cards.
- [x] **[12đ cá nhân]** Tôi đã pitch rõ và challenge nhóm đúng trọng tâm.
- [x] **Nhóm có nhật ký hội tụ từ candidates về 1 bài.**
- [x] **[15đ nhóm]** Nhóm có workflow trước/sau.
- [x] **[20đ nhóm]** Nhóm có Problem Statement v0/v1 với metric và boundary rõ.
- [x] **[15đ nhóm]** Nhóm có so sánh No AI / Rule / Workflow / Agent.
- [x] **[10đ nhóm]** Nhóm có Go / Not Yet / No-Go và lý do rõ.
- [x] **[10đ cá nhân]** Reflection cá nhân có nói rõ vai trò trong nhóm, cách dùng AI, điều học được và nếu làm lại sẽ đổi gì.
- [x] **[6đ cá nhân]** Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp với AI.
