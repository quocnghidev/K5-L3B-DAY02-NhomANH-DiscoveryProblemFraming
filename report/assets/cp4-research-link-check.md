# CP4 — Biên bản mở link research

Ngày kiểm: **2026-11-09**. Không thêm số liệu nếu trang không nói đúng điều đó. Không dùng số của thị trường Mỹ làm bằng chứng cho kho Sheets Việt Nam.

| # | Nguồn | URL | HTTP | Đọc nội dung ngày 2026-11-09 | Khớp claim trong §3.3 |
|---:|---|---|---|---|---|
| 1 | Camsight — quét đơn hoàn | https://camzone.vn/camsight-cap-nhat-tinh-nang-quet-don-hoan-cach-thuc-hien-va-quan-ly-du-lieu | 200 | Trang trả về (~86 KB). Claim trong bảng nhóm giữ từ lần mở trước của nhóm; lượt này không thêm chi tiết mới ngoài việc link còn sống | Giữ: quét mã → video theo đơn hoàn; phụ thuộc đưa được mã vào khung; không phải màn tick từng SKU trước cộng tồn |
| 2 | Ship Xanh — quay đóng/khui | https://shipxanh.com/tdcpt_case_studies/quay-video-dong-goi-khui-hang/ | 200 | Trang trả về (~480 KB). Không thêm claim mới trong lượt này | Giữ: detect mã → clip đóng/khui; bằng chứng video, không thay bước đối chiếu list món |
| 3 | GoWarehouse Return Check | https://docs.gowarehouse.ai/en/operator/return_orders/verification | 200 | Trang docs trả body ngắn (app render). Không trích thêm bước ngoài bảng §3.3 | Giữ: pattern scan → load list expected → check từng món → mới inbound; cần WMS sẵn |
| 4 | ChannelDock — WMS returns | https://channeldock.com/en/blogs/ecommerce-wms-returns-processing/ | 200 | Đọc lại toàn văn | Khớp: scan RMA/nhãn → khớp đơn và SKU → grade → quarantine → **không cộng tồn chỉ vì kiện đã về**; KPI trusted return-to-resale. Bài có ước lượng NRF 2025 (19,3% đơn online Mỹ bị hoàn). **Không dùng con số này** cho G1/G3 |
| 5 | ResReturn — receiving workflow | https://resreturn.com/blog/returns-receiving-workflow | 200 | Đọc lại toàn văn | Khớp: intake scan → unpack/identify → inspect/grade → disposition và post hệ thống. Kiện không khớp máy là **exception lane**, không phải toàn bộ quy trình. Các mốc 24h/48h trong bài là benchmark blog, không phải baseline kho của nhóm |

**Tín hiệu phản bác giữ lại:** cả năm nguồn hoặc giả định quét được mã, hoặc cần WMS/OMS có list sẵn. Không nguồn nào chứng minh kho Sheets vừa ở Việt Nam đang bỏ tick từng dòng.

**Không có file** `report/individual/COMPETITOR_RESEARCH.md`. Bảng §3.3 cộng file này là research của nhóm.
