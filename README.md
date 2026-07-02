# iyf-s11-week-o1-alfredngure
## article
Writing Code That Everyone Can Read: Why Semantic HTML and Accessibility Matter
When you first start building for the web, it’s incredibly tempting to rely entirely on <div> and <span> elements to structure your layout. After all, with a bit of CSS, you can make a <div> look exactly like a button, a navigation bar, or an entire article. But a website shouldn't just look right—it needs to behave right for every single person visiting it.

That is where Semantic HTML comes in.

What is Semantic HTML?
Semantic HTML means using HTML tags that inherently describe the meaning and purpose of the content they contain, rather than just how they look. For example, a <header> tag tells both the browser and assistive technologies exactly what its role is, whereas a <div class="header"> is just generic code requiring extra interpretation.

Using semantic elements is crucial for two main reasons:

Accessibility (a11y): Screen readers and other assistive devices rely on semantic tags to construct an accessibility tree, allowing users with visual or physical impairments to navigate a page efficiently.

SEO & Maintainability: Search engines crawl semantic tags to understand your content hierarchy, which boosts your search ranking. It also makes your codebase infinitely cleaner and easier for other developers to read.

The Transformation: Before vs. After
During my recent portfolio build, I audited my initial landing page markup. Here is a quick look at how shifting from non-semantic to semantic components drastically changes the structural clarity of the code:

Before (Non-Semantic)HTML
<!-- before (non-Semantic )html -->
<div class="header">
  <div class="logo">My Portfolio</div>
  <div class="nav">
    <div class="nav-item">Home</div>
    <div class="nav-item">Projects</div>
  </div>
</div>

<!-- After (Semantic & Accessible) -->
<header>
  <h1>My Portfolio</h1>
  <nav aria-label="Main Navigation">
    <ul>
      <li><a href="index.html">Home</a></li>
      <li><a href="projects.html">Projects</a></li>
    </ul>
  </nav>
</header>
3 Accessibility Fixes Implemented
Running my initial site through Lighthouse and the WAVE audit tool highlighted a few critical issues. Here is how I resolved them:

1. Missing Image Alternative Text
The Issue: I had project screenshots without alt attributes. Screen readers would skip them entirely or read out confusing image filenames.

The Fix: Added concise, descriptive alt text to every <img> tag to describe the context of the visual asset.

2. Broken Heading Hierarchy
The Issue: I skipped from an <h1> directly to an <h3> because I liked the default font size. This breaks the logical document structure for screen reader navigation indices.

The Fix: Re-organized headings sequentially (<h1> followed by <h2>), handling visual resizing purely via CSS.

3. Missing Form Labels
The Issue: My contact form relied solely on placeholder text inside inputs, which disappears once a user starts typing.

The Fix: Explicitly linked proper <label> elements to their respective <input> elements using matching for and id attributes.

Check Out My Project
I've successfully applied these practices to my live personal portfolio! You can check out the clean semantic markup and test its accessibility yourself here:
👉 View My Deployed Portfolio (Note: Remember to update this link with your actual GitHub Pages URL before posting!
