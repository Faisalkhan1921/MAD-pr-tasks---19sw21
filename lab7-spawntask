void main() {
  multithreading();
}

void multithreading() {
  Isolate.spawn((v) {
    for (int i = 0; i < 2; i++) {
      for (int j = 0; j < 2; j++) {
        print("[ISO 1] i = $i, j = $j");
      }
    }
  }, 'Isolate 1');

  void isofunction(var msg) {
    for (int i = 0; i < 2; i++) {
      for (int j = 0; j < 2; j++) {
        debugPrint(msg + "$i" + '$j');
      }
    }
  }

  Isolate.spawn(isofunction, "Isolate Function 2");

  for (int i = 0; i < 2; i++) {
    for (int j = 0; j < 2; j++) {
      debugPrint("Main Function " + "$i" + '$j');
    }
  }
}
