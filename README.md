# database-rinaldiimport 'package:flutter/material.dart';
void main() => runApp(App());

class App extends StatelessWidget {
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter penyimpanan data',
      home: Scaffold(
        appBar: AppBar(
          title: Text('RinaldiPrayoga-6SIA10'),
        ),
        body: Doorsmear(),
      ),
    );
  }
}

class BIAYADOORSMEAR{
  
  String motor;
  String mobil;
  
  
  BIAYADOORSMEAR({ this.motor, this.mobil});
  
}

// class Doorsmear
class Doorsmear extends StatefulWidget {
  _MyappState createState() => _MyappState();
}

class _MyappState extends State<Doorsmear> {
  //deklarasi variabel
  final txtfacial = TextEditingController();
  final txtcreambath = TextEditingController();
  final txtkomplit = TextEditingController();
  

  List<Widget> data = [];

  onTambah() {
    setState(() {
      data.add(ListTile(
        leading: Text(txtmotor.text),
        title: Text(txtmobil.text),
        subtitle: Text(txtmotor.text),
        trailing: Text(txtpilihan.text),
      ));
      txtmotor.clear();
      txtmobil.clear();
      txtmotor.clear();
      txtpilihan.clear();
    });
  }

  Widget build(BuildContext context) {
    return ListView(
      children: <Widget>[
        new Container(
          padding: EdgeInsets.all(10.0),
          child: Column(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
           
              TextField(
                controller: txtmotor,
                decoration: InputDecoration(hintText: 'motor'),
              ),
              TextField(
                controller: txtmobil,
                decoration: InputDecoration(hintText: 'mobil'),
              ),
               TextField(
                controller: txtpilihan,
                decoration: InputDecoration(hintText: 'pilihan'),
              ),
              Divider(height: 5.0),
              ElevatedButton(child: Text("Tambah"), onPressed: onTambah),
            ],
          ),
        ),
        new Column(
          children: data,
        )
      ],
    );
  }
}
