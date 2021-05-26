# CommonJS Implementation of OrbitControls.js library


### OrbitControls.js library, when used with ThreeJS, enables mouse and scroll interaction with 3D objects.

#### Currently, ThreeJS can be used in a CommonJS environment however when incorporating OrbitControls.js it results in errors.


The common errors are - 
```
$ Uncaught ReferenceError: require is not defined at orbitControls.js:7
$ require not defined
$ Uncaught ReferenceError: module is not defined at orbitControls.js:558
```
The require errors can be solved by importing OrbitControls.js via RequireJS.
But this approach doesn't solve `module` error which is due to `module.exports`.

___

### Here, I've come across a workaround to solve this. 

Step 1. Add the cdn for ThreeJS in HTML head.
```HTML
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js" crossorigin="anonymous"></script>
```

Step 2. In the HTML body define the canvas.
```HTML
<canvas id="bg">
</canvas>
```

Step 3. Before closing the body tag, download the orbitcontrols.js from this repo and add it using the appropriate path.
 ```HTML
 <script src="./orbitControls.js"></script>
 ```

Step 4. Add the main.js having the features you've implemented in the ThreeJS and Orbitcontrols.js
```HTML
<script src="./main.js"></script>
```

## Advantages
If you're using this method, a node environment isn't required. Which means your website can easily be hosted on static hosting sites like GitHub Pages.
