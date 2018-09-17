---
layout: post
comments: true
title:  "Bài mở đầu"
<!-- permalink: /toc/ -->
date:   2018-09-18
tags: General
categories: General

---

Trường học không dạy các bạn thiết kế mạch tốc độ cao, trường học chỉ cung cấp cho bạn kiến thức cơ bản. Tôi không định làm lại việc các thầy cô đã làm. Tôi chọn một cách khác để trình bày các khái niệm cơ bản và nâng cao về điện tử, thiết kế mạch high speed, đó là học lý thuyết từ các ví dụ thực tế.

Có một câu nói liên quan giữa lý thuyết và thực hành:

	`There is Nothing More Practical Than A Good Theory` - Kurt Lewin

Do đó, tôi sẽ bắt đầu bằng cách sử dụng một `reference design` phổ biến là kit [Beagle Bone Black][bbb], viết tắt `BBB`. Hình ảnh một kit BBB như hình dưới:

<!-- ![BBB revC][bbb2] -->

<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb.jpg" align = "center" width = "350">
 <div class = "thecap"> Hình 1: Kit Beagle Bone Black RevC. </div>
</div>
<hr>

Các bạn tham khảo thông tin chi tiết về cấu hình phần cứng trên trang [beagleboard.org][bbb]. Dưới đây sơ lược về cấu hình của kit:

*	Processor: AM335x 1GHz ARM® Cortex-A8:
	- 512MB DDR3 RAM\
	- 4GB 8-bit eMMC on-board flash storage
	- 3D graphics accelerator
	- NEON floating-point accelerator
	- 2x PRU 32-bit microcontrollers

*	Software Compatibility
	- Debian
	- Android
	- Ubuntu
	- Cloud9 IDE on Node.js w/ BoneScript library plus much more

*	Connectivity
	- USB client for power & communications
	- USB host
	- Ethernet
	- HDMI
	- 2x 46 pin headers

Đây là một thiết kế Open source, do đó các bạn có thể tải về và thoải mái thay đổi, play around với nó. Lưu ý là BBB được thiết kế trên `Allegro/Orcad` là một phần mềm thương mại. Để sửa được thiết kế bạn cần có license. Tôi dùng phần mềm trên công ty để mở. Nếu chỉ để xem, Allegro có bản Viewer, cho phép bạn xem các layer, path, net.





[bbb]: https://beagleboard.org/black
[bb]: https://beagleboard.org
[bbb2]: https://beagleboard.org/static/ti/product_detail_black_lg.jpg