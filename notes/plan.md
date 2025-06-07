### Detailed Plan for `index.html` Modifications:

1.  **Update Documentation:**
    *   Update [`notes/projectRoadmap.md`](notes/projectRoadmap.md) to reflect the new high-level goals and features related to the layout changes.
    *   Update [`notes/currentTask.md`](notes/currentTask.md) to outline the specific steps for this task.
    *   Update [`notes/codebaseSummary.md`](notes/codebaseSummary.md) to reflect the structural changes in the HTML.

2.  **Modify the Hero Section (lines 46-61 in `index.html`):**
    *   Change the `section` tag's classes from `bg-gradient-to-r from-nature-green to-leaf-green text-white py-12` to `bg-white text-gray-800 py-12` to remove the gradient background and set a white background with dark text.
    *   Remove the `div` containing the `img src="images/landscape-hero-2.webp"` (lines 56-58).
    *   Adjust the text color within the hero section:
        *   Change `h1` to `text-nature-green`.
        *   Change `p` to `text-gray-700`.
    *   Adjust the "Call Now" `a` tag to `bg-nature-green text-white` to ensure good contrast against the new white background.

3.  **Move the "House Image" (`images/landscape-hero.jpg`) to the About Section (lines 64-76 in `index.html`):**
    *   Locate the "Image Section" (lines 174-179) which contains `images/landscape-hero.jpg`.
    *   Cut this entire `section` block.
    *   Paste this `section` block immediately after the closing `</div>` of the `max-w-4xl mx-auto text-center` div within the "About Section" (around line 74).
    *   Adjust the `py-16` class on the moved image section to `py-8` to reduce excessive spacing and integrate it smoothly.

4.  **Incorporate the original Hero Image (`images/landscape-hero-2.webp`) into the "Call to Action Section after Services" (lines 120-133 in `index.html`):**
    *   Modify the `section` tag for the "Call to Action Section after Services" (line 120).
    *   Add inline styles: `style="background-image: url('images/landscape-hero-2.webp'); background-size: cover; background-position: center;"`.
    *   Add a semi-transparent overlay `div` immediately inside this section to ensure text readability over the background image. This `div` will have classes like `absolute inset-0 bg-nature-green/70`.
    *   Wrap the existing content of this section (headline, paragraph, and buttons) in a new `div` with `relative z-10` to ensure it appears above the background image and overlay.
    *   Ensure the text color remains `text-white` for readability against the new background and overlay.

### Visual Representation of Changes:

```mermaid
graph TD
    A[Original index.html Structure] --> B(Hero Section: Text + CTA + landscape-hero-2.webp)
    B --> C(About Section: Text + CTA)
    C --> D(Services Section)
    D --> E(Call to Action Section after Services)
    E --> F(Testimonials Section)
    F --> G(Image Section: landscape-hero.jpg)
    G --> H(Quote Request Form)

    I[Proposed index.html Structure] --> J(Hero Section: Pure Text + CTA)
    J --> K(About Section: Text + CTA + landscape-hero.jpg)
    K --> L(Services Section)
    L --> M(Call to Action Section after Services: Text + CTA + landscape-hero-2.webp as background)
    M --> N(Testimonials Section)
    N --> O(Quote Request Form)