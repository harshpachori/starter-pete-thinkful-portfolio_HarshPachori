# Pete | Artist Portfolio – Redesign

## Project Description

This project is a redesign of Pete's personal artist portfolio website. Pete is a Denver-based artist whose work spans abstract painting, street graffiti, and collaborative art. The goal of the site is to showcase his personality, background, and portfolio pieces in a clean, visually engaging way that makes it easy for potential collaborators or employers to learn about him and get in touch.

The redesign focuses on improving the layout and visual hierarchy of the existing page without changing its content or introducing new colors. The original site had a functional structure but lacked the polished, organized presentation that a professional portfolio calls for. By applying modern CSS layout techniques, the redesigned version more closely matches the provided mock-up and gives Pete's work the presentation it deserves.

---

## Original vs. Revised Layout

### Original Layout
- The header had the logo and navigation stacked or loosely arranged, without clear horizontal alignment.
- In the About section, Pete's photo sat above the "Hi! I'm Pete" text block — everything was stacked vertically in a single column.
- The Portfolio section displayed the three projects stacked vertically, one below the other, making it necessary to scroll to compare them.
- The overall page used a centered `div` with a fixed `600px` width, limiting layout flexibility.

### Revised Layout
- **Header**: The logo ("Pete | Artist") and navigation links are now on a single horizontal row, vertically centered, with the logo on the left and nav on the right. The header uses a dark navy background (`#003049`) with cream-colored text for strong visual contrast.
- **About Section**: Pete's circular photo and the "Hi! I'm Pete" text are displayed side by side in a horizontal row using flexbox. The heading is centered within the text column, and the body text is left-aligned. Pete's Background section appears below this row as its own full-width block.
- **Portfolio Section**: All three portfolio pieces are displayed in a single horizontal row with equal spacing between them. Project descriptions use a font size of 14px.

### Redesign Mock-Up
The mock-up provided showed the following key layout changes (all of which were implemented):
- A horizontal header bar with logo left, nav right
- A two-column about intro (photo | text)
- A three-column portfolio row
- Consistent use of the original color palette throughout

### Implementation Plan
1. Restructure the HTML to wrap the about intro in a flex container with separate `div` elements for the image and text.
2. Restructure the portfolio `section` and its children to support a horizontal flex layout.
3. Update the CSS header styles to use `display: flex` with `justify-content: space-between`.
4. Add `.about-intro`, `.about-text`, `.portfolio-grid`, and `.portfolio-item` CSS classes to control the new layouts.
5. Remove the old fixed-width `div` rule that was constraining the layout, replacing it with a `.main-container` max-width wrapper.
6. Set portfolio description font size to `14px`.

### Design Trade-offs
- **Fixed width vs. fluid layout**: The original CSS applied `width: 600px` to all `div` elements globally, which was brittle. The revised version uses `max-width` on a wrapper container instead, which is more flexible but required overriding some inherited styles carefully.
- **Color consistency vs. visual change**: The decision was made to keep the exact original color palette rather than introduce new colors. This trades visual novelty for consistency and keeps the redesign focused on layout rather than branding.
- **Simplicity vs. responsiveness**: The new flexbox layout works well on desktop but does not include media queries for mobile breakpoints. Adding responsive behavior was out of scope for this exercise but would be a natural next step.

---

## AI Tools Used

**Tool used: Claude (Anthropic) — claude.ai**

Claude was used to assist with writing and refining the HTML and CSS code for the redesign. Specifically, it was used to:
- Generate the updated `index.html` with restructured semantic markup to support the new flex-based layout
- Generate the updated `style.css` with flexbox rules for the header, about section, and portfolio grid
- Troubleshoot the `git clone` error encountered when setting up the project locally
- Help explain what changes were needed and why

**Justification**: Using Claude allowed the focus of this project to stay on understanding the design decisions and layout concepts rather than getting stuck on syntax errors. All generated code was reviewed, tested, and understood before being submitted. AI assistance was treated as a learning aid — similar to referencing documentation or a tutorial — rather than a replacement for understanding the material.

---

## Key Decisions, Challenges & Learning Moments

### Key Decisions

**Using flexbox for all three layout changes** — Rather than using floats, inline-block, or CSS Grid, flexbox was chosen for the header, about section, and portfolio grid because it is purpose-built for one-dimensional row and column layouts. It required fewer lines of code and was easier to reason about for these specific use cases.

**Keeping the original color palette** — No new colors were introduced. The dark navy (`#003049`), warm cream (`#eae2b7`), red (`#d62828`), and orange (`#f77f00`) from the original stylesheet were reused throughout. This kept the redesign visually cohesive and ensured the changes focused on structure rather than style.

**Separating layout concerns with new CSS classes** — Rather than modifying the existing broad selectors (like the global `div` rule), new specific classes like `.about-intro`, `.portfolio-grid`, and `.portfolio-item` were added. This avoided unintended side effects on other parts of the page.

### Challenges & Debugging

**Biggest challenge: Getting the flexbox layout right**

The most difficult part was understanding how flexbox properties interact with each other. For example, when applying `display: flex` to the about intro section, the image and text appeared side by side but the alignment was off — the image was stretching to match the height of the text column. The fix was adding `align-items: flex-start` to the flex container, which tells the children to align to the top rather than stretch to fill the full height.

Another issue was the global `div { width: 600px }` rule from the original CSS. Because it applied to every `div` on the page, it was overriding the flex children and preventing them from resizing naturally within the flex container. This was resolved by replacing it with a `.main-container` class applied only to the outer wrapper, so flex children could size freely.

### Learning Moments

**How flexbox works**

This project made flexbox much more concrete. The key insight was understanding the difference between the **flex container** (the parent, where you set `display: flex`) and the **flex items** (the children, which respond to the flex rules). Properties like `justify-content` control spacing along the main axis (horizontal by default), while `align-items` controls alignment on the cross axis (vertical by default). Once that mental model clicked, applying it to the header, about section, and portfolio all followed the same pattern — just with different values depending on the desired outcome.

It also became clear why flexbox replaced older layout techniques like floats: it is much more predictable, requires less CSS, and doesn't require clearing or hacks to work correctly.
