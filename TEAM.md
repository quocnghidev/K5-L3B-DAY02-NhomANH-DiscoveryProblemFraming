# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: NhomANH
- Candidate problem nhóm chọn (1 câu): Khi khui hoàn (đặc biệt multi-SKU), NV bàn khui kho TMĐT vừa muốn đối chiếu list xuất gốc + tick đủ/thiếu/tráo tại bàn trước khi cộng tồn, để hết restock mù / sót–tráo; nhánh tem fail có AI gợi ý 2–3 đơn + HITL.
- Quyết định cuối (Go / Not Yet / No-Go): **Not Yet**

## Thành viên

| STT | Họ và tên | MSSV | Vai trò trong nhóm | Tài khoản GitHub |
|---:|---|---|---|---|
| 1 | Lê Thanh Hà | 2A202603901 | PM / Điều phối | https://github.com/thanhhale288 |
| 2 | Lã Quốc Nghị | 2A202603947 | Evidence (CP4) | https://github.com/quocnghidev |
| 3 | Phạm Thành An | 2A202603913 | Framing (CP5–CP6) | https://github.com/thanhanbk02 |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò (một người có thể giữ nhiều vai): điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint | Người chính | Người hỗ trợ | Sản phẩm |
|---|---|---|---|
| CP3 — Hội tụ nhóm | Lê Thanh Hà | Cả nhóm pitch | Cluster, cây OST, bảng chấm điểm |
| CP4 — Kiểm chứng | Lã Quốc Nghị | — | Assumption map, snapshot hoặc survey |
| CP4 — Research | Lã Quốc Nghị | — | Bảng research có link |
| CP5 — Quy trình trước/sau | Phạm Thành An | Lê Thanh Hà (phản biện metric) | Quy trình + bảng before/after |
| CP5 — Problem Statement v0 | Phạm Thành An | — | Problem Statement v0 |
| CP6 — Mức can thiệp + Problem Statement v1 | Phạm Thành An | Lã Quốc Nghị | Ma trận, AI Canvas, eval, Problem Statement v1 |
| CP6 — Quyết định | Lê Thanh Hà | Phạm Thành An (ngưỡng metric) | 4 rủi ro + Go/Not Yet/No-Go |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### LeThanhHa-2A202603901

**Phần việc phụ trách:**

- PM / Điều phối: timer, chốt candidate, khóa quyết định Not Yet + ngưỡng dừng; sở hữu `group_report` §1–§2, §8–§9.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- CP1–CP2 + idea chốt tick list + nhánh AI tem fail → mang đi nhóm.
- Facilitation CP3: pitch, phản biện An/Nghị, chốt candidate.
- Draft / chốt framing quyết định Not Yet trên báo cáo nhóm.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `report/individual/2A202603901_LeThanhHa.md`
- `report/individual/idea-chot.md` (nguồn candidate)
- `report/team/group_report.md` mục 1–2, 8–9
- Branch/commit cá nhân: `CP1-CP2-LeThanhHa` — message `bài tập cá nhân CP1-2 của Lê Thanh Hà` (`e020007`); merge `group-report` PR #2

**Điều mình học được từ phần nhóm:**

- Candidate thắng nhờ khả thi + pain rõ hơn “app AI”; Value chưa interview → phải Not Yet, không Go sớm.

### LaQuocNghi-2A202603947

**Phần việc phụ trách:**

- Evidence (CP4): assumption map, Mom Test, research đối thủ có link, assets `cp4-*`.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Pitch card bus (không được chọn); phản biện candidate kho 3 câu (hàng giống / kiểm bằng cơm / AI cải thiện gì).
- Viết mục 3 `group_report`: G1–G5, mở lại link Camsight / Ship Xanh / GoWarehouse / ChannelDock / ResReturn; giữ 0 interview, không bịa snapshot.
- Đẩy nhóm khỏi hướng “cứu tem bằng camera”; khớp quyết định Not Yet vì Value còn giả định.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `report/individual/2A202603947_LaQuocNghi.md`
- `report/assets/cp4-interview-guide.md`, `cp4-interview-snapshot-1.md`, `cp4-research-link-check.md`
- `group_report.md` mục 3 — commit `f2bf7af`

**Điều mình học được từ phần nhóm:**

- Pain lab cần quan sát được: kho tick list rõ hơn pain ETA bus; AI chỉ 1 chỗ khi Rule lọc chưa đủ.

### PhamThanhAn-2A202603913

**Phần việc phụ trách:**

- Framing (CP5–CP6): quy trình Mermaid trước/sau, PS v0/v1, mức AI, eval, hỗ trợ ngưỡng dừng.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Viết `group_report` §4–§7: Mermaid hiện tại/tương lai, before/after, HITL + fallback.
- PS v0 (M1–M3) → v1 (+ M4/M5, AI intervention khi tem fail); ma trận Rule/Workflow; AI Canvas + PAIR.
- Bổ sung ngưỡng dừng gắn metric; chốt mức Workflow (Rule nền luôn bật).

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- `report/individual/2A202603913_PhamThanhAn.md`
- `group_report.md` mục 4–7 — commit `04d9815` (và các commit cập nhật group report sau đó trên `main`)

**Điều mình học được từ phần nhóm:**

- Tách Rule (tick) và AI (chỉ tem fail); metric phải có baseline/target/cách đo dù lab còn giả định.
