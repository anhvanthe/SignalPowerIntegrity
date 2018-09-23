---
layout: post
comments: true
title:  "Lý thuyết đường dây truyền tải"
permalink: /2018/09/22/tl/
date:   2018-09-22
tags: Terms
categories: Basic

---

**Trong bài viết này:** 


<a name="-gioi-thieu"></a>

## 1.Giới thiệu
Hôm nay chúng ta sẽ tìm hiểu về lý thuyết đường dây truyền tải (Transmission Line Theory - TL Theory), một lý thuyết cơ bản trong điện-điện tử nói chung và thiết kế mạch High Speed nói riêng. Khi search trên Google với từ khóa `Transmission Line Theory` tôi nhận được `112,000,000` kết quả trong khi với từ khóa "Mark Zuckerberg" là `30,000,000` kết quả. Điều này chứng tỏ lý thuyết này nhận được sự quan tâm của đông đảo sinh viên, NCS, giảng viên và kỹ sư. Tôi thấy rất nhiều trường giảng dạy về lý thuyết này, cho nhiều môn học khác nhau và dùng trong các ứng dụng khác nhau, cho thấy tầm quan trọng của TL Theory.

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_google.jpg" align = "center" width = "">
 <div class = "thecap"> Tìm kiếm trên google với từ khóa Transmission Line Theory. </div>
</div>
<hr>

Các bạn sinh viên ngành điện, điện tử chắc hẳn sẽ được học môn `Lý thuyết mạch` (LTM). Năm thứ 3 đại học tôi được học môn LTM 2, trong đó có phần về TL Theory, với tên gọi Lý thuyết đường dây dài (Mạch thông số rải). Về tên gọi có vẻ hơi khác chút, nhưng về lý thuyết thì giống. Đối với hệ thống truyền tải điện, chẳng hạn 500 KV, khi khoảng cách giữa nguồn phát và đầu thu là lớn (6000 km) thì ngoài mô hình dòng-áp, mô hình đường dây dài còn phải kể theo yếu tố không gian.

<hr>
<div class="imgcap">
 <img src ="/assets/1_tl/tl_ncp.jpg" align = "center" width = "">
 <div class = "thecap"> TL Theory cho truyền tải điện. [1] </div>
</div>
<hr>

<!-- Khi bạn tăng tần số lên, chẳng hạn 2,000,000 lần -->
TL trong Highspeed thì sao? Tương tự như thế, các đường [Microstrip] trên mạch là các TL. [Cable đồng trục][coxial] cũng là một TL.

<a name="-dinh-nghia"></a>




[Microstrip]: https://en.wikipedia.org/wiki/Microstrip
[coxial]: https://en.wikipedia.org/wiki/Coaxial_cable

### Reference
[1] - 

<!-- 
- Idea (loss less) Transmission line model
- Impedance
- Rise time
- Bandwidth
- Reflection
- Plane and Reference Plane
- Retern Path || Ground

 -->