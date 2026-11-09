# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: NhomANH
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu): Khi khui hoàn (đặc biệt multi-SKU), NV bàn khui kho TMĐT vừa muốn đối chiếu list xuất gốc + tick đủ/thiếu/tráo tại bàn trước khi cộng tồn, để hết restock mù / sót–tráo. *(nguồn chốt: `report/individual/idea-chot.md`)*
- Quyết định cuối: **Not Yet** (chờ phỏng vấn người thật CP4 §3.2) — tạm thời không Go sản phẩm/AI

---

## 2. Hội tụ nhóm (CP3)

> Đã chốt theo `idea-chot.md` + bảng so sánh `CP3_SO_SANH_A_B_D_E.md`. Điền tối thiểu để khóa candidate; chi tiết pitch từng thành viên bổ sung khi có đủ tên trong `TEAM.md`.

### 2.1. Pitch

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện nhận được (ai hỏi) |
|---:|---|---|---|---|---|
| 1 | Cá nhân (idea-chot) | Khi khui hoàn multi-SKU, muốn tick theo list xuất gốc tại bàn để không cộng tồn mù | NV bàn khui kho vừa | Khui → đối chiếu list → ghi nhận | Kho đã hiện list trên OMS chưa? Data list ở đâu? |
| 2 | Shortlist B | Khi xuất/nhận hoàn, muốn tem phụ + SOP + checklist trên file đã có để giảm hàng mù không cần app mới | NV khui + trưởng ca | Thiếu rule bắt buộc tick / nhận bao | Đã có tem phụ / từ chối bao mù chưa? |
| 3 | Shortlist A (nhánh) | Khi tem fail, muốn định danh đơn rồi mới mở list tick | NV bàn khui | Định danh khi không quét được | % kiện máy quét bó tay? Workaround mất bao lâu? |
| 4 | Loại khỏi shortlist | Bàn giao bao cuối ngày khớp số kiện trước khi ký | NV nhận + trưởng ca | Nhận bao ký mù | *(loại — khó quan sát lab)* |

### 2.2. Cluster

| Cluster | Các candidate | Pattern chung |
|---|---|---|
| A — Hồ sơ đơn tại bàn khui | Tick multi-SKU (E); 1 màn hồ sơ + mất mã (A); Rule/SOP (B) | Thiếu đối chiếu đúng trước restock |
| B — Bằng chứng video | Video ≠ mã (đã loại khỏi chốt) | Thị trường Camsight/Ship Xanh đỏ |
| C — Đầu ca / nhận bao | Bàn giao bao (D) | Pain trước bước khui; phụ thuộc bưu tá |

### 2.3. Opportunity Solution Tree rút gọn

```text
OUTCOME: Giảm restock sai / sót–tráo khi nhập lại hàng hoàn tại bàn khui kho vừa
├── Opportunity: Khui multi-SKU không có (hoặc không dùng) list tick tại bàn
├── Opportunity: Chưa có rule tem phụ / SOP / checklist bắt buộc trước cộng tồn
└── Opportunity (nhánh): Tem fail → không định danh được đơn trước khi xử lý
     ✗ "App AI nhận diện kiện"
     ✗ "WMS full / Pack Station all-in-one"
     ✗ "Tự build camera quay theo mã"   ← đụng Camsight/Ship Xanh
```

Những ý đã gạch bỏ vì là solution đội lốt opportunity:

- App/AI nhận diện ảnh đoán đơn; SaaS “cứu tem rách”; clone Camsight; full WMS.

### 2.4. Chấm điểm shortlist (1–5)

| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| E — Tick multi-SKU trước restock | 5 | 5 | 2 | 4 | 5 | 5 | 4 | **30** |
| B — Rule/SOP tem phụ + checklist | 5 | 5 | 2 | 3 | 5 | 5 | 4 | **29** |
| A — 1 màn hồ sơ (+ mất mã) | 5 | 5 | 2 | 4 | 4 | 5 | 4 | **29** |

**Candidate được chọn:** E (outcome) + MVP can thiệp B (Rule/SOP + 1 view trên data đã có); A chỉ là nhánh nếu CP4 chứng minh tem fail tắc thật.

**Vì sao chọn:** Pain gắn hành vi hàng ngày hơn edge-case mất mã; vừa lab; không đua cam; mức đơn giản nhất đủ đo được % tick + phút/kiện.

**Vì sao loại các candidate còn lại:** D khó quan sát cửa nhận; video-theo-mã thị trường đỏ; SaaS micro “mất tem” yếu Viability/integration.

**Xử lý bất đồng (nếu có):** Nếu thành viên muốn pitch “AI kho” → ghi lại và giữ boundary: lab không Agent; chứng minh Rule trước.

---

## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại (Value / Usability / Feasibility / Viability) | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | Ở kho target, NV thường **không** soi list từng dòng khi khui multi-SKU (hoặc list không hiện tại bàn) | Value | 5 | 1 | ✅ Ưu tiên phỏng vấn |
| 2 | List xuất gốc **đã mở được** trên Sheets/OMS kho đang dùng — không cần build đồng bộ đa sàn ngày 1 | Feasibility | 5 | 2 | ✅ Hỏi “data nằm đâu” |
| 3 | Sót/tráo hoặc phút dư đối chiếu đủ đau để trưởng ca chịu **thử SOP/checklist 1–2 ca** | Value | 4 | 1 | ✅ Hỏi chuyện đã xảy ra + cam kết thử |
| 4 | NV sẽ tuân thủ tick trước cộng tồn nếu có rule + 1 màn cố định (không bỏ về thói quen đếm hộp) | Usability | 4 | 1 | Sau khi có SOP thử |
| 5 | Kho target **chưa** có WMS/return-check kiểu GoWarehouse (scan → load list → scan từng món) | Feasibility | 4 | 2 | ✅ Hỏi tool đang dùng |
| 6 | Không cần AI để đạt outcome lab; Rule/Workflow đủ | Viability | 3 | 4 | Research đối thủ đã hỗ trợ |

Giả định nhóm kiểm chứng trong buổi này: **#1, #2, #3** (quan trọng cao, bằng chứng thấp). Guide Mom Test: `report/assets/cp4-interview-guide.md`.

### 3.2. Kiểm chứng

Cách đã dùng: **Research desktop (đã mở link)** + **khung phỏng vấn sẵn** — *chưa có Interview Snapshot người thật tại thời điểm ghi mục này (không bịa)*.

Interview snapshot — template trống (copy khi hỏi xong; hoặc file `report/assets/cp4-interview-snapshot-N.md`):

| Trường | Nội dung |
|---|---|
| Người được hỏi (vai trò, không ghi tên thật) | *(điền sau phỏng vấn)* |
| Câu nói đáng nhớ nhất (nguyên văn) | |
| Lần gần nhất gặp vấn đề này: chuyện gì đã xảy ra? | |
| Hiện đang xử lý bằng cách nào (workaround)? | |
| Mất bao lâu, bao lần? | |
| Insight / opportunity rút ra | |

Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| Phỏng vấn kho / NV khui | **0** (đang mở) | — | — |
| Research tool (Camsight, Ship Xanh, GoWarehouse, ChannelDock, ResReturn) | 5 nguồn đã mở link | Pattern “scan → thấy expected SKU → check trước restock” là best practice WMS; VN mạnh ở **video theo mã** | Tool sẵn **giả định quét được mã** + thường cần WMS/OMS; không chứng minh kho Sheets VN thiếu tick |
| Phản biện thị trường (Gemini — chỉ giữ ý, bỏ số %) | 1 vòng | Micro-tool mất tem khó thu tiền; integration trap | Phân bổ % kho / WTP số cụ thể = chưa xác minh → **không dùng làm bằng chứng** |

**Tín hiệu phản bác (desktop, ghi sớm):** Nếu kho đã Camsight/Ship Xanh + gõ SĐT trên Pancake/Sapo ra list trong &lt;1–2 phút và đã tick/đối chiếu → giả định #1–#2 yếu → **đổi/thu hẹp**.

**Nhóm đã sửa problem thế nào sau kiểm chứng:**

- Trước research: dễ lệch sang “cứu kiện mất mã” hoặc “camera theo mã”.
- Sau research + chốt idea: **core = tick list trước restock**; mất mã = nhánh; **không tự build cam**; mức lab = Rule/SOP + view trên data đã có.
- Sau khi có ≥2 snapshot người thật: cập nhật lại dòng này + nâng/hạ điểm bằng chứng assumption #1–#3; quyết định Go / Not Yet / No-Go ở CP6.

### 3.3. Research giải pháp đã có

> Link đã mở/kiểm nội dung (Nov 2026). Chi tiết dài: `report/individual/COMPETITOR_RESEARCH.md`.

| Công cụ / case / pattern | Link | Giải bước nào trong quy trình? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **Camsight — quét đơn hoàn** | https://camzone.vn/camsight-cap-nhat-tinh-nang-quet-don-hoan-cach-thuc-hien-va-quan-ly-du-lieu | Khui hoàn: quét mã → ghi video theo đơn `[HOÀN]-mã`; đối chiếu video đi/về; xuất Excel danh sách hoàn | Đúng pain bằng chứng khiếu nại VN; thao tác quen shop | **Phụ thuộc đưa được mã vào khung**; không phải màn tick đủ/thiếu từng SKU trước cộng tồn | **Không build cam.** Dùng tool sẵn nếu kho cần video; outcome mình khác = list tick |
| **Ship Xanh — quay đóng/khui** | https://shipxanh.com/tdcpt_case_studies/quay-video-dong-goi-khui-hang/ | Detect QR/mã → tự cắt clip đóng/khui; proof trên video | Có trong suite bán hàng; hỗ trợ webcam/RTSP/ĐT | Tập trung bằng chứng video + trạng thái đơn; không thay bước đối chiếu list món | Thị trường video đỏ → loại khỏi candidate chính |
| **GoWarehouse Return Check** | https://docs.gowarehouse.ai/en/operator/return_orders/verification | Scan return/fulfillment/tracking → **load list SP expected** → scan từng món → confirm check → mới inbound; có thể kèm video | **Gần outcome E nhất**: list + check từng dòng trước restock | Cần hệ thống return/fulfillment sẵn (WMS); kho Sheets khó nhảy vào | Pattern đúng = Workflow WMS. Lab nhái **hành vi** bằng Sheets/OMS nhẹ, không clone WMS |
| **ChannelDock — WMS returns** | https://channeldock.com/en/blogs/ecommerce-wms-returns-processing/ | Scan RMA → match order/SKU → grade → quarantine → restock chỉ khi trusted | Nhấn mạnh: **không cộng tồn chỉ vì kiện đã về**; KPI return-to-resale | Enterprise/WMS mindset; không phải micro-tool VN | Xác nhận core value nhóm: đối chiếu trước restock là chuẩn ops, không phải “ý hay AI” |
| **ResReturn — receiving workflow** | https://resreturn.com/blog/returns-receiving-workflow | Intake → unpack/identify → inspect/grade → disposition + post hệ thống | Unreadable/mismatch = exception path; metric dock rõ | Blog quy trình, không phải sản phẩm nhẹ cho kho Sheets VN | Nhánh mất mã/tem = exception, không phải toàn bộ product |

**Kết luận research (1 đoạn):**

```text
Thế giới đã giải mạnh: (1) video theo mã khi scan được — Camsight/Ship Xanh;
(2) list + scan item trước restock — WMS (GoWarehouse/ChannelDock pattern).
Khoảng trống lab: kho vừa Sheets/OMS nhẹ chưa WMS — ép hành vi tick list tại bàn bằng Rule/SOP + 1 view.
Không Go tự xây AI/cam. Value giả định #1–#3 vẫn chờ người thật.
```

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

Sơ đồ (ASCII, Mermaid hoặc link ảnh trong `report/assets/`):

```text

```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

**Bottleneck chính:**

### 4.2. Quy trình tương lai

Ghi rõ bước nào **Rule**, bước nào **AI**, bước nào **con người**, **boundary** ở đâu, **phương án quay về** khi AI sai.

```text

```

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước | | | |
| Tổng thời gian | | | |
| Số bước thủ công | | | |
| Bottleneck chính | | | |
| Rủi ro mới phát sinh | | | |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** (AI không được làm gì; khi nào cần con người kiểm tra — HITL) | |

Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:

-

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô:

Vì sao:

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | | | | |
| **Rule** | | | | |
| **Workflow** | | | | |
| **Agent** | | | | |

**Mức chọn:**

**Vì sao không chọn mức đơn giản hơn:**

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | |
| **Judgment** — con người cân nhắc, quyết định gì? | |
| **Action** — hành động cuối cùng là gì, ai làm? | |
| **Outcome** — đo kết quả bằng gì? | |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | |

### 6.4. Hai câu hỏi của Google PAIR

- Người dùng muốn **được hỗ trợ (augment)** hay **giao hẳn việc (automate)**? Bằng chứng:
- AI sai kiểu nào tệ hơn, **báo nhầm** hay **bỏ sót**? Vì sao, và thiết kế đã xử lý thế nào:

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** | |
| **AI intervention point** | |
| **Mức chọn** | No AI / Rule / Workflow / Agent |
| **Rủi ro & người kiểm tra** | |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| | | | |

**Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí):**

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | | |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | | |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | | |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | | |

### 8.2. Kết luận

**Quyết định:** Go / Not Yet / No-Go

**Lý do:**

**Nếu Go — pilot nhỏ nhất:**

**Nếu Not Yet — cần kiểm chứng gì trước:**

**Nếu No-Go — nên làm gì thay AI:**

**Ngưỡng dừng** (nếu sau … mà … thì quay về …):

---

## 9. Hạn chế và hướng tiếp theo

-

## 10. Tài liệu tham khảo

-
