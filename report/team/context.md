# Context — Candidate đã chốt (NhomANH)

> Đọc file này trước khi sửa report / hỏi AI tiếp. Chi tiết đầy đủ: `idea-chot.md`, `group_report.md`.  
> Lab = framing, **không build app**. Mọi số = **giả định / chưa đo** (chưa phỏng vấn kho).

---

## Một câu

Kho TMĐT vừa, bàn khui hoàn: **bắt buộc tick list xuất gốc trước khi cộng tồn (Rule)**; khi **tem quét fail**, **AI gợi ý 2–3 đơn → người chọn (HITL)** rồi mới tick. Không cam-theo-mã, không Agent, không gọi vốn.

---

## Job Story

**Khi** khui hoàn (đặc biệt multi-SKU),  
**tôi muốn** đối chiếu list xuất + tick đủ/thiếu/tráo tại bàn,  
**để** hết restock mù / sót–tráo.

| | |
|---|---|
| **Actor** | NV bàn khui kho fulfillment / shop tự kho vừa |
| **Không làm** | WMS enterprise · clone Camsight · forwarder · “mọi seller” |
| **Outcome** | Giảm restock sai / sót–tráo tại bàn khui |
| **Quyết định lab** | **Not Yet** (Value chưa có người thật) |

---

## Luồng (Rule + 1 điểm AI)

```text
Quét OK  → RULE: hiện list → NGƯỜI tick → mới cộng tồn
Quét FAIL → thu SĐT/SKU/ảnh → AI top-3 → HITL chọn
          → list + tick | hoặc “không khớp” → lookup tay / góc chờ
```

**Boundary:** AI không tự chốt đơn, không sửa tồn, không gửi khiếu nại.

| Mức | |
|---|---|
| Rule | Luôn bật (tick bắt buộc) |
| Workflow + AI | Chỉ nhánh tem fail |
| Agent | Không |

---

## Giả định chết người

| ID | Giả định | Sai thì |
|---|---|---|
| G1 | Thường không soi/tick list tại bàn | Đổi ngách / chỉ nhắc miệng |
| G2 | List đã mở được trên Sheets/OMS | Not Yet / SOP giấy |
| G3 | Tem fail + lookup tay vẫn tắc | **Tắt AI**, giữ Rule |
| G4 | Có input an toàn cho AI | Fallback lookup tay |
| G5 | Chọn nhầm đơn tệ hơn bỏ sót gợi ý | Cấm auto-select |

---

## Metric (khi đo được)

- % kiện multi-SKU tick đủ dòng trước restock  
- Phút định danh khi tem fail (trước/sau AI)  
- % lần đơn đúng ∈ top-3 gợi ý  

---

## Cạnh tranh (đừng đua)

- Camsight / Ship Xanh / VietCam → video khi **còn mã**  
- WMS Return Check → list + scan item (cần WMS)  
- Ngách mình → hành vi tick trên kho nhẹ + AI hẹp khi fail  

---

## File liên quan

| File | Việc gì |
|---|---|
| `report/individual/idea-chot.md` | Bản chốt idea |
| `report/team/group_report.md` | CP3–CP6 nhóm |
| `report/assets/cp4-interview-guide.md` | Mom Test (nếu sau này hỏi được) |
| `report/individual/COMPETITOR_RESEARCH.md` | Research đối thủ (nếu có trên nhánh) |

---

## Khi nhờ AI tiếp — nhắc

1. Pain-first; không nhảy Agent / không scaffold app.  
2. Không bịa phỏng vấn hay số WTP/%.  
3. G3 sai → tắt AI trong framing.  
4. Giữ quyết định **Not Yet** đến khi có bằng chứng hành vi.
