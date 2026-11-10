# Báo cáo cá nhân — 2A202603947_LaQuocNghi

> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).

## 1. Thông tin học viên

- Họ tên: Lã Quốc Nghị
- MSSV: 2A202603947
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: Nhóm ANH
- Link repo nhóm: https://github.com/quocnghidev/K5-L3B-DAY02-NhomANH-DiscoveryProblemFraming

---

## 2. Scan problem (CP1)

Lăng kính: **Lặp lại** · **Tốn thời gian** · **Cần đọc, tổng hợp nhiều thông tin** · **Pain từ người khác**.

Bối cảnh: sinh viên đi làm bằng xe bus. App đã hiện giờ xe tới. Pain không còn là “không biết xe tới lúc nào”.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---:|---|---|---|---|
| 1 | Lặp lại | Khi app báo xe còn vài phút nhưng tới sớm/muộn hơn nhiều, tôi muốn biết trên tuyến/giờ của mình ETA thường lệch bao nhiêu, để quyết định ra trạm lúc nào cho khỏi lỡ hoặc đứng quá lâu | Người đi làm trên xe bus | Bị lỡ hoặc đợi vì tin tuyệt đối vào ETA trên app. Chưa đếm số chuyến/tuần |
| 2 | Tốn thời gian | Khi giờ cao điểm phía trước ùn tắc bất ngờ, tôi muốn biết điểm tới còn bị đội lên thêm bao lâu so với ETA đang hiện, để còn biết chuyển sang phương tiện khác hoặc đi bộ | Người đi làm trên xe bus | Các buổi check-in bị muộn so với kế hoạch. Chưa bấm số phút đội |
| 3 | Pain từ người khác | Khi tôi bị muộn vì đang trên xe, tôi muốn biết được chính xác ETA để báo cho team không phải gọi điện lặp đi lặp lại để hỏi | Người đi làm trên xe bus; team đang chờ | Số lần gọi điện hỏi; số lần báo sai thời gian đến. Chưa ghi log cuộc gọi |
| 4 | Lặp lại | Khi xe tới gần đúng giờ app báo nhưng đã chật ních, tôi muốn biết chuyến đó còn lên được không, để quyết định lên ngay hay đợi chuyến sau mà vẫn kịp giờ làm | Người đi làm trên xe bus, giờ cao điểm | Tự nghĩ từ đầu: xe chật ních người. Chưa chấm mức chật từng chuyến |
| 5 | Cần đọc, tổng hợp nhiều thông tin | Khi đã có ETA trên app nhưng vẫn phải khớp giờ check-in, tôi muốn ghép giờ xe tới, mức đội vì tắc và giờ phải có mặt thành một mốc ra khỏi nhà, để khỏi mở nhiều màn hình rồi vẫn đoán | Người đi làm trên xe bus, vừa học vừa làm | Mỗi lần đi phải tự đối ETA với giờ ca. *Ý AI gợi ý, giữ vì đúng việc mình đang làm.* Chưa đếm số nguồn mở |

**Nếu có dùng AI để gợi ý thêm:** ý nào AI gợi ý mà bạn giữ lại, ý nào bỏ và vì sao.

- **Bỏ:** “Không biết xe tới lúc nào.” App đang dùng đã hiện ETA, pain này yếu.
- **Bỏ:** các gợi ý lệch việc đi làm bằng bus (học tập, onboarding, chi tiêu). Không phải pain mình đang gặp trên chuyến đi.
- **Giữ và tự viết lại:** #1, #2, #3. #1 dịch từ pain “xe tới sai giờ” sau khi biết app đã có ETA. #2 là pain tắc đường mình nghĩ từ đầu. #3 là team gọi hỏi khi mình báo muộn.
- **Giữ, ghi rõ nguồn:** #4 xe chật là ý tự nghĩ. #5 là AI gợi ý, giữ vì mình thật sự phải tự ghép ETA với giờ check-in.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | ETA app không đủ tin để ra trạm, đổi xe và báo team một lần | Gộp được #1 #2 #3: cùng một lúc quyết định, có người khác bị ảnh hưởng | Chưa bấm \|ETA − giờ tới thật\| trên tuyến của mình |
| 2 | Xe đúng giờ app nhưng chật, không biết nên lên hay đợi chuyến sau | Pain tự nghĩ, lặp lại giờ cao điểm, tách được khỏi “ETA sai” | Chưa biết app có dữ liệu chỗ trống hay không |
| 3 | Phải tự ghép ETA, tắc và giờ check-in trước khi ra khỏi nhà | Đúng việc mỗi buổi đi làm; thấy bước tổng hợp | Ý từ AI; có thể chỉ là hệ quả của card #1 |

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi đang đi làm bằng bus và app đã hiện ETA nhưng giờ tới hay lệch, nhất là lúc ùn tắc, tôi muốn biết mức đội còn lại tới chỗ làm, để ra trạm hoặc đổi phương tiện kịp check-in và chỉ báo team một lần |
| Actor | Người đi làm bằng xe bus, đã dùng app ETA |
| Thời điểm / bối cảnh | Giờ cao điểm, trước giờ check-in: lúc xem app trước khi ra trạm, hoặc đang trên xe khi đoạn phía trước tắc |
| Quy trình hiện tại (3–7 bước) | Xem ETA → ra trạm / lên xe → theo dõi ETA trên đường → tự đoán còn kịp không, có đổi xe hoặc đi bộ không → nhắn hoặc gọi team → team gọi hỏi lại nếu giờ không khớp → check-in |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước tự đoán “còn kịp / có đổi phương tiện không” khi ETA đang hiện nhưng không phản ánh mức đội. Ước lượng cảm tính, **chưa bấm giờ** (dự kiến vài phút mỗi lần ETA nhảy, có thể lặp trong một chuyến) |
| Impact (nếu không giải thì sao) | Check-in muộn so với kế hoạch; đứng đợi hoặc lỡ chuyến vì tin ETA; team gọi hỏi lặp và nhận giờ tới sai |
| Success metric (baseline → target) | Baseline chưa đo. Dấu hiệu đã có: buổi check-in muộn, lần lỡ/đợi vì tin ETA, số cuộc gọi hỏi lại. Target khi đo được: giảm số buổi check-in muộn/tuần và số cuộc gọi hỏi lại trên mỗi chuyến muộn |
| Phương án không dùng AI | Ra sớm một khoảng cố định theo tuyến và khung giờ; quy tắc viết sẵn “khi nào xuống đi bộ / đổi xe”; một tin nhắn mẫu báo muộn kèm khung giờ; tự ghi 10 chuyến để biết độ lệch ETA của tuyến mình |
| Giả thuyết về AI (nếu có) | Có thể hỗ trợ ước lượng mức đội so với ETA đang hiện. Người vẫn tự quyết đổi xe và tự gửi tin cho team. Chưa kiểm chứng, không phải bài nhóm đã chốt |
| Cảm nhận nhanh | Rule hoặc Workflow / Chưa biết. Không nhắm sửa ETA của cả thành phố |

Quy trình nháp hiện tại:

```text
HIỆN TẠI — ước lượng, chưa bấm giờ

[1 Xem ETA trên app] → [2 Ra trạm / lên xe]
→ [3 Theo dõi ETA trên đường]
→ [4 Tự đoán còn kịp? Đổi xe / đi bộ?]  ← BOTTLENECK
→ [5 Báo team]
→ [6 Team gọi hỏi lại nếu giờ lệch]
→ [7 Check-in: đúng giờ hoặc muộn]
```

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi xe tới gần đúng giờ app báo nhưng đã chật ních, tôi muốn biết chuyến đó còn lên được không, để lên ngay hoặc đợi chuyến sau mà vẫn kịp giờ làm |
| Actor | Người đi làm trên xe bus, giờ cao điểm |
| Thời điểm / bối cảnh | Đứng ở trạm, xe vừa vào, nhìn thấy xe đã đầy |
| Quy trình hiện tại (3–7 bước) | Xem ETA → ra trạm → xe tới → nhìn độ chật bằng mắt → quyết định lên hay đợi → nếu đợi thì xem ETA chuyến sau → đi làm |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước nhìn bằng mắt rồi quyết định lên hay đợi. Không có số chỗ trống. **Chưa bấm giờ**; đợi chuyến sau dễ làm trễ check-in |
| Impact (nếu không giải thì sao) | Lên xe rồi đứng chen cả chuyến, hoặc bỏ chuyến và muộn giờ làm |
| Success metric (baseline → target) | Baseline chưa đo (mức chật và số chuyến phải bỏ). Target: giảm số buổi muộn vì phải đợi chuyến sau |
| Phương án không dùng AI | Ra sớm hơn một chuyến ở khung giờ hay đầy; quy tắc “đầy quá mức này thì đợi”; hỏi người đứng trạm |
| Giả thuyết về AI (nếu có) | Chưa cần. App ETA không nói độ chật; nếu không có dữ liệu chỗ trống thì AI cũng đoán mò |
| Cảm nhận nhanh | No AI / Chưa biết |

Quy trình nháp hiện tại:

```text
HIỆN TẠI — ước lượng, chưa bấm giờ

[1 Xem ETA] → [2 Ra trạm]
→ [3 Xe tới, nhìn độ chật bằng mắt]  ← BOTTLENECK
→ [4 Lên chen hoặc đợi chuyến sau]
→ [5 Check-in]
```

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi đã có ETA trên app nhưng phải khớp giờ check-in, tôi muốn ghép giờ xe tới, mức đội vì tắc và giờ phải có mặt thành một mốc ra khỏi nhà, để khỏi xem vài chỗ rồi vẫn đoán |
| Actor | Người đi làm bằng bus, vừa học vừa làm |
| Thời điểm / bối cảnh | Trước khi ra khỏi nhà, sáng hoặc trước ca |
| Quy trình hiện tại (3–7 bước) | Mở app xem ETA → nhớ giờ check-in → tự cộng thêm phần tắc → chốt giờ ra cửa → đi |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước tự cộng ETA với tắc và giờ ca. Thông tin không nằm trên một màn hình. **Chưa bấm giờ** |
| Impact (nếu không giải thì sao) | Ra cửa quá sớm hoặc vẫn muộn dù đã xem app |
| Success metric (baseline → target) | Baseline chưa đo (số phút để chốt giờ đi; số buổi vẫn trễ sau khi đã chốt). Target: chốt giờ ra cửa nhanh hơn và ít buổi trễ hơn |
| Phương án không dùng AI | Một mốc cố định “ra trước check-in bao lâu” theo từng tuyến, viết ra giấy, không tính lại mỗi ngày |
| Giả thuyết về AI (nếu có) | Có thể ghép giúp các mảnh giờ. Rule “ra sớm N phút” có thể đủ nếu N đã đo trên tuyến của mình |
| Cảm nhận nhanh | Rule / Chưa biết. *Card này từ gợi ý AI* |

Quy trình nháp hiện tại:

```text
HIỆN TẠI — ước lượng, chưa bấm giờ

[1 Mở app ETA] → [2 Nhớ giờ check-in]
→ [3 Tự cộng phần tắc]  ← BOTTLENECK
→ [4 Chốt giờ ra khỏi nhà]
→ [5 Đi làm]
```

### Card muốn pitch nhất

- Card số: **#1**
- Vì sao: Ba pain ETA lệch, tắc đội giờ tới, và team gọi hỏi là một việc: ETA trên app không đủ để quyết định và báo một lần.
- Câu hỏi muốn nhóm phản biện: Bottleneck là ETA sai, hay là mình chưa có quy tắc ra sớm / đổi xe nên AI không cần?

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| App đã hiện giờ xe tới, nên pain “không biết xe bao giờ tới” yếu | Đồng ý | Đổi job story sang độ lệch ETA và mức đội so với ETA đang hiện |
| Dễ trượt thành “làm lại ETA cho cả thành phố”, ngoài sức một buổi lab | Đồng ý | Giữ actor là người đi làm trên một tuyến; phương án không AI là buffer và quy tắc đổi xe |
| Chưa có số phút thật, metric dễ bịa | Đồng ý | Baseline để “chưa đo”; chỉ ghi dấu hiệu đã xảy ra: check-in muộn, lỡ/đợi, bị gọi hỏi |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

> Vai của mình trên `group_report.md`: **Evidence (CP4)**, mục 3, cộng các file `report/assets/cp4-*`. Không viết mục 4–7.

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Pitch card bus: ETA app không đủ tin để ra trạm, đổi xe và báo team | Nhóm không chọn. App đã có ETA; pain khó quan sát trong lab hơn pain kho. Mình giữ card trong file cá nhân |
| Phản biện bài của bạn khác | Với candidate **khui hàng hoàn**, mình hỏi ba câu: (1) Nếu hàng giống nhau, cùng một mẫu mã thì sao? (2) Bình thường người ta đang kiểm tra bằng cơm như thế nào? (3) Dùng AI cho case này có thực sự cải thiện được gì không? | (1) Hàng cùng mẫu / biến thể gần giống là lý do đối chiếu bằng mắt dễ sót hoặc nhận tráo — bài nhóm chuyển sang tick từng dòng list xuất gốc, không nhận diện ảnh. (2) Cách đang làm, theo quy trình nhóm: đếm hộp, ghi chú giấy hoặc Zalo, admin cộng tồn cuối ca; tem fail thì dò SĐT / hỏi Zalo. (3) AI không cải thiện bước tick. AI chỉ gợi ý tối đa 3 đơn khi tem quét fail và Rule lọc vẫn còn hơn 3 đơn. Rule lọc đã đủ thì tắt AI |
| Nhận phản biện | Câu mình nhận về card bus: app đã có ETA; có thể chỉ cần ra sớm và quy tắc đổi xe | Mình thu hẹp pain sang “ETA lệch / không đủ để quyết định”, bỏ hướng sửa ETA toàn hệ thống. Nhóm chốt candidate kho, mình không giữ bus làm bài chung |
| Gom cluster / cây OST | Nghe pitch kho (tick list, tem phụ / SOP, tem fail, bàn giao bao) rồi đọc cây OST trong mục 2 | Thấy bus không cùng pattern với bàn khui. OST của nhóm chỉ giữ pain đối chiếu trước restock; gạch camera và app AI nhận diện kiện |
| Chọn candidate problem | Đồng ý bỏ card bus, chọn tick list trước khi cộng tồn | Candidate chung: Rule tick luôn bật; AI chỉ một nhánh tem fail; quyết định Not Yet |
| Kiểm chứng / research | Phụ trách mục 3. Gắn G1–G5 vào assumption map. Soạn câu hỏi Mom Test. Mở lại 5 link (Camsight, Ship Xanh, GoWarehouse, ChannelDock, ResReturn) ngày 2026-11-09. Đọc lại ChannelDock và ResReturn | Không bịa phỏng vấn: 0 người, snapshot để trống. Tín hiệu phản bác: tool sẵn giả định quét được mã hoặc cần WMS, không chứng minh kho Sheets Việt Nam đang bỏ tick. Không dùng số NRF 19,3% (thị trường Mỹ) cho G1/G3. Research đẩy nhóm khỏi “cứu tem bằng camera” |
| Quy trình nhóm | Đọc mục 4 do bạn framing viết, không vẽ lại | Dùng quy trình đó để kiểm câu “làm bằng cơm”: bottleneck là đối chiếu bằng mắt và dò đơn khi tem fail |
| Problem Statement | Đọc v0 và v1, không viết hộ | Thấy metric có baseline “chưa đo / giả định”, khớp việc lab chưa hỏi người kho |
| Mức can thiệp AI | Đối chiếu câu hỏi của mình với mục 6 | Mức chọn là Workflow: Rule nền luôn bật; AI một bước. Trả lời được câu “AI cải thiện gì”: không cải thiện tick; chỉ rút danh sách đơn khi tín hiệu tem fail còn mơ hồ |
| Quyết định | Khớp mục 8 với bằng chứng mục 3 | Not Yet vì Value (G1, G3) vẫn bằng chứng = 1. Ngưỡng tắt AI nếu lookup tem fail thường dưới 2 phút hoặc Rule lọc đã ra ≤3 đơn ở ≥80% ca fail |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Nhờ gợi ý thêm pain đi bus theo 4 lăng kính, rồi nhờ 5 pain sau khi biết app đã có ETA | Tách được “xe chật” và “ghép nhiều nguồn” khỏi “không biết giờ xe tới” | Gợi ý lúc đầu vẫn có pain “không biết xe tới lúc nào”, trong khi app mình dùng đã hiện ETA | Bỏ pain đó. Tự viết lại #1 #2 #3. Ghi #5 là ý AI |
| CP2 Problem Card | Nhờ gộp 3 scan thành 1 card và đóng vai PM hoài nghi | Chỉ ra card dễ phình thành “sửa ETA cả thành phố” và chưa có số đo | Gắn phút ước lượng như thể đã bấm giờ | Giữ nhãn “chưa bấm giờ”. Phương án không AI = ra sớm + quy tắc đổi xe |
| CP3 Pitch + phản biện | Không dùng AI để nghĩ câu hỏi | — | — | Ba câu hỏi kho hàng là của mình: hàng giống nhau, kiểm bằng cơm, AI có cải thiện gì |
| CP4 Research | Nhờ đối chiếu link và sắp assumption | Nhắc pattern WMS là scan rồi mới restock; chỉ ra số NRF không dùng được cho kho Việt Nam | Dễ bịa snapshot cho đủ bài nếu không chặn | Giữ 0 interview. Viết câu hỏi Mom Test để hỏi sau, không điền câu trả lời giả |
| CP5 Quy trình | Không viết mục này | — | — | Đọc bản bạn framing |
| CP5–6 Problem Statement | Không viết hộ | — | — | Kiểm baseline vẫn là giả định |
| CP6 Mức can thiệp / quyết định | Dùng mục 6 để trả lời câu phản biện của mình | Bảng 4 mức chỉ rõ Rule đủ cho bước tick | — | Giữ Not Yet. AI chỉ khi Rule lọc còn hơn 3 đơn |

---

## 6. Reflection (CP7)

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Card của mình là ETA bus. Hai bạn kia là khui hàng hoàn (tem rách, kiểm bằng tay) và onboarding nhân viên mới. Nghe xong mình thấy cùng một lớp có pain không ghép được thành một bài. Bus thì app đã hiện giờ tới, pain còn lại là độ lệch và quyết định của một người. Kho thì việc lặp mỗi ca, có bước đếm hàng và cộng tồn, sai một dòng là lệch kho. Onboarding là quy trình giấy tờ của công ty, mình không quan sát được trong buổi lab. Mình học được là pitch hay chưa đủ: phải có actor, bước nghẽn, và chỗ đứng nhìn thấy việc đó.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Có. Lúc đầu candidate kho nghiêng về AI OCR cho tem rách, candidate của mình nghiêng về “làm ETA đúng hơn”. Cả hai đều nhảy vào công cụ. Với bus, mình tự thấy app đã có ETA nên giải pháp “thêm một app giờ xe” không trúng pain. Với kho, sau research Camsight và Ship Xanh, nhóm thấy video theo mã đã có người làm, và tool đó cần quét được mã. Nhóm gạch camera và app nhận diện kiện khỏi cây OST, kéo bài về việc đối chiếu list trước khi cộng tồn. AI chỉ còn một chỗ, sau Rule, và có cửa tắt.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Có. Mình từng nghĩ lab là buổi đưa giải pháp, và hỏi AI có áp được vào ETA bus không. Phản biện lại: app đã có ETA; bottleneck có thể chỉ là mình không có quy tắc ra sớm hoặc đổi xe; sửa ETA cả thành phố không vừa một buổi. Mình đổi card từ “biết xe tới lúc nào” sang “ETA đang hiện lệch bao nhiêu nên ra trạm và báo team thế nào”. Đổi ý thứ hai là bỏ card này khỏi bài chung. Ba câu mình hỏi bạn kho (hàng cùng mẫu thì sao, đang kiểm bằng cơm ra sao, AI cải thiện được gì) làm mình thấy bài kho trả lời được từng câu, còn bài bus thì phương án không AI đã khá mạnh.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Chưa hỏi được người trong kho, nên mình không có câu nói nguyên văn để bất ngờ. Bất ngờ nằm ở research. Mình tưởng khui hoàn là khoảng trống chưa ai làm. Mở link thì Camsight và Ship Xanh đã quay video theo mã, GoWarehouse và ChannelDock đã có kiểu quét rồi mới cho hàng vào tồn. ChannelDock viết thẳng: không cộng tồn chỉ vì kiện đã về. ResReturn coi kiện không khớp mã là lối ngoại lệ, không phải cả sản phẩm. Số 19,3% đơn online bị hoàn trên bài ChannelDock là ước lượng thị trường Mỹ, mình không mang vào làm bằng chứng cho kho Sheets ở Việt Nam. Vì không có interview, Value vẫn là giả định và quyết định là Not Yet.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Khó nhất là viết metric khi chưa đứng ở bàn khui và cũng chưa bấm giờ trên xe bus của mình. “Nhanh hơn” hay “đỡ sót” không chấm được. Nhóm phải ghi baseline là ước lượng hoặc giả định, rồi mới đặt target và cách đo (log tick, bấm giờ một mẫu kiện, biên bản kiểm kê). Mình thấy nếu bịa số phút cho có baseline thì cả bài hỏng, nên mục của mình để trống snapshot và để dấu hiệu định tính ở card bus.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Mình sẽ đếm ít nhất 10 chuyến bus của chính mình trước khi pitch, để card có phút lệch thật, không chỉ “check-in bị muộn”. Với nhóm, mình sẽ hỏi sớm hơn đúng ba câu đã hỏi: hàng cùng một mẫu thì mắt người phân biệt bằng gì; ca hôm qua họ tick ở đâu hay chỉ đếm hộp; và nếu Rule lọc theo shop cộng 4 số điện thoại đã ra một đến ba đơn thì AI còn giảm được phút nào. Mình cũng sẽ đòi một dòng trong sơ đồ mục 4 cho khớp mục 6: AI không chạy trên mọi kiện tem fail, chỉ khi Rule lọc còn hơn 3 đơn.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

Người khui hàng hoàn ở kho vừa đang đối chiếu hàng với đơn bằng mắt, nhất là đơn nhiều món, rồi vẫn cộng tồn; tem không quét được thì dò đơn rất lâu hoặc bỏ vào góc không ai theo dõi. Quy trình muốn tới là: quét được thì hiện list và tick từng dòng đủ / thiếu / tráo trước khi cộng tồn; quét fail thì lọc đơn đang hoàn, nếu còn quá nhiều đơn thì AI đưa tối đa 3 gợi ý. Đo bằng tỉ lệ kiện có tick đủ dòng, thời gian mỗi kiện không được chậm hơn trên nhánh tem đúng, độ lệch khi kiểm kê, và đơn đúng có nằm trong top 3 hay không. AI không được tự chọn đơn, không sửa tồn, không gửi khiếu nại; người khui chọn đơn và tick, trưởng ca duyệt dòng thiếu hoặc tráo. Mức chọn là Workflow vì bước tick là Rule, chỉ một bước định danh khi tín hiệu mơ hồ cần AI. Quyết định Not Yet vì chưa có người kho xác nhận họ thật sự không tick và tem fail thật sự tắc; nếu điều đó sai thì tắt AI và giữ Rule.

---

## 7. Tài liệu tham khảo

- Ba job story ETA bus ở mục 2 (pain của mình).
- `report/team/group_report.md` mục 3 (phần Evidence mình phụ trách), mục 4–8 (bản nhóm, mình đọc và phản biện).
- `report/assets/cp4-interview-guide.md`, `cp4-interview-snapshot-1.md`, `cp4-research-link-check.md`.
- Link research trong mục 3.3 của báo cáo nhóm: Camsight, Ship Xanh, GoWarehouse, ChannelDock, ResReturn.
