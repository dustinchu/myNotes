# Flutter


## 如何在Flutter移動應用程序的API調用中傳遞基本身份驗證憑據？ 
## [Stack overflow Link](https://stackoverflow.com/questions/50244416/how-to-pass-basic-auth-credentials-in-api-call-for-a-flutter-mobile-application)。

* 假設您的服務器期望username:password組合將其編碼為UTF-8（有關更多詳細信息，請參閱RFC [7617](https://tools.ietf.org/html/rfc7617)），然後使用：

``` dart
import 'dart:convert';

import 'package:http/http.dart';

main() async {
  String username = 'test';
  String password = '123£';
  String basicAuth =
      'Basic ' + base64Encode(utf8.encode('$username:$password'));
  print(basicAuth);

  Response r = await get('https://api.somewhere.io',
      headers: {'authorization': basicAuth});
  print(r.statusCode);
  print(r.body);
}
```

---

## Flutter 中文網 for android 開發者   [link](https://flutterchina.club/flutter-for-android/)

---

## Dart 中文網 [link](http://dart.goodev.org/guides/get-started)

---

## flutter  gitbook 電子書  https://github.com/flutterchina/flutter-in-action

---

##  google flutter免費課程 [HTTP LINK ](https://www.udacity.com/course/build-native-mobile-apps-with-flutter--ud905)

