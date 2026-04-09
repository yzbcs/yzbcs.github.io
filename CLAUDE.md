# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a **Jekyll-based academic portfolio website** (Academic Pages template) for GitHub Pages. It features publications, talks, teaching, and blog posts organized as Jekyll collections.

## Development Commands

```bash
# Install dependencies (Ruby + Bundler required)
bundle install

# Local development server with live rebuild
jekyll serve -l -H localhost

# Or use bundle exec for dependency isolation
bundle exec jekyll serve -l -H localhost

# Docker-based development (avoids Ruby installation)
docker compose up
# Access at localhost:4000

# Run Jupyter notebooks for markdown generation
jupyter notebook markdown_generator/
```

## Architecture

### Jekyll Collections (Content Types)
- `_publications/` - Academic papers
- `_talks/` - Conference presentations
- `_teaching/` - Teaching experience
- `_portfolio/` - Portfolio projects
- `_posts/` - Blog posts
- `_pages/` - Static pages (about, CV, etc.)

### Template System
- `_layouts/` - Page templates (single, talk, archive, splash, default, cv-layout)
- `_includes/` - Reusable components (author-profile, sidebar, footer, head, etc.)
- `_sass/` - SCSS stylesheets (compressed output)
- `_data/` - YAML data files for structured content

### Configuration
- `_config.yml` - Primary site configuration (title, author, collections, plugins)
- `_config_docker.yml` - Docker-specific overrides

### Asset Pipeline
- `assets/` - CSS, JS, images
- `images/` - Site images including theme screenshots
- `files/` - Downloadable files (PDFs, etc.) served at `/files/`
- `talkmap/` - Talk location visualization data

## Key Files

| File | Purpose |
|------|---------|
| `_config.yml` | Site-wide settings, author profile, social links, collection defaults |
| `Gemfile` | Ruby dependencies (jekyll, plugins) |
| `markdown_generator/` | TSV-to-markdown converters for publications/talks |

## Adding Content

### Publications/Talks
Use `markdown_generator/` notebooks or scripts to bulk-generate from TSV:
```bash
python3 markdown_generator/publications.py publications.csv
python3 markdown_generator/talks.py talks.tsv
```

### Manual Entry
Create a file in the appropriate collection folder with front matter:
```yaml
---
title: "Paper Title"
collection: publications
---
```

## GitHub Pages Deployment

The site deploys via GitHub Pages. Edit `_config.yml` to set `url` and `repository` to match your GitHub Pages URL. The `talkmap.ipynb` workflow automatically geocodes talk locations when pushed to `_talks/`.
