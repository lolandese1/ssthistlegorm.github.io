# Local Jekyll Development Setup

## Prerequisites
- Ruby (version 2.5.0 or higher)
- Bundler

## Installation Steps

### 1. Install Ruby (if not already installed)

**On Ubuntu/Debian:**
```bash
sudo apt-get update
sudo apt-get install ruby-full build-essential zlib1g-dev
```

**On macOS:**
```bash
brew install ruby
```

### 2. Install Bundler
```bash
gem install bundler
```

### 3. Install Jekyll Dependencies
Navigate to your site directory and install gems:
```bash
cd /home/martinus/static-projects/ssthistlegorm.github.io
bundle install
```

This will read the `Gemfile` and install all dependencies locally in the `vendor/bundle` directory.

### 4. Run the Jekyll Server
Start the local development server:
```bash
bundle exec jekyll serve
```

The site will be available at `http://localhost:4000`

### 5. View Your Site
Open your browser and navigate to:
```
http://localhost:4000
```

## Useful Commands

- **Build only:** `bundle exec jekyll build`
- **Serve with live reload:** `bundle exec jekyll serve`
- **Serve on different port:** `bundle exec jekyll serve --port 3000`
- **Include draft posts:** `bundle exec jekyll serve --drafts`

## Updates

To update all gems to their latest compatible versions:
```bash
bundle update
```

## Troubleshooting

If you encounter issues, try:
```bash
bundle clean --force
bundle install
```

## .gitignore Updates

The `.gitignore` file has been updated to exclude:
- Jekyll build output (`_site/`, `.jekyll-cache/`, `.jekyll-metadata`)
- Bundler files (`Gemfile.lock`, `.bundle/`, `vendor/`)
- IDE and OS files (`.vscode/`, `.idea/`, `.DS_Store`, `Thumbs.db`, etc.)
