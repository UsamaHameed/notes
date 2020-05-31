# Frontend Performance

Performance in modern web apps has never been more important. Now that we have apps with many more features than ever before and that we have a platheora of devices and operating systems over ever varrying network conditions makes the topic complicated. 

Performance affects UX. Performance directly co-relates to bounce rates and coversions. 


## [The RAIL Model](https://developers.google.com/web/fundamentals/performance/rail)

### Response
- Process user input events within 50ms to ensure a visible response within 100ms(50ms is reserved for other processes that might be queued earlier). This applies to most inputs, such as clicking buttons, toggling form controls, or starting animations. This does not apply to touch drags or scrolls(These are considered animations).
- Though it may sound counterintuitive, it's not always the right call to respond to user input immediately. You can use this 100ms window to do other expensive work. But be careful not to block the user. If possible, do work in the background.
- For actions that take longer than 50ms to complete, always provide feedback.

### Animation
- Produce each frame in an animation in 10ms or less (1000ms / 60 frames per second ≈ 16ms, browsers need about 6ms to render).
- FPS should be consistent. 
- Make use of the idle time during the 100ms response to pre-calculate expensive work so that you maximize your chances of hitting 60fps.
- Optimize [Critical Render Path](https://developers.google.com/web/fundamentals/performance/rendering).

### Idle
- Maximize idle time to increase the odds that the page responds to user input within 50ms.
- Use idle time to complete deferred work. For example, for the initial page load, load as little data as possible, then use idle time to load the rest.
- Perform work during idle time in 50ms or less. Any longer, and you risk interfering with the app's ability to respond to user input within 50ms.
- If a user interacts with a page during idle time work, the user interaction should always take the highest priority and interrupt the idle time work.

### Load
- Become interactive in under 5 seconds


## Ideal Specs

- First meaningful paint
- First interactice
- Consistently interactive
- 
## Recommendations

Recommendations always depend a bit on what the purpose of the app is and what the users would be expecting. 

Its all about resources JS(by far the most costly resource, libraries have to be downloaded, parsed, compiled and executed), CSS(has to be download, parsed, applied before the site specific styles)
- Code Splitting and Lazy loading
- Minify and uglify text resources
- Optimize images/progressively load them
- Service workers
- HTTP Caching
- Use video instead of animated GIFs

## Benchmarking

- [Speed Score Card](https://www.thinkwithgoogle.com/feature/testmysite/)
- Lighthouse (Chrome devTools)
- Audit (Chrome devTools)

## Additional Reading
- [Render Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css) 
- [The cost of JS](https://medium.com/dev-channel/the-cost-of-javascript-84009f51e99e)
- [HTTP Caching](https://web.dev/http-cache/)
- [HTTP/2](https://developers.google.com/web/fundamentals/performance/http2)
- [Resource Prioritization](https://developers.google.com/web/fundamentals/performance/resource-prioritization)
- [Image Optimization](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/automating-image-optimization)
- [Client Hints](https://httpwg.org/http-extensions/client-hints.html)
- [Network Information API](https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation)
- [PRPL Model](https://web.dev/apply-instant-loading-with-prpl/)
- [Rendering Performance](https://developers.google.com/web/fundamentals/performance/rendering)