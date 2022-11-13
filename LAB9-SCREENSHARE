class HomePage extends StatefulWidget {
  const HomePage({super.key});

  @override
  _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {
  late bool button1, button2;

  static final GlobalKey _globalKey = GlobalKey();

  @override
  void initState() {
    button1 = false;
    button2 = false;
    super.initState();
  }

  @override
  Widget build(BuildContext context) {
    return RepaintBoundary(
      key: _globalKey,
      child: Scaffold(
        appBar: AppBar(
          automaticallyImplyLeading: false,
          title: const Text("Share plus example"),
          centerTitle: true,
        ),
        body: Center(
          child: Column(
            mainAxisAlignment: MainAxisAlignment.center,
            children: <Widget>[
              ElevatedButton(
                style: ElevatedButton.styleFrom(
                  backgroundColor: button1 ? Colors.green : Colors.red,
                  shape: StadiumBorder(),
                ),
                onPressed: _captureSocialPng,
                child: Padding(
                  padding: const EdgeInsets.all(16.0),
                  child: button1
                      ? const CircularProgressIndicator()
                      : const Text(
                          'Share',
                          style: TextStyle(fontSize: 17),
                        ),
                ),
              ),
              SizedBox(
                height: MediaQuery.of(context).size.height * 0.03,
              ),
            ],
          ),
        ),
      ),
    );
  }

  Future<void> _captureSocialPng() {
    List<XFile> images = [];
    final RenderBox box = context.findRenderObject() as RenderBox;
    return Future.delayed(const Duration(milliseconds: 20), () async {
      RenderRepaintBoundary? boundary = _globalKey.currentContext!
          .findRenderObject() as RenderRepaintBoundary?;
      if (boundary!.debugNeedsPaint) {
        Timer(const Duration(seconds: 1), () => _captureSocialPng());
        return;
      }
      ui.Image image = await boundary.toImage();
      final directory = (await getApplicationDocumentsDirectory()).path;
      ByteData? byteData = await image.toByteData(format: ImageByteFormat.png);
      Uint8List pngBytes = byteData!.buffer.asUint8List();
      final file = File('$directory/screenshot.png');
      await file.writeAsBytes(pngBytes);
      XFile imgFile = XFile('$directory/screenshot.png');
      images.add(imgFile);

      await Share.shareXFiles(images,
          subject: 'Share',
          text: 'Check this Out!',
          sharePositionOrigin: box.localToGlobal(Offset.zero) & box.size);
    });
  }
}
