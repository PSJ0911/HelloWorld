과제
======================================================
현재 시각을 표시하는 앱 코
-------------
```Dart
import 'dart:async';

import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: '현재 시각',
      theme: ThemeData(
        colorScheme: ColorScheme.fromSeed(seedColor: Colors.deepPurple),
      ),
      home: const MyHomePage(title: '현재 시각!'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});
  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  String currentTime = '';

  @override
  void initState() {
    super.initState();
    // 1초마다 시각을 갱신하는 타이머 설정
    Timer.periodic(Duration(seconds: 1), (timer) {
      setState(() {
        currentTime = getCurrentTime();
      });
    });
  }

  // 현재 시각을 반환하는 함수
  String getCurrentTime() {
    final now = DateTime.now();
    final hour = now.hour;
    final minute = now.minute;
    final second = now.second;
    final date = now.toLocal().toString().split(' ')[0]; // yyyy-MM-dd 형식

    String period = hour >= 12 ? '오후' : '오전'; // 오전/오후 구분
    String formattedTime = '${hour > 12 ? hour - 12 : hour}:${minute.toString().padLeft(2, '0')}:${second.toString().padLeft(2, '0')}';

    return '$date\n$period $formattedTime';
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Theme.of(context).colorScheme.inversePrimary,
        title: Text(widget.title),
      ),
      body: Center(
        child: Text(
          currentTime,
          style: TextStyle(
            fontSize: 40,
            fontWeight: FontWeight.bold,
          ),
          textAlign: TextAlign.center,
            ),
        ),
      );
  }
}
```

완성 사진
-----------------
![image]()
