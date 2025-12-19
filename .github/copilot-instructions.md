# AI Agent Instructions for starcitizen.today

## Project Overview
Jekyll-based static blog about Star Citizen using a customized Minima theme (v3.0.0.dev). Published via GitHub Pages at starcitizen.today. Author uses AI assistance for content creation and acknowledges dysgraphia in [about.md](about.md).

## Architecture
- **Theme**: Modified Minima v3 embedded as local theme (not gem-based) via [minima.gemspec](minima.gemspec)
- **Layouts**: 4-tier hierarchy - `base.html` → `post.html`/`page.html`/`home.html`
- **Custom Includes**: [fix_or_enjoyed.html](_includes/fix_or_enjoyed.html) injected into all posts with error reporting + referral code (STAR-NC4W-QRHN)
- **Content**: Posts in [_posts/](_posts/) with `YYYY-MM-DD-title.md` naming; drafts in [_fake_posts/](_fake_posts/)

## Key Conventions

### Post Front Matter
Always include these fields (see [2024-08-18-shipshowdown-terrapin-for-the-win.md](_posts/2024-08-18-shipshowdown-terrapin-for-the-win.md)):
```yaml
layout: post
published: true  # false for drafts
title: "Title Here"
description: "SEO description"
categories: [shipshowdown2954]  # gameplay topics
tags: [Star Citizen, specific, keywords]
image: /assets/img/ships/SHIPNAME/CONTEXT/filename.jpg
canonical_url: https://starcitizen.today/...
author: "Kal"
og:image: /assets/img/...  # social media preview
twitter:card: "summary_large_image"
keywords: Comprehensive, comma-separated, keyword list for SEO
```

### Image Organization
Store ship images in `/assets/img/ships/{ship-name}/{context}/` (e.g., `/assets/img/ships/terrapin/shipshowdown2954/`)

### Custom Styling
- Site uses dark skin: `minima.skin: dark` in [_config.yml](_config.yml)
- Custom overrides in [_sass/minima/custom-styles.scss](_sass/minima/custom-styles.scss)
- Logo styling: `.logo` class with 150x150px dimensions

## Development Workflow
- **Local server**: `./script/server` or `bundle exec jekyll serve`
- **Build**: `./script/build` or `bundle exec jekyll build`
- **Dependencies**: Ruby gems via Bundler; run `bundle install` after Gemfile changes

## Analytics & Features
- Google Analytics: G-S7X6SL70XQ ([_config.yml](_config.yml))
- Disqus comments: shortname `starcitizen-today`
- Plugins: jekyll-feed, jekyll-seo-tag, jekyll-sitemap

## Content Guidelines
- Author prefers authentic voice over AI polish (see [about.md](about.md) for tone reference)
- Posts focus on ship reviews, game events, and community engagement
- Include referral code reminders in posts (handled by fix_or_enjoyed.html include)
- Encourage error reporting via GitHub issues link

## Critical Files
- [_config.yml](_config.yml): Site configuration, theme settings, social links
- [_layouts/post.html](_layouts/post.html): Post template including fix_or_enjoyed.html
- [_includes/fix_or_enjoyed.html](_includes/fix_or_enjoyed.html): Error reporting + referral section
