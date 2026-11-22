# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): NguyenPhuongNga        Người kiểm (học viên): TRẦN TRỌNG HOÀNG VŨ  
Ngày: 2026-11-21                               Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): NguyenPhuongNga-front.zip, NguyenPhuongNga-fisheye.zip (revision 1)  
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 75  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 | 1 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 4 | 1 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 15 | 1 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 15 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 15 | 3 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 15 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 12 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 4 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 15 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 11 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 12 | 0 | chính |
| QC1-12 file | lỗi file | 3 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-01 | B05_05780_MVL.png | tag (camera) | nặng | Tag camera gán `fisheye_front`, trong khi tên file là MVL (phải là `fisheye_left`). |
| 2 | QC1-02 | A03_b1c66a42-6f7d68ca.jpg | lane | nặng | Thiếu vạch L1 (vạch phân cách bên trái làn xe chạy không được gán L1). |
| 3 | QC1-03 | A03_b1c66a42-6f7d68ca.jpg | lane (vạch vàng bên trái) | nặng | Vạch tim đường màu vàng bên trái bị gán nhầm thành `position = R1` thay vì `L1`. |
| 4 | QC1-05 | A01_bc5fadac-fa6dd225.jpg | lane (L2) | chính | Vạch L2 bị vẽ thành 2 polyline riêng biệt cùng mang `position = L2`. |
| 5 | QC1-05 | A02_b3c26aff-63a0d7d6.jpg | lane (L1) | chính | Vạch đứt L1 bị tách thành 2 polyline riêng cùng mang `position = L1`. |
| 6 | QC1-05 | A04_b7a8e795-0ff55db2.jpg | lane (L1) | chính | Vạch đôi L1 bị vẽ thành 2 polyline riêng cùng mang `position = L1` và `kind = double`. |
| 7 | QC1-08 | A03_b1c66a42-6f7d68ca.jpg | traffic_light #4 | nhẹ | Box đèn giao thông chiều cao dưới 8 px (không bắt buộc). |

*(Ghi chú đối chiếu: Ảnh B06_04068_MVL.png được kiểm và xác nhận đạt chuẩn, không có lỗi).*

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| Không có | Không có ca tranh chấp cần hỏi lead | — |

## Quyết định
Lỗi nặng: 3   Lỗi chính: 3 / 75 nhãn = 4.0 %   Lỗi nhẹ: 1   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): **Rework**  
Lý do (theo luật của phiếu): Lô có 3 lỗi nặng (sai tag camera ở B05, thiếu L1 ở A03, và sai thuộc tính position ở A03). Theo quy định của Guideline Road v1.0, chỉ cần có ít nhất 1 lỗi nặng thì kết luận là Rework.
