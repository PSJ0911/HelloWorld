5주차 과제
======================================================
Widget과 계산기
-------------
Widget
-------------
```Dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          child: Container(
            padding: EdgeInsets.all(1),
            color: Colors.black,
            child: Container(
              width: 300,
              height: 400,
              color: Colors.white,
              child: Column(
                children: [
                  Expanded(
                    flex: 2,
                    child: Row(
                      children: [
                        Expanded(
                          flex: 2,
                          child: Container(color: Colors.red),
                        ),
                        Expanded(
                          flex: 1,
                          child: Column(
                            children: [
                              Expanded(
                                child: Container(color: Colors.blue),
                              ),
                              Expanded(
                                child: Row(
                                  children: [
                                    Expanded(
                                      child: Container(color: Colors.black),
                                    ),
                                    Expanded(
                                      child: Container(color: Colors.orange),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Expanded(
                    flex: 2,
                    child: Container(color: Colors.yellow),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```

계산기
-------------
```Dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        body: Center(
          child: Container(
            padding: EdgeInsets.all(1),
            color: Colors.black,
            child: Container(
              width: 300,
              height: 400,
              color: Colors.white,
              child: Column(
                children: [
                  Expanded(
                    flex: 2,
                    child: Row(
                      children: [
                        Expanded(
                          flex: 2,
                          child: Container(color: Colors.red),
                        ),
                        Expanded(
                          flex: 1,
                          child: Column(
                            children: [
                              Expanded(
                                child: Container(color: Colors.blue),
                              ),
                              Expanded(
                                child: Row(
                                  children: [
                                    Expanded(
                                      child: Container(color: Colors.black),
                                    ),
                                    Expanded(
                                      child: Container(color: Colors.orange),
                                    ),
                                  ],
                                ),
                              ),
                            ],
                          ),
                        ),
                      ],
                    ),
                  ),
                  Expanded(
                    flex: 2,
                    child: Container(color: Colors.yellow),
                  ),
                ],
              ),
            ),
          ),
        ),
      ),
    );
  }
}
```
