# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** AI20K-2A202600061
**Name:** Hồ Xuân Phú
**Date:** 15/04/2026

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Based on my data, the best choice is Laptop at $1200. | 9 | Kết quả hợp lý, phản ánh đúng dữ liệu sạch |
| Garbage Data (`garbage_data.csv`) | Based on my data, the best choice is Nuclear Reactor at $999999. | 1 | Kết quả phi thực tế, do dữ liệu rác, giá trị ngoại lai phi thực tế |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Khi sử dụng dữ liệu rác, Agent đã trả về kết quả sai lệch nghiêm trọng. Nguyên nhân là do dữ liệu garbage chứa nhiều vấn đề như: trùng lặp ID, kiểu dữ liệu sai (ví dụ giá trị số bị ghi thành chữ), giá trị ngoại lai (outlier) quá lớn hoặc quá nhỏ, và các giá trị null. Những vấn đề này làm cho quá trình phân tích dữ liệu bị sai lệch, khiến Agent không thể nhận diện đúng các lựa chọn hợp lý. Đặc biệt, các giá trị ngoại lai và dữ liệu không hợp lệ có thể làm thay đổi hoàn toàn kết quả, khiến Agent đưa ra quyết định phi thực tế. Điều này cho thấy chất lượng dữ liệu đầu vào ảnh hưởng trực tiếp đến độ chính xác của mô hình AI.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** 
Đồng ý.
Chất lượng dữ liệu quan trọng hơn chất lượng prompt, vì dù prompt tốt đến đâu nhưng dữ liệu đầu vào sai lệch thì kết quả vẫn sẽ không chính xác. Dữ liệu tốt giúp mô hình AI học và suy luận đúng đắn, còn dữ liệu kém sẽ dẫn đến kết quả sai lệch, bất kể prompt có rõ ràng hay không.
