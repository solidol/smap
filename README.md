# MUSIC VISUALISER 

### ABOUT
This project comprises the creation of a space-themed music visualizer with five extensions including **Spectrum**, **WavePattern**, **SolarSpectrum**, **Spinner** and **Needles**. The audio visualiser turns the sound into variety of visualisations.

## TABLE OF CONTENT
1. [HOW TO USE MUSIC VISUALISER](#HOWTOUSEMUSICVISUALISER)
2. [HOW TO TROUBLESHOOT](#HOWTOTROUBLESHOOT)
3. [HOW WAS THE APP TESTED](#HOWWASTHEAPPTESTED)
4. [LIBRARY](#LIBRARY)
5. [EXTENSIONS](#EXTENSIONS)
6. [CHANGES TO PREVIOUS CODE](#CHANGESTOPREVIOUSCODE) 
7. [REFERENCES](#REFERENCES)

### 1. HOW TO USE MUSIC VISUALISER <a name="HOWTOUSEMUSICVISUALISER"></a>
- Press the **Play Button** to turn on the visualisation;
- Press the **Pause Button** to stop the visualisation;
- Press spacebar to show and hide the **Menu**;
- Press keyboard keys to select desired visualisation;
- Press **anywhere** on the screen, except play/pause button, to enter into a Fullscreen mode;

**Interface Design**
![Interface Design](./figures/howtouse.png)

**Menu**
![Menu](./figures/menu.png)


### 2. HOW TO TROUBLESHOOT <a name="HOWTOTROUBLESHOOT"></a>
- Run the app in Live Server;
- Click anywhere on the screen;
- Select **Inspect**;
- Select **Console**;
- Review **Errors** and **Warnings**;

### 3. HOW WAS THE APP TESTED <a name="HOWWASTHEAPPTESTED"></a>
Tested in:
  * Google Chrome;
  * Microsoft Edge;

### 4. LIBRARY <a name="LIBRARY"></a>
* [p5.sound documentation](https://p5js.org/reference/#/p5.FFT)
* [p5 documentation](https://p5js.org/libraries/)

#### Following methods have been used:

- `FFT.analyze()` returns an array of 1024 values between 0 and 255. Each value represents the amplitude (loudness) of a small frequency range (pitch of the sound).

- `FFT.waveform()` returns an array of 1024 values between -1
  and 1. Each value represents the amplitude of the sound for a tiny
  portion of time.

- `FFT.energy(freq1, [freq2])` returns the volume of the sound at
  frequency range specified by the `freq1` and `freq2` parameter. You
  can specify `freq1` as a number or p5.js provides strings for common
  values such as “bass” and “treble”, and leave `freq2` empty.

### 5. EXTENSIONS <a name="EXTENSIONS"></a>

#### (1) SPECTRUM.JS
`Spectrum()`built with following anonymous function expressions:
- `this.drawNorthenLights = function ()` draws **Spectrum** to the screen with a **Northern Lights** effect and draws **Shadow** over the drawn visualisation; 
- `this.drawBlackHoleSpinner = function ()` designed to call following functions to make the code more readable:

      this.drawBlackHole() 
      this.drawCircleWave()

- `this.drawWave = function (hMin, hMax)` draws three `Waves` to the screen; 
  * `hMin` and `hMax`: parameters for positions of each wave;

- `this.drawBlackHole = function (hx, hy, bhSize)` draws `Black Holes` to the screen; 
  * `hx` and `hy`: parameters for **x** and **y** coordinates;
  * `bhSize`: parameter for size of `Black Holes` and `triangle()`;

- `this.drawCircleWave = function (cx, cy, bhSize)` draws two pulsating ellipses to the screen; 
  * `cx` and `cy`: parameters for for **x** and **y** coordinates;
  * `bhSize`: parameter for size of `Ellipses`;

- `this.draw = function () ` designed to call following functions to make the code more readable:

      this.drawNorthenLights()
      this.drawWave() 
      this.drawBlackHoleSpinner()

![Spectrum Extension](./figures/1.%20spectrum.png) 

#### (2) SOLARSPECTRUM.JS
`SolarSpectrum()` built with following anonymous function expressions:
- `this.drawGradientBackground = function ()` draws `setGradient` to the screen;
- `this.drawTimer = function ()` draws `Timer` to the screen with `Math.floor()` and `if/else` statements;
- `this.drawEllipses = function ()` draws **Ellipses** to the screeen; 
- `this.drawEllipseSpectrum = function ()` draws ellipse shaped **Spectrum** to the screen with `line()`, `for loop`, `if/else` statement, `Math.cos()`, `Math.sin()`, `Math.PI`, `map()` and `fourier.analyze()`; 
- `this.draw = function ()` designed to call following functions to make the code more readable:

      this.drawGradientBackground()
      this.drawTimer()
      this.drawEllipseSpectrum()
      this.drawEllipses()

![SolarSpectrum Extension](./figures/2.%20solarspectrum.png) 

#### (3) WAVEPATTERN.JS
`WavePattern()` built with following anonymous function expressions:
- `this.drawMoon = function ()` draws **Moon**, which moves up and down the screen, and shakes randomly on the horizontal axis, with **x** and **y** of `this.moonPosition` coordinates and `if` statement;
- `this.drawNightSky = function ()` draws **Night Sky** and **Stars** to the screen with `for loop`, and `this.stars` **x** and **y** coordinates and `random()`;
- `this.drawWave = function ()` draws **Wave** to the screen with `for loop`, `map()` and `waveform()` and `vertex()`;
- `this.draw = function ()` designed to call following functions to make the code more readable:

      this.drawNightSky()
      this.drawMoon()
      this.drawWave()

![WavePattern Extension](./figures/3.%20wavepattern.png) 

#### (4) SPINNER.JS
`Spinner()`built with following anonymous function expressions:
- `this.drawSpinner = function ()` draws **Spinner**, a spinning spiral, to the screen with `fourier.waveform()`, `map()`, `for loop`, `rotate()`, `line()`, `ellipse()` and `radians()`;
- `this.drawEllipse = function ()`draws an ellipse at the beginning of the spiral for a visually appealing look;
- `this.drawBackgroundSpectrum = function ()` draws a **Pulsating Spectrum Bars** to the screen with `if` statement, `for loops`, `fourier.waveform()`, `fourier.analyze()`, `noise()` and `map()`;
- `this.drawTimer = function ()` draws `Timer` to the screen with `Math.floor()` and `if/else` statements;
- `this.draw = function ()` designed to call following functions to make the code more readable:

      this.drawBackgroundSpectrum()
      this.drawSpinner()
      this.drawEllipse()
      this.drawTimer()

![Spinner Extension](./figures/4.%20spinner.png) 

#### (5) NEEDLES.JS
`Needles()` built with following anonymous function expressions: 
- `this.onResize = function ()` resizes **plots**, **needles** and **ticks**;
- `this.needle = function (energy, centreX, bottomY)` draws a needle to an individual plot;
  * `energy` paramenter: the energy for the current frequency;
  * `centreX` paramenter: central **x** coordinate of the plot rectangle;
  * `bottomY` paramenter: the bottom **y** coordinate of the plot rectangle;

- `this.ticks = function (centreX, bottomY, freqLabel)` draws the graph ticks on an indivisual plot;
  * `centreX` paramenter: central **x** coordinate of the plot rectangle;
  * `bottomY` paramenter: the bottom **y** coordinate of the plot rectangle;
  * `freqLabel`paramenter: label denoting the frequency of the plot;
- `this.draw = function ()` draws needles, ticks and plots to the screen;

![Needles Extension](./figures/5.%20needles.png)

#### SKETCH.JS
- `preload()` preloads sound with `loadSound()`;
- `setup()` sets up canvas with `createCanvas()`, background with `background()`, `controls = new ControlsAndInput()`, `fourier = new p5.FFT()`, `amplitude = new p5.Amplitude()`, `vis = new Visualisations()` and `vis.add()`;
- `draw()` draws: 
  * background with `background()`;
  * visualisation selected by the user with `vis.selectedVisual.draw()`; 
  * the controls on top with `controls.draw()`;
- `mouseClicked()` called after mouse button has been clicked and released;
- `keyPressed()` called every time a key is pressed;
- `windowResized()` called every time the window is resized;
- `timeIt()` used in `Timer()` and increments timer value;

#### PLAYBACKBUTTON.JS
`PlaybackButton()` displays and handles clicks on the playback button and built with following anonymous function expressions: 
- `this.draw = function()`: 
  * if sound is playing it draws  **Pause Button**;
  * if sound is not playing it draws **Play Button**;
- `this.hitCheck = function()`:
  * checks for clicks on the button, starts or pauses playback; 
  * returns true if clicked false otherwise;

#### CONTROLSANDINPUT.JS
`ControlsAndInput()`handles:
  * onscreen menu;
  * keyboard
  * mouse controls

and built with following anonymous function expressions: 

- `this.mousePressed = function ()`makes the window Fullscreen or revert to windowed;
- `this.keyPressed = function (keycode)` responds to keyboard presses;
  * `keycode` parameter: the ascii code of the keypressed;
- `this.draw = function ()` draws `menu()` to the screen;
- `this.menu = function ()`draws out **menu items** for each visualisation;

### 6. CHANGES TO PREVIOUS CODE <a name="CHANGESTOPREVIOUSCODE"></a>

#### spectrum.js
- `this.draw = function ()`:
  * moved **Spectrum** into a separate function named `this.drawNorthenLights = function ()`to make the code more readable;
  * calls `this.drawNorthenLights()`, `this.drawWave` and `this.drawBlackHoleSpinner()`;
  * starts and stops **Spectrum** and **Black Holes** by use of a `playbackButton` button;
- created `this.drawBlackHoleSpinner = function ()`, which is designed to call `this.drawBlackHole()` and `this.drawCircleWave()` to make the code more readable;
- created `this.drawWave = function (hMin, hMax)`, which draws three `waves` to the screen by using *for loop*;
- created `this.drawBlackHole = function (hx, hy, bhSize)`, which draws `Black Holes` to the screen. Quantity of `Black Holes` can be modified in the `setup()` under `vis.add(new Spectrum(5))`;
- created `this.drawCircleWave = function (cx, cy, bhSize)`, which draws two ellipses to the screen;

#### wavepattern.js
- `this.draw = function ()`:
  * moved **Wave** into a separate function named `this.drawWave = function ()`
  * calls `this.drawNightSky()`, `this.drawMoon()` and `this.drawWave()`, which made code more readable;
- created `this.drawNightSky = function ()`, which draws **Night Sky** and **Stars** to the screen;
- created `this.drawMoon = function ()`, which draws `Moon` to the screen;


#### needles.js
- changed `var backgroundColor` purple color; 
- `onResize()`:
  * added `this.wpad = width / 20`
  * revised `this.dialRadius` to include if/else statement, which is designed to keep all elements in place when window is resized;
- `this.draw = function ()` draws:
  * ticks
  * needels and
  * calculates the size of plots;
- `this.ticks()`: 
  * in `text(freqLabel, 0, -(this.dialRadius - 40))` changed `this.plotHeight` to `this.dialRadius`;

#### index.html
Added: 
- `<html lang="en_us">`
- `<meta charset="utf-8">`
- **Timer** font 
  * `<link rel="preconnect" href="https://fonts.googleapis.com">`
  * `<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>`
  * `<link href="https://fonts.googleapis.com/css2?family=Exo:wght@400;500;700&family=Play:wght@400;700&display=swap" rel="stylesheet">`

### 7. REFERENCES

#### (1) SPECTRUM.JS
*selective list of references*

*General*
- https://p5js.org/reference/#/p5/createGraphics
- https://p5js.org/reference/#/p5/colorMode
- https://p5js.org/reference/#/p5/noise
- https://p5js.org/reference/#/p5/random
- https://p5js.org/reference/#/p5/triangle
- https://p5js.org/reference/#/p5/ellipse
- https://p5js.org/reference/#/p5.FFT/analyze
- https://p5js.org/reference/#/p5.FFT/waveform
- https://p5js.org/reference/#/p5.FFT
- https://p5js.org/reference/#/p5/RADIANS
- https://p5js.org/reference/#/p5/translate
- https://p5js.org/reference/#/p5/lerpColor
- https://p5js.org/reference/#/p5/map
- https://p5js.org/reference/#/p5/floor
- https://p5js.org/examples/math-sine.html
- https://p5js.org/reference/#/p5/cos
- https://p5js.org/reference/#/p5/image
- https://p5js.org/reference/#/p5/line
- https://p5js.org/reference/#/p5/vertex
- https://p5js.org/reference/#/p5.Amplitude/getLevel
- https://p5js.org/reference/#/p5/rotate

*this.drawCircleWave*
taken inspiration from following code, but adapted and refined for the project: 
- https://editor.p5js.org/ethanprintz/sketches/SJ2mTiYc7
- https://itp.nyu.edu/classes/cc-f18/category/production-assignments/sound-and-light/

*this.drawNorthenLights*
taken inspiration from following code, but adapted and refined for the project: 
- https://editor.p5js.org/js6450/sketches/XYnHHUIP7

*this.drawBlackHole*
taken inspiration from following code, but adapted and refined for the project:
- https://js6450.github.io/audio-viz/index.html

#### (2) SOLARSPECTRUM.JS
*General*
taken visual inspiration from the following YouTube video: 
- https://www.youtube.com/watch?v=GkZKUC2BIII

used from external sources directly with minor changes:
- Gradient background: https://p5js.org/examples/color-linear-gradient.html

*this.drawTimer*
taken inspiration from following code, but adapted and refined for the project:
- http://javascript.ru/forum/dom-window/66782-tajjmer-obratnogo-otscheta-minuty-sekundy.html
- https://editor.p5js.org/denaplesk2/sketches/ryIBFP_lG

*this.drawEllipsespectrum*
used following resources to create ellipse shaped spectrum:
- https://en.wikipedia.org/wiki/Polar_coordinate_system
- https://p5js.org/examples/math-polartocartesian.html
- https://coderoad.ru/28510378/Как-нарисовать-полярные-координаты-с-помощью-P5-js

#### (3) WAVEPATTERN.JS
*this.drawMoon* 
used from external sources directly with minor changes, created this.moonPosition = {}:
- https://p5js.org/examples/hello-p5-animation.html

*this.drawNightSky*
taken inspiration from following code, but adapted and refined for the project:
- https://editor.p5js.org/hosken/sketches/LRCedfGPY

#### (4) SPINNER.JS
*this.drawSpinner*
taken inspiration from following code, but adapted and refined for the project:
- https://js6450.github.io/audio-viz/index.html
- https://p5js.org/reference/#/libraries/p5.sound

*this.drawBackgroundSpectrum*
taken inspiration from following code, but adapted and refined for the project:
- https://editor.p5js.org/js6450/sketches/XYnHHUIP7

*this.drawTimer*
taken inspiration from following code, but adapted and refined for the project:
- http://javascript.ru/forum/dom-window/66782-tajjmer-obratnogo-otscheta-minuty-sekundy.html
- https://editor.p5js.org/denaplesk2/sketches/ryIBFP_lG

#### mouseClicked()
- https://p5js.org/reference/#/p5/mouseClicked

#### keyPressed()
- https://p5js.org/reference/#/p5/keyPressed

#### windowResized()
- https://p5js.org/reference/#/p5/windowResized

#### TESTING
- https://www.browserstack.com/guide/learn-software-application-testing
- https://www.softwaretestinghelp.com/what-is-non-functional-testing/


