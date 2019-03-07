# Flutter Cheat Sheet
You need to get started quickly with Flutter? Here are some cheats that will help you build your next billion dollar app!!
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) ![Branch master](https://img.shields.io/badge/branch-master-brightgreen.svg?style=flat-square)
 [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/temidtech/flutter-cheat-sheet/master/LICENSE)
 
## Table of Contents

- [Layouts](#layouts)
- [Aligning widgets evenly](#aligning-widgets-evenly)
- [Buttons](#buttons)
- [Navigation](#navigation)


## Layouts

###   Card Layout

```dart
@override
Widget build(BuildContext context) {
  return Card(
    // Set elevation value here
    elevation: 4.0,
    child: Container(
      color: Palette.White, // set card's color
      padding: EdgeInsets.symmetric(vertical: 8.0), // Set layout padding
      child: Row(
        children: <Widget>[
      Expanded(
      child: Column(
        crossAxisAlignment: CrossAxisAlignment.center,
        children: [
          Text(
            title, // Set the text value
            style: TextStyles.caption, //Set your custom style here
          ),
          Text(
            body, // Set the text value
            style: TextStyle(
              fontSize: 20.0,
              fontWeight: FontWeight.w500, // Set font weight
              color: Colors.black87, // Set text color
            ),
          ),
        ],
      ),
    ),
  ),
 ],
),
),
);
}
  ```
  
## 2. Aligning widgets evenly
  ###   Horizontal MainAxisAlignment
    Setting the main axis alignment to spaceEvenly divides the free horizontal space 
    evenly between, before, and after each image
  ![alt text](https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/img1.PNG)
   ```dart
   Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('img/1.jpg'),
    Image.asset('img/2.jpg'),
    Image.asset('img/3.jpg'),
  ],
);
   ```
 ###   Vertical MainAxisAlignment
    Setting the main axis alignment to spaceEvenly divides the free vertical space 
    evenly between, before, and after each image
  ![alt text](https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/img2.PNG)
   ```dart
   Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('img/1.jpg'),
    Image.asset('img/2.jpg'),
    Image.asset('img/3.jpg'),
  ],
);
 ```
 ###   Packing Widgets
    By default, a row or column occupies as much space along its main axis as possible,
    but if you want to pack the children closely together, set its mainAxisSize to MainAxisSize.min. 
    The following example uses this property to pack 3 buttons together.
    
 <img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/Packing-widget.png" width="280"/> 
   
   ```dart
        new Row(
               mainAxisSize: MainAxisSize.min, // This is the magic. :)
                children: <Widget>[
                  new RaisedButton(
                    padding: const EdgeInsets.all(8.0),
                    textColor: Colors.white,
                    color: Colors.blue,
                    onPressed: onClick, // Button onClick function
                    child: new Text("Button 1"),
                  ),
                  new RaisedButton(
                    onPressed: subtractNumbers,
                    textColor: Colors.white,
                    color: Colors.red,
                    padding: const EdgeInsets.all(8.0),
                    child: new Text(
                      "Button 2",
                    ),
                  ),
                  new RaisedButton(
                    onPressed: subtractNumbers,
                    textColor: Colors.white,
                    color: Colors.red,
                    padding: const EdgeInsets.all(8.0),
                    child: new Text(
                      "Button 3",
                    ),
                  ),
                ],
              )
 ```
 
 ## 3. Buttons
 ###  Raised Button Effect
    A Raised button is based on a Material widget whose Material.elevation increases when the button is pressed.
    Do you want to add an elevation effect to your button? Use the snippet below
    Please avoid using elevated buttons on already-elevated content such as dialogs or cards.
    
 <img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/Raised-button.png" width="280"/> 
   
   ```dart
         new Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: <Widget>[
                  new RaisedButton(
                    padding: const EdgeInsets.all(8.0),
                    textColor: Colors.white,
                    color: Colors.blue,
                    onPressed: onClick, // Button onClick function
                    child: new Text("Plus"),
                  ),
                  new RaisedButton(
                    onPressed: subtractNumbers,
                    textColor: Colors.white,
                    color: Colors.red,
                    padding: const EdgeInsets.all(8.0),
                    child: new Text(
                      "Minus",
                    ),
                  ),
                ],
              )
 ```
  ###  Toggle Effect
    You can toggle the color of a raised button with few lines. The snippet below shows how you can achieve this.
    
 <img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/toggle-button.png" width="280"/> 
   
   ```dart
   1. This button will need to be created in the build of a State of a StatefulWidget
   2. The State must have a member variable bool isPressed = false;;
         new Row(
                mainAxisAlignment: MainAxisAlignment.spaceEvenly,
                children: <Widget>[
                  
                  new RaisedButton(
                    child: new Text('Toggle me!'),
                    textColor: Colors.white,
                    shape: new RoundedRectangleBorder(
                      borderRadius: new BorderRadius.circular(30.0),
                    ),
                    color: isPressed ? Colors.grey : Colors.blue,
                    onPressed: () => setState(() => isPressed = !isPressed), // make state changes in a setState
                  )
                ],
              )
 ```
 
  ###  Floating Action Button
    Creating a simple FAB using the code snippet below
    
 <img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/fab-button.png" width="280"/> 
   
   ```dart
    return new Scaffold(
        appBar: new AppBar(
          title: new Text("FAB Example"),
        ),
        floatingActionButton: FloatingActionButton(
          onPressed: () => {},
          tooltip: 'Add me!',
          child: Icon(Icons.add),
        ),
        body:...
     );
 ```

 ## 4. Navigation
 

### Bottom Navigation Bar
Creating bottom navigation in flutter is fatanstic, truth be told! I thought I'd write some complex code to make this happen. But see how I achieved it!

#### Create a Bottom Navigation Bar without style
<img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/bottom-bar-1.png" width="280"/> 
   
   ```dart
    return new Scaffold(
        appBar: new AppBar(
          title: new Text("FAB Example"),
        ),
        bottomNavigationBar:BottomNavigationBar(
          currentIndex: 0,   // Set initial state of BottomNavigationBar
          items: [           // Create your BottomNavigationBar items
            BottomNavigationBarItem(
              icon: new Icon(Icons.playlist_add),
              title: new Text("Playlist"),
            ),
            BottomNavigationBarItem(
              icon: new Icon(Icons.person),
              title: new Text("My Profile")
            ),
            BottomNavigationBarItem(
              icon: new Icon(Icons.mail),
              title: new Text("Inbox")
            )
          ],
        ),
        body:...
     );
 ```
 #### Create a Bottom Navigation Bar with custom style
<img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/bottom-bar-2.png" width="280"/> 
   
   ```dart
    return new Scaffold(
        appBar: new AppBar(
          title: new Text("FAB Example"),
        ),
            bottomNavigationBar: Theme(  // Create your custom style with Flutter Theme
          data: Theme.of(context).copyWith(
              canvasColor: Colors.blueAccent, // Choose your preferred color as the BottomNavigationBar background
              primaryColor: Colors.white30, // Choose your preferred color as the primary color
              textTheme: Theme.of(context) // The text theme goes here
                  .textTheme
                  .copyWith(caption: new TextStyle(color: Colors.white))),
          child: BottomNavigationBar(
            currentIndex: 0, // Set initial state of BottomNavigationBar
            items: [          // Create your BottomNavigationBar items
              BottomNavigationBarItem(
                icon: new Icon(Icons.playlist_add),
                title: new Text("Playlist"),
              ),
              BottomNavigationBarItem(
                  icon: new Icon(Icons.person), title: new Text("My Profile")),
              BottomNavigationBarItem(
                  icon: new Icon(Icons.mail), title: new Text("Inbox"))
            ],
          ),
        ),
        body:...
     );
 ```
 
 ### Prepare for Navigation
 
 You'd definetly want to navigate between multiple pages using bottom navigation bar. Here is how you can do that seamlessly!
 
 ##### Step 1:
      Add two new instance properties to your State class. Something like this:
 ```dart
       class _FreeDemoState extends State<FreeDemo> {
              int _currentIndex = 0;
              final List<Widget> _children = [];
             ...
 ```
 
  ##### Step 2:
      Add children to a list in your State class. Something like this:
 ```dart
    // Declare all the widgets you want to navigate on bottom bar item click
    final List<Widget> _children = [
    PlaceholderWidget(Colors.white), 
    PlaceholderWidget(Colors.green),
    PlaceholderWidget(Colors.blue)
  ];
 ```
  ##### Step 3:
      Create a function that will update the value of _currentIndex in your State class.
      It'd be called when user taps on a bottombar item. Something like this:
 ```dart
    void onTabTapped(int index) {
   setState(() {
     _currentIndex = index;
   });
 }
 ```
 
 ##### Step 4:
     Create a class called PlaceholderWidget.This widget will be displayed when Bottom bar is tapped.
 ```dart
import 'package:flutter/material.dart';

class PlaceholderWidget extends StatelessWidget {
  final Color color;

  PlaceholderWidget(this.color);

  @override
  Widget build(BuildContext context) {
    return Container(
      color: color,
      child: new Center(
        child: new Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            new Text(
              'Try me!',
              style: new TextStyle(
                fontWeight: FontWeight.bold,
                fontSize: 100.0,
                fontFamily: 'Roboto',
              ),
            ),
           ...
          ],
        ),
      ),
    );
  }
}
 ```
  ##### Step 5:
     Create a class called PlaceholderWidget.This widget will be displayed when Bottom bar is tapped.
 ```dart
@override
 Widget build(BuildContext context) {
   return Scaffold(
     appBar: AppBar(
       title: Text('My Flutter App'),
     ),
     bottomNavigationBar: Theme(
          data: Theme.of(context).copyWith(
              canvasColor: Colors.blueAccent,
              primaryColor: Colors.white30,
              textTheme: Theme.of(context)
                  .textTheme
                  .copyWith(caption: new TextStyle(color: Colors.white))),
          child: BottomNavigationBar(
            currentIndex: _currentIndex, // Set the value of _currentIndex to currentIndex
            onTap: onTabTapped,       // Set the onTabTapped function we creatd earlier
            items: [
              BottomNavigationBarItem(
                icon: new Icon(Icons.playlist_add),
                title: new Text("Playlist"),
              ),
              BottomNavigationBarItem(
                  icon: new Icon(Icons.person), title: new Text("My Profile")),
              BottomNavigationBarItem(
                  icon: new Icon(Icons.mail), title: new Text("Inbox"))
            ],
          ),
        ),
        body:_children[_currentIndex] // Change Widget based on item selected
   );
 }
 ```
##### Yaaaaaaaassssss!!!! We just did it! Take a look at the result
<img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/bottom-tap-1.png" width="280"/> <img src="https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/screenshots/bottom-tap-2.png" width="280"/> 
 
 
