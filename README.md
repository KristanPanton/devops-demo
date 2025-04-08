# devops-demo

## Hands-On Assignment: Deploy a Static Website (5 minutes)

**Objective**: Create a CI/CD pipeline to deploy an HTML page automatically.

### Steps

1. **Create a GitHub Repository**

   - Name: `devops-demo`
   - Add `index.html` with basic content (e.g., “Hello, DevOps!”).

2. **Configure GitHub Actions**

   - Create `.github/workflows/deploy.yml`:

   ```yaml

   name: Deploy to GitHub Pages
   on: [push]
   jobs:
   deploy:
       runs-on: ubuntu-latest
       permissions:
       contents: write
       pages: write
       id-token: write
       steps:
       - uses: actions/checkout@v4
       - name: Deploy
           uses: peaceiris/actions-gh-pages@v3
           with:
           github_token: ${{ secrets.GITHUB_TOKEN }}
           publish_dir: ./

   ```

3. **Verify Deployment**
   - Push changes to GitHub.
   - Navigate to `https://.github.io/devops-demo` to see the live site.
