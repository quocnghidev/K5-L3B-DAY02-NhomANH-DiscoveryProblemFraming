# Idea đã chốt — mang đi nhóm

> Bản chốt (cá nhân → nhóm). **Mọi số & hành vi kho = giả định / chưa đo** (lab không có phỏng vấn người trong kho).  
> Không pitch gọi vốn. Không build product trong lab — chỉ framing.

---

## 1. Idea (1 câu)

**Trạm khui hoàn kho TMĐT vừa:** bắt buộc **list xuất gốc + tick đủ/thiếu/tráo** trước khi cộng tồn (**Rule/SOP + 1 view** trên data đã có); khi **tem quét fail**, thêm **1 bước AI gợi ý 2–3 đơn ứng viên** → người chọn (HITL) → mới mở list tick. Không đua camera-theo-mã, không Agent tự chốt đơn/tồn.

---

## 2. Problem (Job Story)

**Khi** đang khui hàng hoàn (đặc biệt đơn nhiều món / biến thể gần giống),  
**tôi muốn** đối chiếu đúng list xuất gốc ngay tại bàn và tick đủ–thiếu–tráo,  
**để** không cộng tồn mù và không sót hàng / nhận tráo trước khi cất kệ.

| | |
|---|---|
| **Actor** | NV bàn khui kho fulfillment / shop tự kho **vừa** (~50–300 kiện hoàn/ngày, *giả định*); quét + Sheets/OMS nhẹ + cam góc |
| **Bottleneck** | (1) Thiếu / không dùng list tick trước restock · (2) *Giả định nhánh AI:* tem fail → dò đơn lâu |
| **Stakeholder** | Dùng: NV khui · Duyệt: trưởng ca · Chịu tiền: chủ shop / chủ kho |

---

## 3. Core value & giả định (khai báo rõ — chưa kiểm chứng người thật)

**Core value:** *Đối chiếu đúng trước khi restock.*

| # | Giả định | Vai trò | Nếu sai thì… |
|---|---|---|---|
| G1 | NV thường không soi list từng dòng (hoặc list không hiện tại bàn) | Value — lý do có Rule | Chỉ cần nhắc miệng / đã đủ OMS |
| G2 | List xuất gốc đã mở được trên Sheets/OMS — không build đồng bộ đa sàn ngày 1 | Feasibility Rule | Thu hẹp SOP giấy / Not Yet |
| G3 | Tem fail + lookup thủ công (SĐT/Sheets) vẫn tốn nhiều phút / dễ sai đơn | Value — **lý do có AI** | **Tắt AI**, chỉ giữ Rule + tick |
| G4 | Có input an toàn cho AI mỗi lần fail: metadata đơn gần đây (SĐT rút, SKU, shop…) ± ảnh tem/SP nếu kho cho phép | Feasibility AI | AI không chạy; fallback lookup tay |
| G5 | Sai **chọn nhầm đơn** tệ hơn **không gợi ý** → AI chỉ suggest, không auto-select | Usability / boundary | Cấm auto-chốt |

**Không có phỏng vấn:** điểm bằng chứng = thấp → quyết định lab mặc định **Not Yet** trên Value; framing vẫn viết đủ Rule + điểm AI có điều kiện G3.

---

## 4. Giải pháp chốt = Rule mặc định + 1 điểm AI (Workflow)

```text
[RULE] Quét OK
  → Hiện list xuất gốc (1 màn)
  → NV tick đủ | thiếu | tráo
  → Mới cộng tồn

[RULE → AI → HITL] Quét FAIL
  → Thu thập tín hiệu tối thiểu (SĐT/SKU/shop/ảnh còn đọc được)
  → AI xếp hạng gợi ý tối đa 2–3 đơn (kèm lý do ngắn)
  → NGƯỜI chọn 1 đơn hoặc “không khớp → góc chờ / lookup tay”
  → Hiện list + tick như trên
  → AI không tự chốt đơn, không sửa tồn, không gửi khiếu nại
```

| Mức | Vai trò |
|---|---|
| **No AI / Rule** | Bắt buộc tick; cấm cộng tồn khi chưa tick; tem phụ lúc xuất (nếu được) — **luôn bật** |
| **Workflow + AI** | Chỉ nhánh tem fail: AI rank ứng viên → HITL — **bật khi giả định G3** |
| **Agent** | **Không chọn** |
| **Không làm** | Clone Camsight · WMS full · AI tự đoán đơn không HITL |

**Vì sao không chỉ Rule?** Nếu G3 đúng, lookup tay vẫn là bottleneck định danh — Rule tick không giải được “đúng đơn nào”.  
**Vì sao không Agent?** Bước tiếp theo cố định; chỉ một chỗ cần gợi ý.  
**Token / chi phí:** ước lượng / chưa đo — 1 lần gọi model nhỏ mỗi kiện fail; đo sau nếu pilot.

**Bảo mật (framing):** Chỉ gửi trường cần cho match; che SĐT một phần nếu được; không đưa toàn bộ DB đơn lên model; ảnh chỉ khi đã đồng ý.

---

## 5. Metric & quyết định

| Metric | Baseline | Target (đề xuất) | Cách đo *khi có điều kiện* |
|---|---|---|---|
| % kiện multi-SKU tick đủ dòng trước restock | chưa đo | ↑ rõ sau SOP | Quan sát / checklist |
| Phút định danh khi tem fail | chưa đo | ↓ ≥50% vs lookup tay *nếu bật AI* | Log mẫu kiện fail |
| % lần HITL chọn đúng trong top-3 gợi ý (eval AI) | — | ngưỡng do nhóm đặt sau mẫu | So với đơn thật sau khi đã xác định |

**Go (có điều kiện giả định):** G1+G2 cho Rule; thêm G3+G4 mới bật AI trong pilot framing.  
**Not Yet (mặc định lab không interview):** giữ framing, không claim pain đã chứng minh.  
**No-Go AI / tắt AI:** G3 sai (lookup &lt;1–2’) → quay về chỉ Rule.  
**No-Go cả bài:** G2 sai nặng (không có list đâu cả).

---

## 6. Cạnh tranh

| Họ | Họ giải | Mình |
|---|---|---|
| Camsight / Ship Xanh | Video khi **còn mã** | Không build cam |
| WMS Return Check | List + scan item (cần WMS) | Nhái hành vi tick trên Sheets/OMS nhẹ |
| **Ngách** | Rule tick + **AI chỉ khi tem fail** (HITL) | Không SaaS “chỉ cứu tem” |

---

## 7. Việc nhóm làm tiếp

1. Mang idea này vào CP5–CP6: quy trình trước/sau + PS v0/v1 + eval AI.  
2. Không bịa Interview Snapshot; ghi rõ *giả định / chưa đo*.  
3. Nếu sau này có người kho: kiểm G1–G3 trước — sai G3 thì **tắt AI** trong báo cáo.

---

## 8. Pitch 20 giây

> “Outcome: hết restock mù — bắt buộc tick list xuất tại bàn (Rule). AI không thay SOP: chỉ **gợi ý 2–3 đơn khi tem fail**, người chọn rồi mới tick. Không interview được thì mọi số là giả định → **Not Yet** trên Value; tắt AI nếu lookup tay đã đủ nhanh.”
