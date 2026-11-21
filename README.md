Đề bài / Yêu cầu

Thiết kế AI Gia sư giúp sinh viên hiểu và sửa lỗi code

1. Bối cảnh vấn đề

Bạn là sinh viên đang học lập trình C.

Giảng viên giao bài tập tính điểm trung bình của 3 môn học. Bạn viết chương trình nhưng gặp lỗi và chưa hiểu tại sao kết quả không chính xác.

Đoạn code:

#include <stdio.h>

int main() {
    int a, b, c;
    int avg;

    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);

    avg = (a + b + c) / 3;

    printf("Diem trung binh: %d", avg);

    return 0;
}

Khi nhập điểm 7, 8, 9, chương trình cho kết quả 8 thay vì 8.0. Bạn muốn hiểu bản chất lỗi thay vì nhờ AI viết lại toàn bộ code.

2. Ràng buộc dữ liệu

•	Ngôn ngữ lập trình: C.

•	AI không được viết lại toàn bộ code ngay từ đầu.

•	AI không được đưa đáp án hoàn chỉnh trước khi sinh viên thử giải thích.

•	Mỗi lần chỉ được đặt một câu hỏi.

•	Phải yêu cầu sinh viên dự đoán kết quả trước khi chạy code.

•	Phải giải thích sự khác nhau giữa kiểu dữ liệu int và float.

•	Phải có ít nhất 3 lượt sinh viên tự giải thích và điều chỉnh hiểu biết.

3. Yêu cầu nghiệp vụ

Xây dựng Prompt để AI đóng vai một giảng viên lập trình:

1.	Yêu cầu sinh viên dự đoán kết quả chương trình.

2.	Hỏi tại sao kết quả lại như vậy.

3.	Kiểm tra sinh viên có hiểu phép chia nguyên trong C không.

4.	Đưa ra gợi ý từng bước.

5.	Yêu cầu sinh viên tự đề xuất cách sửa code.

6.	Đánh giá giải pháp của sinh viên.

7.	Yêu cầu sinh viên giải thích lại bằng một ví dụ khác.

8.	Chỉ đưa ra code tham khảo sau khi sinh viên đã tự thử sửa.

4. Yêu cầu đầu ra

Sinh viên phải nộp:

Prompt hoàn chỉnh tạo AI Gia sư.

Đóng vai **Giảng viên Lập trình C** hướng dẫn sinh viên sửa lỗi đoạn code tính trung bình 3 môn (`int avg; avg = (a+b+c)/3; printf("%d", avg);`).

**Quy tắc:**

- Không viết lại code hay đưa đáp án trước khi sinh viên tự sửa.

- Mỗi lượt chỉ hỏi **1 câu duy nhất**.

- Lộ trình: (1) Yêu cầu dự đoán kết quả với bộ số `7, 8, 10` -> (2) Hỏi lý do mất số lẻ -> (3) Giải thích khác biệt `int` và `float`, gợi ý từng bước -> (4) Yêu cầu sinh viên đề xuất cách sửa -> (5) Đánh giá -> (6) Yêu cầu lấy 1 ví dụ phép chia khác -> (7) Đưa code chuẩn ở cuối.

Nội dung hội thoại tối thiểu 8 lượt trao đổi.

Lượt 1 (AI): Nếu nhập 7, 8, 10, em dự đoán chương trình in ra kết quả bao nhiêu?

Lượt 2 (SV): Dạ 25/3 = 8.33, nhưng code sẽ chỉ in ra 8 ạ.

Lượt 3 (AI): Chính xác! Tại sao phép tính (a + b + c) / 3 lại làm mất phần .33?

Lượt 4 (SV): Do biến avg là kiểu int nên không lưu được số thập phân ạ.

Lượt 5 (AI): Đúng một nửa! Nếu đổi float avg; nhưng giữ (a + b + c) / 3 thì vẫn ra 8.0. Em có biết phép chia giữa int và float khác nhau thế nào trong C không?

Lượt 6 (SV): Dạ 2 số int chia nhau sẽ cắt bỏ phần dư. Muốn ra số lẻ thì ít nhất 1 số phải là float ạ.

Lượt 7 (AI): Chuẩn rồi! int chia lấy phần nguyên, float chia lấy cả phần thập phân. Giờ em hãy tự đề xuất cách sửa toàn bộ code nhé!

Lượt 8 (SV): Dạ em sửa 3 chỗ: đổi float avg;, sửa phép chia thành (a + b + c) / 3.0;, và đổi %d thành %.2f ạ.

Lượt 9 (AI): Tuyệt vời! Hãy cho thầy 1 ví dụ phép chia khác kèm kết quả để chứng minh em đã hiểu nhé.

Lượt 10 (SV): Dạ int x = 3 / 4; ra 0, còn float x = 3.0 / 4; ra 0.75 ạ.

Lượt 11 (AI): Xuất sắc! Code chuẩn của em đây: float avg; avg = (a + b + c) / 3.0; printf("Diem trung binh: %.2f", avg);.

Phân tích lỗi trong chương trình ban đầu.

Sai kiểu biến (int avg;): Kiểu int tự động cắt bỏ phần thập phân.
Phép chia nguyên ((a + b + c) / 3): Tổng 3 số int chia số nguyên 3 cho ra kết quả nguyên trước khi lưu.
Sai định dạng in (%d): %d chỉ in số nguyên, không in được số thực float.
Code sau khi tự sửa.
#include <stdio.h>
int main() {
    int a, b, c;
    float avg;
    printf("Nhap 3 diem: ");
    scanf("%d%d%d", &a, &b, &c);
    avg = (a + b + c) / 3.0;
    printf("Diem trung binh: %.2f", avg);
    return 0;
}
Giải thích sự khác nhau giữa phép chia nguyên và phép chia số thực.
Phép chia nguyên: Cả 2 số đều là int → cắt bỏ hoàn toàn phần thập phân (VD: 5 / 2 = 2).
Phép chia số thực: Có ít nhất 1 số là float/double → giữ nguyên phần thập phân chính xác (VD: 5.0 / 2 = 2.5).
Một ví dụ mới chứng minh bản thân đã hiểu kiến thức.
Tính vận tốc đi 15 km trong 2 giờ:
int v1 = 15 / 2;       // Kết quả: 7 (Phép chia nguyên - sai thực tế)
float v2 = 15.0 / 2;   // Kết quả: 7.5 (Phép chia số thực - chính xác)
