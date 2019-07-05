# SwiftyGFX

A swift graphics library intended for my SwiftyOLED library.

## Key features

* Ability to render any font provided in _.ttf_ or _.otf_

## TODO

* Write unit tests that makes sense
* Provide a defualt path to look for fonts
* Add more triangle initializers (using trigonometry magic to extrapolate data)

## Documentation

### Coordinate system

This library uses iOS like coordinate system. The X axis is increasing to the right. The Y axis is increasing downwards.

### Primitives

Each of defined primitives conforms to _Drawable_ protocool. The library defines following groups of primitives:

#### Lines

The Bresenham's was used for drawing oblique lines. Even though you can draw horizontal and vertical lines with `ObliqueLine` class it is way faster to used either `HorizontalLine` or `VerticalLine` class.

```swift
    ObliqueLine(from origin: Point, to endPoint: Point)
    HorizontalLine(from origin: Point, lenght: Int)
    VerticalLine(from origin: Point, lenght: Int)
```

#### Rectangles

```swift
    Rectangle(at origin: Point = Point(x: 0, y: 0), height: Int, width: Int)
    Square(at origin: Point = Point(x: 0, y: 0), sideSize a: Int)
```

#### Ellipses

```swift
    Ellipse(at origin: Point = Point(x: 0, y: 0), yRadius: Int, xRadius: Int)
    Ellipse(at origin: Point = Point(x: 0, y: 0), height: Int, width: Int)
    Circle(at origin: Point = Point(x: 0, y: 0), radius: Int)
    Circle(at origin: Point = Point(x: 0, y: 0), width: Int)
```

#### Triangles

```swift
    Triangle(at origin: Point = Point(x: 0, y: 0), corner1: Point, corner2: Point, corner3: Point)
```

#### Text

```swift
    Text(_ text: String, font pathToFont: String, at origin: Point = Point(x: 0, y: 0), pixelHeight: UInt32 = 16, pixelWidth: UInt32 = 16)

```

### Rendering

The _Drawable_ protocool guarantes that for each object you can generate array of tuplets of integer and integer by calling `.generatePointsForDrawing()`. This effectively is array of points (each having X and Y coordinate). They can be passed to the display library of your choice and therefore be displayed. 

## Contributing

Feel free to sugest changes, report bugs and issues, create pull requests.

