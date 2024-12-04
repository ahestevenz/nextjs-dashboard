# Next JS Tutorial
 
Here's an Overview of Features You'll Learn About in This Course:
 
- **Styling**: The different ways to style your application in Next.js.
- **Optimizations**: How to optimize images, links, and fonts.
- **Routing**: How to create nested layouts and pages using file-system routing.
- **Data Fetching**: How to set up a database on Vercel, and best practices for fetching and streaming.
- **Search and Pagination**: How to implement search and pagination using URL Search Params.
- **Mutating Data**: How to mutate data using React Server Actions, and revalidate the Next.js cache.
- **Error Handling**: How to handle general and 404 not found errors.
- **Form Validation and Accessibility**: How to do server-side form validation and tips for improving accessibility.
- **Authentication**: How to add authentication to your application using [NextAuth.js](https://next-auth.js.org/) and Middleware.
- **Metadata**: How to add metadata and prepare your application for social sharing.

## [Chapter 1](https://nextjs.org/learn/dashboard-app/getting-started)

### Exploring the Project

Unlike tutorials that have you write code from scratch, much of the code for this course is already written for you. This better reflects real-world development, where you'll likely be working with existing codebases.

Our goal is to help you focus on learning the main features of Next.js, without having to write all the application code.

After installation, open the project in your code editor and navigate to `nextjs-dashboard`.

- **/app**: Contains all the routes, components, and logic for your application. This is where you'll be mostly working from.
- **/app/lib**: Contains functions used in your application, such as reusable utility functions and data fetching functions.
- **/app/ui**: Contains all the UI components for your application, such as cards, tables, and forms. To save time, we've pre-styled these components for you.
- **/public**: Contains all the static assets for your application, such as images.
- **Config Files**: You'll also notice config files such as `next.config.js` at the root of your application. Most of these files are created and pre-configured when you start a new project using `create-next-app`. You will not need to modify them in this course.


## [Chapter 2](https://nextjs.org/learn/dashboard-app/css-styling)

Here Are the Topics We’ll Cover

- How to add a global CSS file to your application.
- Two different ways of styling: Tailwind and CSS Modules.
- How to conditionally add class names with the `clsx` utility package.

## [Chapter 3](https://nextjs.org/learn/dashboard-app/optimizing-fonts-images)

Here Are the Topics We’ll Cover

- How to add custom fonts with `next/font`.
- How to add images with `next/image`.
- How fonts and images are optimized in Next.js.

[Cumulative Layout Shift](https://vercel.com/blog/how-core-web-vitals-affect-seo) is a metric used by Google to evaluate the performance and user experience of a website. With fonts, layout shift happens when the browser initially renders text in a fallback or system font and then swaps it out for a custom font once it has loaded. This swap can cause the text size, spacing, or layout to change, shifting elements around it.

### Recommended reading
There's a lot more to learn about these topics, including optimizing remote images and using local font files. If you'd like to dive deeper into fonts and images, see:

- [Image Optimization Docs](/docs/app/building-your-application/optimizing/images)
- [Font Optimization Docs](/docs/app/building-your-application/optimizing/fonts)
- [Improving Web Performance with Images (MDN)](https://developer.mozilla.org/en-US/docs/Learn/Performance/Multimedia)
- [Web Fonts (MDN)](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Web_fonts)
- [How Core Web Vitals Affect SEO](https://vercel.com/blog/how-core-web-vitals-affect-seo)


## [Chapter 4](https://nextjs.org/learn/dashboard-app/creating-layouts-and-pages)

Here are the topics we’ll cover

- Create the dashboard routes using file-system routing.
- Understand the role of folders and files when creating new route segments.
- Create a nested layout that can be shared between multiple dashboard pages.
- Understand what colocation, partial rendering, and the root layout are.

## [Chapter 5](https://nextjs.org/learn/dashboard-app/navigating-between-pages)

Here are the topics we’ll cover

- How to use the `next/link` component.
- How to show an active link with the `usePathname()` hook.
- How navigation works in Next.js.

### Why optimize navigation?

To link between pages, you'd traditionally use the <a> HTML element. At the moment, the sidebar links use <a> elements, but notice what happens when you navigate between the home, invoices, and customers pages on your browser.

Did you see it?

There's a full page refresh on each page navigation!

## [Chapter 6](https://nextjs.org/learn/dashboard-app/setting-up-your-database)

Here are the topics we’ll cover

- Push your project to GitHub.
- Set up a Vercel account and link your GitHub repo for instant previews and deployments.
- Create and link your project to a Postgres database.
- Seed the database with initial data.

## [Chapter 7](https://nextjs.org/learn/dashboard-app/fetching-data)

Here are the topics we’ll cover

- Learn about some approaches to fetching data: APIs, ORMs, SQL, etc.
- How Server Components can help you access back-end resources more securely.
- What network waterfalls are.
- How to implement parallel data fetching using a JavaScript pattern.

### Using Server Components to Fetch Data

By default, Next.js applications use React Server Components. Fetching data with Server Components is a relatively new approach, and there are several benefits to using them:

- **Simplified Asynchronous Handling**:  
  Server Components support promises, providing a simpler solution for asynchronous tasks like data fetching. You can use `async/await` syntax without relying on `useEffect`, `useState`, or external data-fetching libraries.

- **Server-Side Execution**:  
  Server Components execute on the server, allowing you to keep expensive data fetches and logic on the server while only sending the result to the client.

- **Direct Database Queries**:  
  Since Server Components execute on the server, you can query the database directly without needing an additional API layer.



## [Chapter 8](https://nextjs.org/learn/dashboard-app/static-and-dynamic-rendering)

Here are the topics we’ll cover:

- What static rendering is and how it can improve your application's performance.
- What dynamic rendering is and when to use it.
- Different approaches to make your dashboard dynamic.
- Simulate a slow data fetch to see what happens.


## [Chapter 9](https://nextjs.org/learn/dashboard-app/streaming)

Here are the topics we’ll cover:

- What streaming is and when you might use it.
- How to implement streaming with `loading.tsx` and `Suspense`.
- What loading skeletons are.
- What route groups are, and when you might use them.
- Where to place `Suspense` boundaries in your application.


### What is streaming?
Streaming is a data transfer technique that allows you to break down a route into smaller "chunks" and progressively stream them from the server to the client as they become ready.

![](assets/server-rendering-with-streaming.avif)

Diagram showing time with sequential data fetching and parallel data fetching
By streaming, you can prevent slow data requests from blocking your whole page. This allows the user to see and interact with parts of the page without waiting for all the data to load before any UI can be shown to the user.

![](assets/server-rendering-with-streaming-chart.avif)

## [Chapter 10](https://nextjs.org/learn/dashboard-app/partial-prerendering)

Here are the topics we’ll cover:

- What Partial Prerendering Is
- How Partial Prerendering Works

### Recap: Optimizing Data Fetching in Your Application

You've made several key optimizations to enhance data fetching in your application:

1. **Database Optimization**  
   - Created a database in the same region as your application code to reduce latency between your server and database.

2. **Server-Side Data Fetching with React Server Components**  
   - Fetched data on the server, keeping expensive data fetches and logic on the server.  
   - Reduced the client-side JavaScript bundle size.  
   - Prevented database secrets from being exposed to the client.

3. **Efficient Data Queries**  
   - Used SQL to fetch only the data you needed, minimizing data transfer for each request.  
   - Reduced the JavaScript needed to transform the data in-memory.

4. **Parallelized Data Fetching**  
   - Leveraged JavaScript to parallelize data fetching where it made sense.

5. **Implemented Streaming**  
   - Prevented slow data requests from blocking your entire page.  
   - Enabled users to start interacting with the UI before everything finished loading.

6. **Scoped Data Fetching**  
   - Moved data fetching to the components that need it, isolating dynamic parts of your routes.


## [Chapter 11](https://nextjs.org/learn/dashboard-app/adding-search-and-pagination)

Here are the topics we’ll cover:

- Learn how to use the Next.js APIs: `useSearchParams`, `usePathname`, and `useRouter`.
- Implement search and pagination using URL search parameters.


