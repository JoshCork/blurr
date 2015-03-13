# blurr
This Repo holds my project 4 learnings and code.  I've optimized the pages for both the Google page rank score as well as the frames per second on the animated pizza page.  

### how to use this repo
This repo has been broken up into a few folders:  
    - At the root is the project that I downloaded for optimization.
    - Classroom Material: This holds the reflections and projects I worked through while taking the supporting classes for this project. 

To view the code that I updated just work in the root directory.
To view my live optimized code running online please use the gh-pages branch of this repo. 

- You can browse to http://joshcork.github.io/blurr and view the pages that i have optimized.
- point google page speed insights at the above url or you can click on [this](https://developers.google.com/speed/pagespeed/insights/?url=joshcork.github.io%2Fblurr&tab=mobile) link.
- Browse to the pizza page and open dev tools.  Do some scrolling and watch the frame rates.  You can also turn on the frame rate visualization in dev tools if you are so inclined. 
- Browse to the pizza page and open dev tools.  Scroll down to the pizza sizing slider.  Slide it to different positions.  The console in dev tools should reflect the time to resize the pizza and it should be < 5ms. 


### optimizations I performed
- In-lined CSS
- Used an async javascript loader for the font vs. the default reference to the web font.
- In-lined some critical javascript used for resizing the pizza
- Moved unnecessary code out of the for loop and into a cached variable (as opposed to calculating on each run through the loop).


### naming convention of this repo
The transformer name I chose for this repo is: Blurr... he is the fastest Autobot on land. He was used primarily by the Autobots as a high speed messenger. Blurr was also portrayed having extremely fast speaking mannerisms, and a nervous streak when dealing with his superiors. With his top speed of 800 miles-per-hour, Forbes named Blurr as the fastest fictional car in 2008.


