6주차 과제
======================================================
실습
-------------
페이지 203 ~ 208 페이지 내용 실습
-------------
```Dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Practice',
      home: FirstPage(),
    );
  }
}

class FirstPage extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    print('FirstPage - build');
    return Scaffold(
      appBar: AppBar(title: Text('FirstPage!')),
      body: Center(
        child: ElevatedButton(
          child: Text('다음'),
          onPressed: () {
            Navigator.push(
              context,
              MaterialPageRoute(builder: (context) => SecondPage()),
            );
          },
        ),
      ),
    );
  }
}

class SecondPage extends StatefulWidget {
  @override
  _SecondPageState createState() => _SecondPageState();
}

class _SecondPageState extends State<SecondPage> {
  @override
  void initState() {
    super.initState();
    print('SecondPage - initState');
  }

  @override
  void dispose() {
    print('SecondPage - dispose');
    super.dispose();
  }

  @override
  Widget build(BuildContext context) {
    print('SecondPage - build');
    return Scaffold(
      appBar: AppBar(title: Text('SecondPage!!')),
      body: Center(
        child: ElevatedButton(
          child: Text('뒤로'),
          onPressed: () {
            Navigator.pop(context);
          },
        ),
      ),
    );
  }
}
```
