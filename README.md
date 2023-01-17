# CTF-Write-Up

        ***Tuyển Thành Viên Ban Chuyên Môn KCSC - Write-Up***
    
    
* PHPRI PHPRAI (WEB)
    Đề bài: http://47.254.251.2:8889/
  *Hướng giải: Theo em đây là tổng gộp của 5 bài nhỏ hợp lại, nên em cần phải xử lý từng bài nhỏ để trang hiện đủ cả 5 phần của flag.*
  *Cả 5 bài này đều là phải nhập tham số vào từ URL sao cho tham số đó thỏa mãn yêu cầu đề bài để hiện ra flag.*
  - Bài 1: Em cần phải nhập vào 2 mảng 1[] và 2[] sao cho nó không rỗng, và thỏa mãn điều kiện 2 chuỗi em nhập vào khác nhau, mà md5 Hash của 2 chuỗi này giống nhau. Em đã chọn mảng &1[] = 1 và &2[] = 2 vì em biết giá trị của nó khác nhau, nhưng khi khi md5 2 mảng này nó ra lỗi, 2 mảng cùng lỗi thì giống nhau, em đã thử với các số và nhận ra chỉ cần là 2 số khác nhau thì sẽ thỏa mãn nên em đã chọn 1 và 2. Nếu không chọn đúng theo yêu cầu đề bài thì em chắc phải chọn 1 cặp chuỗi mà cùng MD5 Hash mà có giá trị khác nhau, em đã thử và nó cũng đúng. Cuối cùng em ra được phần đầu của flag: KCSC{B0_u_Bu_S4
  - Bài 2: Em cần phải nhập vào 1 mảng 3[] sao cho khi so sánh với chuỗi flag thì nó trùng, nên em đoán nó là trống, nên em đã nhập là &3[]="" và ra được phần flag tiếp theo: C_8usssssss_htt
  - Bài 3: Em cần phải nhập vào chuỗi 4 vừa có phần đầy đủ phần từ 1.4e5 mà nó cũng phải khác 1.4e5 sau khi dùng lệnh trim, mà lệnh trim ở đây không không cắt đi thứ gì, nên em đã nhập là 01.4e5 và được phần flag tiếp theo: ps://www.youtub
  - Bài 4: Em cần phải nhập vào chuỗi 5 có giá trị là 69, và trong mảng phải khác 69, đồng thời sau khi trim thì độ dài chuỗi là 2. Thì em nghĩ là sẽ để thêm dấu cách, nên nó sẽ là &5=%2069, sau khi trim thì nó 69 nên thỏa mãn yêu cầu đề bài. Em có phần flag tiếp theo: e.com/watch?v=x
  - Bài 5: Em cần phải nhập vào chuỗi 6 mà khi thay thế bằng câu lệnh preg_replace. Theo đề thì nó sẽ thay đổi chuỗi mà em nhập vào bằng khoảng trống, nghĩa là giờ em cần phải nhập chữ KaCeEtCe như nào để khi tham số của em bị xóa hết chữ KaCeEtCe thì vẫn còn 1 chữ KaCeEtCe nữa. Em không thể dùng chuỗi 'KaCeEtCeKaCeEtCe' vì như vậy nó sẽ xóa hết chuỗi và không thỏa mãn đề bài, nên đã chọn là đẩy 1 chữ e về đằng sau, cụ thể là: &6= KaCeEtCKaCeEtCee. Lúc này câu lệnh kia sẽ thay chữ 'KaCeEtCe' thành khoảng trống, thì ghép lại sẽ thành chữ 'KaCeEtCe'. Và em có phần cuối của flag: QtC3F8fH6g} 
  
  Như vậy, với payload đầy đủ là: http://47.254.251.2:8889/?2[]=1&1[]=2&3[]=%22%22&4=01.4e5&5=%2069&6=KaCeEtCKaCeEtCee
    -> Em có flag đầy đủ: KCSC{B0_u_Bu_S4C_8usssssss_https://www.youtube.com/watch?v=xQtC3F8fH6g}
