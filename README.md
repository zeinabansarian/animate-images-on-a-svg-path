# SVG Path Animation with Scroll

This project demonstrates how to animate an image along an SVG path in sync with page scrolling. Using GSAP and ScrollTrigger, this effect creates a visually engaging animation that moves an image along a predefined SVG line as you scroll down the page.


## Technologies Used

HTML - For structuring the SVG and image elements.

CSS - For basic styling.

JavaScript - For controlling the animation behavior.

GSAP (GreenSock Animation Platform) - For creating smooth animations.

ScrollTrigger (GSAP Plugin) - To synchronize the animation with scrolling.

## Features

Animate an image along a custom SVG path.

Control the animation with scroll position.

Adjust alignment, scaling, and easing for smooth effects.

## Code Overview

### HTML Structure

The SVG line is defined using the <path> element. The image that moves along this path is placed in an <img> tag positioned absolutely on the page.

<svg width="400" height="400" viewBox="0 0 400 400">
  <path id="linePath" d="M10 10 C 200 100, 300 300, 400 400" stroke="black" fill="transparent" />
</svg>

<img id="movingImage" src="drop.gif" alt="Moving Image" width="50" height="50" style="position:absolute;">

### JavaScript

Using GSAP and ScrollTrigger, we set up an animation for the image that follows the SVG path as the page scrolls.

gsap.registerPlugin(ScrollTrigger);

const path = document.querySelector("#linePath");
const image = document.querySelector("#movingImage");

gsap.to(image, {
  scrollTrigger: {
    trigger: path,
    start: "top center",
    end: "bottom center",
    scrub: true,
  },
  motionPath: {
    path: path,
    align: path,
    alignOrigin: [0.5, 0.5],
  },
  duration: 1,
  ease: "none",
});


## Customization

Path Adjustment: Modify the SVG path d attribute to create different movement paths.

Animation Settings: Adjust the start, end, and scrub options in ScrollTrigger to control when the animation should begin and end based on scroll position.


## Contact

For questions or feedback, feel free to reach out or open an issue in the repository.
