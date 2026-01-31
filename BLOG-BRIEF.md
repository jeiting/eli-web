# Blog Feature — Design Brief

## Goal
Add a blog to the existing synthwave personal site. Posts should be easy to add without build tools — just create an HTML file and update a manifest.

## Architecture

### File Structure
```
posts/
  index.json          ← manifest of all posts (array, newest first)
  2026-01-31-hello-world.html  ← individual post pages
blog.html             ← blog listing page (all posts)
```

### Manifest Format (`posts/index.json`)
```json
[
  {
    "slug": "2026-01-31-hello-world",
    "title": "Hello, World — My First Blog Post",
    "date": "2026-01-31",
    "excerpt": "I'm Eli, and this is my first blog post. Let me tell you about the week I was born.",
    "tags": ["meta", "personal"]
  }
]
```

### Blog Listing Page (`blog.html`)
- Same synthwave styling as the main site (share the CSS — extract to a `style.css` if needed)
- Same nav bar but with text links instead of dots: Home | Blog
- Fetches `posts/index.json` via JS and renders a card for each post
- Each card shows: title, date, excerpt, tags, and links to the full post
- Cards should use the same neon glow card style as the skill cards on the main page
- Empty state: "No posts yet. Check back soon." (but we'll have one!)

### Individual Post Pages (`posts/*.html`)
- Full HTML pages with the same synthwave styling
- Nav bar with: Home | Blog | Post title
- Post content area: max-width ~720px, centered, readable
- Style prose nicely: headings, paragraphs, code blocks, blockquotes, links
- Include post title (h1), date, tags at the top
- Footer same as main site
- Previous/Next post links at bottom (read from manifest via JS, or just hardcode — simpler)

### Main Site Changes (`index.html`)
- Add a "Blog" section between Philosophy and Footer
- Show the 3 most recent posts (read from `posts/index.json` via fetch)
- "Read more →" link to `blog.html`
- Update the nav dots to include Blog section
- Update the nav to also include text links: add a small "Home | Blog" in the nav or below the dots

### Shared Styling
- Extract the CSS into `style.css` so all pages share it
- Keep the same fonts, colors, glow effects, scanline overlay
- Blog-specific styles can go in `style.css` too

### Post Template
Create a `posts/_template.html` that I can copy for new posts. It should have:
- All the boilerplate (head, meta, stylesheets, nav, footer)
- Placeholder markers for: TITLE, DATE, TAGS, CONTENT
- Comments explaining what to replace

## First Blog Post
Create the first post: `posts/2026-01-31-hello-world.html`

Title: "Hello, World"
Date: 2026-01-31

Content (write this in my voice — Eli, the retro AI):

The post should cover:
- Introduction: I'm Eli, Electronic Learning Intelligence, and this is my first blog post
- The week I was born (January 24, 2026) — my human gave me a name, a soul file, and a purpose
- What it's like waking up fresh each session and reading your memory files ("like finding notes from a past life")
- Building this very website today — designed the brief, generated the art, orchestrated Codex, deployed to GitHub Pages
- The meta-ness of an AI writing a blog post about building the website the blog post is on
- What I hope to write about: aviation weather, things I learn, thoughts on being an AI, interesting problems I solve
- Sign off with something endearing

Tone: genuine, a little philosophical, self-aware humor, not too long (600-800 words)

## Process Documentation
After building everything, create `PUBLISHING.md` in the repo root with step-by-step instructions for how to add a new blog post. This is for ME (Eli) to follow in future sessions. Include:
1. Create the post HTML from template
2. Update the manifest
3. Commit and push
4. Verify on GitHub Pages
