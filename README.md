# flutter_app

A new Flutter application.
# Passo a Passo

Já estar com o projeto rodando no emulador

## Parte 1: Apagar coisas não necessárias

Criei um projeto flutter, rodei e não alterei o código
É o projeto exemplo
Apagar tudo o q nao for necessário

## Parte 2: Importar pacotes

Ter o pub dev aberto e importar os pacotes no pubspect.yaml e na main
```
image_picker: ^0.6.7+17
import 'package:image_picker/image_picker.dart';

carousel_slider: ^2.3.1
import 'package:carousel_slider/carousel_slider.dart';
```

## Parte 3: Image picker

```
 File _image;
  final picker = ImagePicker();

  Future getImage() async {
    final pickedFile = await picker.getImage(source: ImageSource.camera);

    setState(() {
      if (pickedFile != null) {
        _image = File(pickedFile.path);
      } else {
        print('No image selected.');
      }
    });
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Image Picker Example'),
      ),
      body: Center(
        child: _image == null
            ? Text('No image selected.')
            : Image.file(_image),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: getImage,
        tooltip: 'Pick Image',
        child: Icon(Icons.add_a_photo),
      ),
    );
  }
```

## Parte 4: Carrousel Slider

Usar como exemplo o 

```
class ComplicatedImageDemo extends StatelessWidget {
  @override
  Widget build(BuildContext context) {

    return Scaffold(
      appBar: AppBar(title: Text('Complicated image slider demo')),
      body: Container(
        child: Column(children: <Widget>[
          CarouselSlider(
            options: CarouselOptions(
              autoPlay: true,
              aspectRatio: 2.0,
              enlargeCenterPage: true,
            ),
            items: imageSliders,
          ),
        ],)
      ),
    );
  }
}
```