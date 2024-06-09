# Vue GitHub Pages Deploy

This project is a Vue.js application set up for continuous deployment to GitHub Pages using GitHub Actions. 
The workflow includes automated static code analysis using ESLint to ensure code quality.

## Features

- Continuous deployment to GitHub Pages on any commit.
- Static code analysis with ESLint.
- Follows best practices for code quality.

## Setup

1. **Install Vue CLI:**
   ```bash
   vue create my-vue-app
   cd my-vue-app
   npm run build
   git branch -M main
	
   git remote add origin https://github.com/kartal5/vue-github-pages-auto-deploy-workflow.git
   git add .
   git commit -m "Initial commit"
   git push -u origin main

   mkdir -p .github/workflows
   git add .github/workflows/deploy.yml
   git commit -m "Add GitHub Actions workflow for deployment and linting"
   git push

   npm run lint
   npm run build

   git add public/index.html
   git commit -m "Update source index.html"
   git push origin main

   git add README.md
   git commit -m "Updated README.md for documentation"

