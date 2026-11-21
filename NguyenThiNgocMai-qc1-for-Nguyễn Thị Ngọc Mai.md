# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): Nguyễn Thị Ngọc Mai        Người kiểm (học viên): Nguyễn Thị Ngọc Mai
Ngày:  21/11/2026                        Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest):  NguyenThiNgocMai-front.zip, NguyenThiNgocMai-fisheye.zip (`revision: 1`)
Số ảnh kiểm: 20 (+ __ ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag):  305

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 20 | 0 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 12 | 0 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 53 | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 78 | 1 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 53 | 5 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 53 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 40 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 45 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 83 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 62 | 5 | nhẹ |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 8 | 1 | chính |
| QC1-12 file | lỗi file | 1 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-04 | A01_bc5fadac-fa6dd225.jpg | `lane` #2 @(459,510) | chính | Điểm đầu cao hơn điểm cuối (vẽ ngược chiều từ xa về gần) |
| 2 | QC1-05 | A04_b7a8e795-0ff55db2.jpg | `lane` (`position: L1`) | chính | Có 2 polyline cùng gán `position = L1` |
| 3 | QC1-05 | A06_b8c66e31-37045eec.jpg | `lane` (`position: L1`) | chính | Có 2 polyline cùng gán `position = L1` |
| 4 | QC1-05 | A08_c0deebc1-16cfa791.jpg | `lane` (`position: L1`) | chính | Có 2 polyline cùng gán `position = L1` |
| 5 | QC1-05 | A09_c7e6d5d1-c8af9fe3.jpg | `lane` (`position: L1`) | chính | Có 2 polyline cùng gán `position = L1` |
| 6 | QC1-05 | A11_c1f35f18-b529c043.jpg | `lane` (`position: L1`) | chính | Có 2 polyline cùng gán `position = L1` |
| 7 | QC1-11 | B08_05783_MVR.png | `lane` #1 @(65,748) | chính | Chỉ có 3 điểm trên ảnh fisheye, cần đặt thêm điểm theo cung cong |
| 8 | QC1-10 | A03_b1c66a42-6f7d68ca.jpg | `traffic_sign` #9 @(656,306) | nhẹ | Box thấp hơn 8 px (không bắt buộc gán) |
| 9 | QC1-10 | A10_b6ff1331-f6d3fba8.jpg | `traffic_sign` #5 @(441,233) | nhẹ | Box thấp hơn 8 px (không bắt buộc gán) |
| 10 | QC1-10 | A10_b6ff1331-f6d3fba8.jpg | `traffic_sign` #7 @(488,236) | nhẹ | Box thấp hơn 8 px (không bắt buộc gán) |
| 11 | QC1-10 | A10_b6ff1331-f6d3fba8.jpg | `traffic_sign` #9 @(827,226) | nhẹ | Box thấp hơn 8 px (không bắt buộc gán) |
| 12 | QC1-10 | A10_b6ff1331-f6d3fba8.jpg | `traffic_sign` #13 @(535,236) | nhẹ | Box thấp hơn 8 px (không bắt buộc gán) |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| A05_b2576c8c-2de20b8a.jpg | Ảnh mặt đường thực tế không có vạch sơn kẻ đường `L1` và `R1` (`[QC1-02 nặng]`), xác nhận miễn lỗi bỏ sót `L1/R1` | Đã đối chiếu ảnh thực tế không có vạch kẻ, miễn lỗi `QC1-02` |
| A06_b8c66e31-37045eec.jpg | Bên phải làn xe thực tế không có vạch sơn kẻ đường `R1` (`[QC1-02 nặng]`), xác nhận miễn lỗi bỏ sót `R1` | Đã đối chiếu ảnh thực tế không có vạch `R1`, miễn lỗi `QC1-02` |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 7 / 305 nhãn = 2.30 %   Lỗi nhẹ: 5   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): Release  
Lý do (theo luật của phiếu): Không có lỗi nặng thực tế (3 cảnh báo `QC1-02` ở `A05`, `A06` do mặt đường không có vạch kẻ); không còn ca chờ lead (0 ca); tỉ lệ lỗi chính đạt 7 / 305 = 2.30% (thấp hơn ngưỡng tối đa 5.0%). Định dạng file zip và manifest hợp lệ. 

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
