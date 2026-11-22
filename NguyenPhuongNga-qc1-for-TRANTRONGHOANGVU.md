# Phiếu QC 1 — Road v1.0

Lô được kiểm (học viên): TRANTRONGHOANGVU        Người kiểm (học viên): NguyenPhuongNga  
Ngày: 2026-11-21                                 Phiên bản guideline: Road v1.0  
File được kiểm (tên + `revision` trong manifest): TRANTRONGHOANGVU-front.zip, TRANTRONGHOANGVU-fisheye.zip (revision 1)  
Số ảnh kiểm: 6 (+ 0 ảnh thêm, ghi riêng)   Số nhãn đã kiểm (shape + tag): 62  

## Tổng hợp theo mã
| Mã | Loại lỗi | Số mục kiểm | Số lỗi | Mức |
| --- | --- | ---: | ---: | --- |
| QC1-01 tag camera | sai thuộc tính / bỏ sót | 6 | 3 | nặng |
| QC1-02 đủ L1, R1 | bỏ sót | 4 | 2 | nặng |
| QC1-03 position | sai thuộc tính / thừa | 11 | 1 | nặng |
| QC1-04 tâm vạch, chiều, điểm dừng | sai phạm vi / bỏ sót | 11 | 0 | chính |
| QC1-05 vạch đứt, che | sai phạm vi / sai thuộc tính | 11 | 1 | chính |
| QC1-06 style, color, kind | sai thuộc tính | 11 | 0 | chính |
| QC1-07 vùng lái | sai phạm vi / bỏ sót / thừa | 14 | 0 | chính |
| QC1-08 đèn, màu | bỏ sót / sai phạm vi / sai thuộc tính | 9 | 0 | nặng / chính |
| QC1-09 facing, type, group, biển phụ | sai thuộc tính | 11 | 0 | chính |
| QC1-10 hình in, đủ biển | bỏ sót / sai phạm vi | 2 | 0 | chính |
| QC1-11 fisheye | sai phạm vi / sai thuộc tính | 19 | 1 | chính |
| QC1-12 file | lỗi file | 3 | 0 | nhẹ / nặng |

## Danh sách lỗi (mỗi lỗi một dòng)
| # | Mã | Ảnh | Nhãn (label, id) | Mức | Mô tả ngắn |
| --- | --- | --- | --- | --- | --- |
| 1 | QC1-01 | B01_02688_FV.png | tag (camera) | nặng | Tag camera gán `front`, trong khi ảnh là camera trước fisheye (phải là `fisheye_front`). |
| 2 | QC1-01 | A06_b8c66e31-37045eec.jpg | tag (camera) | nặng | Ảnh chưa gắn bất kỳ tag nào, thiếu hoàn toàn tag `camera`. |
| 3 | QC1-01 | A07_b41ace08-c8468690.jpg | tag (camera) | nặng | Ảnh chưa gắn bất kỳ tag nào, thiếu hoàn toàn tag `camera`. |
| 4 | QC1-02 | A01_bc5fadac-fa6dd225.jpg | lane | nặng | Thiếu vạch kẻ làn bên phải `R1`. |
| 5 | QC1-02 | A07_b41ace08-c8468690.jpg | lane | nặng | Thiếu cả vạch `L1` và `R1`. |
| 6 | QC1-03 | B07_01216_MVR.png | lane | nặng | Ảnh camera sườn phải (MVR) nhưng vạch lane không gán `position = other`. |
| 7 | QC1-05 | A01_bc5fadac-fa6dd225.jpg | lane (L1) | chính | Vạch đứt L1 bị tách thành 4 polyline riêng cùng mang `position = L1`. |
| 8 | QC1-11 | B07_01216_MVR.png | lane | chính | Polyline chỉ vẽ 3 điểm, không đi theo cung cong của ống kính fisheye. |
| 9 | QC1-01 | A06_b8c66e31-37045eec.jpg | tag (time/weather/src) | nhẹ | Thiếu 3 tag: `timeofday`, `weather`, `source`. |
| 10 | QC1-01 | A07_b41ace08-c8468690.jpg | tag (time/weather/src) | nhẹ | Thiếu 3 tag: `timeofday`, `weather`, `source`. |

*(Ghi chú đối chiếu: Ảnh A03_b1c66a42-6f7d68ca.jpg được kiểm tra và xác nhận đạt chuẩn, không có lỗi).*

## Ca mơ hồ
| Ảnh | Câu hỏi cho lead | Lời đáp (nếu có) |
| --- | --- | --- |
| Không có | Không có ca tranh chấp cần hỏi lead | — |

## Quyết định
Lỗi nặng: 6   Lỗi chính: 2 / 62 nhãn = 3.2 %   Lỗi nhẹ: 2   Ca chờ lead: 0  
Quyết định (Release / Hold / Rework): **Rework**  
Lý do (theo luật của phiếu): Lô có 6 lỗi nặng liên quan đến thiếu/sai tag camera (B01, A06, A07), thiếu vạch L1/R1 (A01, A07) và sai position ở camera hai bên (B07). Theo Guideline Road v1.0, có ít nhất một lỗi nặng phải kết luận Rework.
