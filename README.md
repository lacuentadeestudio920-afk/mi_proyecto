import 'package:flutter/material.dart';

void main() {
  runApp(
      const MaterialApp(
          home: Loco()
      )
  );
}
class Loco extends StatefulWidget{
  const Loco({super.key});

  @override
  State<Loco> createState() => _Loco();
}

class _Loco extends State<Loco>{
  bool isLoding=true;

  void initState(){
    super.initState();
    Future.delayed(Duration(seconds: 4),(){
      setState(() {
        isLoding=!isLoding;
      });
    });
  }
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: isLoding ? Lodingscreen() : Mainscreen(),
    );
  }
}
class Lodingscreen extends StatelessWidget{
  const Lodingscreen({super.key});
  @override
  Widget build(BuildContext context) {
    return Container(
      color: Colors.orange,
      width: double.infinity,
      child: Column(
        mainAxisAlignment: MainAxisAlignment.center,
        children: [
          Image.asset('assets/img/blackpink1.jpeg'),
          SizedBox(height: 90.0,),
          Text(
            '제니 보면서 기다려',
            style: TextStyle(
                color: Colors.white,
                fontSize: 20.0,
                fontWeight: FontWeight.w600),),
          SizedBox(height: 30.0,),
          CircularProgressIndicator()
        ],
      ),
    );
  }
}


class Mainscreen extends StatelessWidget{
  const Mainscreen({super.key});
  @override
  Widget build(BuildContext context) {
    return Center(
        child: Text(
            'ㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋㅋ',
          style: TextStyle(color: Colors.red,
          fontSize: 30.0,
          fontWeight: FontWeight.w700),
        ),
    );
  }
}
