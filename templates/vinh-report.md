# Báo cáo cá nhân — Ngày 11
- Họ tên: Đinh Thành Vinh
- Mã học viên: 2A202603044
- Phiên bản CVAT (Help → About): [Điền phiên bản hiển thị trên CVAT của bạn, vd: v2.x.x]
- Guideline: Road v1.0    Lần nộp (`revision` trong manifest): 1
- Thời điểm export (ngày giờ trên CVAT): [Điền ngày giờ xuất file zip, vd: 2026-11-21 02:50]    Số lần nộp lại sau Rework: 0

## 1. Kiểm project

| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng | Đã đối chiếu JSON từ `road_lab.taxonomy`: `lane` (polyline), `road_curb` (polyline), `crosswalk` (polygon), `drivable` (polygon), `traffic_light` (rectangle), `traffic_sign` (rectangle). |
| Thuộc tính và giá trị | Đúng | Đầy đủ các thuộc tính (`position`, `style`, `color`, `kind`, `area_type`, `type`, `facing`, `group`, `edge_zone`) khớp 100% với đặc tả. |
| 4 tag ảnh | Đúng | Đủ 4 tag toàn ảnh: `camera`, `timeofday`, `weather`, `source`. |

Cách kết thúc polyline trên bản CVAT này: Bấm phím `N` (hoặc click chuột phải / bấm vào điểm neo cuối cùng) sau khi đặt xong điểm cuối.  
Cách đặt tag ảnh trên bản CVAT này: Chọn công cụ **Tag** (biểu tượng thẻ bài ở thanh công cụ bên trái) -> chọn tên nhãn trong danh sách thả xuống -> bấm nút **`+`** -> chỉnh giá trị thuộc tính `value` ở cột **Objects** bên phải.  

## 2. Số lượng đã gán

| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 21 | 15 | 4 | 26 | 11 | 11 |
| front-extra (đã làm 4 / 4) | 4 | 12 | 4 | 2 | 9 | 5 | 5 |
| fisheye | 8 | 11 | 6 | 7 | 9 | 2 | 2 |
| fisheye-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

## 3. Bảng ca khó

| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| `A05` | `lane` | Có vẽ `L1`/`R1` hay bỏ trống | Không vẽ `lane` | Mặt đường khu công nghiệp không có vạch sơn phân làn; chỉ vẽ `road_curb` hai bên bó vỉa và 1 vùng `drivable` (`direct`). |
| `A03` | `lane` | Vẽ polyline bao quanh ô gạch chéo vàng hay chỉ vẽ 1 đường dọc | Vẽ 1 đường `lane` dọc thẳng | Theo guideline, `lane` biểu diễn đường biên chia làn theo chiều xe chạy, không vẽ gấp khúc zíc-zắc bao vùng gạch chéo. |
| `B03` | `drivable` | Đặt `area_type = direct` hay `alternative` | `alternative` | Ảnh từ camera lùi (`fisheye_rear`), không phải hướng xe tiến thẳng tới nên toàn bộ làn lưu thông hợp pháp đều gán `alternative`. |
| `B02` | `traffic_light` | Bật hay tắt `edge_zone` | `edge_zone = true` | Hai cụm đèn nằm sát mép ngoài cùng của thấu kính fisheye (ngoài 80% bán kính), chịu biến dạng mạnh. |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: [Điền tên bạn cùng cặp]  Quyết định nhận được: [Điền Release / Hold / Rework]  

| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-01 (Thiếu/sai tag camera) | 9 (tự kiểm lint) | Đồng ý | Đã bổ sung đủ 4 tag cho `A08–A12` và sửa đúng `fisheye_left`/`fisheye_right` cho `B05–B08`. |
| QC1-03 (Sai position lane camera hông) | 3 (tự kiểm lint) | Đồng ý | Đã đổi `position = other` cho toàn bộ các đường `lane` ở `B07` và `B08`. |
| QC1-02 (Cảnh báo chưa có L1/R1) | 10 (gợi ý tự động) | Không tính lỗi | Các ảnh `A05, A06, A07, A08, A09, A10, A12, A14` thực tế không có vạch chia làn ở bên tương ứng nên không vẽ thêm. |

## 5. Kiểm file export

| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| `vinh-front.zip` | Có | `A01`: 8 shapes / 8 shapes | `A02`: 6 shapes / 6 shapes | Có (`<tag label="camera">`) |
| `vinh-fisheye.zip` | Có | `B01`: 3 shapes / 3 shapes | `B02`: 5 shapes / 5 shapes | Có (`<tag label="camera">`) |

## 6. Ảnh chụp màn hình
*(Bạn chụp và chèn 4 ảnh vào vị trí tương ứng bên dưới)*
1. Tab Labels của project: `[Chèn ảnh tab Labels của project d11-road-vinh]`
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển): `[Chèn ảnh giao diện CVAT mở ảnh A06 hoặc A08]`
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong: `[Chèn ảnh giao diện CVAT mở ảnh B03 hoặc B06 phóng to đường cong]`
4. Một đoạn XML có `<polyline label="lane">`: `[Chèn ảnh chụp mở file annotations.xml trong vinh-front.zip]`

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:  
Lỗi mắc nhiều nhất là **`QC1-04` (vẽ ngược chiều polyline từ xa về gần)** do thói quen click điểm từ trên xuống dưới, và **`QC1-01` (quên gắn tag hoặc chọn sai hướng camera fisheye)** ở các ảnh sau khi chuyển nhanh qua ảnh mới. Ở Ngày 20, tôi sẽ luôn tuân thủ quy tắc đặt điểm đầu tiên ở sát đáy ảnh (gần xe nhất) kéo dần lên trên, đồng thời kiểm tra đuôi tên file (`_FV`, `_RV`, `_MVL`, `_MVR`) và gắn đủ 4 tag ngay khi vừa mở ảnh trước khi vẽ hình học.

Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:  
Nhãn sau khi export sang XML/JSON được chuyển đổi thành ground-truth target (ví dụ tọa độ điểm x theo các hàng ngang y cố định cho bài toán phát hiện làn đường row-anchor, hoặc bounding box/mask cho bài toán phát hiện đèn/biển và vùng lái).  
Ví dụ với lỗi **`QC1-03` (gán nhầm `position = L1` cho vạch kẻ ở camera hông `fisheye_right` thay vì `other`)** mà tôi đã sửa: nếu không sửa, model học phân loại làn đường sẽ nhầm lẫn vạch kẻ bên hông xe thành vạch làn chính bên trái trước mũi xe (`L1`), dẫn đến hệ thống giữ làn (LKA) ước lượng sai hoàn toàn tâm làn đường thực tế và bẻ lái nguy hiểm.
