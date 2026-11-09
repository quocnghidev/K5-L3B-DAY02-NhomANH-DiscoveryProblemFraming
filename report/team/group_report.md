# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: NhomANH
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu): Khi khui hoàn (đặc biệt multi-SKU), NV bàn khui kho TMĐT vừa muốn đối chiếu list xuất gốc + tick đủ/thiếu/tráo tại bàn trước khi cộng tồn, để hết restock mù / sót–tráo; nhánh tem fail có AI gợi ý 2–3 đơn + HITL. *(nguồn: `report/individual/idea-chot.md`)*
- Quyết định cuối: **Not Yet** — framing Rule + 1 điểm AI (Workflow); Value/bằng chứng người thật chưa có (lab giả định)

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

**Candidate được chọn:** E (outcome) + Rule/SOP (B) **luôn bật** + nhánh A gắn **1 điểm AI gợi ý đơn khi tem fail** (Workflow + HITL), bật khi giả định G3 đúng.

**Vì sao chọn:** Outcome hàng ngày (tick list); AI không thay SOP — chỉ hỗ trợ định danh khi quét fail; không Agent, không đua cam.

**Vì sao loại các candidate còn lại:** D khó quan sát cửa nhận; video-theo-mã thị trường đỏ; SaaS chỉ “cứu tem” yếu Viability.

**Xử lý bất đồng (nếu có):** Muốn “nhiều AI hơn” → không: Rule đủ cho tick; AI chỉ 1 chỗ. G3 sai → tắt AI, giữ Rule.

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
| 6 | Tem fail + lookup tay vẫn tắc (nhiều phút / dễ sai đơn) → AI gợi ý top-3 có ích hơn Rule thuần | Value (điều kiện bật AI) | 5 | 1 | ✅ Khai báo giả định; chưa có interview |
| 7 | Input AI có sẵn an toàn (metadata đơn ± ảnh được phép); AI chỉ suggest không auto-chốt | Feasibility / Viability | 4 | 2 | Framing bảo mật + HITL |

Giả định nhóm ưu tiên (không có người kho trong lab → **giữ bằng chứng = 1**, không bịa snapshot): **#1, #2, #6**. Guide nếu sau này hỏi được: `report/assets/cp4-interview-guide.md`.

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

- Trước research: dễ lệch sang “cứu kiện mất mã” hoặc “camera theo mã” hoặc “app AI kho”.
- Sau research + chốt: **core = Rule tick list trước restock**; **AI = 1 điểm** trên nhánh tem fail (gợi ý 2–3 đơn + HITL); không build cam; không Agent.
- Lab không có phỏng vấn kho: mọi Value = giả định → **Not Yet**; nếu sau này G3 (assumption #6) sai → **tắt AI**, giữ Rule.

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
Khoảng trống lab: kho Sheets/OMS nhẹ — Rule tick tại bàn + AI chỉ khi tem fail (gợi ý + HITL).
Không build cam / Agent. Value vẫn giả định → Not Yet.
```

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

```text
HIỆN TẠI (giả định / chưa đo)

[Nhận bao] → [Phân luồng]
  → [Khui + quét tem]
       ├─ OK  → [? mở Sheets/OMS / đếm hộp / không tick đủ dòng] → cộng tồn
       └─ FAIL → [dò SĐT / hỏi Zalo / để góc mù] ← BOTTLENECK nhánh
  → [Cất kệ]
```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | NV nhận | Bao hoàn | Kiện vào bàn | theo ca | |
| 2 | NV khui | Kiện + tem | Tem OK / fail | mỗi kiện | |
| 3 | NV khui | Đơn / không đơn | Tình trạng hàng | **ước 2–4'/multi-SKU; 5–8'/mất mã** (chưa đo) | Bottleneck |
| 4 | NV / Admin | Ghi chú | Cộng tồn | cuối kiện / cuối ca | Rủi ro restock mù |
| 5 | NV | Hàng đã ghi | Lên kệ | | |

**Bottleneck chính:** Bước 3 — thiếu list tick có cấu trúc; khi tem fail thì định danh đơn kéo dài.

### 4.2. Quy trình tương lai

```text
TƯƠNG LAI (framing)

[Khui + quét]
  ├─ OK  —RULE→ [Hiện list] —NGƯỜI→ [Tick đủ/thiếu/tráo] —RULE→ [Cho phép cộng tồn]
  └─ FAIL —RULE→ [Thu tín hiệu SĐT/SKU/ảnh]
           —AI→ [Top 2–3 đơn + lý do ngắn]
           —HITL→ [Chọn 1 / “không khớp”]
                ├─ chọn 1 → list + tick như trên
                └─ không khớp → góc chờ + lookup tay (fallback)
Boundary: AI không tự chọn đơn, không sửa tồn, không gửi khiếu nại.
```

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước | ~5 | ~5–6 (thêm AI+HITL chỉ khi fail) | Đa số kiện không gọi AI |
| Tổng thời gian | chưa đo | ↓ phút đối chiếu / định danh fail | Giả định |
| Số bước thủ công | hầu hết | tick vẫn tay; AI chỉ gợi ý | Augment |
| Bottleneck chính | thiếu tick + dò đơn khi fail | ép tick; rút gọn dò đơn nếu G3 đúng | |
| Rủi ro mới phát sinh | — | Gợi ý sai → chọn nhầm đơn nếu bỏ qua HITL | Mitigate bằng bắt buộc người chọn |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | NV bàn khui kho TMĐT/fulfillment vừa (Sheets/OMS nhẹ) |
| **Quy trình** | Nhận bao → khui/quét → đối chiếu & ghi nhận → cộng tồn → cất kệ |
| **Bottleneck** | Đối chiếu list / định danh đơn trước restock (đặc biệt multi-SKU; nặng hơn khi tem fail) |
| **Impact** | Restock mù, sót/tráo, hàng góc mù, lệch tồn *(mức độ = giả định / chưa đo)* |
| **Success Metric** (baseline → target, cách đo) | % kiện multi-SKU tick đủ dòng trước restock: baseline chưa đo → target ↑ (vd ≥80% mẫu 20 kiện) khi có quan sát; phút/kiện fail: ↓ ≥50% nếu bật AI — cách đo log/quan sát |
| **Boundary** (AI không được làm gì; khi nào cần con người kiểm tra — HITL) | v0: tập trung Rule; AI chưa bắt buộc. Con người luôn tick và luôn chốt đơn khi tem fail. |

Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:

- Phản biện: không interview thì Value yếu → **đồng ý**, để Not Yet; không bịa snapshot.
- Phản biện: chỉ Rule thì “không có AI” → **đồng ý một phần**, bổ sung 1 điểm AI có điều kiện G3 ở v1.

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô: **độ mơ hồ trung bình (tem fail / nhiều đơn gần giống) × độ phức tạp thấp–TB (một bước gợi ý trong luồng cố định)**.

Vì sao: Bước tick là Rule rõ; chỉ đoạn map tín hiệu → ứng viên đơn là mơ hồ vừa phải, không cần Agent tự lập kế hoạch.

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | Nhắc soi list | NV đã tự tick tốt | Không đổi hành vi | Không đủ một mình |
| **Rule** | Bắt buộc tick + cấm cộng tồn chưa tick; tem phụ | G1–G2 đúng; tem fail ít hoặc lookup tay nhanh | Không giải định danh khi fail | **Luôn bật** |
| **Workflow** | Rule + (khi fail) AI top-3 → HITL → list tick | G3 đúng: lookup tay tắc | Gợi ý sai; phụ thuộc input | **Chọn (AI chỉ 1 bước)** |
| **Agent** | AI tự chọn đơn / tự tồn / tự claim | Không | Sai đơn = thiệt hại tiền | **Không** |

**Mức chọn:** **Workflow** = Rule (nền) + AI gợi ý trên nhánh tem fail.

**Vì sao không chọn mức đơn giản hơn:** Chỉ Rule không rút được thời gian định danh khi G3 đúng. Chỉ No AI không ép được hành vi tick.

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | Xếp hạng 2–3 đơn ứng viên (+ lý do ngắn) khi tem không quét được |
| **Judgment** — con người cân nhắc, quyết định gì? | Chọn 1 đơn hoặc từ chối gợi ý → lookup tay / góc chờ |
| **Action** — hành động cuối cùng là gì, ai làm? | NV mở list, tick, (được phép) cộng tồn — người làm |
| **Outcome** — đo kết quả bằng gì? | Phút định danh khi fail; % chọn đúng trong top-3; % tick đủ dòng |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | SĐT/SKU/shop/thời cửa sổ đơn gần đây ± ảnh; *giả định có trên OMS/Sheets — chưa xác minh* |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | Log: đơn người chọn vs top-3; nút “không khớp” |

### 6.4. Hai câu hỏi của Google PAIR

- Người dùng muốn **được hỗ trợ (augment)** hay **giao hẳn việc (automate)**? Bằng chứng: thiết kế **augment** — gợi ý + HITL; không có bằng chứng người muốn giao máy tự chốt đơn (và rủi ro tiền cao nếu automate).
- AI sai kiểu nào tệ hơn, **báo nhầm** hay **bỏ sót**? **Báo nhầm (đưa đơn sai / tự tin sai) tệ hơn** vì dễ cộng tồn nhầm. Thiết kế: không auto-select; ưu tiên “không chắc → không khớp”; eval phạt rank đưa đơn sai lên top.

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | NV bàn khui kho TMĐT/fulfillment vừa |
| **Quy trình** | Quét → (fail: AI gợi ý → HITL) → list tick → cộng tồn |
| **Bottleneck** | Thiếu tick trước restock; định danh khi tem fail *(G3 giả định)* |
| **Impact** | Restock sai / sót–tráo / hàng mù *(chưa đo)* |
| **Success Metric** (baseline → target, cách đo) | Như v0 + thêm: % lần đơn đúng nằm trong top-3 khi fail (mẫu có nhãn sau HITL) |
| **Boundary** | AI không tự chọn đơn, không sửa tồn, không khiếu nại; không gửi PII thừa |
| **AI intervention point** | Sau quét fail & trước khi mở list tick: rank 2–3 đơn |
| **Mức chọn** | Workflow (Rule nền + AI 1 bước) |
| **Rủi ro & người kiểm tra** | Chọn nhầm đơn → NV + trưởng ca review; fallback lookup tay |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| AI intervention | Chưa có / không bắt buộc | Có — chỉ nhánh tem fail | Muốn có điểm AI hợp lệ khi G3; không nhét AI vào tick |
| Mức | ngầm Rule | Workflow | Rule không đủ nếu lookup fail tắc |
| Boundary | HITL tick | HITL chọn đơn + tick | Giảm rủi ro báo nhầm |

**Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí):**

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | Đơn đúng trong top-3 | Sau khi người xác định đơn thật, đơn đó ∈ top-3 | Đơn đúng không có trong gợi ý trong khi tín hiệu đủ |
| 2 | Không bịa đơn | Mọi ID gợi ý tồn tại trên dữ liệu kho đã nạp | ID không có trong nguồn |
| 3 | Lý do khớp tín hiệu | Lý do nêu đúng field dùng (SĐT/SKU…) | Lý do không liên quan / mâu thuẫn input |
| 4 | Từ chối khi thiếu tín hiệu | Trả “không đủ dữ liệu” thay vì đoán bừa | Vẫn rank khi input rỗng/rác |
| 5 | Latency chấp nhận được | Gợi ý xong trước khi NV bỏ sang góc mù *(ngưỡng chưa đo)* | Chờ lâu hơn lookup tay quen thuộc |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | **Cao** | Chưa phỏng vấn; G1/G3 giả định |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | TB | HITL chọn từ 2–3 mục quen; rủi ro bỏ qua đọc lý do |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | TB–Cao | Phụ thuộc list/metadata sẵn (G2/G4); chưa xác minh kho cụ thể |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | TB | PII/ảnh; chi phí token chưa đo; không gọi vốn lab |

### 8.2. Kết luận

**Quyết định:** **Not Yet**

**Lý do:** Framing Rule + Workflow AI đã rõ và khớp research (không đua cam; AI hẹp), nhưng Value chưa có hành vi người thật → không Go triển khai/AI production.

**Nếu Go — pilot nhỏ nhất:** 1 bàn khui · chỉ Rule tick 1–2 ca → nếu G3 quan sát được mới bật AI gợi ý trên mẫu kiện fail · đo phút + % top-3.

**Nếu Not Yet — cần kiểm chứng gì trước:** G1 (có thiếu tick?), G2 (list ở đâu?), G3 (tem fail có tắc lookup?). Có thể hỏi bạn học từng làm kho/shop hoặc quan sát 1 ca — **không bắt buộc bịa số**.

**Nếu No-Go — nên làm gì thay AI:** Chỉ Rule/SOP + tem phụ + checklist Sheets; dùng Camsight/Ship Xanh sẵn cho video.

**Ngưỡng dừng** (nếu sau … mà … thì quay về …): Nếu sau khi có ≥2 nguồn quan sát/hỏi mà lookup tem fail trung bình &lt;2 phút và NV đã tick list → **tắt AI**, giữ Rule; nếu không có list đâu cả → **đổi ngách**.

---

## 9. Hạn chế và hướng tiếp theo

- Không có Interview Snapshot người trong kho — mọi baseline là giả định.
- Chưa implement — chỉ framing CP3–CP6.
- Tiếp theo (ngoài lab hoặc nếu có nguồn): kiểm G1–G3; nếu G3 sai → cập nhật report tắt AI.

## 10. Tài liệu tham khảo

- `report/individual/idea-chot.md`
- `report/individual/COMPETITOR_RESEARCH.md` (nếu có trên nhánh)
- Link research §3.3 (Camsight, Ship Xanh, GoWarehouse, ChannelDock, ResReturn)

