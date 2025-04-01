실습
======================================================
구구단
-------------
```Dart
void main() {
  for (int i = 2; i < 10; i++) {
    for (int j = 1; j < 10; j++) {
      print('$i X $j =  ${j * i}');
    }
    print('');
  }
}
```

사각형
---------------
```Dart
void main() {
  var n = 10;
  var result = '';
  for (var y = 0; y < n; y++) {
    for (var x = 0; x < n; x++) {
      var c = f1(x,y,n);
      if (c) {
        result += '=';
      }
      else {
        result += ' ';
      }
    }
    result += '\n';
  }
  
  print(result);
}

bool f1(int x, int y, int size) {
  return x == 0
    || y == 0
    || x == size - 1
    || y == size - 1;
}
```
요일
---------------
```Dart
void main() {
  var input = '2025-03-17';
  
  DateTime date = DateTime.parse(input);
  
  List<String> weekdays = ['월요일', '화요일', '수요일', '목요일', '금요일', '토요일', '일요일'];
  
  String day = weekdays[date.weekday - 1];
  print('$input은 $day입니다.');
}
```
