# Wave

In this section we're going to introduce you to an important concept in C4: Animations. We'll also show you how to work with gradients and timers to create a wave effect. When we're done, we'll show you how to tweak a single line of code to get some different aesthetics out of the example.

Start by creating a new C4 project called Waves.

## Animations
In C4, you'll be working a lot with objects that contain properties. For example, all shapes have a `fillColor` and `strokeColor`. C4 lets you create animations by changing the properties of objects. Rather than calculating all the steps between `a` and `b`, you can focus on thinking about states. For example, the following snippet will create a 0.25 second animation where a circle's fill color will shift to red: 

```
C4ViewAnimation(duration: 0.25) {
    circle.fillColor = red
}
```

Now's a good time to check out the basics of animtions and properties over at: http://www.c4ios.com/basics/

##Gradients
For this section, we're going to create a wave of gradients by using a `for` loop and a timer to offset our animations. You can create a simple gradient by giving it a frame and a set of colors, like so:

```
override func setup() {
    let g = C4Gradient(frame: C4Rect(0,0,40,200), colors: [C4Pink,C4Blue])
    g.center = canvas.center
    canvas.add(g)
}
```

![A basic gradient][gradient01.png]


By default, the gradient draws from top to bottom of its frame. If you want to change that you can specify a new value for either its `startPoint` or `endPoint`.

By adding the following line to `setup()` the gradient will draw from its top-left corner to its bottom-right:

```
g.endPoint = C4Point(1,1)
```

![Changing the endPoint of a gradient][gradient02.png]


* Wave
 * Animations
 * Gradients
 * Timers
 * Experiments
