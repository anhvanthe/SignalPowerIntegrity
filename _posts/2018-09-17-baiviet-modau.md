---
layout: post
comments: true
title:  "Bài mở đầu"
permalink: /2018/09/17/bai-viet-mo-dau/
date:   2018-09-18
tags: Basic
categories: Basic

---

Trường học không dạy các bạn thiết kế mạch tốc độ cao, trường học chỉ cung cấp cho bạn kiến thức cơ bản. Tôi không định làm lại việc các thầy cô đã làm. Tôi chọn một cách khác để trình bày các khái niệm cơ bản và nâng cao về điện tử, thiết kế mạch high speed, đó là học lý thuyết từ các ví dụ thực tế.

Có một câu nói liên quan giữa lý thuyết và thực hành:

	`There is Nothing More Practical Than A Good Theory` - Kurt Lewin

Do đó, tôi sẽ bắt đầu bằng việc giải thích các khái niệm cơ bản như trở kháng, rise time, bandwidth, transmission line, phối hợp trở kháng dựa trên một `reference design` phổ biến là kit [Beagle Bone Black][bbb], (viết tắt `BBB`). 

Trong blog này, tôi tập trung giới thiệu về phần cứng của kit BBB. Đây là bước cơ sở cho những bài viết sau.

Hình ảnh một kit BBB như hình dưới:

<!-- ![BBB revC][bbb2] -->

<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb_comment.jpg" align = "center" width = "">
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


<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb_block.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 2: Block Diagram. </div>
</div>
<hr>
Đây là một thiết kế Open source, do đó các bạn có thể tải về và thoải mái thay đổi, play around với nó. Lưu ý là BBB được thiết kế trên `Allegro/Orcad` là một phần mềm thương mại. Để sửa được thiết kế bạn cần có license. Tôi dùng phần mềm trên công ty để mở. Nếu chỉ để xem, Allegro có bản Viewer, cho phép bạn xem các layer, net. Cách thứ 2 là bạn dùng một phần mềm thương mại khác là Altium để import vào và xem trên Altium. Có một blog viết khá nhiều bài về Altium là [PCBViet][pcbviet] của **Nguyễn Sỹ Hậu**. Các bạn cần có thể qua bên đó tham khảo. Tôi cũng sẽ có một bài review về các phần mềm thiết kế mạch, các phần mềm mô phỏng trong blog sau.

Quay trở lại với mạch BBB, tôi chụp lại các layer của board như hình 2. Hình 3 là ảnh chụp một số tín hiệu RAM (DDR3) và hình 4 là các đường tín hiệu vi sai (differential pair)
<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb_all_layer.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 3: Top view. </div>
</div>
<hr>

<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb_ram.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 4: DDR3 signals </div>
</div>
<hr>

<hr>
<div class="imgcap">
 <img src ="/assets/0_modau/bbb_diff.jpg" align = "center" width = "">
 <div class = "thecap"> Hình 5: Differential pair signal. </div>
</div>
<hr>

Các bạn chú ý từ thông tin cấu hình của kit BBB, có nhiều các tín hiệu là tín hiệu tốc độ cao (High speed) như tín hiệu giữa Chip và DDR3, tín hiệu HDMI, USB và kể cả RMII (Ethernet). Trong bài tiếp theo, tôi sẽ trình bày về các khái niệm cơ bản như trở kháng đường dây, rise time, bandwidth, phản xạ tín hiệu là những khái niệm quan trọng trong tín hiệu High speed.


Chào thân ái và hẹn gặp lại.

<!-- RAM được sử dụng là DDR3L SDRAM (L - Low power), có `part no` là `MT41K256M16HA-125:E`, dung lượng 512MB, `Data rate` 1600MT/s (Mega Transfer per second). Tôi sẽ có bài trình bày về DDR SDRAM sau. Link download datasheet của DDR3L SDRAM [tại đây][ddr3l]. Tín hiệu giao tiếp giữa AM  -->


## Tham khảo:

[1] [https://beagleboard.org/black](https://beagleboard.org/black)

[2] [https://github.com/beagleboard/beaglebone-black/wiki/System-Reference-Manual](https://github.com/beagleboard/beaglebone-black/wiki/System-Reference-Manual)

File schematic và layout:

[3] [https://github.com/CircuitCo/BeagleBone-Black](https://github.com/CircuitCo/BeagleBone-Black)


<!-- https://www.micron.com/~/media/documents/products/data-sheet/dram/ddr3/4gb_ddr3l_addendum_pachinko.pdf -->

[bbb]: https://beagleboard.org/black
[bb]: https://beagleboard.org
[bbb2]: https://beagleboard.org/static/ti/product_detail_black_lg.jpg
[pcbviet]: http://pcbviet.com/
[ddr3l]: https://www.micron.com/parts/dram/ddr3-sdram/mt41k256m16ha-125-xit?matpart=%7B8D513B85-615C-4DA6-AF9B-29456AAF5133%7D