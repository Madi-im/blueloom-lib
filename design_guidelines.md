# BlueLoom Library Design Guidelines

## Design Approach
**Reference-Based Approach** - Drawing inspiration from richly designed library and reading platforms (Goodreads, Kindle, Apple Books) with a distinctive blue theme and maximalist, textured aesthetic that evokes physical bookshelf warmth.

## Core Design Principles
1. **Richly Layered, Non-Minimalist**: Every surface has depth—textured backgrounds, gradient overlays, decorative elements, and multi-layer shadows
2. **Blue-Themed Throughout**: All shades of blue from deep royal to sky blue, with glowing highlights and soft gradients
3. **Physical Bookshelf Metaphor**: Wood textures, shelf shadows, decorative ribbons, and tangible card depth to evoke a cozy library

## Typography
- **Headings**: Serif font (Playfair Display or Merriweather) for literary elegance - sizes: text-4xl to text-6xl
- **Body Text**: Sans-serif (Inter or Open Sans) for readability - text-base to text-lg
- **Reader Mode**: Highly readable serif (Crimson Text or Lora) with adjustable sizes (14px-24px range)
- **Decorative Elements**: Script font for taglines and category ribbons

## Layout System
- **Spacing Units**: Tailwind units of 4, 6, 8, 12, 16, 20, 24 for consistent rhythm
- **Containers**: max-w-7xl for main content, max-w-4xl for reading content, full-bleed for hero sections
- **Grid Patterns**: 
  - Book cards: grid-cols-2 md:grid-cols-3 lg:grid-cols-4 xl:grid-cols-5
  - Bookshelf rows: horizontal scroll with shelf metaphor
  - Featured sections: asymmetric 2-column layouts

## Color Palette (Blue Theme)
- **Deep Royal Blue**: Primary backgrounds, headers, navigation (#1e3a8a, #1e40af)
- **Sky Blue**: Accents, hover states, highlights (#38bdf8, #0ea5e9)
- **Powder Blue**: Soft backgrounds, cards (#bae6fd, #e0f2fe)
- **Navy**: Text, borders, depth (#0c4a6e, #164e63)
- **Gradient Overlays**: Blue-to-cyan, royal-to-sky for dynamic surfaces
- **Glowing Effects**: Bright blue (#60a5fa) for borders and interactive states

## Component Library

### Homepage Structure
1. **Hero Banner**: Full-width gradient (royal blue to deep cyan), large tagline "BlueLoom Library — Cozy reads, big skies, endless pages", floating book covers with subtle parallax, prominent search bar with blue glow
2. **Trending Carousel**: Horizontal auto-scrolling cards with large covers, blue gradient backdrop, navigation arrows with glow
3. **Bookshelf Rows**: Repeating sections with wood-texture shelf base (blended with blue tint), books standing upright, subtle tilt on hover, shelf shadow underneath
4. **Category Sections**: Decorative ribbon headers (think medal ribbons in blue gradients), 3-4 column grids of book cards
5. **New Releases Grid**: 4-5 column dense grid, smaller cards, staggered animations on load

### Book Cards (Highly Detailed)
- **Structure**: Large cover image (240x360px minimum), title (text-lg font-bold), author (text-sm text-blue-300), rating stars (gold on blue), 2-3 genre tags (rounded-full badges in sky blue), short description (2 lines, truncated)
- **Styling**: Layered design with:
  - Base: Subtle paper grain texture
  - Middle: Gradient overlay (transparent to blue-900/20)
  - Border: 2px border-blue-500/30, glowing border-blue-400 on hover
  - Shadow: Multi-layer drop-shadow (0 4px 12px blue-900/40, 0 8px 24px blue-900/20)
- **Interactions**: Lift on hover (translate-y-2), glow intensifies, slight rotation (rotate-1)
- **Buttons**: "Read Now" (solid blue-600 with glow), "Add to Shelf" (outline blue-400 with icon)

### Book Details Page
- **Layout**: 2-column asymmetric (cover left 40%, details right 60%)
- **Cover Section**: Extra large cover (400x600px), decorative frame border, soft shadow, background gradient blur
- **Details Section**: 
  - Title (text-5xl), author with avatar placeholder, rating with review count
  - Full description (max-w-prose, text-lg, leading-relaxed)
  - Metadata grid: Publisher, Pages, Language, ISBN in blue-tinted cards
  - Author bio snippet (collapsible)
  - Mock reviews section with user avatars, ratings, blue-card containers
- **CTA**: Large "Open Reader" button (blue-600, w-full, py-4, text-xl, glow effect)

### Reader Mode (Full-Screen)
- **Layout**: Clean reading pane (max-w-4xl centered), blue-accented sidebar controls (collapsible)
- **Controls Panel**: 
  - Font size slider (16-24px)
  - Line-height adjuster (1.5-2.5)
  - Margin width (narrow/normal/wide)
  - Light/Dark toggle (light: cream background, dark: blue-950 with reduced contrast)
- **Navigation**: 
  - Keyboard: Arrow keys for page turn with smooth transitions
  - Mobile: Swipe gestures with page curl animation
  - Progress bar: Blue gradient, thin at top, shows % completion
- **Page Turn Animation**: CSS transform-based flip (rotateY) or slide-fade transition
- **Typography**: Serif font, generous line-height (1.8), comfortable margins (px-12 to px-20)

### Search & Filters
- **Global Search Bar**: Prominent in header, blue glow focus state, dropdown suggestions with covers
- **Filter Panel**: Collapsible sidebar with:
  - Genre checkboxes (blue accent when selected)
  - Rating range slider (stars in blue)
  - Language dropdown
  - Tag chips (removable, blue-500 background)
- **Advanced Filters**: Accordion-style expandable sections (Publication Year, Pages, Format)

### Admin "Fetch & Add" Interface
- **Form Layout**: Clean vertical form with blue-tinted input fields
- **Input Options**: ISBN field, Title search field, URL input (mutually exclusive tabs)
- **Fetch Button**: Large "Fetch & Add" button, loading spinner with blue animation
- **Preview Panel**: Shows fetched metadata (cover, title, author, description) before confirming add
- **File Upload**: Drag-and-drop zone with blue dashed border, supported formats (PDF/EPUB/TXT) displayed

### Navigation & Header
- **Header**: Sticky top bar, deep blue background (blue-900/95 with backdrop blur), logo left, search center, user/favorites right
- **Navigation Links**: Horizontal menu (Home, Browse, Favorites, Admin), blue-400 underline on active
- **Mobile**: Hamburger menu with slide-in drawer (blue gradient background)

### Footer
- **Layout**: 4-column grid (About, Categories, Help, Newsletter)
- **Styling**: Blue-900 background with subtle texture, white/blue-100 text
- **Newsletter**: Email input with "Subscribe" button, blue glow on focus
- **Social Links**: Icon links with hover glow effect

## Textures & Visual Effects
- **Paper Grain**: Subtle noise texture overlay (10% opacity) on card backgrounds
- **Wood Shelf**: Horizontal wood grain (blue-tinted) for bookshelf rows, realistic shadow cast by books
- **Ribbons**: Decorative category ribbons with gradient (blue-500 to blue-700), subtle 3D fold effect
- **Glowing Borders**: Use box-shadow with blue color (0 0 20px rgba(59, 130, 246, 0.5))
- **Gradient Overlays**: Frequently used for depth (linear-gradient from transparent to blue-900/30)

## Animations & Micro-Interactions
- **Card Hover**: Lift + glow + slight rotation (150ms ease-out)
- **Favorite Button**: Heart icon fills with blue, scale pulse animation
- **Book Addition**: Success toast slides in from top with blue background
- **Page Load**: Staggered fade-in for book grids (delay increasing by 50ms per card)
- **Reader Page Turn**: 400ms transform transition with slight perspective
- **Search Suggestions**: Slide down with fade-in, each result animates individually

## Accessibility
- **Contrast**: All text on blue backgrounds meets WCAG AA (minimum 4.5:1)
- **Focus States**: Visible blue-400 outline (3px) on all interactive elements
- **ARIA Labels**: Buttons, inputs, and navigation clearly labeled
- **Reader Mode**: Adjustable font sizes and high-contrast dark mode option
- **Keyboard Navigation**: All functions accessible via keyboard, skip links provided

## Responsive Breakpoints
- **Mobile** (< 768px): Single column, stacked bookshelf rows, hamburger menu, simplified reader controls
- **Tablet** (768px - 1024px): 2-3 column grids, side-by-side book details
- **Desktop** (> 1024px): Full multi-column layouts, sidebar filters visible, spacious reader margins

## Images
- **Hero Section**: Large decorative background image of books/library with blue color overlay (40% opacity), or abstract blue gradient with floating book cover elements
- **Book Covers**: Always use high-quality cover images from API (300x450px minimum), display at various sizes depending on context
- **Category Headers**: Optional decorative imagery (blue-tinted book spines, reading scenes) as background textures
- **Empty States**: Illustrated blue-themed graphics (empty bookshelf, magnifying glass for no search results)