# AGENTS.md - Developer Guidelines

## Project Overview

This is a static personal resume website built with HTML, CSS, and vanilla JavaScript. It is hosted on GitHub Pages from the `docs/` directory.

## Project Structure

```
docs/
├── index.html       # Main resume page
├── resume.html      # Alternative resume layout
├── assets/
│   ├── styles.css   # Main stylesheet
│   ├── script.js    # Client-side JavaScript
│   ├── resume.pdf   # PDF version of resume
│   └── images/      # Image assets
└── CNAME            # Custom domain configuration
```

## Build & Development Commands

This is a static website with no build system. To view locally:

- **Serve locally**: Use any HTTP server (e.g., `python -m http.server 8000` or VS Code Live Server)
- **Open in browser**: Navigate to `index.html` directly or use a local dev server

There are no linting or testing frameworks configured for this project.

## Code Style Guidelines

### General Principles

- Keep JavaScript minimal - use vanilla JS only
- Prefer semantic HTML5 elements
- Use CSS variables for theming and consistency
- Avoid external dependencies unless absolutely necessary

### HTML

- Use semantic elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`)
- Include proper `alt` attributes on images
- Use lowercase for tags and attributes
- Quote attribute values

### CSS

- Use CSS custom properties (variables) for colors, spacing, and breakpoints
- Follow mobile-first responsive design patterns
- Use BEM-like naming convention for complex components (e.g., `.nav-toggle`, `.nav-links`)
- Group related styles logically
- Use flexbox and grid for layouts

### JavaScript

- Use `const` by default, `let` only when reassignment is needed
- Use arrow functions for callbacks
- Prefer `querySelector` and `addEventListener` over older APIs
- Use modern ES6+ features
- Keep functions small and focused
- Use semantic variable names

**Example (from existing code):**
```javascript
document.addEventListener('DOMContentLoaded', () => {
    const navToggle = document.querySelector('.nav-toggle');
    navToggle.addEventListener('click', () => {
        navLinks.classList.toggle('active');
    });
});
```

### Naming Conventions

- Classes: kebab-case (e.g., `.site-header`, `.nav-toggle`)
- Variables: camelCase (e.g., `navToggle`, `scrollPosition`)
- Constants: UPPER_SNAKE_CASE for true constants
- File names: kebab-case for assets

### Error Handling

- Always check if elements exist before manipulating them
- Use optional chaining and null checks for DOM queries
- Wrap potentially failing operations in conditionals

### Accessibility

- Maintain keyboard navigability
- Use appropriate ARIA labels where needed
- Ensure sufficient color contrast
- Make interactive elements focusable

## Common Tasks

### Adding a new section
1. Add HTML in `index.html` within appropriate semantic tags
2. Add corresponding styles in `assets/styles.css`
3. Add any JavaScript interactions in `assets/script.js`

### Updating resume content
1. Edit `index.html` for the web version
2. Replace `assets/resume.pdf` with the new PDF version
3. Update `assets/resume.html` if separate layout is needed

### Deployment

The site deploys automatically via GitHub Pages from the `docs/` directory. Push to main branch triggers deployment.

## Notes

- This is a personal portfolio/resume site - prioritize simplicity and maintainability
- No testing framework is configured - manually verify changes
- No TypeScript or transpilation - write directly for modern browsers

## Git Workflow

### Branch Strategy
- Main branch (`main`) is the production branch
- Make changes on feature branches and merge via pull request
- Use descriptive branch names: `feature/`, `fix/`, `update/`

### Commit Messages
- Use clear, descriptive commit messages
- Start with verb: "Add", "Fix", "Update", "Remove"
- Keep subject line under 72 characters

### Pull Requests
- Create PRs for all changes, even small ones
- Describe what was changed and why
- Request review before merging

## Browser Support

- Target modern browsers (Chrome, Firefox, Safari, Edge - last 2 versions)
- Use progressive enhancement - basic features should work everywhere
- Test in mobile browsers (iOS Safari, Chrome Mobile)

## Performance Guidelines

### Images
- Use appropriate formats: WebP for photos, SVG for icons/graphics
- Compress images before adding to `assets/images/`
- Specify dimensions to prevent layout shifts

### CSS
- Keep CSS minimal - avoid unused styles
- Use CSS animations over JavaScript where possible
- Group related styles with comments

### JavaScript
- Defer non-critical scripts when possible
- Keep initial bundle small
- Use event delegation for multiple similar elements

## File Organization

### CSS Organization (styles.css)
Order styles in this sequence:
1. CSS custom properties (variables)
2. Reset/base styles
3. Typography
4. Layout (header, footer, grid)
5. Components
6. Utilities
7. Media queries

### JavaScript Organization (script.js)
Order code in this sequence:
1. DOM element selections
2. Configuration/constants
3. Event listeners
4. Helper functions
5. Initialization

## SEO Considerations

- Use proper heading hierarchy (single H1 per page)
- Include meta description in HTML head
- Use meaningful link text (avoid "click here")
- Ensure sufficient text content for indexing

## Validation

Since there are no automated tests:
- Validate HTML with W3C validator
- Check CSS for syntax errors
- Test all interactive elements manually
- Verify links work correctly
- Test responsive behavior at multiple viewport sizes
