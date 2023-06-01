---
title: 'Flutter Kỳ Truyện (part 1): Cưỡi ngựa xem hoa'
createdAt: 2019-03-12 10:21:33
description: Giới thiệu sơ lược về flutter
tags:
  - flutter
  - technical
  - mobile
---

Flutter là gì?

### Hành tinh Jupiter

Cứ hàng năm vào dịp cuối thu gần đông, các anh hùng keyboard võ lâm cái thế lẫn cùi bắp đều tụ họp về **Hagon **(một thành phố lớn ở **Jupyter**) để tham gia ngày hội công nghệ lớn nhất năm. Đã tới giờ hành lễ, trưởng bối **Gugo** mở lời:

_"Có lẽ dạo gần đây các sư huynh đệ trong và ngoài giang hồ ắt hẳn đều ít nhiều nghe thiên hạ rỉ tai, luyên thuyên về Flutter mà lòng không khỏi tò mò về cái thứ hay ho ấy. Trong đại hội lần này, chúng tôi đã mời về tiến sĩ Bilin, người có nhiều năm kinh nghiệm về Android nói riêng và Flutter nói chung sẽ chủ trì chủ đề lần này"_

_“Bilin, Bilin, Bilin”_ Xung quanh đại hội, sự háo hức ngày một dâng cao, tiếng vỗ tay và reo hò từ hàng người phía dưới ngày một to dần.

Hầu hết các anh hùng đến tham dự đại hội ai nấy đều mong muốn được học hỏi và biết thêm một môn thứ gì đó hay ho, được hiểu rõ hơn về nó thay vì nghe những lời luyên thuyên bên tai. Số còn lại (gọi họ là **Antilovely**) thì tham dự để nói cho cả thế giới biết rằng _"bố m\* còn lạ gì cái này nữa..."_

Từ xa, một người đàn ông bước lên sân khấu đại hội, tiếng reo hò ngày một lớn hơn. Thì ra đó là Bilin, ông là Software Architect của một công ty gần **Hagon**. Ông cầm lấy micro và dõng dạc nói:

> _"Chào toàn thể sư huynh đệ đang có mặt ở đây. Tôi là Bilin, tôi làm software được 15 năm nếu tính cả thời gian OT (nói một cách hoa mỹ là thời gian cày cuốc, nghiên cứu). Ngày hôm nay, tôi rất cảm ơn mọi người đã bỏ thời gian công sức để đến nghe tôi chia sẽ một chút kiến thức của tôi về Flutter và mong nó sẽ giúp đỡ được phần nào về thắc mắc của mọi người. Thôi không làm mất thời gian của mọi người, chúng ta bắt đầu nào!"_

## Flutter là gì?

Flutter là một bộ công cụ đồ họa của Google (Google's UI toolkit) giúp các developer xây dựng các ứng dụng chất lượng, đẹp mắt. Các ứng dụng đó sẽ được **biên dịch nguyên bản** (natively compiled) sang các nền tảng mobie, web và desktop với cùng một mã nguồn duy nhất.

Flutter giúp cho ứng dụng của bạn chạy ổn định, mượt mà và tự nhiên trên nhiều nền tảng khác nhau. Lí do là Flutter đã tối ưu các thành phần như cuộn trang "scroll behavior", kiểu chữ, biểu tượng,...

![Build Flutter App with beautiful UI](https://cdn-images-1.medium.com/max/2000/1*9Oy0zO_ZkxVVKxWw1AOn1w.gif)

### Tại sao nên sử dụng Flutter?

Như các lợi ích đã nói tới như ở trên, Flutter còn có nhiều thứ hay, hỗ trợ các anh em rất nhiều như:

- Cùng một mã nguồn duy nhất nhưng biên dịch được trên nhiều nền tảng giúp bạn giảm được rất nhiều chi phí trong quá trình xây dựng và bảo trì sản phẩm

- Tận dụng tối đa bộ UI của 2 nền tảng mobile được Flutter xây dựng sẵn là IOS (cupertino)và Android (material). Anh em chỉ customize lại nếu thấy cần thiết, còn không cũng rất tiện lợi đúng không nào

- Flutter hỗ trợ animation tận răng, chạy ngon lành trên nhiều nền tảng, giúp cho ứng dụng của các bạn có trải nghiệm tốt hơn rất nhiều

- Flutter hỗ trợ hot-reload trong quá trình phát triển (develop). Anh em không phải cật lực sửa xong build lại (Cơ chế hot-reload như thế nào tôi sẽ giải thích rõ ở phần sau nhé)

- Flutter được cung cấp bởi Google nên anh em sẽ được hỗ trợ (LTS) nếu có lỗi gì từ framework

- Thích thì dùng, không thích thì dùng (deprecated)

![Flutter native perfomance on IOS and Android](https://cdn-images-1.medium.com/max/2000/1*s6XA0f_rzVaLLeAvvO1KoA.gif)

### Flutter ngon như vậy, nhưng phù hợp với ai?

Vì Flutter xây dựng sẵn 2 bộ UI là Material và Cupertino sẽ không có gì khác biệt đối với anh em frontend developer và designer

Đối với các startup thì việc lựa chọn một đối thủ nặng ký như Flutter là cực kỳ phù hợp với ngân sách và khả năng phát triển lâu dài cho ứng dụng của bạn

### Nghe có vẻ hay ho, vậy cơ chế hoặc động của Flutter như thế nào?

Một tên trong hội **Antilovely** luyên thuyên: _"Flutter là một hibrid-app được xây dựng bởi Dart"_

Mọi người nghe hắn nói vậy bèn hỏi nhau _"Vậy Dart là gì, Dart là gì?"_

Mời bạn đón đọc tập tiếp theo: [Flutter Kỳ Truyện (part 2.1): Vạch lá tìm sâu](/posts/flutter-architecture-layer)

### References

- [https://flutter.dev/](https://flutter.dev/)

> Xuất bản lần đầu không tránh khỏi sai sót, mong các bạn góp ý nhé ^^

> Cảm ơn các bạn đã ghé thăm bài viết của mình ❤
