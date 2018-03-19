# Video Speed Controller

A video speed controller. Built for Wes Bos' [JavaScript 30](https://javascript30.com/) course.

[![Screenshot of Video Speed Controller](https://res.cloudinary.com/gerhynes/image/upload/v1519425012/Screenshot-2018-2-23_Video_Speed_Scrubber_vyj6vw.png)](https://gk-hynes.github.io/video-speed-controller/)

## Notes

The goal is to be able to update the video playback speed by hovering over the speed controller.

First, select the `speed` div, the `bar` div within it, and the video.

Add a mousemove event listener to `speed` and connect it to the function `handleMove`.

Inside `handleMove`, set `y` to `e.pageY - this.offsetTop`.

Get the `percent` by setting it to `y / this.offsetHeight`.

Don't use an arrow function as you need `this` to be equal to the speedbar itself.

Set `min` to 0.4 and `max` to 4, or whatever min and max speeds you want.

To have the bar respond to user input, set `height` to `Math.round(percent * 100)`, and set `bar.style.height` to `height`. Then set `playbackRate` to be `percent * (max - min) + min` and set the textContent of `bar` to be `playbackRate.toFixed(2)`. (This rounds it to two decimal places).

Finally, you want to apply `playbackRate` to the video, so set `video.playbackRate` to be `playbackRate`.
