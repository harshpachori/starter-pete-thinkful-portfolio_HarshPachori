# Pete | Artist Portfolio – Redesign Notes

## Design Justifications

### Header
The header now uses **flexbox** with `justify-content: space-between` and `align-items: center` to place the logo text and navigation on a single horizontal row, both vertically centered. The background color was changed to **#003049** (the site's dark navy, already used for body text) to create a strong, anchoring bar at the top of the page. Nav links are styled in the warm **#eae2b7** (the page's background color) for contrast, with an orange hover state that ties into the existing accent palette. This creates a cohesive, intentional header that frames the page without introducing new colors.

### About Section
The "Hi! I'm Pete" block uses **flexbox** (`flex-direction: row`) to place Pete's circular photo and the introductory text side by side, matching the mock-up. The `h3` heading is centered within the text column while the paragraphs and list remain left-aligned, providing visual hierarchy and readability. Pete's Background section sits below as its own full-width block, maintaining the reading flow from the mock-up.

### Portfolio Section
The three portfolio items use **flexbox** (`flex-direction: row`, `gap: 24px`) to display all three projects on a single row with even spacing between them. Project description text is set to **14px** as specified. Images scale within each flex column so they align cleanly across the row.

### Color & Theme
No new colors were introduced. The redesign uses the existing palette:
- `#003049` – navy (primary/dark)
- `#eae2b7` – warm cream (background/light)
- `#d62828` – red (link)
- `#f77f00` – orange (hover accent)

This keeps the overall look consistent with the original design while improving layout and structure.
