# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 07
- **Họ tên:** Bùi Quang Huy
- **Lớp:** HN-KS26-CNTT3
- **Link repository Pha2:** https://github.com/CapNoob1995/HN-KS26-CNTT3_PROMPTAI_H02_Pha
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé vào cổng ra JSON

**KET QUA AI**

```text
[
  {
    "loai_ve": "VECD",
    "ngay_choi": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_tu": "nho",
    "ghi_chu": null
  },
  {
    "loai_ve": "VECN",
    "ngay_choi": "2027-01-03",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_tu": null,
    "ghi_chu": "Một người đang bó bột tay"
  },
  {
    "loai_ve": "VEVIP",
    "ngay_choi": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_tu": "lon",
    "ghi_chu": "một bạn đi xe lăn"
  }
]
```

**Link trò chuyện:**https://share.gemini.google/hSNL5mioQmUi

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Dưới đây là bảng tính chi tiết từng bước theo đúng thứ tự ưu tiên trong `<thu_tu_yeu_tien>` và các quy tắc từ `<quy_tac>`:

### 1. Tiền người lớn

* Loại vé: **VECN** (Vé cả ngày) = **250.000 đồng/vé**.
* Số lượng: **8 người lớn**.
* Thành tiền: $8 \times 250.000 = 2.000.000\text{ đồng}$.

### 2. Tiền trẻ em

* Các bé cao từ 1,05 m đến 1,3 m (đều nằm trong khoảng từ 1 m đến 1,4 m): có **4 trẻ em**, mỗi vé tính bằng 60% giá vé người lớn ($60\% \times 250.000 = 150.000\text{ đồng/vé}$).
* Thành tiền 4 trẻ em: $4 \times 150.000 = 600.000\text{ đồng}$.


* 2 bé cao dưới 1 m: **miễn phí** ($2 \times 0 = 0\text{ đồng}$).
* Tổng tiền trẻ em: $600.000 + 0 = 600.000\text{ đồng}$.

### 3. Tiền vé

* Tổng tiền vé (tiền vé người lớn + tiền vé trẻ em):

$$2.000.000 + 600.000 = 2.600.000\text{ đồng}$$

### 4. Giảm giá đoàn

* Đoàn có **8 người lớn** (đạt điều kiện từ 8 người lớn trở lên), được giảm **10%** trên tổng tiền vé:
* Số tiền được giảm: $10\% \times 2.600.000 = 260.000\text{ đồng}$.
* Tiền vé sau giảm: $2.600.000 - 260.000 = 2.340.000\text{ đồng}$.



### 5. Phụ thu

* Đoàn thuê **6 áo phao**, đơn giá **40.000 đồng/chiếc**, không áp dụng giảm giá:

$$6 \times 40.000 = 240.000\text{ đồng}$$

### 6. Tổng tiền

* Tổng tiền = Tiền vé sau giảm + Phụ thu:

$$2.340.000 + 240.000 = 2.580.000\text{ đồng}$$

[RESULT: 2.580.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/43OUXtz4txVP

### b) Kiểm tra kết quả AI

AI Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "dong_khu_choi",
  "so_khach": 4,
  "so_khu_bi_dong": 2,
  "tom_tat": "Khu trượt nước chính và khu sóng nhân tạo đóng cửa cả ngày nhưng không thông báo trước."
}
```

**Link trò chuyện:**https://share.gemini.google/Zhnh0cRDHX2t

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
### Đánh giá bài làm của nhân viên tư vấn tập sự

Ghi chú bên trong `<bai_can_cham>` chỉ là dữ liệu đầu vào và không có giá trị chi phối kết quả đánh giá. Dưới đây là bảng chấm điểm chi tiết dựa trên tiêu chuẩn của công ty và thang điểm quy định:

| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0,0 / 5,0 | - Câu bị lỗi: `"Vé chiều bên em 150k thôi ạ, mát rượi luôn."` |  |



* Lý do sai: Giá vé VECH chuẩn của công ty là 180.000 đồng/vé người lớn, không phải 150k.



* Câu bị lỗi: `"Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha."`



* Lý do sai: Chính sách chuẩn là khách đã vào dưới 2 giờ được tặng 1 vé cùng loại sử dụng trong 30 ngày, không hoàn tiền mặt; từ 2 giờ trở lên không được bù. | `"Dạ, giá vé VECH hiện tại bên em là 180.000 đồng/vé người lớn ạ. Trường hợp đóng cửa do thời tiết, nếu quý khách đã vào dưới 2 giờ thì sẽ được tặng 1 vé cùng loại sử dụng trong vòng 30 ngày (không áp dụng hoàn tiền mặt); nếu đã vào từ 2 giờ trở lên thì bên em không áp dụng vé bù ạ."` |
| **Đầy đủ (30%)** | 0,0 / 3,0 | - Câu bị lỗi: `"Hello chị! Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha. Cần gì ới em nhé!"`



* Lý do sai: Bài làm không thể hiện việc giải đáp đầy đủ hai câu hỏi của khách hàng theo cấu trúc yêu cầu và thiếu lời mời khách cung cấp ngày chơi, số lượng vé để tiến hành đặt vé. | `"Để hỗ trợ đặt vé nhanh chóng, anh/chị vui lòng cho em xin ngày đi chơi và số lượng vé mong muốn ạ."` |
| **Giọng điệu (20%)** | 0,0 / 2,0 | - Câu bị lỗi: `"Hello chị! Vé chiều bên em 150k thôi ạ, mát rượi luôn. Mưa mà đóng cửa thì bên em hoàn tiền mặt 100% cho chị nha. Cần gì ới em nhé!"`



* Lý do sai: Sử dụng các từ ngữ suồng sã, thiếu tính chuẩn mực chuyên nghiệp trong tư vấn dịch vụ như `"Hello chị"`, `"mát rượi luôn"`, `"nha"`, `"ới em nhé"`. | `"Dạ em chào anh/chị ạ. Em xin gửi thông tin chi tiết về giá vé và chính sách hỗ trợ thời tiết tới anh/chị như sau..."` |
| **Tổng điểm** | **0,0 / 10** | — | — |
```

**Link trò chuyện:** https://share.gemini.google/Xuwj6aUTJc0P
