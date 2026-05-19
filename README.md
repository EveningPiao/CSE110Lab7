Preferred test placement: Within a GitHub Action that runs whenever code is pushed.

Explanation:
- This ensures tests run automatically on every change before code is merged or deployed.
- It catches regressions early and keeps the development pipeline reliable.
- Manual local testing is useful, but CI automation is a stronger safety net for team workflows.

---

## Check Your Understanding

### 3) What is the difference between navigation and snapshot mode?

Navigation mode analyzes a page right after it loads from scratch. It reloads the page, measures the entire load process, and produces metrics about performance. It is the best mode for getting an overall performance score, but it cannot analyze user interactions or changes to the page after it has loaded.

Snapshot mode, on the other hand, analyzes the page in its current state without reloading it. It is best used for finding accessibility issues or auditing a particular state of the page. Because it does not observe the page loading, it cannot measure JavaScript performance, network activity, or changes to the DOM tree over time.


### 4) Name three things we could do to improve the CSE 110 shop site based on the Lighthouse results.

1. **Add proper image dimensions and use modern image formats.** The product images on the site are loaded without explicit `width` and `height` attributes set in a way that prevents layout shift, and they are served in older formats.

2. **Improve accessibility by adding meaningful labels and color contrast.** Lighthouse typically flags issues such as buttons or links without accessible names, insufficient color contrast between text and background, and missing ARIA attributes. Adding descriptive `aria-label` attributes to icon-only buttons, ensuring sufficient contrast for the "Add to Cart" button text, and properly associating form labels would make the site more usable for people relying on screen readers.

3. **Eliminate render-blocking resources and defer non-critical JavaScript.** The site loads its scripts and styles in a way that blocks the initial render of the page. Adding `defer` or `async` to non-critical `<script>` tags, inlining critical CSS, and lazy-loading product images that are below the fold would significantly improve First Contentful Paint and Time to Interactive metrics.
