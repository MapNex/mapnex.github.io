# GitHub Pages Portfolio Site - AI Instructions

## Project Overview
This is a personal portfolio website for Mathias Jarbekk built on the BreezyCV template. It's a single-page application hosted on GitHub Pages with smooth animated transitions between sections. The site showcases cybersecurity expertise, projects, and professional background.

## Architecture Patterns

### Single-Page Application Structure
- **Main file**: `index.html` contains all content sections as `<section data-id="section-name">` elements
- **Navigation**: Hash-based routing (`#about-me`, `#portfolio`, etc.) with animated transitions
- **Section loading**: JavaScript handles section visibility and animations via `data-id` attributes
- **Template pages**: `Blog-template.html` serves as the structure for blog posts; portfolio items use individual HTML files (`portfolio-1.html`, etc.)

### Asset Organization
```
css/              # All stylesheets (main.css is primary, others are vendor)
js/               # JavaScript files (main.js contains custom logic)
img/              # Images organized by type (blog/, portfolio/, testimonials/, clients/)
contact_form/     # PHP contact form handler with Google reCAPTCHA
fonts/            # Custom fonts (Linear Icons, FontAwesome)
```

### Key Dependencies
- **jQuery**: Core DOM manipulation and animations
- **Bootstrap Grid**: Layout system (`bootstrap-grid.min.css`)
- **Owl Carousel**: Text rotation and testimonials slider
- **Magnific Popup**: Lightbox for portfolio images
- **Perfect Scrollbar**: Custom scrollbars
- **Shuffle.js**: Portfolio filtering system

## Critical Development Patterns

### Content Updates
- **Personal info**: Update header section in `index.html` (lines 44-96)
- **Services/skills**: Modify "What I Do" section (around line 200)
- **Portfolio items**: Add to portfolio grid with proper `data-groups` for filtering
- **Blog posts**: Create new HTML files following `blog-post-1.html` structure

### Portfolio System
- Filter categories defined in `data-group` attributes: `category_all`, `category_projects`, `category_websites`
- Portfolio items link to external sites or use lightbox (`lbimage`) or AJAX loading (`ajax-page-load`)
- Add new portfolio items with proper category classification

### Mobile-First Responsive Design
- Mobile menu toggle at 1025px breakpoint (handled in `main.js`)
- Header becomes mobile-responsive with `.mobile-menu-hide` class
- Use Bootstrap grid classes (`col-xs-`, `col-sm-`, etc.) for all layouts

### Animation System
- Sections animate via CSS transitions controlled by JavaScript
- Loading animation (`.preloader`) shown on page load
- Animated background (`.lm-animated-bg`) with configurable image
- Arrow navigation for section browsing

## Contact Form Integration
- PHP backend in `contact_form/contact_form.php` requires:
  - Update `$from` and `$sendTo` email addresses
  - Valid Google reCAPTCHA keys (currently using placeholder keys)
  - Server with PHP and mail capability for form submissions

## Common Modifications
- **Add new section**: Create `<section data-id="new-section">` and add navigation link
- **Update social links**: Modify `.social-links` in header (LinkedIn, GitHub currently configured)
- **Change color scheme**: Edit gradient values in `css/main.css` (lines 34-35)
- **Update skills**: Modify skill percentages and add new `.skill-container` classes in CSS

## File Naming Conventions
- HTML files use kebab-case (`blog-post-1.html`, `portfolio-1.html`)
- CSS classes use BEM-like naming (`portfolio-item-img`, `blog-card`)
- Image files organized by category in subfolders

## Testing Workflow
Since this is a static site, test locally by:
1. Opening `index.html` directly in browser for basic functionality
2. Using a local server for contact form testing (PHP required)
3. Verify all asset paths are relative for GitHub Pages deployment