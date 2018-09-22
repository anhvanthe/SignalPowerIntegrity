---
layout: post
title:  "Giới thiệu về blog"
date:   2018-09-12 21:03:33 +0700
categories: General
---
Lí do và mục đích tôi đã nêu rõ trong phần [`About me`][About-me], không cần nói lại nữa.

Tôi gọi các bài viết trong blog này là các `tutorial` vì nó được viết bởi cá nhân cho mục đích cá nhân. Kiến thức thu thập từ nhiều nguồn khác nhau. Tôi sẽ cố gắng trích dẫn đầy đủ các tài liệu tham khảo, nguồn các bài viết, các cuốn sách. Đôi khi tôi sẽ chỉ dịch các bài báo hoặc tóm tắt những bài viết tôi đọc được.

Blog này được tạo  trên nền tảng Jekyll, dựa vào các bài hướng dẫn online và đặc biệt là cuốn sách `20 giờ đầu tiên - Cách học nhanh bất cứ thứ gì` của tác giả Josh Kaufman. Tôi đọc cuốn sách này từ năm 2015, với mong muốn gia tăng tốc độ học các kiến thức mới, cụ thể hơn là cách dùng autocad (tại thời điểm tôi đọc cuốn sách). Khi đọc tôi có lướt qua chương 6, Lập trình nhưng lại nghĩ mình chẳng bao giờ cần dùng đến một ngôn ngữ bậc cao như Ruby, cũng không có ý định làm web vì tôi đã có blog trên wordpress. Và rồi khi có ý định làm một blog mới với tên miền của riêng mình, tôi nhớ đến cuốn sách liền lấy ra đọc lại quá trình tạo blog của tác giả.

Tôi không dùng `sinatra` như tác giả, mà dùng `Jekyll`. Template của blog được dùng từ mã nguồn của anh Vũ Hữu Tiệp, tác giả blog [Machine Learning Cơ bản][ml-coban], trên nền tảng Windows 10. Nếu bạn có định muốn làm một blog tương tự thì tham khảo các đường link sau:

[1- Ruby-Lang](https://www.ruby-lang.org/en/downloads/)

[2- Jekyll](https://jekyllrb.com/docs/pages/)

[3- tiepvupsu.github.io](https://github.com/tiepvupsu/tiepvupsu.github.io)

Với Windows 10, bạn tải [RubyInstaller](https://rubyinstaller.org/) `WITH DEVKIT`, version tôi sử dụng là [rubyinstaller-devkit-2.4.4-2-x64.exe](https://github.com/oneclick/rubyinstaller2/releases/download/rubyinstaller-2.4.4-2/rubyinstaller-devkit-2.4.4-2-x64.exe) theo recommend của trang. Tôi khuyên bạn nên theo recommendation nếu bạn chưa biết gì. (Còn nếu bạn biết gì rồi thì chắc hẳn đã không đọc tiếp tới đây :D)

Bạn bật terminal lên và gõ:

	gem install jekyll bundler

Ruby sẽ tự động cài jekyll và Bundler. Đây là hai package cần dùng để build trang web của bạn.

Để khởi đầu suôn sẻ, bạn nên theo [Step by Step Tutorial][step-by-step-tutorial] này. Goodluck!




<!-- You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk]. -->

[About-me]: /about
[ml-coban]: https://machinelearningcoban.com
[step-by-step-tutorial]: https://jekyllrb.com/docs/step-by-step/01-setup/

<!-- [jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
 -->