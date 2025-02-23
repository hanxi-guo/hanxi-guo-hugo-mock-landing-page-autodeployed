# DormGenie Mock Landing Page

Welcome to the **DormGenie** Mock Landing Page project! This is a minimalistic, fast, and responsive landing page built using [Hugo](https://gohugo.io/getting-started/installing/)—one of the world’s fastest static site generators. The theme is built based on the [Bootstrap template](https://github.com/filipecarneiro/hugo-bootstrap-theme). The site introduces *DormGenie*, a smart relocation assistant designed to streamline packing, shopping, and room setup for students, expats, and busy professionals.

---

## Automating the Deployment of a Hugo Website

To streamline the deployment process, I have set up GitHub Actions to automatically build and deploy the Hugo site. You can find the workflow code file here: [`.github/workflows/gh-pages-deployment.yaml`](.github/workflows/gh-pages-deployment.yaml).

### Workflow Overview
This workflow automates the deployment of the Hugo site by:
1.  Triggering on pushes to the `main` branch and pull requests targeting `main` branch too.
2.  **Build**: The workflow installs Hugo, checks out the latest changes from the repository, and compiles the static site files using the `hugo -D --gc --minify`.
3. **Report Build Status**: The workflow then ensures that the build completes successfully, logs any issues, and updates the status to GitHub for tracking.
4. **Deploy**: If the build passes, the generated site files are deployed to the `gh-pages` branch using the `peaceiris/actions-gh-pages` version 3.9.3 of GitHub Action, making the site live on GitHub Pages.


### Key Notes
- Importing the repository [`hugo-mock-landing-page`](https://github.com/hanxi-guo/hugo-mock-landing-page) for automated deployment.
- Ensure the `baseURL` in `config.toml` matches the deployment URL.
- **Important: Do not change** the GitHub Pages source from `gh-pages` to GitHub Actions, as this would deactivate the pages. The detailed explanation from ChatGPT could be viewed in  [`EXPLANATION-OF-PAGE-SOURCE.pdf`](EXPLANATION-OF-PAGE-SOURCE.pdf).
- Modify the default `GITHUB_TOKEN` to have **Read and write** permissions for deployment to work correctly.

---

## Getting Started

Ensure you have the following installed:
- **Hugo**  
- **Git**

To run the site locally:
```sh
hugo server -D
```

---

## Troubleshooting

### **Common Issues & Fixes**
1. **Broken icons or images:**
   - See [Issue report](./Issue.md)
2. **Site showing the README instead of the page:**
   - Ensure the static files in `public/` are correctly pushed to the `gh-pages` branch.
   - Verify that GitHub Pages is set to serve from `gh-pages`.
3. **Resource 404 errors:**
   - Double-check the `baseURL` in `config.toml` to match the deployment URL.

---

## Contributing

Contributions are welcome!
- Report issues or request features via the Issues tab.
- Submit pull requests for enhancements or bug fixes.

---

## License

This project is licensed under the MIT License.

---

Happy coding! 🎉 Let me know if you build something exciting with this repository. 😊

