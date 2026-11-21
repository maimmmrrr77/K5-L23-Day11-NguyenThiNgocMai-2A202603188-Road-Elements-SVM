# Báo cáo cá nhân — Ngày 11
Họ tên: Nguyễn Thị Ngọc Mai               Mã học viên: 2A202603188
Phiên bản CVAT (Help → About):  2.82.1
Guideline: Road v1.0    Lần nộp (`revision` trong manifest):  1
Thời điểm export (ngày giờ trên CVAT): Nov 21st 26, 11:49   Số lần nộp lại sau Rework:  0

## 1. Kiểm project
| Mục | Đúng như guideline Road v1.0? | Ghi chú |
| --- | --- | --- |
| 6 label, đúng kiểu | Đúng | Đủ 6 nhãn: `lane` (polyline), `road_curb` (polyline), `crosswalk` (polygon), `drivable` (polygon), `traffic_light` (rectangle), `traffic_sign` (rectangle). |
| Thuộc tính và giá trị | Đúng | Đủ các thuộc tính quy định (`position`, `style`, `color`, `kind`, `area_type`, `type`, `facing`, `group`, `edge_zone`). |
| 4 tag ảnh | Đúng | Đủ 4 tag trên mọi ảnh: `camera`, `timeofday`, `weather`, `source`. |
Cách kết thúc polyline trên bản CVAT này:  Bấm phím N
Cách đặt tag ảnh trên bản CVAT này:  Mở bảng công cụ bên trái - chọn biểu tượng hình thẻ tag - chọn tên tag trong danh sách thả xuống rồi bấm dấu cộng, chỉnh sửa thuộc tính của tag ở bảng object bên phải.

## 2. Số lượng đã gán
| Task | Ảnh | lane | road_curb | crosswalk | drivable | traffic_light | traffic_sign |
| --- | ---: | ---: | ---: | ---: | ---: | ---: | ---: |
| front | 12 | 39 | 15 | 7 | 28 | 41 | 33 |
| front-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| fisheye | 8 | 14 | 10 | 17 | 12 | 4 | 5 |
| fisheye-extra (đã làm 0 / 4) | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

## 3. Bảng ca khó
| Ảnh | Nhãn | Phân vân giữa | Đã chọn | Lý do |
| --- | --- | --- | --- | --- |
| `A05_b2576c8c-2de20b8a.jpg` | `lane` (`L1`, `R1`) | Gán thêm `lane` hay bỏ trống để không vẽ sai | Không gán `lane` | Mặt đường thực tế trong ảnh không có vạch sơn kẻ đường phân làn (`L1`, `R1`), chỉ có bó vỉa (`road_curb`); tuân thủ nguyên tắc không tự vẽ thêm khi không có vạch sơn. |
| `A06_b8c66e31-37045eec.jpg` | `lane` (`R1`) | Gán `R1` sát vỉa phải hay chỉ gán `road_curb` | Không gán `R1` | Phía bên phải làn xe chỉ có bó vỉa hè (`road_curb`), không có vạch kẻ sơn biên phải. |
| `A04_b7a8e795-0ff55db2.jpg` | `traffic_sign` (biển trắng `KEEP INTERSECTION CLEAR`) | `group: prohibitory` hay `group: mandatory` | `prohibitory` | Biển quy định hạn chế dừng/đỗ trong khu vực giao lộ của Mỹ, mang tính chất cấm dừng cản trở giao thông. |
| `B05_05780_MVL.png` | `drivable` (`alternative`) | Có vẽ `alternative` sang phần đường bên kia dải gờ vàng hay không | Không vẽ sang bên kia | Hàng khối gờ bê tông màu vàng là dải phân cách cứng tách biệt làn xe chạy, xe không thể chuyển làn vượt qua. |
| `B01_02688_FV.png` | `traffic_light` (đèn đi bộ rìa trái) | `edge_zone: true` hay `false` | `edge_zone: true` | Tâm hộp chữ nhật nằm sát mép rìa ngoài vòng ảnh fisheye (ngoài 80% bán kính ống kính). |

## 4. Phiếu QC 1 nhận được
Bạn kiểm lô của tôi: Nguyễn Thị Ngọc Mai Quyết định nhận được:  Realease
| Mã lỗi | Số lỗi | Đồng ý? | Đã sửa? |
| --- | ---: | --- | --- |
| QC1-03 | 1 | Đồng ý | Đã sửa |
| QC1-11 | 4 | Đồng ý | Đã sửa |
| QC1-05 | 5 | Đồng ý | Ghi nhận |
| QC1-04 | 1 | Đồng ý | Ghi nhận |

## 5. Kiểm file export
| File | Mở lại được? | Số shape ảnh 1 (job / file) | Số shape ảnh 2 (job / file) | Tag camera có trong XML? |
| --- | --- | --- | --- | --- |
| `NguyenThiNgocMai-front.zip` | Có | 11 / 11 | 8 / 8 | Có |
| `NguyenThiNgocMai-fisheye.zip` | Có | 7 / 7 | 8 / 8 | Có |

## 6. Ảnh chụp màn hình
1. Tab Labels của project.
2. Một ảnh camera trước đã gán đủ (làn, vùng lái, đèn/biển).
3. Một ảnh fisheye đã gán, phóng to đoạn polyline cong.
4. Một đoạn XML có <polyline label="lane">.

## 7. Tự đánh giá
Lỗi bạn mắc nhiều nhất hôm nay (theo mã QC1-xx), và cách tránh ở Ngày 20:  
- Lỗi mắc nhiều nhất là `QC1-05` (5 lỗi: gán 2 polyline cùng `position = L1` do quên đổi vạch làn kế tiếp sang `L2` hoặc lỡ tách rời vạch đứt) và lỗi `QC1-03` / `QC1-11` trên ảnh fisheye (quên đổi `position = other` cho camera hai bên và thiếu `edge_zone`).  
- Cách tránh ở Ngày 20: Luôn dùng chức năng lọc/kiểm tra danh sách Objects bên thanh phải của từng ảnh trước khi chuyển ảnh mới để đảm bảo mỗi ảnh front chỉ có duy nhất một `L1` và một `R1`; đối với camera fisheye hai bên (`MVL`, `MVR`), thiết lập mặc định `position = other` ngay từ đường `lane` đầu tiên và chạy công cụ `lint` sớm ngay sau khi làm xong 3–4 ảnh đầu để bắt lỗi quy ước kịp thời.
Nhãn của bạn đi vào model ở đâu? Chọn một lỗi đã sửa và nói nó làm model học sai thế nào:  
- Nhãn gán trên CVAT được chuyển đổi thành mặt nạ phân vùng (segmentation mask) cho `drivable`/`crosswalk`, tọa độ các điểm neo theo hàng ngang cho `lane`/`road_curb` để huấn luyện các mô hình nhận thức làn đường, và hộp giới hạn cùng phân loại trạng thái cho mô hình nhận diện đèn/biển báo.  
- Ví dụ lỗi đã sửa (`QC1-03` trên ảnh `B07` - gán nhầm `position = L1` cho vạch làn trên camera fisheye bên hông `MVR`): Nếu không sửa lỗi này, bộ chuyển đổi dữ liệu sẽ ghép nhầm vạch đường ở bên hông xe thành vạch ranh giới trái của làn xe đang chạy thẳng phía trước, khiến mô hình định vị làn đường học sai hình học không gian, dẫn đến hệ thống giữ làn (LKA) ước tính sai tâm làn đường và đánh lái lệch nguy hiểm khi xe vận hành thực tế.

## 8. (Tùy chọn, buffer) Từ polyline đến đích row-anchor
| y | 720 | 680 | 640 | 600 | 560 |
| --- | ---: | ---: | ---: | ---: | ---: |
| x của chúng tôi |  |  |  |  |  |
| x của bạn kia |  |  |  |  |  |

Trả lời 3 câu:

1. Năm số x đó chính là đích mà một model row-anchor học cho vạch này. Nếu bạn dừng polyline sớm 40 px, hàng nào đổi thành "không có làn"?
2. So với bạn được kiểm (cùng ảnh): ở hàng 720 và hàng 560, hai bạn lệch nhau bao nhiêu pixel? Lệch ở hàng nào ảnh hưởng LKA nhiều hơn (slide 25)?
3. Nếu polyline vẽ từ xa về gần (ngược quy tắc 2), cách tính trên có đổi không? Script nào sẽ gặp khó?
