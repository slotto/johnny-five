<!--remove-start-->
# 

Run with:
```bash
node eg/slider-log.js
```
<!--remove-end-->

```javascript
var five = require("johnny-five"),
  board, slider, servo, scalingRange;

board = new five.Board();

board.on("ready", function() {

  slider = new five.Sensor({
    pin: "A0",
    freq: 50
  });

  // log out the slider values to the console.
  slider.scale(0, 100).on("slide", function(err, value) {
    if (err) {
      console.log("error: ", err);
    } else {
      console.log(Math.floor(this.value));
    }
  });
});

```








<!--remove-start-->
## License
Copyright (c) 2012, 2013, 2014 Rick Waldron <waldron.rick@gmail.com>
Licensed under the MIT license.
Copyright (c) 2014, 2015 The Johnny-Five Contributors
Licensed under the MIT license.
<!--remove-end-->
