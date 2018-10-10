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



<a name="-gioi-thieu"></a>

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

Miền tần số được chuyển đổi từ miền thời gian thông qua phép biến đổi Fourier. Có một số phương pháp thực hiện như:

* Fourier Integral (FI)
* Discrete Fourier Transform (DFT)
* Fast Fourier Transform (FFT)

...

(typing)


<!-- <a name="-dinh-nghia"></a>
## 2. 
 -->



## Reference
[1] https://en.wikipedia.org/wiki/Fourier_series

[2] https://www.astro.umd.edu/~lgm/ASTR410/ft_ref2.pdf

[3]- Signal and Power Integrity - Simplified 2nd - Eric Bogatin


<!-- ========================== -->
[wiki]: https://en.wikipedia.org/wiki/Fourier_transform