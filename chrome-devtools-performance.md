# Chrome DevTools Performance 
You should keep an eye at the following (these also give important insight into how react internally works): 

- Main thread activity
- Frames per second
- Layouts and style recalculations per second
- CPU usage
- JS heap size
- No of DOM nodes, JS event listeners, documents, frames on the page
- Network requests in the networks tab, also shows the KBs transfered and total no of requests
- Enable screenshots to see how the page looked at a particular time in the waterfall graph
- Interactions in the waterfall graph show how the user interacted with the page
- Use the *Rendering* tab to see paints, scroll performance, FPS, layout shifts etc in real time
- See different overlapping layers (compositing and rasterization)
- See the detailed paint calculations in the paint profiler

[Source](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)