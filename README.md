# Flutter: um guia para sair do zero

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

```

## Column

```

```

## Padding

```

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
