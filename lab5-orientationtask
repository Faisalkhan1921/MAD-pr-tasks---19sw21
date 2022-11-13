class ImageShow extends StatefulWidget {
  ImageShow({Key? key}) : super(key: key);

  @override
  State<ImageShow> createState() => _ImageShowState();
}

class _ImageShowState extends State<ImageShow> {
  int value = 0;
  List<String> list = [
    'https://www.miresbeck.co.uk/_webedit/cached-images/1370-0-0-0-8180-10000-532.jpg',
    'https://www.miresbeck.co.uk/_webedit/cached-images/976-0-0-603-10000-7921-1084.png',
    'https://www.miresbeck.co.uk/_webedit/cached-images/984-0-0-0-10000-10000-532.jpg',
    'https://www.miresbeck.co.uk/_webedit/cached-images/1370-0-0-0-8180-10000-532.jpg',
    'https://www.miresbeck.co.uk/_webedit/cached-images/976-0-0-603-10000-7921-1084.png',
  ];
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('ImageViewer'),
      ),
      body: OrientationBuilder(
        builder: (context, orientation) {
          if (MediaQuery.of(context).orientation == Orientation.portrait) {
            if (value < 4) {
              value = value + 1;
            }
            return Image.network(
              list[0],
              width: MediaQuery.of(context).size.width,
              height: MediaQuery.of(context).size.height,
              fit: BoxFit.cover,
            );
          } else {
            if (value > 0) {
              value = value - 1;
            }

            return Image.network(
              list[1],
              width: MediaQuery.of(context).size.width,
              height: MediaQuery.of(context).size.height,
              fit: BoxFit.cover,
            );
          }
        },
      ),
    );
  }
}
