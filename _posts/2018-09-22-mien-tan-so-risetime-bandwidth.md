---
layout: post
comments: true
title:  "Miền tần số, Rise time, Bandwidth"
permalink: /2018/09/22/mien-tan-so-risetime-bandwidth/
date:   2018-09-29
tags: Basic
categories: Basic

---

**Trong bài viết này:** 

- [1. Miền tần số - Miền thời gian](#-mien-tan-so-mien-thoi-gian)
- [2. Risetime](#-risetime)
- [3. Bandwidth](#-bandwidth)
- [4. Tóm tắt](#-tom-tat)
- [5. Reference](#-Reference)

<a name="-mien-tan-so-mien-thoi-gian"></a>

## 1. Miền thời gian - Miền tần số
<!-- Trong bài viết này tôi trình bày về miền thời gian và  -->
**Miền tần số** là thuật ngữ quen thuộc với nhiều kỹ sư, nhưng ít ai đặt câu hỏi tại sao. Tại sao là miền tần số chứ không phải miền thời gian? Nó có ưu điểm gì mà người ta lại dùng nó? Nó có thật hay là do con người tưởng tượng ra? Bài viết này trả lời cho bạn câu hỏi đó. 

Trước hết, chúng ta cùng quay lại những năm đại cương một chút. Năm thứ 1 Đại học tôi được học môn `Giải tích 3`, trong đó có chương về phép biến đổi Fourier cũng như chuỗi Fourier.

Chuỗi Fourier (Fourier Series) là biểu diễn của một hàm tuần hoàn \\(f(x) \\) theo các hàm `sin` và `cosin`. Hình 1 là 4 thành phần đầu tiên của một chuỗi Fourier của một xung vuông.

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_fourier_series.png" align = "center" width = "">
 <div class = "thecap"> Hình 1: Bốn thành phần đầu của Chuỗi Fourier biểu diễn tín hiệu xung vuông. [1] </div>
</div>
<hr>

Phép biến đổi Fourier chuyển một hàm tuần hoàn theo thời gian thành một hàm theo tần số (tạo hên hàm tuần hoàn đó). Để nhớ lại hoàn chỉnh hơn về phép biến đổi Fourier, các bạn xem thêm tại [Wikipedia][wiki]. Hình 2 là phép biến đổi Fourier của hàm Sin.

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_fs_sin.png" align = "center" width = "">
 <div class = "thecap"> Hình 2: Phép biến đổi Fourier của tín hiệu sin [2] </div>
</div>
<hr>

Ta thấy, tín hiệu sin được biểu diễn theo tần số là 2 gạch đứng tại vị trí tương ứng với tần số của tín hiệu, chiều cao bằng độ lớn của tín hiệu sin. 

Trong thực tế, ta chỉ xét các tín hiệu từ t=0 trở đi (tần số không thể là số âm), do đó ta chỉ xét nửa bên phải của hình 2.

Cơ sở toán học đã đủ, chúng ta cùng nhau đi khám phá **Miền tần số** là gì.

Miền tần số (frequency domain), theo định nghĩa dùng để phân tích các hàm, tín hiệu toán học theo biến số là tần số. Miền tần số hoàn toàn là trong tưởng trí tưởng tượng ra, là giả thiết, thuần túy toán học, chỉ có miền thời gian là có thực. Theo [3], Eric Bogatin viết: "The time domain is the real world. It is the only domain that actually exists."

Nhờ có miền tần số mà các tín hiệu được biểu diễn đơn giản hơn. Như tín hiệu xung vuông 1ns trên hình 3, bao gồm thành phần cơ bản (fundamental) tại tần số 100MHz, các hài bậc lẻ tại 300MHz, 500MHz,...

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_square.png" align = "center" width = "">
 <div class = "thecap"> Hình 3: Tín hiệu xung vuông 1ns </div>
</div>
<hr>

Miền tần số được chuyển đổi từ miền thời gian thông qua phép biến đổi Fourier. Có một số phương pháp thực hiện như:

* Fourier Integral (FI)
* Discrete Fourier Transform (DFT)
* Fast Fourier Transform (FFT)

Phép biến đổi tích phân Fourier: là kỹ thuật toán học chuyển đổi một biểu thức toán học lý tưởng trong miền thời gian thành một hàm toán mới trên miền tần số. FI hay còn gọi là CFI (Continuous Fourier transform - Biến đổi Fourier liên tục)

Trong thực tế, chúng ta không nhìn thấy tín hiệu biến đổi liên tục theo thời gian, mà chỉ thấy các điểm rời rạc được đo liên tục trong một chu kì T. Lấy ví dụ là một tín hiệu clock có chu kì 1ns, có biên độ 1V. Để biểu diễn một chu kì của tín hiệu này, ta cần đo đo liên tục 1000 điểm cách nhau 1ps như hình 4.

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_1ns_pulse.png" align = "center" width = "">
 <div class = "thecap"> Hình 4: Tín hiệu xung vuông 1ns được đo liên tục và biểu diễn theo thời gian</div>
</div>
<hr>

Để chuyển tín hiệu trên hình 4 sang miền tần số, ta sử dụng kỹ thuật số để tính toán (thay vì sử dụng tích phân như FI).
Đó là ý tưởng của phương pháp DFT. 

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_1ns_pulse_fd.png" align = "center" width = "">
 <div class = "thecap"> Hình 5: Tín hiệu xung vuông 1ns được đo liên tục và biểu diễn trên miền tần số</div>
</div>
<hr>


FFT, ý tưởng giống DFT, ngoại trừ sử dụng một gải thuật **đại số ma trận** để tính toán giá trị biên độ. Nếu số điểm tính toán là bội của 2, ví dụ 256, 1024,... thì tốc độ tính toán sẽ nhanh hơn DFT từ 100 đến 1000 lần.


<a name="-risetime"></a>

## 2. Rise-time
Rise Time (RT) cho biết thời gian tín hiệu chuyển tiếp từ trạng thái thấp sang trạng thái cao. Theo định nghĩa, rise time là khoảng thời gian tín hiệu đạt 10% đến 90% độ lớn của tín hiệu đó. Người ta gọi là 10-90 rise time. 

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_risetime.PNG" align = "center" width = "">
 <div class = "thecap"> Hình 6: Định nghĩa rise time </div>
</div>
<hr>


Có một số tài liệu định nghĩa khoảng thời gian từ 20% đến 80% của độ lớn tín hiệu. Thông số rise time là một thông số quan trọng đối với các tín hiệu high speed. 



<a name="-bandwidth"></a>

## 3. Bandwidth
Bandwidth (BW) và Rise time (RT) có mối quan hệ chặt chẽ với nhau. Rise time sẽ giới hạn BW của tín hiệu theo công thức:

\\[
BW = 0.35 / RT
\\]

Thông thường, RT cỡ ns (nano giây) hoặc ps (pico giây), nên BW cỡ GHz.

Thông số RT của một tín hiệu có thể lấy từ datasheet của nhà sản xuất, như hình 7.

<hr>
<div class="imgcap">
 <img src ="/assets/2/2_risetime_table.PNG" align = "center" width = "">
 <div class = "thecap"> Hình 7: Thông số rise time của IC LAN8710A </div>
</div>
<hr>

Theo thông số từ Hình 7, bandwidth của tín hiệu RMII là: \\(BW = 0.35/5ns = 0.07GHz = 70MHz\\)

Quay lại schematic của BBB, tín hiệu  **MII1_TXCLK** là tín hiệu clock 50MHz từ AM3358 đưa tới LAN8710A. Với rise time và bandwidth như vậy, clock 50MHz là phù hợp. Giả sử muốn đẩy tốc độ lên 1000Mbps, sử dụng các chuẩn như GMII, RGMII thì cũng không được, do clock của RGMII là 125MHz. (Tất nhiên là sẽ phải đổi PHY rồi).

<a name="-tom-tat"></a>
## 4. Tóm tắt
Bài viết này trình bày những khái niệm cơ bản của SI:
* Miền tần số, miền thời gian
* Rise time
* Bandwidth



<a name="-reference"></a>

## 5. Reference
[1] https://en.wikipedia.org/wiki/Fourier_series

[2] https://www.astro.umd.edu/~lgm/ASTR410/ft_ref2.pdf

[3]- Signal and Power Integrity - Simplified 2nd - Eric Bogatin


<!-- ========================== -->
[wiki]: https://en.wikipedia.org/wiki/Fourier_transform
