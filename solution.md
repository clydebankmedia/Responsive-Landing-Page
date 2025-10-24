# Solution Code - Responsive Landing Page

<details>
<summary> Step 1 Solution - Build Your Semantic Structure</summary>

HTML - `index.html`

```html
<!-- =======================
     HEADER + NAV
     ======================= -->
<header>
  <nav>
    <div class="logo">
      <h1>BrandName</h1>
    </div>

    <ul class="nav-links">
      <li><a href="#">Home</a></li>
      <li><a href="#">Features</a></li>
      <li><a href="#">Pricing</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>

<!-- =======================
     MAIN CONTENT
     ======================= -->
<main>
  <section class="hero">
    <div class="hero-text">
      <h2>Build for Every Device</h2>
      <p>
        Create responsive layouts that adapt to your users, no matter the screen size.
        Start small, grow big.
      </p>
      <a href="#" class="btn-primary">Get Started</a>
    </div>

    <div class="hero-image">
      <img src="assets/img/hero-placeholder.png" alt="Illustration showing devices for responsive design" />
    </div>
  </section>
</main>
```

</details>

<details>
<summary>Step 2 Solution – Apply Mobile-First Styling</summary>

CSS - `styles.css`

```css
/* Base (mobile-first) styles — STEP 2 */

/* Header spacing for breathing room */
header {
  padding: 1rem;
}

/* Nav: stacked column, centered */
nav {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem;
  gap: 1rem;
}

.nav-links{
  display: flex;
  flex-direction: column;
  /* stacked on mobile */
  align-items: center;
  gap: 1rem;
}

/* Hero: text above image, centered; side padding on small screens */
.hero {
  display: flex;
  flex-direction: column; /* text above image */
  align-items: center;
  text-align: center;
  padding-left: 1rem;
  padding-right: 1rem;
}

/* Use theme tokens for text; keep copy readable */
.hero-text {
  color: var(--text-color);
  font-family: var(--font-family);
  line-height: 1.5;
}

/* CTA button uses theme tokens */
.btn-primary {
  background-color: var(--primary-color);
  padding: var(--space-sm) var(--space-md);
}
```

</details>  
<details>
<summary>Step 3 Solution – Add Desktop Breakpoint Rules</summary>

CSS - `styles.css`

```css
/* STEP 3 — Desktop enhancements */
@media (min-width: 768px) {
  /* Nav becomes a horizontal row with space between brand and links */
  nav {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  /* Links in a row with a clear gap */
  .nav-links {
    display: flex;
    flex-direction: row;
    gap: 1rem;
  }

  /* Accessible hit targets (~2.75rem total height via padding) */
  .nav-links a {
    padding: 0.75rem 0.5rem;
  }

  /* Hero: side-by-side layout; text on left, image centered on right */
  .hero {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    text-align: left;
    padding: 3rem 2rem; /* a bit more room on desktop */
  }

  /* Make the split ~50/50 without shorthand for clarity */
  .hero-text {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 50%;
    padding-right: 2rem; /* space between text and image */
  }

  .hero-image {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  /* Keep image fluid but capped so it doesn't balloon */
  .hero-image img {
    width: 100%;
    height: auto;
    max-width: 30rem;
  }

  /* Slight desktop bump for heading size */
  h2 {
    font-size: 1.75rem;
  }
}
```

</details>   
<details>

<summary> Step 4 Solution – Fine-Tune Readability and Spacing</summary>

CSS - `styles.css`

```css
/* STEP 4 — Readability & rhythm */
.hero-text {
  max-width: 45rem;  /* within the 40–50rem guidance */
  margin: 0 auto;    /* centers the text block when needed */
  line-height: 1.5;  /* body text ~1.5–1.6 */
}

/* Headings: compact, still readable */
h2 {
  line-height: 1.3;
}
```

</details>   



<details>

<summary> Step 5 Solution – Add Visual Depth and Micro-Interactions</summary>

CSS - `styles.css`


```css
/* STEP 5 — Add Visual Depth and Micro-Interactions */

/* Hero visual polish */
.hero {
  border-radius: var(--radius-md);     /* smooth, rounded corners */
  box-shadow: var(--shadow-soft);      /* subtle depth from theme token */
}

/* Primary button interaction refinements */
.btn-primary {
  transition: background-color 0.2s ease, transform 0.2s ease;
}

.btn-primary:hover {
  transform: scale(1.05);              /* small hover lift */
}

.btn-primary:active {
  transform: scale(0.98);              /* gentle press effect */
}
```

</details>   


<details>
<summary>Final Solution</summary>

HTML - `index.html`

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Responsive Landing Page</title>

  <!-- Theme variables and reset -->
  <link rel="stylesheet" href="theme.css" />
  <!-- Your styles -->
  <link rel="stylesheet" href="styles.css" />
</head>

<body>
  <!-- =======================
       HEADER + NAV
       ======================= -->
  <header>
    <nav>
      <div class="logo">
        <h1>BrandName</h1>
      </div>

      <ul class="nav-links">
        <li><a href="#">Home</a></li>
        <li><a href="#">Features</a></li>
        <li><a href="#">Pricing</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <!-- =======================
       MAIN CONTENT
       ======================= -->
  <main>
    <section class="hero">
      <div class="hero-text">
        <h2>Build for Every Device</h2>
        <p>
          Create responsive layouts that adapt to your users, no matter the screen size.
          Start small, grow big.
        </p>
        <a href="#" class="btn-primary">Get Started</a>
      </div>

      <div class="hero-image">
        <img src="assets/img/hero-placeholder.png"
             alt="Illustration showing devices for responsive design" />
      </div>
    </section>
  </main>

</body>
</html>

```

CSS - `styles.css`

```css
/* ==================================================================
   HTML & CSS 08 – Responsive Landing Page
   Final Combined Stylesheet (Steps 1–5)
   ================================================================== */

/* ==================================================================
   Mobile-first Base (STEP 2)
   ================================================================== */

/* Header + Nav: stacked, centered, breathable spacing */
header {
  padding: 1rem;
}

nav {
  display: flex;
  flex-direction: column;   /* stacked on mobile */
  align-items: center;      /* centered horizontally */
  padding: 1rem;            /* breathing room */
}

/* Vertical space between nav links (~0.5 rem) */
.nav-links a {
  margin: 0.5rem 0;
}

/* Hero: text above image, centered; side padding for small screens */
.hero {
  display: flex;
  flex-direction: column;   /* text above image */
  align-items: center;
  text-align: center;
  padding-left: 1rem;
  padding-right: 1rem;
  background-color: white;
}

/* Apply theme tokens explicitly called out */
.hero-text {
  color: var(--text-color);
  font-family: var(--font-family);
}

/* ==================================================================
   Readability & Rhythm (STEP 4)
   ================================================================== */
.hero-text {
  max-width: 45rem;         /* within 40–50 rem guidance */
  margin: 0 auto;           /* centered block */
  line-height: 1.5;         /* body text ~1.5–1.6 */
}

h2 {
  line-height: 1.3;         /* compact but readable heading spacing */
}

/* ==================================================================
   Desktop Enhancements (STEP 3) @ 768 px
   ================================================================== */
@media (min-width: 768px) {
  /* Navigation: row layout with space between brand and links */
  nav {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }

  /* Links in a row with clear gap */
  .nav-links {
    display: flex;
    gap: 1rem;
  }

  /* Accessible hit targets (~2.75 rem height) */
  .nav-links a {
    padding: 0.75rem 0.5rem;
  }

  /* Hero: side-by-side layout, text left, image centered */
  .hero {
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    text-align: left;
    padding: 3rem 2rem;           /* more breathing room on desktop */
  }

  /* Make 50/50 split explicit without shorthand */
  .hero-text {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 50%;
    padding-right: 2rem;          /* space between text and image */
  }

  .hero-image {
    flex-grow: 1;
    flex-shrink: 1;
    flex-basis: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  /* Keep image fluid but capped so it doesn’t balloon */
  .hero-image img {
    width: 100%;
    height: auto;
    max-width: 30rem;
  }

  /* Slight desktop bump for heading size (beginner-friendly) */
  h2 {
    font-size: 1.75rem;
  }
}

/* ==================================================================
   STEP 5: Visual Depth and Micro-Interactions
   ================================================================== */

/* Hero section depth & rounding */
.hero {
  border-radius: var(--radius-md);
  box-shadow: var(--shadow-soft);
}

/* Primary button hover & press effects */
.btn-primary {
  transition: background-color 0.2s ease, transform 0.2s ease;
}

.btn-primary:hover {
  transform: scale(1.05);
}

.btn-primary:active {
  transform: scale(0.98);
}
```
</details>