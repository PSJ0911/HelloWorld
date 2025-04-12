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
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        backgroundColor: Colors.black,
        body: SafeArea(
          child: Column(
            children: [
              Expanded(
                flex: 2,
                child: Container(
                  alignment: Alignment.bottomRight,
                  padding: EdgeInsets.all(16),
                  child: Text(
                    '0',
                    style: TextStyle(
                      fontSize: 60,
                      color: Colors.white,
                      fontWeight: FontWeight.w300,
                    ),
                  ),
                ),
              ),

              Expanded(
                flex: 5,
                child: Padding(
                  padding: EdgeInsets.symmetric(horizontal: 8),
                  child: Column(
                    children: _buildButtonRows(),
                  ),
                ),
              ),
            ],
          ),
        ),
      ),
    );
  }

  List<Widget> _buildButtonRows() {
    final List<List<String>> buttons = [
      ['%', 'CE', 'C', '⌫'],
      ['½x', 'x²', '²√x', '÷'],
      ['7', '8', '9', '×'],
      ['4', '5', '6', '−'],
      ['1', '2', '3', '+'],
      ['+/-', '0', '.', '='],
    ];

    return buttons.map((row) {
      return Expanded(
        child: Row(
          children: row.map((text) {
            return _buildButton(text);
          }).toList(),
        ),
      );
    }).toList();
  }

  Widget _buildButton(String text) {
    bool isOperator = ['+', '−', '×', '÷', '=', '⌫'].contains(text);
    Color color = isOperator ? Colors.grey.shade600 : Colors.grey.shade800;

    return Expanded(
      child: Padding(
        padding: EdgeInsets.all(4),
        child: Container(
          decoration: BoxDecoration(
            color: color,
            borderRadius: BorderRadius.circular(8),
          ),
          alignment: Alignment.center,
          child: Text(
            text,
            style: TextStyle(fontSize: 22, color: Colors.white),
          ),
        ),
      ),
    );
  }
}
```
