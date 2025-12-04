# RoCreate Jewelry Website

Welcome! This guide will help you update and maintain your website without needing any technical knowledge.

## Table of Contents
- [Editing the Home Page](#editing-the-home-page)
- [Editing the About Page](#editing-the-about-page)
- [Managing Gallery Images](#managing-gallery-images)
- [Adding a Blog Post](#adding-a-blog-post)
- [Technical Information](#technical-information)

---

## Editing the Home Page

The home page consists of several sections you can customize:

### Hero Section (Top Banner)
Edit the file: `_layouts/home.html`

Look for this section:
```html
<h1>{{ site.title }}</h1>
<p>Handcrafted Jewelry with Love</p>
<a href="{{ site.baseurl }}/gallery/">View Gallery</a>
```

- Change the text between `<p>` and `</p>` to update the tagline
- The hero background image is located at: `assets/images/home-hero.jpg` (replace with your own image, keep the same filename)

### Main Content
Edit the file: `index.md`

This file contains the main paragraph that appears below the hero image. Simply edit the text in this file to update what visitors see.

### Highlight Cards
Edit the file: `_data/highlights.yml`

This file controls the three feature cards on the home page. Each card has:
- **title**: The heading
- **description**: The description text
- **image**: The image filename (store images in `assets/images/`)
- **link_url**: Where the card links to (e.g., `/gallery/`, `/blog/`, `/about/`)
- **link_text**: The blue link text at the bottom

Example:
```yaml
- title: Unique Designs
  description: Each piece is one-of-a-kind, designed with creativity and passion.
  image: /assets/images/pendants1.jpg
  link_url: /gallery/
  link_text: View Our Gallery
```

---

## Editing the About Page

Edit the file: `about.md`

This is a simple text file where you can:
- Update the main heading
- Edit the paragraphs about your business
- Change the about page image by replacing `assets/images/about1.jpg` with your own photo (keep the same filename, or update the reference in the file)

The file uses simple formatting:
- `## Heading` creates a heading
- Regular text becomes paragraphs
- Leave a blank line between paragraphs

---

## Managing Gallery Images

### To Add or Remove Gallery Items

Edit the file: `gallery.md`

Look for the `gallery_items:` section. Each item looks like this:

```yaml
- image: pendants1.jpg
  title: Elegant Pendants
  description: Beautiful handcrafted pendant collection
```

**To add a new item:**
1. Upload your image to the `assets/images/` folder
2. Copy one of the existing items
3. Paste it at the end of the list
4. Update the image filename, title, and description

**To remove an item:**
- Simply delete the 3 lines for that item

**To reorder items:**
- Cut and paste items in the order you want them to appear

### Image Requirements
- Recommended size: At least 600x600 pixels
- Format: JPG or PNG
- Store all images in: `assets/images/`

---

## Adding a Blog Post

Blog posts are stored in the `_posts/` folder.

### Step 1: Create a New File
Create a new file in the `_posts/` folder with this naming format:
```
YYYY-MM-DD-your-post-title.md
```

Example: `2025-12-03-new-spring-collection.md`

**Important**: The date must be in the format YYYY-MM-DD (year-month-day)

### Step 2: Add Front Matter
At the very top of your file, add this:

```yaml
---
layout: post
title: "Your Post Title Here"
date: 2025-12-03
categories: blog
image: /assets/images/your-image.jpg
---
```

- **title**: The title of your blog post
- **date**: The date (YYYY-MM-DD format)
- **image**: Optional featured image (upload to `assets/images/` first)

### Step 3: Write Your Content
Below the `---`, write your post using simple formatting:

```markdown
## Subheading

This is a paragraph of text. Leave a blank line between paragraphs.

This is another paragraph.

### Smaller Heading

You can also create lists:
- First item
- Second item
- Third item
```

### Step 4: Save and Publish
Once you save the file and push it to GitHub, your blog post will automatically appear on your site!

### Example Blog Post
```markdown
---
layout: post
title: "Announcing Our Spring Collection"
date: 2025-03-15
categories: blog
image: /assets/images/spring-collection.jpg
---

## New Designs for Spring

We're excited to announce our new spring collection featuring vibrant colors and nature-inspired designs.

Each piece has been carefully crafted with attention to detail and uses premium materials.

Visit our gallery to see the full collection!
```

---

## Technical Information

### Architecture
This website is built using Jekyll, a static site generator that converts simple text files into a complete website. It's hosted on GitHub Pages.

### Key Components
- **Jekyll**: Static site generator
- **Minima Theme**: Base theme with custom styling
- **GitHub Pages**: Free hosting and automatic deployment
- **Liquid Templates**: Template language for dynamic content

### File Structure
- `_layouts/`: Page templates (home, gallery, default)
- `_posts/`: Blog posts (markdown files)
- `_data/`: Data files (highlights configuration)
- `_sass/`: Custom styling (CSS/SCSS)
- `assets/images/`: All images
- `_config.yml`: Site-wide configuration

### Local Development
To run the site locally:
```bash
bundle install
bundle exec jekyll serve
```
Visit: http://localhost:4000

### Deployment
Changes pushed to the `main` branch are automatically deployed to GitHub Pages within a few minutes.
