void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return ChangeNotifierProvider(
      create: (context) => DataProvider(),
      child: MaterialApp(
        title: 'Lab Task',
        theme: ThemeData(
          primarySwatch: Colors.blue,
        ),
        home: Scaffold(
          appBar: AppBar(
            title: const Text('Lab Task'),
          ),
          body: ScreenOne(),
        ),
      ),
    );
  }
}

class DataProvider extends ChangeNotifier {
  String data = '19SW27';

  void onDataChange(String value) {
    data = value;
    notifyListeners();
  }
}

class TextWidget extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text(Provider.of<DataProvider>(context, listen: false).data);
  }
}

class MyTextField extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return TextField(
      onChanged: (newValue) {
        Provider.of<DataProvider>(context, listen: false)
            .onDataChange(newValue);
      },
    );
  }
}

class ScreenOne extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Container(
      child: ScreenTwo(),
    );
  }
}

class ScreenTwo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Column(
      children: [
        MyTextField(),
        SizedBox(
          height: 20,
        ),
        ScreenThree(),
      ],
    );
  }
}

class ScreenThree extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text(Provider.of<DataProvider>(context).data);
  }
}
