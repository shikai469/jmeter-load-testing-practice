# Báo Cáo Bài Tập Kiểm Thử Hiệu Năng Bằng JMeter

**Sinh viên thực hiện:** Nguyễn Hữu Hưng.

**Mã sinh viên:** 23010124.

**Lớp/Môn học:** CSE703010-1-3-25(COUR01.LT3) - Đánh giá và kiểm định chất lượng phần mềm.

---

## 1. Mục tiêu bài tập
* Tìm hiểu công cụ Apache JMeter để thực hiện kiểm thử chịu tải (Load Testing).
* Thiết lập các thông số (Thread Group, Ramp-up, Loop Count) để mô phỏng lượng người dùng truy cập đồng thời.
* Thực thi kiểm thử thực tế trên hai môi trường: Chế độ giao diện đồ họa (GUI) và chế độ dòng lệnh (Non-GUI).

## 2. Kịch Bản Kiểm Thử (Test Plan)
* **Mục tiêu test:** Kiểm tra khả năng xử lý của máy chủ Cổng thông tin sinh viên Phenikaa.
* **Endpoint (HTTP Request):** `GET https://qldtbeta.phenikaa-uni.edu.vn/congsinhvien/Login.aspx`
* **Cấu hình Thread Group:**
  * Số lượng Threads (Users): `10`
  * Ramp-up Period (Seconds): `2`
  * Loop Count: `10`
  * Tổng số request phát sinh: `100`

## 3. Kết Quả Thực Hiện

### 3.1. Chạy kịch bản qua giao diện đồ họa (GUI Mode)
* **Mô tả:** Chạy kịch bản trực tiếp trên ứng dụng JMeter. Sử dụng Listener `View Results Tree` để quan sát chi tiết từng request.
* **Kết quả:** Các request gửi đi đều nhận được phản hồi thành công (Mã trạng thái `200 OK`), máy chủ trả về đầy đủ cấu trúc HTML của trang đăng nhập.
* **Ảnh minh họa (Giao diện JMeter & Response Data):**

<img width="1920" height="1080" alt="Screenshot 2026-06-03 164209" src="https://github.com/user-attachments/assets/b02ab5cc-546b-47c5-b9ba-be0b9c8cae42" />
<img width="1920" height="1080" alt="Screenshot 2026-06-03 164236" src="https://github.com/user-attachments/assets/057963cb-7409-41e7-a1fb-6abb44f76ec1" />


### 3.2. Chạy kịch bản qua dòng lệnh (Non-GUI Mode)
* **Mô tả:** Thực thi kịch bản bằng PowerShell để tối ưu tài nguyên phần cứng, xuất báo cáo tổng hợp ra file định dạng `.csv`.
* **Câu lệnh sử dụng:** ```powershell
  .\jmeter.bat -n -t "View Results Tree.jmx" -l ketqua_test.csv

<img width="1919" height="482" alt="image" src="https://github.com/user-attachments/assets/28fca5e0-4971-46c0-be6e-88980db86fcb" />
