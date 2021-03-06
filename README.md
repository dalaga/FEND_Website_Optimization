##Launch the application:

Open the index.html file with a browser. Chrome is recommended so you may use the Chrome Dev Tools.

--Change made to optimize index.html --
1) Added 'async' to google analytics
2) Added 'media = print' to print.css link
3) Minified style.css with http://cssminifier.com/
4) Minified perfmatter.js with http://www.minifier.org/
5) Resized and compressed images with FileOptimizer
6) Inlined style.css into index.html
7) Removed external font link to Font API. (Redirect error goes away)
    **note:  also changed all the http: to https for the font API link and it was not stable for speed test.

--Modifications for main.js --
1) Change in updatePositions function:
    a) Change 200 pizzas to 20 pizzas in document.addEventListener
    b) Changed querySelectorAll to getElementsByClassName
    c) Moved items declaration and document.body.scrollTop outside of the function's for loop
    d) Moved window.performance.mark("mark_start_frame"); after the for loop
    e) Separated original for loop into two for loops
    f) Replaced items[i].style.left with items[i].style.transform and added transformX code
    g) Replaced elem.basicLeft = (i % cols) * s; with elem.style.left = (i % cols) * s + 'px';
    h) Added requestAnimationFrame function

2) Changes in changePizzaSizes function:
    a) Removed newwidth from for loop and created switch-case to establish percentages and determine size
    b) Removed dx from for loop, no longer necessary after establishing sizes in switch-case
    c) Created randomContainer variable to calculate document.getElementsByClassName("randomPizzaContainer") outside of for loop
    d) Changed querySelectorAll to getElementsByClassName

3) Added to style.css
    a) transform: translateZ(0);
    b) will-change: transform;
    c) transform: translate3d(0,0,0);
    d) backface-visibility: hidden;

================================================================================

## Website Performance Optimization portfolio project

Your challenge, if you wish to accept it (and we sure hope you will), is to optimize this online portfolio for speed! In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository and inspect the code.

### Getting started

####Part 1: Optimize PageSpeed Insights score for index.html

Some useful tips to help you get started:

1. Check out the repository
1. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

1. Open a browser and visit localhost:8080
1. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ./ngrok http 8080
  ```

1. Copy the public URL ngrok gives you and try running it through PageSpeed Insights! Optional: [More on integrating ngrok, Grunt and PageSpeed.](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/)

Profile, optimize, measure... and then lather, rinse, and repeat. Good luck!

####Part 2: Optimize Frames per Second in pizza.html

To optimize views/pizza.html, you will need to modify views/js/main.js until your frames per second rate is 60 fps or higher. You will find instructive comments in main.js.

You might find the FPS Counter/HUD Display useful in Chrome developer tools described here: [Chrome Dev Tools tips-and-tricks](https://developer.chrome.com/devtools/docs/tips-and-tricks).

### Optimization Tips and Tricks
* [Optimizing Performance](https://developers.google.com/web/fundamentals/performance/ "web performance")
* [Analyzing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/analyzing-crp.html "analyzing crp")
* [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
* [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
* [Optimizing JavaScript](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/adding-interactivity-with-javascript.html "javascript")
* [Measuring with Navigation Timing](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/measure-crp.html "nav timing api"). We didn't cover the Navigation Timing API in the first two lessons but it's an incredibly useful tool for automated page profiling. I highly recommend reading.
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/eliminate-downloads.html">The fewer the downloads, the better</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer.html">Reduce the size of text</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/image-optimization.html">Optimize images</a>
* <a href="https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/http-caching.html">HTTP caching</a>

### Customization with Bootstrap
The portfolio was built on Twitter's <a href="http://getbootstrap.com/">Bootstrap</a> framework. All custom styles are in `dist/css/portfolio.css` in the portfolio repo.

* <a href="http://getbootstrap.com/css/">Bootstrap's CSS Classes</a>
* <a href="http://getbootstrap.com/components/">Bootstrap's Components</a>
