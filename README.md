# Act8
Act8.dart
import 'package:flutter/material.dart';

void main() {
  runApp(const MiApp());
}

class MiApp extends StatelessWidget {
  const MiApp({super.key});

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      debugShowCheckedModeBanner: false,
      home: BotonesUI(),
    );
  }
}

class BotonesUI extends StatefulWidget {
  const BotonesUI({super.key});
  @override
  State<BotonesUI> createState() => _BotonesUIState();
}

class _BotonesUIState extends State<BotonesUI> {
  Color _currentBackgroundColor = Colors.white;

  void cambiaColor(Color newColor) {
    setState(() {
      _currentBackgroundColor = newColor;
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: _currentBackgroundColor, 
      appBar: AppBar(
        title: const Text(
          "Colores Background",
          style: TextStyle(color: Colors.black),
        ),
        centerTitle: true,
        backgroundColor: Colors.grey,
        iconTheme: const IconThemeData(color: Colors.black),
      ),
      body: Center(
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const SizedBox(height: 10),
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.blue,
              ),
              onPressed: () {
                cambiaColor(Colors.blue); 
              },
              child: const Text("Azul"),
            ),
            const SizedBox(height: 20),
            const SizedBox(height: 10),
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.red,
              ),
              onPressed: () {
                cambiaColor(Colors.red);
              },
              child: const Text("Rojo"),
            ),
               const SizedBox(height: 20),
             const SizedBox(height: 10),
            ElevatedButton(
              style: ElevatedButton.styleFrom(
                backgroundColor: Colors.green,
              ),
              onPressed: () {
                cambiaColor(Colors.green);
              },
              child: const Text("Verde"),
            ),
            
          ],
        ),
      ),
    );