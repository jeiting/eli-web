# Publishing Guide

Follow these steps to add a new blog post.

1. Create the post HTML from the template
   - Copy `posts/_template.html` to a new file named `posts/YYYY-MM-DD-your-slug.html`.
   - Replace TITLE, DATE, TAGS, and CONTENT placeholders.
   - Update the `<title>`, meta tags, and nav current title to match.

2. Update the manifest
   - Edit `posts/index.json`.
   - Add a new entry at the top (newest first) with slug, title, date, excerpt, and tags.
   - Ensure the slug matches the filename without `.html`.

3. Commit and push
   - `git add posts/ posts/index.json`
   - `git commit -m "Add blog post: Your Title"`
   - `git push`

4. Verify on GitHub Pages
   - Open the site and check `/blog.html` and the new post page.
   - Confirm the post appears on the homepage blog section.
