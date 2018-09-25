---
layout: post
comments: true
title:  "Lý thuyết đường dây truyền tải"
permalink: /2018/09/22/ly-thuyet-duong-day-truyen-tai/
date:   2018-09-22
tags: Basic
categories: Basic

---

**Trong bài viết này:** 


<a name="-gioi-thieu"></a>

## 1.Giới thiệu
Hôm nay chúng ta sẽ tìm hiểu về lý thuyết đường dây truyền tải (Transmission Line Theory - TL Theory), một lý thuyết cơ bản trong điện-điện tử nói chung và thiết kế mạch High Speed nói riêng. Khi search trên Google với từ khóa `Transmission Line Theory` tôi nhận được `112,000,000` kết quả trong khi với từ khóa "Mark Zuckerberg" là `30,000,000` kết quả. Điều này chứng tỏ lý thuyết này nhận được sự quan tâm của đông đảo sinh viên, NCS, giảng viên và kỹ sư. Tôi thấy rất nhiều trường giảng dạy về lý thuyết này, cho nhiều môn học khác nhau và dùng trong các ứng dụng khác nhau, cho thấy tầm quan trọng của TL Theory.

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_google.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 1: Tìm kiếm trên google với từ khóa Transmission Line Theory. </div>
</div>
<hr>

Các bạn sinh viên ngành điện, điện tử chắc hẳn sẽ được học môn `Lý thuyết mạch` (LTM). Năm thứ 3 đại học tôi được học môn LTM 2, trong đó có phần về TL Theory, với tên gọi Lý thuyết đường dây dài (Mạch thông số rải). Về tên gọi có vẻ hơi khác chút, nhưng về lý thuyết thì giống. Đối với hệ thống truyền tải điện, chẳng hạn 500 KV, khi khoảng cách giữa nguồn phát và đầu thu là lớn (6000 km) thì ngoài mô hình dòng-áp, mô hình đường dây dài còn phải kể theo yếu tố không gian.

Theo công thức \\( \lambda = \frac{C}{f} \\) với C là tốc độ ánh sáng, f là tấn số của tín hiệu, ta có:

\\[
\lambda = 3 \times 10^8 / 50 = 6 \times 10^6 m
\\]
Hay với tín hiệu sin có tần số 100MHz được truyền đi trên đường mạch có độ dài 10 inch (25.4 cm), có bước sóng là \\(\lambda = 3m\\).
Dù tín hiệu của bạn có là điện lưới (50Hz) hay tín hiệu Clock của DDR3 SDRAM cỡ hàng trăm MHz, khi độ dài đường truyền là đủ lớn so với bước sóng, ta phải tính yêu tố độ dài đường truyền tín hiệu vào trong mô hình tính toán. 

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_ncp.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 2: TL Theory cho truyền tải điện. [3] </div>
</div>
<hr>

Ngoài ví dụ về đường truyền tải điện là một TL, có nhiều TL ở cấp độ bo mạch như [Cable đồng trục][coxial], các đường [Microstrip][Microstrip]. 

<a name="-dinh-nghia"></a>
## 2. Định nghĩa
Theo [1], TL được định nghĩa như sau:

`A transmission line is formed with two or more conductors. The signal conductor carries the signal energy from a generator to a load,
and the second conductor (the return) completes the circuit by returning the signal current back to the generator.`

Tạm dịch là: Một đường truyền tải được cấu thành từ hai hay nhiều dây dẫn. Dây dẫn tín hiệu mang tín hiệu từ nguồn đến tải và dây dẫn thứ 2 (dây dẫn trở về) khép mạch kín bằng cách dẫn tín hiệu trở lại nguồn. 

Tôi thích cách định nghĩa của Eric Bogatin trong [2] hơn, nó đơn giản và dễ hiểu:

`
Fundamentally, a transmission line is composed of any two conductors that have length. This is all it takes to make a transmission line.`

`To distinguish the two conductors, we refer to one as the signal path and the other as the return path.`

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_tl.png" align = "center" width = "">
 <div class = "thecap"> Hình 3: Đinh nghĩa một TL. [2] </div>
</div>
<hr>

<a name="-mo-hinh-toan"></a>
## 3. Mô hình toán
Xét một TL như hình 3 có độ dài z, ta chia nhỏ thành các phần tử giống nhau, có độ dài \\( \Delta z \\) và có các thông số giống nhau như hình 4.

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_tl_deltaz.png" align = "center" width = "">
 <div class = "thecap"> Hình 4: Chia nhỏ TL thành các phần tử </div>
</div>
<hr>

Mỗi phần tử có các thông số như sau:

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_tl_rlgc.png" align = "center" width = "">
 <div class = "thecap"> Hình 5: Mô hình RLGC </div>
</div>
<hr>

Mô hình như trên được gọi là `Lumped-element circuit model` (Mô hình thông sổ rải) hay mô hình `RGLC`.

* R' biểu diễn cho điện trở của dây dẫn trên một đơn vị độ dài (Ohm/m) 
* L' biểu diễn cho điện cảm của dây dẫn trên một đơn vị độ dài (H/m) 
* G' biểu diễn cho điện dẫn của dây dẫn trên một đơn vị độ dài (S/m) 
* C' biểu diễn cho điện dung của dây dẫn trên một đơn vị độ dài (F/m) 

Với ý tưởng như vậy, áp dụng định luật Kirchhoff viết các phương trình dòng, áp, bạn sẽ tìm ra được phương trình đặc trưng của TL. Tham khảo tài liệu [3] hoặc [1] để biết từng bước tính toán. 

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_equation.png" align = "center" width = "">
 <div class = "thecap"> Hình 5: Phương trình biểu diễn TL </div>
</div>
<hr>

Phương trình này cho thấy mối liên hệ giữa dòng điện, điện áp và các phần tử R,G,L,C.

Người ta gọi 

\\[
\gamma = \sqrt{(R' + j\omega L')(L' + j\omega C')}
\\]

là hằng số lan truyền.


Và
\\[
Z_o = \sqrt{ \frac{R' + j\omega L'}{G' + j\omega C'} }
\\]
là trở kháng đặc trưng.

<a name="-tro-khang-dac-trung"></a>
## 4.Trở kháng đặc trưng
<!-- Để hiểu rõ hơn về **Trở kháng đặc trưng** (characteristic impedance) -->
Trở kháng đặc trưng (characteristic impedance), thường được gọi vắn tắt là trở kháng đã gây ra nhiều hiểu lầm và sự lẫn lộn cho nhiều kỹ sư. Khi nói: Trở kháng đường dây HDMI là 90\\(\Omega \\)  **thì có nghĩa là đường tín hiệu đó có điện trở là 90 Ohm hay trở kháng đặc trưng của đường truyền tín hiệu là 90\\(\Omega \\)?**

Nhiều bạn nói ngay được câu trả lời nằm ở vế sau. Như tôi, dù chưa biết gì về TL và Trở kháng đặc trưng cũng có thể suy luận được là vế sau (vì điện trở chỉ khoảng vài m\\(\Omega \\)).

Để hiểu rõ hơn về **Trở kháng đặc trưng**, chúng ta cùng phân tích hình 6:

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_tl_wave.png" align = "center" width = "">
 <div class = "thecap"> Hình 6: Sóng đến và sóng phản xạ trên TL </div>
</div>
<hr>

Đầu tiên, tín hiệu highspeed là một microwave, áp dụng những lý thuyết trong vật lý được học về sóng và phản xa để giải thích hiện tượng phản xạ tín hiệu. Tín hiệu đến là \\(V_o^+, I_o^+ \\). Khi tín hiệu đến gặp tải, môi trường truyền dẫn bị thay đổi gây ra hiện trượng phản xa. Tín hiệu phản xạ là \\(V_o^-, I_o^- \\). Yếu tố `môi trường truyền dẫn bị thay đổi gây ra hiện tượng phản xạ sóng` là yếu tố then chốt ở đây. Bạn đọc nên nhớ kĩ. Nó là cơ sở cho một loạt các khái niệm cũng như công việc bạn phải làm trong thiết kế như: phối hợp trở kháng, termination,...

Ta có: 
\\[
\frac{V_o^+}{I_o^+} = Z_o = \frac{-V_o^-}{I_o^-}
\\]
từ đó suy ra 
\\[
Z_o = \frac{R' + j\omega L'}{\gamma} = \sqrt{ \frac{R' + j\omega L'}{G' + j\omega C'} }
\\]
như đã nêu ra ở mục 3.

Ta thấy, \\(Z_o \\) phụ thuộc vào đặc trưng của đường dẫn \\(R', G', L', C' \\) và tần số của tín hiệu (\\(\omega = 2\pi f \\) ).



**(Còn tiếp)**



[Microstrip]: https://en.wikipedia.org/wiki/Microstrip
[coxial]: https://en.wikipedia.org/wiki/Coaxial_cable

## Reference
[1] - Understanding Signal Integrity - Stephen C. Thierauf

[2] - Signal and Power Integrity - Simplified 2nd - Eric Bogatin

[3] - https://sites.google.com/site/ncpdhbkhn/bai-giang/ly-thuyet-mach

<!-- 
- Idea (loss less) Transmission line model
- Impedance
- Rise time
- Bandwidth
- Reflection
- Plane and Reference Plane
- Retern Path || Ground

 -->