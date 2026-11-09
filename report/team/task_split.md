# Phân công task & commit — NhomANH (Day 02)

> Idea đã chốt: **Rule tick list xuất gốc tại bàn khui** + **AI gợi ý 2–3 đơn khi tem fail (HITL)** → quyết định lab mặc định **Not Yet** (chưa có interview người kho).  
> Nguồn framing: `report/individual/idea-chot.md`, `report/team/group_report.md`.

---

## Luật commit (để điểm nhóm khớp)

1. Mỗi người **chỉ commit phần mình viết/sửa** — không commit hộ.
2. File cá nhân `report/individual/MSSV_HoTen.md` = **bắt buộc 1 người 1 file**, commit bằng GitHub của mình.
3. `group_report.md`: mỗi người sửa **đúng mục mình sở hữu** (1–2 commit rõ message).
4. Không viết hộ reflection / mục Cá nhân trong `TEAM.md`.
5. Ai làm gì trong `TEAM.md` phải khớp commit của người đó.

---

## Phân công theo vai (cân commit)

Điền tên vào cột Owner. Lab chuẩn **3 người**; nếu 4 người → người thứ 4 hỗ trợ B (interview/survey) + review link research.

| Vai | Owner | Sở hữu `group_report` | Commit gợi ý (message) | Done khi |
|---|---|---|---|---|
| **A — PM / Điều phối** | *(điền tên)* | §1, §2 (CP3), §8–§9 (quyết định, hạn chế) + checklist `SUBMISSION.md` | `CP3: điền pitch + lý do chốt candidate` → `CP6: khóa Not Yet + ngưỡng dừng` | Pitch có tên người + câu phản biện từng thành viên; Go/Not Yet có ngưỡng dừng |
| **B — Evidence** | *(điền tên)* | §3 (CP4 assumption + kiểm chứng + research) + `report/assets/cp4-*` | `CP4: assumption map + research có link đã mở` → `CP4: ghi rõ 0 interview / thêm snapshot nếu hỏi được` | Bảng research ≥2–3 link mở được; **không bịa** snapshot; có ≥1 tín hiệu phản bác |
| **C — Framing** | *(điền tên)* | §4–§7 (quy trình Mermaid, PS v0/v1, mức AI, eval) + Mermaid trong report | `CP5: Mermaid trước/sau + before/after + PS v0` → `CP6: Workflow + AI Canvas + eval + PS v1` | Có HITL + fallback; metric baseline/target/cách đo; v1 khác v0 có lý do |

**Nếu A đã draft nhiều sườn:** vẫn để A **chốt/chỉnh** §2 + §8 (1–2 commit refine). B và C **bổ sung / verify** phần mình (Mermaid, link research, bảng eval) — đừng để A commit hết.

---

## Phần mỗi người đều phải làm (commit riêng)

| Task | File | Ai |
|---|---|---|
| CP1 + CP2 | `report/individual/MSSV_HoTen.md` | Mỗi người |
| CP7 reflection (≥200 từ, tự viết) | cùng file, mục 4–6 | Mỗi người |
| Phần Cá nhân | `TEAM.md` | Mỗi người tự điền |
| 1 câu hỏi phản biện trong bảng pitch §2.1 | `group_report.md` | Mỗi người (A có thể gom sau khi cả nhóm gửi Discord) |

---

## Thứ tự làm (tránh đụng file)

```text
1) Cả 3: tạo/điền file individual — song song, commit riêng
2) B: xong §3 CP4 trước (research → chốt vào group_report; không bịa interview)
3) C: §4–§7 (sau khi B khóa “Value = giả định / Not Yet”)
4) A: §2 pitch đủ tên + §8 quyết định + đọc SUBMISSION
5) Cả 3: TEAM.md phần mình + push
6) A: merge/review lần cuối (không viết hộ nội dung)
```

**Tránh conflict:** một thời điểm chỉ 1 người sửa `group_report.md`; hoặc mỗi người branch `docs/cpX-<ten>` rồi PR ngắn.

---

## Map nhanh với idea đã chốt

| Vai | Bảo vệ / nhấn mạnh |
|---|---|
| **B** | G1/G2/G3 giả định; research Camsight / WMS return-check; vì sao **Not Yet** |
| **C** | Rule luôn bật; AI chỉ nhánh tem fail; HITL; eval top-3; không Agent |
| **A** | Vì sao chọn E+B (+ nhánh A); loại video-theo-mã / nhận bao D; ngưỡng tắt AI nếu lookup &lt;2' |

---

## Checklist cổng nộp (nhanh)

- [ ] `TEAM.md`: bảng thành viên + phân công CP + mỗi người phần Cá nhân
- [ ] Mỗi người có `report/individual/MSSV_HoTen.md` (đúng format tên)
- [ ] `group_report.md` đủ mục 2–8; số liệu gắn *ước lượng / chưa đo* nếu chưa hỏi người kho
- [ ] Không PII trong snapshot; không bịa phỏng vấn
- [ ] Mỗi acc GitHub có ≥1 commit thật trên phần mình phụ trách
- [ ] Checklist `SUBMISSION.md` đã đọc to / xác nhận trước khi nộp LMS

---

## Điền Owner (sau Align)

| Thành viên | GitHub | Vai (A/B/C) |
|---|---|---|
| | | |
| | | |
| | | |
