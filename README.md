# Flutter Cheat Sheet
You need to get started quickly with Flutter? Here are some cheats that will help you build your next billion dollar app!!


# 1. Card Layout

```java
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
  
  # 2. Aligning widgets evenly
  ##   Horizontal MainAxisAlignment
    Setting the main axis alignment to spaceEvenly divides the free horizontal space 
    evenly between, before, and after each image
  ![alt text](https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/img1.PNG)
   ```java
   Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('img/1.jpg'),
    Image.asset('img/2.jpg'),
    Image.asset('img/3.jpg'),
  ],
);
   ```
 ##   Vertical MainAxisAlignment
    Setting the main axis alignment to spaceEvenly divides the free vertical space 
    evenly between, before, and after each image
  ![alt text](https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/img2.PNG)
   ```java
   Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('img/1.jpg'),
    Image.asset('img/2.jpg'),
    Image.asset('img/3.jpg'),
  ],
);
 ```
  ##   Packing Widgets
    By default, a row or column occupies as much space along its main axis as possible,
    but if you want to pack the children closely together, set its mainAxisSize to MainAxisSize.min. 
    The following example uses this property to pack 3 buttons together.
    
   <img src="(https://github.com/Temidtech/Flutter-Cheat-Sheet/blob/master/Packing-widget.png" width="280")/> 
   
   ```java
   Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('img/1.jpg'),
    Image.asset('img/2.jpg'),
    Image.asset('img/3.jpg'),
  ],
);
 ```
