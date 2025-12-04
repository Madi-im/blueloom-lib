# BlueLoom Library

A visually rich, blue-themed online book library with web-fetched metadata and an in-browser reader.

## Overview

BlueLoom Library is a full-stack web application that allows users to:
- Browse and search books with metadata fetched from Google Books and Open Library APIs
- Read books in a full-screen reader with adjustable settings
- Save favorite books to a personal bookshelf
- Add new books via ISBN or title search (Admin feature)

## Tech Stack

- **Frontend**: React, TypeScript, Tailwind CSS, Framer Motion
- **Backend**: Node.js, Express
- **Database**: PostgreSQL with Drizzle ORM
- **Routing**: Wouter
- **State Management**: TanStack Query

## Project Structure

```
client/
├── src/
│   ├── components/
│   │   ├── ui/              # Shadcn UI components
│   │   ├── book-card.tsx    # Book display card component
│   │   ├── bookshelf-row.tsx # Horizontal scrolling book row
│   │   ├── footer.tsx       # Site footer
│   │   ├── header.tsx       # Site header with navigation
│   │   ├── hero-section.tsx # Homepage hero
│   │   ├── reader-mode.tsx  # Full-screen book reader
│   │   ├── search-filters.tsx # Filter panel
│   │   └── theme-provider.tsx # Dark/light theme
│   ├── pages/
│   │   ├── admin.tsx        # Admin add book page
│   │   ├── book-details.tsx # Book detail view
│   │   ├── browse.tsx       # Search and browse
│   │   ├── favorites.tsx    # User's saved books
│   │   ├── home.tsx         # Homepage
│   │   └── not-found.tsx    # 404 page
│   └── App.tsx
server/
├── db.ts                     # Database connection
├── index.ts                  # Server entry point
├── routes.ts                 # API routes
├── storage.ts                # Database operations
└── vite.ts                   # Vite dev server
shared/
└── schema.ts                 # Drizzle schema & types
```

## API Endpoints

### Books
- `GET /api/books` - List/search books (query, genre, minRating, language params)
- `GET /api/books/:id` - Get single book
- `GET /api/books/:id/content` - Get book content for reader
- `POST /api/books/fetch` - Fetch metadata from Google Books/Open Library
- `POST /api/books/seed` - Seed ~20 curated public domain books

### Favorites
- `GET /api/favorites` - Get user's favorites
- `GET /api/favorites/with-books` - Get favorites with full book data
- `POST /api/favorites` - Add book to favorites
- `DELETE /api/favorites/:bookId` - Remove from favorites

## Database Schema

### Books Table
- id, title, authors[], description, coverUrl, isbn, isbn13
- publisher, publishedDate, pageCount, categories[]
- language, averageRating, ratingsCount, previewLink
- contentType, contentPath, contentUrl, source
- isFeatured, isTrending, viewCount, createdAt

### Favorites Table
- id, sessionId, bookId, createdAt

## Design Theme

BlueLoom uses a rich blue color palette:
- Deep Royal Blue (#1e3a8a, #1e40af) - Primary backgrounds
- Sky Blue (#38bdf8, #0ea5e9) - Accents, highlights
- Powder Blue (#bae6fd, #e0f2fe) - Soft backgrounds
- Navy (#0c4a6e, #164e63) - Text, depth

## Features

### Reader Mode
- Full-screen immersive reading
- Adjustable font size (14-28px)
- Line height control (1.5-2.5)
- Margin options (narrow/normal/wide)
- Light/dark reading modes
- Keyboard navigation (arrow keys)
- Progress bar
- Page turn animations

### Book Cards
- Cover image with hover effects
- Star ratings
- Genre badges
- Favorite toggle
- "Read Now" button

## Running the Project

The application runs on port 5000 with both frontend and backend.

```bash
npm run dev
```

## User Preferences

- Theme: Dark mode by default, stored in localStorage as "blueloom-theme"
- Session: Cookie-based session for favorites (blueloom_session)
