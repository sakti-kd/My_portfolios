# Saktikanta Dhal — Optimized Multi-page Portfolio

A static, responsive portfolio with separate pages and distinct motion styles for each page.

## Pages
- `index.html` — Home with animated hero, interactive floating specialty cards, and clickable destination cards
- `about.html` — About page with staggered reveal cards
- `skills.html` — Interactive skills explorer; clicking a Home specialty opens the matching skill detail
- `projects.html` — Project cards with staggered 3D-style entrance motion
- `experience.html` — Animated career timeline
- `contact.html` — Animated contact panel and staggered contact actions

## What was fixed
- Home specialty cards now link to `skills.html` with the selected skill in the URL.
- The Skills page reads that selection and displays the corresponding detail panel.
- Home's bottom section cards and hero CTA links now navigate to their dedicated pages.
- Each page has a distinct entrance animation and staggered card effects.
- Mobile navigation uses normal page links; the menu button opens/closes the responsive navigation.
- Reduced-motion preferences are respected.
- All pages retain the existing dark neon theme, profile photo, resume, and favicon.

## Deploy to GitHub Pages
1. Extract this ZIP.
2. Open the `Sakti_Portfolio_Multi_Page_Optimized` folder.
3. Upload the files inside that folder (not the containing folder itself) to the root of your existing `sakti-kd/My_portfolios` repository.
4. Replace the previous versions of matching files and commit the changes to the branch used by GitHub Pages.
5. Wait for the Pages workflow to complete, then test each menu, the bottom Home cards, and all eight specialty cards on desktop and mobile.

The site uses static HTML, CSS, and JavaScript. No build step or external JavaScript library is required.


## Animation fix
The latest build includes a page-entry animation replay patch. Each page re-triggers its page-specific heading and content animations on load and browser back/forward restoration. The `prefers-reduced-motion` accessibility setting is still respected.


## Page animation selector correction
This build targets the actual `.page-heading`, `.content-view`, `.info-card`, `.skill-choice`, `.project-card`, `.timeline-item`, `.contact-panel`, `.skill-orb`, and `.quick-card` classes used in the page markup. Each page has a distinct entrance animation and staggered content effects. The page-load replay script and reduced-motion support are retained.


## Animation system
This version uses a timed intro overlay modeled on the supplied reference, followed by a different page-specific content reveal on Home, About, Skills, Projects, Experience, and Contact. Clicking/tapping the intro skips it. Reduced-motion preferences remain respected.


## Page-specific 3D visuals
The About, Skills, Projects, Experience, and Contact pages now include lightweight CSS 3D scenes: a rotating identity sphere, wireframe cube, floating glass panels, animated career bars, and a holographic envelope. These scenes use CSS transforms and keyframes (no additional WebGL dependency), sit behind the page content, reduce in size/opacity on mobile, and respect reduced-motion preferences. The Home page keeps its existing animated globe.


## Smooth navigation and continuous 3D scenes

- Inner pages no longer show a timed intro overlay; page content is available immediately.
- About, Skills, Projects, Experience, and Contact each use a continuously animated Three.js globe with page-specific 3D accents.
- Native cross-document View Transitions are enabled where the browser supports them; unsupported browsers navigate immediately.
- Three.js loads from cdnjs, so the 3D scenes require an internet connection. If WebGL/CDN loading fails, the existing lightweight CSS scene remains as a fallback.
- The Home page and its current hero animation are preserved.


## Dedicated 3D scenes update

Each inner page now has a full-width, dedicated Three.js scene area: About uses a holographic human figure and orbital rings; Skills uses a connected icosahedral constellation; Projects uses a 3D automation pipeline with moving signals; Experience uses rising career bars and a moving timeline signal; Contact uses a 3D envelope and a connected communication network. These are distinct scenes, not a repeated globe. The page content is available immediately; there is no timed intro gate. Scene dimensions respond to mobile widths, device pixel ratio is capped, rendering pauses while the tab is hidden, and reduced-motion preferences are respected. Three.js is loaded from a CDN, so an internet connection is required for the WebGL scenes.


## Compact 3D scene update

- Each inner page keeps its own real-time Three.js scene: holographic identity (About), technology constellation (Skills), automation pipeline (Projects), career progression (Experience), and communication network (Contact).
- The dedicated scene panel is now shorter on phones (about 200–250 CSS px for the canvas) and more compact on desktop, so page content appears sooner.
- Canvas framing adapts to viewport width for improved mobile visibility.
- Rendering pauses when the scene is off-screen or the browser tab is hidden, reducing unnecessary GPU work.
- Navigation remains immediate; no timed intro blocks page changes.

Open `index.html` locally or deploy the folder contents to GitHub Pages. Three.js is loaded from a CDN, so the 3D scenes require an internet connection.
