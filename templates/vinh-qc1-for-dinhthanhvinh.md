# Phiếu QC 1 — Road v1.0

- Lô được kiểm (học viên): Đinh Thành Vinh
- Người kiểm (học viên): Đinh Thành Vinh
- Ngày: 21/11/2026
- Phiên bản guideline: Road v1.0
- File được kiểm (tên + `revision` trong manifest): `vinh-front.zip`, `vinh-fisheye.zip` (`revision` 1)
- Số ảnh kiểm: 20 (+ 4 ảnh thêm `A13–A16`, ghi riêng)   Số nhãn đã kiểm (shape + tag): 258 (162 shapes + 96 tags)  

## Tổng hợp theo mã

| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 24 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 24 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 44 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 44 | 33 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 44 | 0 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 44 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 44 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 18 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 36 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 31 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 37 | 8 | chính |
| QC1-12 file | lỗi file | 2 | 1 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)

| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-12 | `A01` | `lane`, `#0` | nhẹ | 1 điểm lặp liền nhau tại tọa độ `(333, 505)` do click đúp |
| 2 | QC1-04 | `A01` | `lane`, `#0, #4, #5, #6` | chính | Điểm đầu cao hơn điểm cuối (vẽ theo chiều từ xa về gần) |
| 3 | QC1-04 | `A02` | `lane`, `#3, #4` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 4 | QC1-04 | `A03` | `lane`, `#1, #2` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 5 | QC1-04 | `A04` | `lane`, `#0, #3` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 6 | QC1-04 | `A06` | `lane`, `#11` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 7 | QC1-04 | `A07` | `lane`, `#1` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 8 | QC1-04 | `A08` | `lane`, `#7, #10` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 9 | QC1-04 | `A09` | `lane`, `#0, #3` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 10 | QC1-04 | `A10` | `lane`, `#1, #2` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 11 | QC1-04 | `A11` | `lane`, `#5, #6` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 12 | QC1-04 | `A12` | `lane`, `#4` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 13 | QC1-04 | `A13` | `lane`, `#2, #4, #5` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 14 | QC1-04 | `A14` | `lane`, `#0, #6` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 15 | QC1-04 | `A15` | `lane`, `#2, #3, #4` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 16 | QC1-04 | `A16` | `lane`, `#0, #1, #2, #4` | chính | Điểm đầu cao hơn điểm cuối (vẽ từ xa về gần) |
| 17 | QC1-11 | `B02` | `lane`, `#0` | chính | Chỉ có 3 điểm trên ảnh fisheye, cần thêm điểm theo độ cong |
| 18 | QC1-11 | `B03` | `lane` (`#0, #1`), `road_curb` (`#4`) | chính | Chỉ có 3 điểm trên ảnh fisheye, cần thêm điểm theo độ cong |
| 19 | QC1-11 | `B04` | `lane`, `#0` | chính | Chỉ có 3 điểm trên ảnh fisheye, cần thêm điểm theo độ cong |
| 20 | QC1-11 | `B07` | `lane`, `#2, #3` | chính | Chỉ có 3 điểm trên ảnh fisheye, cần thêm điểm theo độ cong |
| 21 | QC1-11 | `B08` | `lane`, `#1` | chính | Chỉ có 2 điểm trên ảnh fisheye, cần thêm điểm theo độ cong |

## Ca mơ hồ

| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| `A05, A06, A07, A08, A09, A10, A12, A14` | Script `lint` cảnh báo `[QC1-02] chưa có L1/R1`, nhưng thực tế các ảnh này đường 1 làn hoặc sát dải phân cách/vỉa hè không có vạch sơn bên tương ứng — xác nhận bỏ qua không vẽ thêm. | Đã đối chiếu trực quan: không có vạch kẻ thực tế, hợp lệ. |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 41 / 258 nhãn = 15.89 %   Lỗi nhẹ: 1   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Hold  
Lý do (theo luật của phiếu): Lô đạt 0 lỗi nặng (đủ 4 tag/ảnh, không kèm ảnh, đúng taxonomy), tuy nhiên tỷ lệ lỗi chính vượt ngưỡng do lỗi chiều vẽ polyline (`QC1-04`: 33 lỗi) và thiếu điểm cong fisheye (`QC1-11`: 8 lỗi), cần giữ lại (`Hold`) để đảo chiều polyline và bổ sung điểm neo trước khi Release.  

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
