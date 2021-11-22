# PandaCanvas (Simple Drawing Canvas)

PandaCanvas is a simple drawing canvas for Android apps to cater all the use cases of sketchpad, with all basic functionalities such as, setting color, stroke and shadow as well as different option to pick such as pen, highlighter, eraser, moreover, it also includes undo and redo functionality along with a complete clear canvas option

## Getting Started


### Step 1

Add maven repository in project level build.gradle.
```
    repositories {
        google()
        mavenCentral()
        maven { url "https://jitpack.io" }
    }
```  


### Step 2

Add PandaFCM dependencies in App level build.gradle.
```
    dependencies {
        implementation 'com.github.Funsol-DevOps:PandaCanvas:1.0'
    }
```  

### Step 3

Add the PandaCanvas widget in your xml
```
    <com.pandalibs.pandacanvaslib.CanvasPad
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
```
After this your canvas is ready to draw.

### Functions / Setters

You can use various setters to achieve a fully functioning sketchpad.

To set color:
```
  binding.canvas.setColor(color)
```

To set stroke:
```
  binding.canvas.setLineThickness(30f)
```

To set stroke:
```
  binding.canvas.setLineThickness(30f)
```

To set eraser:
```
  binding.canvas.setEraser()
```

To handle undo and redo (enable/disabled):
```
        binding.canvas.setOnClickListener {
            binding.undo.isEnabled = binding.canvas.pathSize() > 0
            binding.redo.isEnabled = binding.canvas.undoPathSize() > 0

        }
```

To undo:
```
          binding.undo.setOnClickListener {
            binding.canvas.onClickUndo()
            binding.undo.isEnabled = binding.canvas.pathSize() > 0
            binding.redo.isEnabled = binding.canvas.undoPathSize() > 0
        }
```


To redo:
```
        binding.redo.setOnClickListener {
            binding.canvas.onClickRedo()
            binding.undo.isEnabled = binding.canvas.pathSize() > 0
            binding.redo.isEnabled = binding.canvas.undoPathSize() > 0
        }
```

To clear canvas:
```
 binding.canvas.clearCanvas()
```

Checkout the sample app to see implementation of these options.


## License

MIT License

Copyright (c) [2021] [Saad Ali Shujaat]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
