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

- [1. Giới thiệu](#-gioi-thieu)
- [2. Định nghĩa](#-dinh-nghia)
- [3. Mô hình toán](#-mo-hinh-toan)
- [4. Trở kháng đặc trưng](#-tro-khang-dac-trung)
- [5. Tóm tắt](#-tom-tat)
- [6. Reference](#-Reference)

<a name="-gioi-thieu"></a>

## 1. Giới thiệu
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
## 4. Trở kháng đặc trưng
<!-- Để hiểu rõ hơn về **Trở kháng đặc trưng** (characteristic impedance) -->
Trở kháng đặc trưng (characteristic impedance), thường được gọi vắn tắt là trở kháng đã gây ra nhiều hiểu lầm và sự lẫn lộn cho nhiều kỹ sư. Khi nói: Trở kháng đường dây HDMI là 100\\(\Omega \\)  **thì có nghĩa là đường tín hiệu đó có điện trở là 90 Ohm hay trở kháng đặc trưng của đường truyền tín hiệu là 100\\(\Omega \\)?**

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

Ta thấy, \\(Z_o \\) phụ thuộc vào đặc tính của đường dẫn \\(R', G', L', C' \\) và tần số của tín hiệu (\\(\omega = 2\pi f \\) ). 
\\(Z_o \\) không phụ thuộc vào tải. 

Quay trở lại câu hỏi ở trên, yêu cầu trở kháng đường dây HDMI là 100\\(\Omega \\), ta phải thiết kế (độ rộng đường mạch và [stack-up][stackup]) sao cho trở kháng đặc trưng của đường truyền HDMI là 100\\(\Omega \\). 

Công thức biễu diễn **Trở kháng đặc trưng** ở trên là công thức tổng hợp, chứa các thông số đường truyền. Xét trường hợp lý tưởng \\(R' = 0, G' = 0 \\), người ta gọi là **đường truyền không tổn hao** (The lossless transmission line). Khi đó:
\\[
Z_o = \sqrt{\frac{L'}{C'}}
\\]

**Trở kháng đặc trưng** của trường truyền không tổn hao chỉ phụ thuộc vào các thông số \\(L', C' \\).

Ví dụ 1:

Tính toán trở kháng của một TL không tổn hao có thông số C' = 3.3pF, L' = 8.25nH.

Kq: \\(Z_o = 50\Omega\\)


Trong thực tế thiết kế, bạn sẽ không gặp vấn đề như **Ví dụ 1**, mà là bài toán ngược lại và tất nhiên sẽ phức tạp hơn chút: Bạn biết trở kháng đường dây yêu cầu, TL của bạn là một Microstrip Line, bạn vật liệu làm PCB, độ dày,... Công việc cần làm là tính toán độ rộng đường dây để bạn layout đạt được trở kháng yêu cầu.

Ví dụ 2:
Đường tín hiệu bạn đang layout yêu cầu đạt trở kháng đặc trưng \\(Z_o = 50\Omega\\) chạy trên lớp TOP. Lớp Reference là lớp thứ 2 (Plane GND). Vật liệu PCB là FR-4 có `Dielectric constant` (hằng số điện môi) \\(\epsilon_r = 4\\). Chiều cao lớp điện môi là h = 0.2mm. Tính toán độ rộng đường dây (w) để TL đạt được trở kháng đặc trưng yêu cầu.

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_ms.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 6: Sóng đến và sóng phản xạ trên TL </div>
</div>
<hr>


Cách nhanh nhất để tính toán độ rộng đường dây là dùng các công cụ tính toán online như:

* [Online tool](https://www.pasternack.com/t-calculator-coax-cutoff.aspx)
* [Offline tool - Saturn](https://www.saturnpcb.com/pcb_toolkit/)

Bạn tự tìm ra đáp án của mình và comment ở phần Comments nếu muốn trao đổi thêm nhé :D 

<a name="-tom-tat"></a>
## 5. Tóm tắt
* Lý thuyết về đường truyền tín hiệu, đường truyền tín hiệu không tổn hao và ứng dụng thực tế.
* Cơ sở lý thuyết cho thiết kế mạch tốc độ cao


<a name="-Reference"></a>
## 6. Reference
[1] - Understanding Signal Integrity - Stephen C. Thierauf

[2] - Signal and Power Integrity - Simplified 2nd - Eric Bogatin

[3] - [https://sites.google.com/site/ncpdhbkhn/bai-giang/ly-thuyet-mach](https://sites.google.com/site/ncpdhbkhn/bai-giang/ly-thuyet-mach)

[4] - [http://www.emtalk.com/mscalc.php](http://www.emtalk.com/mscalc.php)



[Microstrip]: https://en.wikipedia.org/wiki/Microstrip
[coxial]: https://en.wikipedia.org/wiki/Coaxial_cable
[stackup]: http://www.hottconsultants.com/techtips/pcb-stack-up-1.html
<!-- 
- Idea (loss less) Transmission line model
- Impedance
- Rise time
- Bandwidth
- Reflection
- Plane and Reference Plane
- Retern Path || Ground

 -->