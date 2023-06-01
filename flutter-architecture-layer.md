---
title: 'Flutter Kỳ Truyện (part 2.1): Vạch lá tìm sâu'
createdAt: 2019-03-12 10:21:33
description: Tìm hiểu về kiến trúc flutter
tags:
  - flutter
  - technical
  - mobile
---

Tìm hiểu về kiến trúc của Flutter - Flutter framework layer

### Hành tinh Jupiter

Mọi người nghe hắn nói vậy bèn hỏi nhau: _“Vậy Dart là gì, Dart là gì?”_

Bilin đang thuyết trình ở trên thì nghe thấy, ông nói lớn:

_"Tôi biết quý vị ở đây đang rất nôn nóng nhưng với kinh nghiệm nhiều năm, tôi sẽ dẫn dắt mọi người đi từng bước thật chậm nhưng rất chắc chắn để mọi người cùng hiểu rõ cơ chế và các vấn đề sâu rộng không chỉ là Flutter... "_

Bỗng hội trường lặng im, đám đông không còn phát ra tiếng động nào.

### Flutter Architecture

Bạn có thể hiểu kiến trúc của Flutter như là một chương trình được cấu tạo từ 3 thành phần riêng biệt (layers) gồm Framework, Engine và Platform.

![](https://cdn-images-1.medium.com/max/2000/0*rx2dEzMZUpxSbJmy.png)

#### 1.Framework

Đây là lớp framework được xây dựng sẵn bởi **Dart**, trong đó có một số library điển hình như:

> **Dart**: Một ngôn ngữ được Google giới thiệu lần đầu tiên vào 10–12–2011 tại hội thảo GOTO. Chúng ta sẽ tìm hiểu chi tiết về về Dart trong các bài viết sắp tới

#### [Foundation](https://api.flutter.dev/flutter/foundation/foundation-library.html)

Đây được xem là core library, định nghĩa và cung cấp những **_utility classes, functions _**và được nhiều lớp (layer) khác sử dụng trong Flutter.

#### [Animation](https://api.flutter.dev/flutter/animation/animation-library.html)

Thư viện này cung cấp các khối xây dựng cơ bản (basic building blocks) cho việc thực hiện hóa các chuyển động trong flutter.

Các lớp khác của framework sử dụng các khối này để hỗ trợ xây dựng các chuyển động nâng cao cho ứng dụng.

Thư viện này được xây dựng dựa trên các library gồm **core dart libraries **và [\*\*physics](https://api.flutter.dev/flutter/physics/physics-library.html)\*\* library

> Chúng ta sẽ đi sâu vào animation trong flutter ở một bài viết sau. Các bạn nhớ đón đọc nhé <3

![](https://cdn-images-1.medium.com/max/2000/0*gr6m4FB-xDe3_nMR.gif)

#### [Painting](https://api.flutter.dev/flutter/painting/painting-library.html)

Thư viện vẽ (painting) bao gồm nhiều classes được xây dựng để gọi tới **Flutter engine’s painting API **từ đó hỗ trợ để xây dựng giao diện với nhiều mục đính khác nhau trong flutter.

Một số ví dụ cần painting như phóng to, thu nhỏ hình ảnh (scale image), nội suy bóng mờ (interpolation of shadow), vẽ khung, viền khung (border-box), vv...

Một số lớp điển hình là [TextPainter](https://api.flutter.dev/flutter/painting/TextPainter-class.html) được sử dụng để painting text hay [Decoration](https://api.flutter.dev/flutter/painting/Decoration-class.html) (hay cụ thể là [BoxDecoration](https://api.flutter.dev/flutter/painting/BoxDecoration-class.html)) để vẽ khung/hộp,..

![](https://cdn-images-1.medium.com/max/2000/0*CZSze09mbjCbJYCX.gif)

#### [Gesture](https://api.flutter.dev/flutter/gestures/gestures-library.html)

Thư viện được xây dựng để nhận dạng các tương tác cử chỉ (gesture) của người dùng như Drag, Long Press, Tap, vv...

![](https://cdn-images-1.medium.com/max/2000/0*t41uX9eei8NVF92q.png)

#### [Rendering](https://api.flutter.dev/flutter/rendering/rendering-library.html)

Trong Flutter, UI components được tổ chức dưới dạng cây phân tầng (hierarchy tree) gần giống với DOM Tree trong HTML, khác biệt ở chỗ mỗi node trong HTML là HTML element thì ở trong Flutter là [RenderObject](https://api.flutter.dev/flutter/rendering/RenderObject-class.html)

Rendering Tree là hệ thống layout cấp thấp (low-level) và painting được tổ chức dưới dạng Tree Object, với những object là lớp kế thừa của RenderObject.

Widget được xây dựng theo dạng cây với những object là lớp kế thừa của RenderObject, cho nên cũng có thể nói widget là một dạng TreeObject. Thông thường thì developer không cần phải làm việc trực tiếp với RenderObject mà sẽ làm việc thông qua widget.

![Example for Flutter Text Rendering](https://cdn-images-1.medium.com/max/2000/0*6-h-gWJ2lWTzob5v.png)

#### [Widgets](https://api.flutter.dev/flutter/widgets/widgets-library.html)

Flutter Widget được xây dựng bởi Dart và lấy cảm hứng từ [React](https://reactjs.org).

Ý tưởng trọng tâm của widgets là bạn sẽ xây dựng UI dựa trên các widgets này. Widgets nhận và lưu trữ trạng thái (state) của UI và widget sẽ được rebuild nếu state thay đổi.

Widget có 2 dạng là StatefulWidget và StatelessWidget

Những kiến thức theo tôi nếu bạn đã có thì rất dễ để tiếp cận với Flutter widget gồm: [React Component](https://reactjs.org/docs/react-component.html), [Dumb and Smart Component](https://medium.com/@dan_abramov/smart-and-dumb-components-7ca2f9a7c7d0), [FlexBox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

![Widget architecture](https://cdn-images-1.medium.com/max/2000/0*3kz_OR3VV08WWVq8.jpg)

> Chúng ta sẽ tìm hiểu sâu hơn và so sánh StatefulWidget và StatelessWidget ở một bài khác, các bạn nhớ đón đọc nhé

#### [Material](https://api.flutter.dev/flutter/material/material-library.html)

Được xây dựng từ widgets library và thực hiện hóa theo chuẩn Material Design

Tìm hiểu thêm về Material design: [https://material.io/design/](https://material.io/design/)

![](https://cdn-images-1.medium.com/max/2000/0*nQ90pF0QFKrBNwdP.jpg)

#### [Cupertino](https://api.flutter.dev/flutter/cupertino/cupertino-library.html)

Được xây dựng từ widgets library và thực hiện hóa theo ngôn ngữ thiết kế của iOS hiện tại.

Tìm hiểu thêm về iOS interface design: [https://developer.apple.com/design/human-interface-guidelines/ios/overview/themes/](https://developer.apple.com/design/human-interface-guidelines/ios/overview/themes/)

![](https://cdn-images-1.medium.com/max/2000/0*0V6_bYoZdnAi-3vu.jpg)

### Hành tinh Jupiter

Mọi người vẫn chăm chú nghe Bilin giảng thuyết, bỗng dưng Bilin hỏi lớn:

_"Tôi đã trình bày cho quý vị xong kiến thức về lớp framework của Flutter architecture, liệu quý vị nào có thắc mắc cần hỏi tôi không?"_

Hội trường im lặng, mọi người đang ngẫm lại những kiến thức vừa nghe lúc nãy. Hầu như ai cũng đang như mê ngủ, vừa nghĩ vừa gật đầu ra vẻ hiểu biết thật sự. Thật ra, một số **antilovely** vẫn là người trên thông thiên văn, dưới tường địa lý nhất, họ đang chờ thời cơ để bóc phốt Bilin mà vẫn chưa có được cơ hội đó.

Bilin lại lớn tiếng: _"Nếu quý vị có thắc mắc gì hãy comment xuống dưới, sau hội nghị tôi có online medium và trả lời các vị"_

Nghe vậy cả hội trường vỗ tay không ngừng, vừa vỗ tay vừa đồng thanh: _"nói tiếp phần sau đi Bilin"_

Mời bạn đón đọc tập tiếp theo: **Flutter Kỳ Truyện (part 2.2): Vạch lá tìm sâu - Fluter architecture - Flutter engine layer**

### References

- [https://flutter.dev/](https://flutter.dev/)

- [https://api.flutter.dev/](https://api.flutter.dev/)

> Xuất bản lần đầu không tránh khỏi sai sót, mong các bạn góp ý nhé ^^

> Cảm ơn các bạn đã ghé thăm bài viết của mình ❤
