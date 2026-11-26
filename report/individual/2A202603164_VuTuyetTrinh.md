# Báo cáo Day 13 — Vũ Tuyết Trinh, 2A202603164

> Xoá mọi dấu TODO và dòng gợi ý (dòng bắt đầu bằng `>`). Mỗi con số lấy từ **bảng A** hoặc **phiếu tự kiểm** trong `submission/`, kèm đơn vị (m, °). Ảnh để trong `report/individual/images/` (nộp LMS trong file zip, không commit); trong báo cáo chỉ ghi **tên file ảnh**. Báo cáo này nằm trên repo public: không chép biển số, chữ trên biển hiệu hay biển chỉ đường, tên đường, địa danh; nhắc tới bạn khác thì ghi MSSV, không ghi họ tên. Cả báo cáo ~2 trang.

## 1. Kết luận trước
- Mã số: 2A202603164 · Task: `D13-2A202603164`
- 10 frame: s01f07, s01f27, s02f03, s02f20, s03f01, s03f52, s04f09, s04f51, s05f08, s05f31
- Hệ điều hành: Windows 11 Pro · Trình duyệt: Microsoft Edge · CVAT: Server 2.83.0
- MSSV bạn ngồi cạnh: 2A202603229

Tổng 75 cuboid. Ít nhất là 5 frame s03f01, s03f52, s04f51, s05f08, s05f31 (mỗi frame 6 cuboid), vì vật ở xa, thưa điểm. `selfcheck` cờ 3/75 cuboid, cả ba là Car có đáy thấp hơn mặt đường (chìm?): s01f27 #10 (0,49 m), s03f52 #6 (0,73 m), s04f51 #6 (0,32 m). Tôi tin nhất phần hướng (yaw); yếu nhất là vật xa.

Cách dùng CVAT:
- Đổi góc nhìn: kéo chuột trái để xoay, kéo chuột phải để dời, cuộn để phóng to; xoay cảnh cho tới khi nhìn từ trên xuống.
- Vẽ và chỉnh cuboid: chọn công cụ cuboid, chọn label, bấm Shape, nháy vào đám điểm; nháy đúp để chọn, rồi kéo cạnh và xoay trong các khung Top/Side/Front.
- Hướng và ảnh camera: bật Cuboid orientation trong Settings; xem ảnh camera đi kèm frame ngay trong CVAT, kết hợp chạy `preview`.

## 2. Đọc frame (Bước 2)
Hai frame đọc kỹ. Ảnh: `t1-<frame>-3d`, `t1-<frame>-top` (ảnh nhìn từ trên xuống, có đánh dấu phía trước, +x, +y).

| Frame | Phía trước xe ở cạnh nào của ảnh nhìn từ trên xuống; +x, +y chỉ về đâu | Mặt đường (phẳng/dốc; thấp hơn LiDAR ~ m) | Vật xa nhất đọc được (~ m) | Loại vật thấy | Vật phía sau / hai bên | Cụm chưa đọc được |
|---|---|---|---|---|---|---|
| s01f07 | Trước: cạnh trên; +x: trái; +y: dưới (phía sau) | Phẳng; thấp hơn LiDAR ~1,6 m | Xe buýt/xe tải phía trước, ~30 m; góc không camera nào thấy: chéo phía sau | Xe con, xe buýt/xe tải, người đi bộ, xe máy/xe đạp có người | Phía sau: xe con; hai bên: cây/bụi cây, nhà | Không có |
| s01f27 | Trước: cạnh trên; +x: trái; +y: dưới (phía sau) | Phẳng; thấp hơn LiDAR ~1,6 m | Xe con, ~30 m | Xe con, xe buýt/xe tải | Phía sau và hai bên: xe con | Không có |

TODO(học viên): 3 điều **chỉ camera** cho biết và 3 điều **chỉ LiDAR** cho biết, lấy từ chính hai frame trên.

Tám frame lướt:

| Frame | Phía trước ở cạnh nào của ảnh nhìn từ trên xuống | Điều lạ (nếu có) |
|---|---|---|
| TODO(học viên) | | |

## 3. Ba cuboid có hướng dẫn (Bước 3)
Ảnh: `t2-a-car`, `t2-b-bus-truck`, `t2-c-ped-cyclist`.

| Vật | Frame, idx | Class | Mũi tên yaw đúng hướng? | Đáy chạm đường? | Đã kiểm Top/Side/Front + ảnh? | Kích thước trong bảng 4.3? |
|---|---|---|---|---|---|---|
| (a) xe con gần | TODO(học viên) | | | | | |
| (b) xe buýt hoặc xe tải | TODO(học viên) | | | | | |
| (c) người đi bộ hoặc xe hai bánh | TODO(học viên) | | | | | |

TODO(học viên): vòng hiệu chuẩn: cuboid của bạn lệch so với các bạn ở điểm nào, cả lớp chốt cách hiểu guideline nào? Và các vật bạn **bỏ qua vì không đủ cơ sở** (frame, vị trí, mô tả, loại nghi vấn như UNCERTAIN_CLASS / LOW_VISIBILITY), hoặc ghi "không có".

## 4. Bốn hiện tượng chất lượng (Bước 4)
Nguyên nhân ghi là **giả thuyết**. Frame mượn thì ghi rõ nguồn: task chung, hoặc MSSV của bạn cho mượn.

| Hiện tượng | Frame / tên ảnh / nguồn | Nguyên nhân (giả thuyết) | Thấy gì trên point cloud | Hệ quả khi gán (theo guideline) |
|---|---|---|---|---|
| 1. Bóng che | TODO(học viên) | | | |
| 2. Thưa ở xa | TODO(học viên) | | | |
| 3. Phản xạ thấp / ít điểm bất thường | TODO(học viên) | | | |
| 4. Điểm lạ | TODO(học viên) | | | |

## 5. Số từ cuboid của tôi (Bước 5)
Lấy từ `submission/D13-<MÃ SỐ>-bangA.csv`; số điểm lấy từ cột `points_in` của `-tukiem.csv`. Mặt đường khoảng −1,7 m: z đáy lệch hơn 0,3 m là lơ lửng hoặc chìm.

| Cuboid (frame, idx, class) | z | h | z đáy = z − h/2 | dist_m | r = √(x²+y²+z²) | yaw_deg | Nhận xét (lơ lửng / chìm / chạm đường) |
|---|---|---|---|---|---|---|---|
| TODO(học viên) | | | | | | | |
| TODO(học viên) | | | | | | | |
| TODO(học viên) | | | | | | | |

TODO(học viên): (a) cuboid **gần nhất** và **xa nhất**: `dist_m` và r của từng cái. (b) Kích thước l, w, h của một người đi bộ (hoặc xe hai bánh) và một xe con so với bảng 4.3: chiều nào ngoài khoảng, vì sao. (c) `yaw_deg` của một xe cùng chiều phía trước và một xe ngược chiều (nếu có): có gần 270° và 90° không.

Mật độ theo khoảng cách (4 cuboid ở các `dist_m` khác nhau):

| Cuboid (frame, idx, class) | dist_m | Số điểm (`points_in`) |
|---|---|---|
| TODO(học viên) | | |

TODO(học viên): một câu quy luật ("xa gấp … lần thì số điểm còn khoảng …") và so với đường cong ở slide bài giảng (xe con: khoảng 1968 điểm ở 0–10 m, 718 ở 10–20 m, 214 ở 20–30 m, 72 ở 30–40 m, 19 ở 60–80 m). Rồi phần tự kiểm: hai cuboid bạn **đã sửa** sau `preview` / `selfcheck` (frame, idx, sửa gì), và những cảnh báo bạn **giữ nguyên** kèm lý do.

TODO(học viên): đổi kiểm: MSSV người đã kiểm chéo với bạn, hai con số nào được đối chiếu với bảng A, khớp hay lệch (lệch thì đã sửa gì).

## 6. Ý nghĩa của nhãn, cách dùng AI và điều còn chưa chắc
(b) Dùng AI:
- Công cụ: Claude Code.
- Câu hỏi chính: cài môi trường Python, nâng cấp CVAT lên 2.83, chạy các lệnh của lab, đổi tên file báo cáo, hướng dẫn các bước làm lab; nhờ lưu, đổi tên ảnh chụp và vẽ chú thích hướng (Trước/+x/+y) lên 2 ảnh `-top` theo hướng tôi tự xác định.
- Dùng kết quả: làm theo các lệnh cài đặt; không dùng AI để vẽ cuboid, đọc bảng A hay viết nhận xét. Lưu ý: tôi đã lỡ dán 12 ảnh chụp màn hình CVAT vào Claude Code để nhờ lưu file, trái quy định không đưa ảnh chụp cho AI; AI không dùng ảnh để đọc cảnh, chọn hiện tượng hay điền số. Ở §1 và dòng s01f27 của §2, AI hỏi tôi bằng câu trắc nghiệm và câu hỏi ngắn, rồi chép câu trả lời của tôi vào file; số liệu do tôi tự đọc và gõ, câu chữ cách dùng CVAT ở §1 là đáp án AI soạn sẵn, tôi chọn cái đúng với cách tôi làm.

TODO(học viên): (a) hai câu, nói từ phía model sẽ học trên nhãn này: vì sao nhãn 3D đo bằng mét chứ không phải pixel; vì sao vật thưa điểm cần quy tắc riêng. (b) Dùng AI? Ghi 3 dòng: công cụ, câu hỏi chính, bạn dùng kết quả thế nào. Không dùng: ghi "không dùng". (c) Điều còn chưa chắc, lỗi phát hiện sau hạn (không chấm; viết bằng lời, không chép số từ phiếu hồ sơ lỗi).
