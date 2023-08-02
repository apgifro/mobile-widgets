# Flutter: um guia para sair do zero

Listagens.

## Explicação inicial

```
import 'package:flutter/material.dart';
void main() {
  runApp(const MaterialApp(
    home: HelloWorld(),));
}

class HelloWorld extends StatelessWidget {
  const HelloWorld({super.key});
  @override
  Widget build(BuildContext context) {
    return const Placeholder();
  }
}
```

## Stateless

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
    Widget build(BuildContext context) {
      return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: const Center(
            child: Text(
          "Bem-vindo!",
          style: TextStyle(fontSize: 30.0),
        )),
      );
    }
}
```

## Row

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    var urlToImage = 'https://github.com/alexgirardello.png';
    return Scaffold(
      appBar: AppBar(
        title: const Text("Inicío"),
      ),
      body: Center(
        child: Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            CircleAvatar(
              backgroundImage: NetworkImage(urlToImage),
            ),
            const Text(
              "Bem-vindo",
              style: TextStyle(fontSize: 30.0),
            ),
            const Text(
              "23ºC",
              style: TextStyle(fontSize: 30.0),
            )
          ],
        ),
      )
    );
  }
}
```

## Column

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    var urlToImage = 'https://github.com/alexgirardello.png';
    return Scaffold(
      appBar: AppBar(
        title: const Text("Inicío"),
      ),
      body: Center(
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.start,
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            CircleAvatar(
              backgroundImage: NetworkImage(urlToImage),
            ),
            const Text(
              "Bem-vindo",
              style: TextStyle(fontSize: 30.0),
            ),
            const Text(
              "23ºC",
              style: TextStyle(fontSize: 30.0),
            )
          ],
        ),
      )
    );
  }
}
```

## Padding

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Inicío"),
      ),
      body: const Column(
        children: [
          Padding(
            padding: EdgeInsets.fromLTRB(60, 30, 0, 0),
            child: Text(
              "Algum texto.",
              style: TextStyle(fontSize: 30.0),
            ),
          ),
          Text(
            "Mais texto.",
            style: TextStyle(fontSize: 30.0),
          ),
        ],
      )
    );
  }
}
```


## Stateful

```
class Example extends StatefulWidget {
  const Example({super.key});

  @override
  State<Example> createState() => _ExampleState();
}

class _ExampleState extends State<Example> {
  var value = 1;
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text("Início"),
      ),
      body: Center(
        child: Row(
          mainAxisAlignment: MainAxisAlignment.spaceEvenly,
          children: [
            IconButton(
                onPressed: () => setState(() { value++; }),
                icon: const Icon(Icons.add)),
            Text(
              value.toString(),
              style: const TextStyle(fontSize: 25.0),
            ),
            IconButton(
                onPressed: () => setState(() { value--; }),
                icon: const Icon(Icons.remove)),
          ],
        ),),);}}
```
