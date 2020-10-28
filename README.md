# Flutter-Interview-Questions

This repository is a part of HacktoberFest-an event organised by DigitalOcean. You are requested to create your profile using the above link to be a part of it.

1. What is Flutter?

Flutter is Google's UI toolkit for crafting beautiful, natively compiled applications for mobile, web, and desktop from a single codebase.

2. What are the different types of widgets in Flutter?

Two types of widgets present in the Flutter are stateless and stateful.

The stateless widgets don’t store any values which will change in the future. The stateless widgets don’t store any state. Icon, text widgets are some examples of stateless widgets.

The stateful widgets have a state object to keep track of all the changes and updates happening in the UI. These widgets are immutable but the state object is used to keep track of the changes. Checkbox and image are some of the examples of stateful widgets.

3. Difference b/w Stateful widget and Stateless widget.

Stateless widgets cannot change their state during the runtime of the app, which means the widgets cannot be redrawn while the app is in action.

Stateful Widgets are the ones that change its properties during run-time. They are dynamic i.e., they are mutable and can be drawn multiple times within its lifetime.

4. What is the use of pubspec.yaml file in Flutter?

The pubspec. yaml file is the most important file in any Flutter project. It is the place where you provide all the required dependencies of your Flutter project.

5. What is Dart? Why Flutter uses Dart as Programming Language? Dart is an object-oriented, garbage-collected programming language that you use to develop Flutter apps. It is created by Google. Dart was chosen as the language of Flutter for the following reason:

i. Dart is AOT (Ahead Of Time) compiled to fast, predictable, native code, which allows almost all of Flutter to be written in Dart. This makes Flutter fast

ii. Dart can also be JIT (Just In Time) compiled for exceptionally fast development cycles and game-changing workflow (hotreload).

iii. Dart allows Flutter to avoid the need for a separate declarative layout language like XML, because Dart’s declarative, programmatic layout is easy to read and visualize. i.e we can do both UI and Buisness Logic using one language only which is "DART"

iv. Dart Team + Flutter Team As both Dart and Flutter is developed and maintained by Google, hence both Flutter Team and Dart Team work together to solve the problem.

6. What is the difference between NetworkImage and Image.network in flutter?

NetworkImage class creates an object the provides an image from the src URL passed to it. It is not a widget and does not output an image to the screen. Image.network creates a widget that displays an image on the screen. It is just a named constructor on the Image class (a stateful widget). It sets the image property using the NetworkImage . This image property is used finally to display the image.

7. What are mixins in dart?

Mixins are used for a unique kind of inheritance, they allow other classes to inherit it's baked in methods for use, without actually being a child of the parent Mixin class. In simple words, Mixins are our usual normal classes from which we can borrow methods, without extending the class.

8. What is hot reload in flutter?

Flutter’s hot reload feature helps you quickly and easily experiment, build UIs, add features, and fix bugs. Hot reload works by injecting updated source code files into the running Dart Virtual Machine (VM). After the VM updates classes with the new versions of fields and functions, the Flutter framework automatically rebuilds the widget tree, allowing you to quickly view the effects of your changes.

9. What are the two types of Streams available in Flutter?

There are two types of Streams available in Flutter which are: ..* Single subscription streams ..* Broadcast streams Single subscription streams : It is a popular and commom type of stream. It consist of series of events that are parts of a large whole. The events here have to be delivered in a defined order without even missing a single event.

Broadcast streams : This stream is meant for the individual messages that can be handeled one at a time. Multiple listener can listen at a time and it also gives the user the chance to listen after the cancellation of the previous subscription.

10. What is a Flutter Inspector ?

Flutter Inspector is a tool that helps in visualizing and exploring the widget trees. It also helps in understanding the present layout and rectify the layout issues.

11. Is CI/CD possible in Flutter?

Yes, CI/CD is possible in Flutter. There is CI/CD tool dedicated to Flutter the name is CODE MAGIC. With the help of CODE MAGIC we can easily automate the process of CI/CD for flutter apps from single automation.

12. What’s the difference between hot reload and hot restart? 
  Hot reload maintains the app state while updating the UI almost instantaneously whereas Hot restart resets the app state to its initial conditions before updating the UI.

13. What are Null-aware operators in Flutter ?

Dart offers some handy operators for dealing with values that might be null.

a.One is the ??= assignment operator, which assigns a value to a variable only if that variable is currently null
b.Another null-aware operator is ??, which returns the expression on its left unless that expression’s value is null, in which case it evaluates and returns the expression on its right

14. What is use of Navigation.push and Navigation.pop function?

The push method is used to add a route to the stack of routes managed by the navigator. The pop method is used to remove the current route from the stack of routes managed by the navigator.



# Sample Flutter code for login screen application
## lib/main.dart

import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        // This is the theme of your application.
        //
        // Try running your application with "flutter run". You'll see the
        // application has a blue toolbar. Then, without quitting the app, try
        // changing the primarySwatch below to Colors.green and then invoke
        // "hot reload" (press "r" in the console where you ran "flutter run",
        // or simply save your changes to "hot reload" in a Flutter IDE).
        // Notice that the counter didn't reset back to zero; the application
        // is not restarted.
        primarySwatch: Colors.blue,
      ),
      home: MyHomePage(title: 'Flutter Demo Home Page'),
    );
  }
}

class MyHomePage extends StatefulWidget {
  MyHomePage({Key key, this.title}) : super(key: key);

  // This widget is the home page of your application. It is stateful, meaning
  // that it has a State object (defined below) that contains fields that affect
  // how it looks.

  // This class is the configuration for the state. It holds the values (in this
  // case the title) provided by the parent (in this case the App widget) and
  // used by the build method of the State. Fields in a Widget subclass are
  // always marked "final".

  final String title;

  @override
  _MyHomePageState createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      // This call to setState tells the Flutter framework that something has
      // changed in this State, which causes it to rerun the build method below
      // so that the display can reflect the updated values. If we changed
      // _counter without calling setState(), then the build method would not be
      // called again, and so nothing would appear to happen.
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // This method is rerun every time setState is called, for instance as done
    // by the _incrementCounter method above.
    //
    // The Flutter framework has been optimized to make rerunning build methods
    // fast, so that you can just rebuild anything that needs updating rather
    // than having to individually change instances of widgets.
    return Scaffold(
      appBar: AppBar(
        // Here we take the value from the MyHomePage object that was created by
        // the App.build method, and use it to set our appbar title.
        title: Text(widget.title),
      ),
      body: Center(
        // Center is a layout widget. It takes a single child and positions it
        // in the middle of the parent.
        child: Column(
          // Column is also a layout widget. It takes a list of children and
          // arranges them vertically. By default, it sizes itself to fit its
          // children horizontally, and tries to be as tall as its parent.
          //
          // Invoke "debug painting" (press "p" in the console, choose the
          // "Toggle Debug Paint" action from the Flutter Inspector in Android
          // Studio, or the "Toggle Debug Paint" command in Visual Studio Code)
          // to see the wireframe for each widget.
          //
          // Column has various properties to control how it sizes itself and
          // how it positions its children. Here we use mainAxisAlignment to
          // center the children vertically; the main axis here is the vertical
          // axis because Columns are vertical (the cross axis would be
          // horizontal).
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.display1,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: Icon(Icons.add),
      ), // This trailing comma makes auto-formatting nicer for build methods.
    );
  }
}




