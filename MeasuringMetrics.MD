When it comes to measuring the performance of React applications, several key metrics are commonly used to assess user experience. These metrics are important for understanding different aspects of performance. Here are some of the key metrics:

1. **TTI (Time to Interactive)**: TTI measures the time it takes for a web page to become fully interactive. It marks the point at which the page has displayed useful content, and the user can interact with it. TTI is crucial because it indicates when the user can start engaging with the application.

2. **FCP (First Contentful Paint)**: FCP measures the time it takes for the browser to render the first piece of content on the screen. This content could be text, an image, or any visible element. FCP provides a visual indication to the user that the page is loading.

3. **FMP (First Meaningful Paint)**: FMP measures the time it takes for the primary content of a web page to become visible and recognizable to the user. It provides a more user-centric perspective compared to FCP, as it considers when the meaningful content, not just any content, is rendered.

4. **LCP (Largest Contentful Paint)**: LCP measures the loading performance of a web page. It reports the render time of the largest content element visible within the viewport. LCP helps in understanding when the most significant content of the page has been fully loaded.

5. **CLS (Cumulative Layout Shift)**: CLS measures the visual stability of a web page. It quantifies how often users experience unexpected layout shifts, which can be disruptive and lead to a poor user experience. CLS is calculated by multiplying the impact fraction (how much an element shifted) by the distance fraction (how far the element shifted) for all unexpected layout shifts during the entire lifespan of the page load.

6. **CPU and Memory Usage**: Monitoring the CPU and memory usage of a React application is essential to ensure that it's not consuming excessive resources, leading to a sluggish user experience. Tools like browser developer tools or specialized profiling tools can provide insights into CPU and memory usage.

7. **Network Requests and Latency**: The number of network requests made by the application and their latency can impact the loading time significantly. Optimizing network requests, using techniques like code splitting and lazy loading, can help in reducing latency and improving overall performance.

8. **Bundle Size**: The size of the JavaScript bundle is critical, especially for React applications. Large bundle sizes can lead to longer download times, particularly on slower network connections. Minification, tree shaking, and code splitting are common techniques used to reduce bundle size.

9. **Error Rates**: Monitoring error rates, such as JavaScript errors or API request failures, is crucial for understanding the stability of the application. High error rates can lead to a poor user experience and impact user trust in the application.

10. **Time to First Byte (TTFB)**: TTFB measures the time taken by the browser to receive the first byte of data from the server after a request is made. A fast TTFB ensures that the server is responding quickly, reducing the overall loading time of the application.

An example of a tool we can get to give us this kind of report is  lighthouse in dev tools and google page speed[https://pagespeed.web.dev/]

Live demo, analysing a sample website using lighthouse and page speed
