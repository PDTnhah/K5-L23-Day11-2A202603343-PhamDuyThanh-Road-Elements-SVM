# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên):  Phạm Duy Thạnh        Người kiểm (học viên):  Trần Trọng Thái
Ngày:  2026-11-21                        Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest):  PhamDuyThanh-front.xml, PhamDuyThanh-fisheye.xml (revision: 1)
Số ảnh kiểm: 20 (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 230

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót |  |  | nặng |
| QC1-02 đủ L1, R1 | bỏ sót |  |  | nặng |
| QC1-03 position | sai thuộc tính / thừa |  | 0 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót |  |  | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính |  |  | chính |
| QC1-06 style, color, kind | sai thuộc tính |  |  | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa |  | 1 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính |  |  | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính |  | 1 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi |  |  | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính |  | 8 | chính |
| QC1-12 file | lỗi file |  |  | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-07 | A11 | drivable (direct) | chính | Khuyết góc quanh xe SUV, guideline cấm khoét quanh xe khác |
| 2 | QC1-09 | A03 | traffic_sign | chính | group = information, nhưng là biển vàng người đi bộ, phải là warning |
| 3 | QC1-11 | B03 | lane#4 | chính | Chỉ 3 điểm, trên fisheye cần đặt điểm theo cung |
| 4 | QC1-11 | B06 | lane#0 | chính | Chỉ 3 điểm, trên fisheye cần đặt điểm theo cung |
| 5 | QC1-11 | B02 | traffic_light#0, #1, #3 | chính | edge_zone đang tắt, nhưng tâm box nằm ngoài 80 % bán kính vòng ảnh, phải bật (3 đèn) |
| 6 | QC1-11 | B03 | traffic_sign#1 | chính | edge_zone đang tắt, tâm box ngoài 80 % bán kính |
| 7 | QC1-11 | B04 | traffic_sign#3 | chính | edge_zone đang tắt, tâm box ngoài 80 % bán kính |
| 8 | QC1-11 | B05 | traffic_sign#4 | chính | edge_zone đang tắt, tâm box ngoài 80 % bán kính |

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| A10 | Tag weather đang là overcast nhưng mặt đường ướt rõ, phản chiếu đèn: có phải rain không? |  |
| A06 | Biển "ONE WAY" đang ghi supplementary, có phải mandatory không? |  |
| A03 | Các vạch kẻ vàng chéo ở trái xe có cần gán không |  |
| B01, B02 | Traffic light như vậy thì coi là side hay front |  |

## Quyết định
Lỗi nặng: 0   Lỗi chính: 10 / 230 nhãn = 4,3 %   Lỗi nhẹ: 0   Ca chờ lead: 4  
Quyết định (Release / Hold / Rework):  Release
Lý do (theo luật của phiếu):  Không có lỗi nặng; lỗi chính 10 / 230 nhãn (shape + tag) = 4,3 %, không vượt ngưỡng 5 %. Các ca chờ lead (A10 weather, A06 nhóm biển, A03 vạch vàng chéo, B01–B02 side/front) không đổi kết luận.

Loại lỗi: bỏ sót = thiếu nhãn phải có; thừa = gán cái không phải đối tượng; sai phạm vi = hình lệch, sai chiều, dừng sai chỗ, tràn vùng. Ba loại này theo cách chia lỗi gán nhãn của ISO/IEC 5259-4 (mục 8.4.2); "sai thuộc tính" và "lỗi file" là khóa học thêm. Cách xếp mức: [thang mức lỗi](../docs/qc_severity_road_v1.0.md).
