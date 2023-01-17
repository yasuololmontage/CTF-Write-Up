# CTF-Write-Up

        Tuyển Thành Viên Ban Chuyên Môn KCSC - Write-Up
    
    
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
  
  
* TET_IS_YA_BEST (CRYPTO):
   - Đề bài: 1 file txt gồm các ký tự đã bị mã hóa: lyl, rwns dmsfm rn wkmrx myf iyrx pynljorw, jn luy ejvvynl lxrqjljsmrw pynljorw jm ojyl mrh. lyl jn knkrwwi pxsh luy ymq sp trmkrxi ls yrxwi pyexkrxi. eypsxy lyl, ojylmrhyny cxycrxy hrmi lujmvn psx luy luxyy hrjm qrin. luyi gwyrm luyjx uskny rmq qygsxrly fjlu pwsfyxn nkgu rn dkhbkrl lxyy sx cyrgu ewsnnsh. r ukvy rhskml sp pssq fjww ey eskvul eypsxy lyl psx hrdjmv lxrqjljsmrw qjnuyn. ermu gukmv, ermu lyl, vjs gur, asj rmq hkl, …rmq grmqjyn rxy luy pssqn lurl hknl uroy sm lyl uswjqrin. qkxjmv lyl, cyscwy ojnjl luyjx xywrljoyn’ ushyn rmq vjoy fjnuyn. usfyoyx, luy ojylmrhyny eywjyoy lurl luy pjxnl ojnjlsx r prhjwi xygyjoyn jm luy iyrx qylyxhjmyn luyjx psxlkmy psx luy ymljxy iyrx, cyscwy myoyx ymlyx rmi uskny sm luy pjxnl qri fjluskl eyjmv jmojlyq pjxnl. rmsluyx gknlsh jn vjojmv wkgdi hsmyi, fujgu jn ckl jmls r xyq ymoywscy rn r nihesw sp wkgd rmq fjnu psx r myf rvy. lxrqjljsmrwwi, ywqyxn fjww vjoy wkgdi hsmyi ls gujwqxym rmq luy swqynl cyscwy jm luy prhjwi. usfyoyx, msfrqrin, cyscwy grm vjoy jl ls rmismy jmgwkqjmv pxjymqn, crxymln, myjvuesxn,… eynjqyn, ojylmrhyny knkrwwi vs ls crvsqrn sx lyhcwyn ls cxri psx uyrwlu, fyrwlu, nkggynn,… ls ojylmrhyny, lyl jn luy urccjynl ljhy sp rww iyrx rxskmq, hyheyxn jm r prhjwi grm vrluyx lsvyluyx, fujgu jn r hyrmjmvpkw hynnrvyn sp wkmrx myf iyrx pynljorw. rww jm rww, lyl jn rww reskl ergd ls sxjvjmn, ey vssq ls sluyxn, ymtsi luy cxygjskn hshyml, rmq fjnu psx luy eynl ls gshy. luy pwrv jn: dgng{lyl_lyl_lyl_lyl_qym_xsj__gukg_grg_erm_mrh_hsj_lurl_mujyk_nkg_dusy__wko_pxsh_wkwkkkkkkkkkkkk}
   - Hướng giải: Sau khi quan sát em biết chắc phần cuối chính là flag, nên em sử dụng trang web https://www.boxentriq.com/code-breaking/cipher-identifier để xác định dạng mã hóa của đoạn mã. Sau đó em sử dụng https://www.boxentriq.com/code-breaking/cryptogram để giải mã đoạn mã trên, và có được flag như sau:
        KCSC{tet_tet_tet_tet_den_roi_chuc_cac_ban_nam_moi_that_nhieu_suc_khoe_luv_from_luluuuuuuuuuuuu}
   

* EZENC (CRYPTO):
   - Đề bài:  1 file txt gồm các ký tự đã bị mã hóa: 4e544d7a4d44526c4e5451314d544d7a4e7a51304e6a59794e6d51305a5463324e5745304e7a5a6a4e7a553159544d784d7a6b305954597a4d7a457a4f5451304e6a497a4d6a4d354e7a4d304f54557a4e4455324f4459324e54457a5a444e6b
   - Hướng giải: em sử dụng https://gchq.github.io/CyberChef/ để giải mã đoạn mã này theo trình tự: From Hex - From Base64 - From Hex - From Base64
   Cuối cùng em có flag: KCSC{Encoding_Is_Cool!!!}

* FIND ME (REVERSE)
   Đề bài: souce.exe
   *Hướng giải: Em cần phải biết được file exe này được code bằng gì, từ đó xem được source code của chương trình*
   - Đầu tiên em sẽ sử dụng tool Detect It Easy để xem file souce.exe này sử dụng ngôn ngữ nào. Vì sau khi chạy lệnh chương trình biến mất luôn và gài flag giả vào tất cả folder của ổ C. Sau khi sử dụng tool DIE.exe thì nó cho em ra kết quả file souce.exe này được code bằng python với packer là PyInstaller. Nên em đã tìm cách để chuyển ngược lại file này thành file souce.pyc rồi decompile. 
   - Vì file này chạy trên máy của em mà không cần python, nghĩa là file đã được đóng gói nên em cần tool để giải nén file exe này về file pyc. Tiếp theo em sử dụng tool PyInstaller Extractor ở trên github, sau đó đưa file souce.exe vào trong file pyinstxtractor-master để thực hiện việc giải nén. Sử dụng câu lệnh:               $ python pyinstxtractor.py souce.exe
   - Sau đấy sẽ xuất hiện file souce.exe_extracted, thì việc còn lại chỉ là deompyle file souce.pyc về thành souce.py là có thể xem đc source code. Em tìm được tool uncompyle6 ở trên github và em đã sử dụng nó với câu lệnh: uncompyle6 souce.pyc và em đã xem được source. Trong đấy em đã tìm thấy flag là:                        KCSC{T3t_n4y_4nh_kh0ng_th3m_d0t_ph4o_V1_ti3ng_cu0i_3m_r0n_r4_l0ng_4nh_r0i!}
   
   
