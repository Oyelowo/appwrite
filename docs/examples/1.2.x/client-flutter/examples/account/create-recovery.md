import 'package:appwrite/appwrite.dart';

void main() { // Init SDK
  Client client = Client();
  Account account = Account(client);

  client
    .setEndpoint('https://<REGION>.cloud.appwrite.io/v1') // Your API Endpoint
    .setProject('5df5acd0d48c2') // Your project ID
  ;
  Future result = account.createRecovery(
    email: 'email@example.com',
    url: 'https://example.com',
  );

  result
    .then((response) {
      print(response);
    }).catchError((error) {
      print(error.response);
  });
}
