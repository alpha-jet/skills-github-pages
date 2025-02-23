name: Build and Deploy Jekyll Site

on:
  push:
    branches:
      - main  # Change to your default branch name

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest

    steps:
      # Checkout the repository
      - name: Checkout code
        uses: actions/checkout@v3

      # Set up Ruby
      - name: Set up Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: 3.1  # Use a compatible Ruby version for Jekyll

      # Install dependencies
      - name: Install Bundler
        run: gem install bundler

      - name: Install dependencies
        run: bundle install

      # Build the Jekyll site
      - name: Build site
        run: bundle exec jekyll build

      # Deploy to GitHub Pages
      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
