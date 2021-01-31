# Week 01

## Shapes (Polygons): Collections of Points

### Triangle

- Collection of three points

- Basis for complex and wireframe models

### Circle

- Infinite collection of points that are the same distance from the cenre of a circle
- However, Java class is just a finite collection of points

## Why Semantics: Motivation to Read Code

### Semantic

- Basically means "meaning" of each part of the code
- How to execute it step-by-step by hand using pen and paper only

## Variables

### Default Value

- When a variable is declared using programming language like C, no default value is given
	- Java provides two solutions:
		1. an initial default value of 0 is given to instance variables
		2. an explicit error is given for using a local variable

```java
int x = 4;
int y = x + 2;
int z = x + y;
```

- In the above example, declaration and initialization are combined into the same statement

## Mathematical Operators

`+ - * / %`

## Functions

```java
int myFunction(int x, int y){
  int z = 2 * x - y;
  return z * x;
}
int f(int n){
  return 3 + myFunction(n, n+1);
}
int g(){
  int a;
  a = myFunction(3, 7);
  int b = f(a * a);
  return b;
}
```

## Conditions

```java
int f(int x, int y){
	if (x < y){
    System.out.println("x < y");
    return y + x
  }
  else {
    System.out.println("x >= y");
    if (x > 8){
      return y + 7;
    }
  }
  return x - 2;
}

int g(){
  int a = f(3, 4);
  int b = f(a, 5);
  return b;
}
```

## Classes

- OOP combines the `data` and the `code` that manipulates it, together into logical units called `objects`
-  A `class` is a template to make objects

```java
public class Point { // declares a class named Point
  private int x; // declares integer x
  private int y; // declares integer y
  public Point(int startx, int starty){ // declares constructor
    x = startx;
    y = starty;
  }
 	public int getX() { return x; } // declares method getX
  public int getY() { return y; } // declares method getY
  public double distance(Point otherPt){ // declares method distance
    int dx = x - otherPt.getX(); // calls the getX mthod on the otherPt object
    int dy = y - otherPt.getY(); // calls the getY mthod on the otherPt object
    return Math.sqrt(dx * dx + dy * dy);
  }
  public static void main(String[] args){ // declares a static method, main
    Point p1 = new Point(3,4);
    Point p2 = new Point(6,8);
    System.out.println(p1.distance(p2));
  }
}
```

- Variables in an objects are called `fields` or `instance variables`, since they are present in all instances created by the object
- `Private` means only code in this class can directly manipulate these fields
- `Public` means any code can use it
- `Constructor` is the code that gets run when an object is created to initialize that object
	- It looks like a function but has `no return type`
	- Named the same as the class
- `Methods` are `functions` inside classes, so technically, all functions in Java are methods
- `Main` is a special method, execution begins in main before any objects are even created

