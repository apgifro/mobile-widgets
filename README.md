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

## Images e SizedBox

```
# To add assets to your application, add an assets section, like this:
assets:
  - images/portrait.png
```

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    var urlToImage = "https://dynamic-media-cdn.tripadvisor.com/media"
        "/photo-o/1a/08/97/69/aurora-borealis-senja.jpg?w=1000&h=700&s=1";
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.symmetric(vertical: 10),
          child: Column(
            children: [
              Image.network(urlToImage),
              const SizedBox(height: 10,),
              Image.asset('images/portrait.png')
            ],
          ),
        ));
  }
}
```

## Container

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Center(
          child: Column(
            children: [
              const SizedBox(height: 10,),
              Container(
                width: 350,
                height: 200,
                color: Colors.blue,
              ),
              const SizedBox(height: 10,),
              Container(
                width: 350,
                height: 200,
                color: Colors.lightBlueAccent,
              ),
            ],
          ),
        ));
  }
}
```

## BoxDecoration

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    var urlToImage = "https://dynamic-media-cdn.tripadvisor.com/media"
        "/photo-o/1a/08/97/69/aurora-borealis-senja.jpg?w=1000&h=700&s=1";
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.symmetric(vertical: 10),
          child: Column(
            children: [
              Container(
                height: 300,
                margin: const EdgeInsets.symmetric(horizontal: 8.0),
                decoration: BoxDecoration(
                    borderRadius: BorderRadius.circular(20),
                    image: DecorationImage(
                        image: NetworkImage(urlToImage),
                        fit: BoxFit.cover)
                ),
              ),
            ],
          ),
        ));
  }
}
```

## TextFormField

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    TextEditingController _nameController = TextEditingController();
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.all(8),
          child: Column(
            children: [
              TextFormField(
                controller: _nameController,
                decoration: const InputDecoration(
                    labelText: 'Qual o seu nome?',
                    border: OutlineInputBorder(),
                    prefixIcon: Icon(Icons.person)),
                onFieldSubmitted: (String value) {
                  print(value);
                },
              ),
            ],
          ),
        ));
  }
}
```

## SingleChildScrollView

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    final TextEditingController _name = TextEditingController();
    final TextEditingController _marital = TextEditingController();
    final TextEditingController _work = TextEditingController();
    final TextEditingController _identity = TextEditingController();
    final TextEditingController _cpf = TextEditingController();
    final TextEditingController _number = TextEditingController();
    final TextEditingController _value = TextEditingController();
    final TextEditingController _date = TextEditingController();
    final TextEditingController _phone = TextEditingController();
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: SingleChildScrollView(
          child: Padding(
            padding: const EdgeInsets.fromLTRB(10, 20, 10, 20),
            child: Column(
              children: [
                TextFormField(
                  controller: _name,
                  autofocus: true,
                  textInputAction: TextInputAction.next,
                  decoration: const InputDecoration(
                      label: Text('Nome'),
                      border: OutlineInputBorder(),
                      icon: Icon(Icons.face)),
                ),
                const SizedBox(
                  height: 15,
                ),
                Padding(
                  padding: const EdgeInsets.fromLTRB(40, 0, 0, 0),
                  child: TextFormField(
                    controller: _marital,
                    textInputAction: TextInputAction.next,
                    decoration: const InputDecoration(
                      label: Text('Estado civil'),
                      border: OutlineInputBorder(),
                    ),
                  ),
                ),
                const SizedBox(
                  height: 15,
                ),
                Padding(
                  padding: const EdgeInsets.fromLTRB(40, 0, 0, 0),
                  child: TextFormField(
                    controller: _work,
                    textInputAction: TextInputAction.next,
                    decoration: const InputDecoration(
                      label: Text('Profissão'),
                      border: OutlineInputBorder(),
                    ),
                  ),
                ),
                const SizedBox(
                  height: 30,
                ),
                TextFormField(
                  controller: _identity,
                  textInputAction: TextInputAction.next,
                  decoration: const InputDecoration(
                      label: Text('RG'),
                      border: OutlineInputBorder(),
                      icon: Icon(Icons.perm_identity)),
                ),
                const SizedBox(
                  height: 15,
                ),
                Padding(
                  padding: const EdgeInsets.fromLTRB(40, 0, 0, 0),
                  child: TextFormField(
                    textInputAction: TextInputAction.next,
                    controller: _cpf,
                    keyboardType: TextInputType.number,
                    decoration: const InputDecoration(
                      label: Text('CPF'),
                      border: OutlineInputBorder(),
                    ),
                  ),
                ),
                const SizedBox(
                  height: 30,
                ),
                TextFormField(
                  textInputAction: TextInputAction.next,
                  controller: _number,
                  keyboardType: TextInputType.number,
                  decoration: const InputDecoration(
                      label: Text('Número do apartamento'),
                      suffixText: '/10',
                      border: OutlineInputBorder(),
                      icon: Icon(Icons.looks_two_outlined)),
                ),
                const SizedBox(
                  height: 15,
                ),
                Padding(
                  padding: const EdgeInsets.fromLTRB(40, 0, 0, 0),
                  child: TextFormField(
                    textInputAction: TextInputAction.next,
                    controller: _value,
                    keyboardType: TextInputType.number,
                    decoration: const InputDecoration(
                      label: Text(r'R$'),
                      border: OutlineInputBorder(),
                    ),
                  ),
                ),
                const SizedBox(
                  height: 30,
                ),
                TextFormField(
                  controller: _phone,
                  keyboardType: TextInputType.number,
                  decoration: const InputDecoration(
                      label: Text('Telefone'),
                      border: OutlineInputBorder(),
                      icon: Icon(Icons.phone_outlined)),
                ),
                const SizedBox(
                  height: 30,
                ),
                TextFormField(
                  readOnly: true,
                  initialValue: 'Setor',
                  decoration: const InputDecoration(
                      label: Text('Setor'),
                      border: OutlineInputBorder(),
                      icon: Icon(Icons.map_outlined)),
                ),
              ],
            ),
          ),
        ));
  }
}
```

## ElevatedButton

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.only(top: 10, left: 10),
          child: Column(
            children: [
              ElevatedButton(
                  onPressed: () {
                    // Faz algo
                    print("Salvei!");
                  },
                  child: const Text('Salvar')
              )
            ],
          ),));
  }
}
```

## MediaQuery

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    var screenWidth = MediaQuery.of(context).size.width;
    var screenHeigth = MediaQuery.of(context).size.height;
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.all(5),
          child: Column(
            children: [
              Container(
                width: screenWidth,
                child: ElevatedButton(
                    onPressed: () {
                      // Faz algo
                      print("Salvei!");
                    },
                    child: const Text('Salvar')
                ),
              )
            ],
          ),));
  }
}
```

## GestureDetector e SnackBar

```

class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Padding(
          padding: const EdgeInsets.all(5),
          child: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                GestureDetector(
                    onTap: () {
                      var snackBar = const SnackBar(
                        content: Text('Clicou!'),
                      );
                      ScaffoldMessenger.of(context).showSnackBar(snackBar);
                    },
                    child: const Text(
                      'Clique em mim!',
                      style: TextStyle(fontSize: 30.0),
                    ))
              ],
            ),
          ),
        ));
  }
}
```

## ListView

```
class Example extends StatelessWidget {
  const Example({super.key});
  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: ListView(
          padding: const EdgeInsets.all(8),
          children: const [
            ListTile(
              title: Text('Dart'),
              trailing: Icon(Icons.check),
            ),
            Divider(thickness: 2,),
            ListTile(
              title: Text('Java'),
              trailing: Icon(Icons.check_box_outline_blank),
            ),
            Divider(thickness: 2,),
            ListTile(
              title: Text('Kotlin'),
              trailing: Icon(Icons.check_box_outline_blank),
            ),
            Divider(thickness: 2,),
            ListTile(
              title: Text('Python'),
              trailing: Icon(Icons.check),
            ),
          ],
        ));
  }
}
```

## ListView.builder

```
import 'package:device_preview/device_preview.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(DevicePreview(
      enabled: true,
      builder: (BuildContext context) => MaterialApp(
            debugShowCheckedModeBanner: false,
            useInheritedMediaQuery: true,
            home: Example(
              items: List<String>.generate(100, (i) => 'Item $i'),
            ),
          )));
}

class Example extends StatelessWidget {
  final List<String> items;

  const Example({super.key, required this.items});

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text('Início'),
        ),
        body: ListView.builder(
          itemCount: items.length,
          itemBuilder: (context, index) {
            return ListTile(
              title: Text(items[index]),
            );
          },
      ),
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

## pubspec.yaml

```
dependencies:
  flutter:
    sdk: flutter
  cupertino_icons: ^1.0.2
  device_preview: ^1.1.0
  http: ^1.1.0
  video_player: ^2.6.1
```

## DevicePreview

```
import 'package:device_preview/device_preview.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(DevicePreview(
      enabled: true,
      builder: (BuildContext context) => const MaterialApp(
            debugShowCheckedModeBanner: false,
            useInheritedMediaQuery: true,
            home: Example(),
          )));
}
```


## HTTP

```
import 'dart:convert';

import 'package:device_preview/device_preview.dart';
import 'package:flutter/material.dart';
import 'package:http/http.dart' as http;

void main() {
  runApp(DevicePreview(
      enabled: true,
      builder: (BuildContext context) => const MaterialApp(
            debugShowCheckedModeBanner: false,
            useInheritedMediaQuery: true,
            home: Example(),
          )));
}


Future <Map<String, dynamic>> fetchAddress (String cep) async {
  final String url = 'https://viacep.com.br/ws/$cep/json/';
  final http.Response response = await http.get(Uri.parse(url));
  return json.decode(response.body);
}

class Example extends StatefulWidget {
  const Example({super.key});

  @override
  State<Example> createState() => _ExampleState();
}

class _ExampleState extends State<Example> {
  String cep = "76873256";
  Map<String, dynamic> addressData = {};

  @override
  void initState() {
    super.initState();
    fetchAddress(cep).then((value) {
      setState(() {
        addressData = value;
      });
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
        appBar: AppBar(
          title: const Text("Inicío"),
        ),
        body: Center(
          child: Padding(
            padding: const EdgeInsets.only(top: 15),
            child: Column(
              children: [
                Text("Logradouro: ${addressData['logradouro']}", style: const TextStyle(fontSize: 25.0),),
                Text("Bairro: ${addressData['bairro']}", style: const TextStyle(fontSize: 25.0),),
                Text("Cidade: ${addressData['localidade']}", style: const TextStyle(fontSize: 25.0),),
              ],
            ),
          ),
        ));
  }
}
```

## VideoPlayer

```
import 'package:flutter/material.dart';
import 'package:video_player/video_player.dart';

class VideoScreen extends StatefulWidget {
  const VideoScreen({Key? key}) : super(key: key);

  @override
  State<VideoScreen> createState() => _VideoScreenState();
}

class _VideoScreenState extends State<VideoScreen> {
  late VideoPlayerController _video;

  @override
  void initState() {
    super.initState();
    _video = VideoPlayerController.network(
        'https://flutter.github.io/assets-for-api-docs/assets/videos/bee.mp4')
      ..initialize().then((_) {
        setState(() {});
      });
  }

  @override
  void dispose() {
    super.dispose();
    _video.dispose();
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text(
          'Video Player',
        ),
      ),
      body: SingleChildScrollView(
        child: Column(children: [
          Center(
            child: _video.value.isInitialized
                ? AspectRatio(
                    aspectRatio: _video.value.aspectRatio,
                    child: VideoPlayer(_video),
                  )
                : const Center(child: CircularProgressIndicator()),
          ),
          Row(
            mainAxisAlignment: MainAxisAlignment.center,
            children: [
              IconButton(
                onPressed: () {
                  setState(() {
                    _video.setPlaybackSpeed(1);
                  });
                },
                icon: const Icon(
                  Icons.slow_motion_video,
                  size: 28,
                ),
              ),
              IconButton(
                onPressed: () {
                  setState(() {
                    _video.value.isPlaying ? _video.pause() : _video.play();
                  });
                },
                icon: Icon(
                  _video.value.isPlaying ? Icons.pause : Icons.play_arrow,
                  size: 28,
                ),
              ),
              IconButton(
                onPressed: () {
                  setState(() {
                    _video.setPlaybackSpeed(2.0);
                  });
                },
                icon: const Icon(
                  Icons.speed,
                  size: 28,
                ),
              ),
            ],
          ),
        ]),
      ),
    );
  }
}
```


