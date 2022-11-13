class ImageShow extends StatefulWidget {
  ImageShow({Key? key}) : super(key: key);

  @override
  State<ImageShow> createState() => _ImageShowState();
}

class _ImageShowState extends State<ImageShow> {
  double _scale = 1.0;
  double _previousScale = 0;
  int value = 0;
  List<String> list = [
    'https://www.miresbeck.co.uk/_webedit/cached-images/1370-0-0-0-8180-10000-532.jpg',
    'https://www.miresbeck.co.uk/_webedit/cached-images/976-0-0-603-10000-7921-1084.png',
    'https://www.miresbeck.co.uk/_webedit/cached-images/984-0-0-0-10000-10000-532.jpg'
  ];
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('ImageViewer'),
      ),
      body: GestureDetector(
        onPanUpdate: (DragUpdateDetails details) {
          if (details.delta.dx > 0) {
            setState(() {
              if (value < 2) {
                value = value + 1;
              } else {
                value = 0;
              }
              print(value);
            });
          } else if (details.delta.dx < 0) {
            setState(() {
              if (value > 0) {
                value = value - 1;
              } else {
                value = 2;
              }
              print(value);
            });
          }
        },
        child: Transform(
          transform: Matrix4.diagonal3Values(_scale, _scale, _scale),
          alignment: FractionalOffset.center,
          child: Image.network(
            list[value],
            width: MediaQuery.of(context).size.width,
            height: MediaQuery.of(context).size.height,
            fit: BoxFit.cover,
          ),
        ),
      ),
    );
  }
