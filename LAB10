class URLLauncherExample extends StatelessWidget {
  URLLauncherExample({Key? key}) : super(key: key);

  final Uri emailLaunchUri = Uri(
    scheme: 'mailto',
    path: 'jmrchelani@gmail.com',
    query:
        '${Uri.encodeComponent('subject')}=${Uri.encodeComponent('Buggy Application')}',
  );

  final Uri smsLaunchUri = Uri(
    scheme: 'sms',
    path: '090078601',
    queryParameters: <String, String>{
      'body': Uri.encodeComponent(
        'Fix this shit please',
      ),
    },
  );

  void _sendSms() async {
    await launchUrl(smsLaunchUri);
  }

  void _sendEmail() async {
    await launchUrl(emailLaunchUri);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Url Launcher Example'),
        centerTitle: true,
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            ElevatedButton(
              onPressed: _sendSms,
              child: const Text('Send SMS'),
            ),
            ElevatedButton(
              onPressed: _sendEmail,
              child: const Text('Send Email'),
            ),
          ],
        ),
      ),
    );
  }
}
