# Idea đã chốt — mang đi nhóm

> Bản chốt đề xuất (cá nhân → pitch CP3). Nhóm có thể sửa sau phỏng vấn CP4; mọi số là **ước lượng / chưa đo**.  
> Không pitch gọi vốn. Không build app/AI trong lab.

---

## 1. Idea (1 câu)

**Trạm khui hoàn kho TMĐT vừa:** bắt buộc **hiện list xuất gốc + tick đủ/thiếu/tráo tại bàn** trước khi cộng tồn — làm bằng **Rule/SOP + 1 view trên data kho đã có** (Sheets/OMS đang dùng), không làm SaaS “cứu tem rách”, không đua camera-theo-mã.

---

## 2. Problem (Job Story)

**Khi** đang khui hàng hoàn (đặc biệt đơn nhiều món / biến thể gần giống),  
**tôi muốn** đối chiếu đúng list xuất gốc ngay tại bàn và tick đủ–thiếu–tráo,  
**để** không cộng tồn mù và không sót hàng / nhận tráo trước khi cất kệ.

| | |
|---|---|
| **Actor** | NV bàn khui kho fulfillment / shop tự kho **vừa** (~50–300 kiện hoàn/ngày, giả định); công cụ: quét + Sheets hoặc OMS nhẹ + cam góc |
| **Không phải actor** | Kho enterprise đã WMS full; forwarder; shop nails; “mọi seller sàn” |
| **Bottleneck** | Bước **khui → đối chiếu list → ghi nhận** (trước cộng tồn) |
| **Triệu chứng dễ nhầm** | “Chậm vì mất tem” — đó là **nhánh phụ**; core = thiếu / không dùng list tick |
| **Stakeholder** | Dùng: NV khui · Duyệt: trưởng ca · Chịu tiền: chủ shop / chủ kho |

---

## 3. Core value & giả định chết người

**Core value (giữ 1):** *Đối chiếu đúng trước khi restock* (đủ / thiếu / tráo), không phải “có AI” hay “có app”.

| # | Giả định chết người | Nếu sai thì… |
|---|---|---|
| 1 | Ở kho target, NV **thường không** soi list từng dòng khi khui multi-SKU (hoặc list không hiện tại bàn) | Đổi ngách |
| 2 | List xuất gốc **đã nằm** ở Sheets/OMS mở được — không cần nhóm build đồng bộ Shopee/TikTok ngày 1 | Not Yet / thu hẹp chỉ SOP giấy |
| 3 | Sót/tráo hoặc phút dư đối chiếu đủ đau để trưởng ca chịu thử SOP 1–2 ca | No-Go sản phẩm; chỉ ghi nhận quan sát |

**Nhánh phụ (không phải lý do chốt):** kiện mất/rách tem. Chỉ mở rộng path lookup nếu CP4 đo được tần suất + workaround thật sự tắc.

---

## 4. Giải pháp chốt (mức tối thiểu đủ dùng)

```text
Quét / mở đơn
  → Hiện list xuất gốc (1 màn / 1 tab cố định tại bàn)
  → NV tick: đủ | thiếu | tráo | (ghi chú)
  → Mới được cộng tồn / chuyển rổ

Tem quét fail (nhánh sau)
  → Lookup tối thiểu (SĐT / mã phụ / ảnh) + NGƯỜI chọn 1 đơn
  → Rồi quay lại list + tick
  → Máy không tự chốt đơn, không tự sửa tồn
```

| Mức | Làm gì trong lab |
|---|---|
| **No AI** | Đủ cho MVP |
| **Rule** | Đơn ≥N SKU bắt buộc tick; cấm cộng tồn khi chưa tick; tem phụ lúc xuất (nếu kho chịu) |
| **Workflow** | 1 view list + checkbox + log ca (Sheets hoặc màn OMS sẵn) |
| **Agent** | **Không chọn** |
| **Không làm** | Camsight/VietCam clone · WMS full · Pack Station all-in-one · nhận diện ảnh đoán đơn |

**Vì sao không đơn giản hơn nữa?** Chỉ “nhắc miệng soi list” không tạo hành vi đo được.  
**Vì sao không phức tạp hơn?** Micro-SaaS đa sàn chết ở tích hợp + WTP; camera-theo-mã thị trường đã đỏ.

---

## 5. Metric & ngưỡng quyết định (lab)

| Metric hành vi | Baseline | Target đề xuất | Cách đo |
|---|---|---|---|
| % kiện multi-SKU được tick đủ dòng trước restock | chưa đo | tăng rõ sau SOP (vd ≥80% mẫu 20 kiện) | Quan sát / checklist 1 ca |
| Phút đối chiếu / kiện nhiều món | ước 2–4' (chưa đo) | giảm về ≤1' hoặc ↓ ≥50% | Log mẫu 10–20 kiện |
| Số vụ sót/tráo hoặc lệch tồn gắn khâu hoàn / tháng | hỏi kho | hướng giảm (ngưỡng sau khi có số) | Hỏi trưởng ca + sổ khiếu nại |

**Go:** giả định 1+2 đứng sau 2–3 interview/quan sát + kho chịu chạy SOP thử.  
**Not Yet:** pain có nhưng list đã sẵn trên OMS và NV đã tick / lookup &lt;1–2'.  
**No-Go:** không tiếp cận được actor hoặc data list không tồn tại mà không ai chịu xuất file.

---

## 6. Cạnh tranh (góc đứng)

| Họ | Họ giải | Mình không đua |
|---|---|---|
| Camsight / Ship Xanh / VietCam | Quét được mã → video theo đơn | Không build cam |
| Pancake / Sapo / KiotViet / WMS | OMS/WMS rộng; lookup khi còn mã | Không thay OMS |
| **Ngách mình** | **Hành vi tick list tại bàn** trên kho Sheets/OMS nhẹ — Rule/Workflow, HITL | Feature vận hành đo được, không story “startup mất tem” |

---

## 7. Việc nhóm làm tiếp (theo thứ tự)

1. **CP3:** Hội tụ quanh idea này (outcome E + MVP B); không pitch 3 pain rời hay “tool AI kho”.  
2. **CP4:** Hỏi 2–3 người — (a) multi-SKU có soi list không? (b) data list ở đâu? (c) lệch/sót gần nhất? (d) chịu thử checklist 1 ca không?  
3. Có tín hiệu → viết Problem Statement v0 + quy trình trước/sau; quyết định Go / Not Yet / No-Go.  
4. Ghi log nếu đổi idea (vì sao).

---

## 8. Pitch 20 giây

> “Ở bàn khui hoàn kho vừa, pain không phải thiếu AI hay thiếu camera — mà là **cộng tồn trước khi tick đủ list xuất gốc**. Mình chốt outcome: hết restock mù / sót–tráo. MVP lab: Rule + 1 màn list trên data kho đã có, đo % tick và phút/kiện. Mất tem chỉ là nhánh sau nếu phỏng vấn thấy thật sự tắc.”
