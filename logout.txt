import 'package:flutter/material.dart';
import 'Login.dart';
import 'package:shared_preferences/shared_preferences.dart';



class Logout extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Blood Drop Logout'),
        centerTitle: true,
      ),
      backgroundColor: Colors.red,
      body: Center(
          child: RaisedButton(
              child: Text("Log out",
              style: TextStyle(fontSize: 40,fontWeight: FontWeight.w600),),
              color: Colors.white,
              textColor: Colors.black,
              padding: EdgeInsets.symmetric(vertical: 10,horizontal: 10),
              onPressed: () => Navigator.push(
                  context,
                  MaterialPageRoute(
                    builder: (BuildContext context) => Login(),
                  )))),
    );


  }
static Future<bool> clear() async {
    final pref = await SharedPreferences.getInstance();
    return await pref.clear();
}
}