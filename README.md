# NOVA AI — GitHub Pages edition

A purple-themed static AI chat website. It uses Transformers.js in the visitor's browser and the `onnx-community/LFM2.5-350M-ONNX` model. GitHub Pages only serves the website files; it does not run the AI model on a server.

## Publish for free with GitHub Pages

1. Sign in to GitHub and open https://github.com/new.
2. Create a repository named `nova-ai` and set it to **Public**. A public repository is required for GitHub Pages on GitHub Free.
3. Open the new repository and choose **Add file → Upload files**.
4. Upload `index.html`, `README.md`, and `.nojekyll` from this folder. Keep them in the repository's top level (not inside another folder).
5. Click **Commit changes**.
6. Open the repository's **Settings → Pages**.
7. Under **Build and deployment**, choose **Deploy from a branch**.
8. Choose branch **main** and folder **/(root)**, then click **Save**.
9. After the deployment finishes, your site will be at `https://YOUR-GITHUB-USERNAME.github.io/nova-ai/` (replace the username with your GitHub username).

GitHub says a Pages site can take up to 10 minutes to become available after changes are pushed. See https://docs.github.com/en/pages/quickstart.

## How chat works

- The web page is hosted as static files by GitHub Pages.
- When a visitor presses **Load NOVA AI**, Transformers.js downloads the model from Hugging Face and runs it on that visitor's device.
- No OpenAI API key, server, Gradio app, Ollama, or paid GitHub Pages plan is required for a public repository.
- The first model download is large (the model's Q4 ONNX data file is about 294 MB, plus supporting files), so it needs a reliable internet connection and may take several minutes. The browser may cache downloaded files for future visits.
- WebGPU is used when available; otherwise the app attempts the slower WASM/CPU path. Some older devices or browsers may not have enough memory or supported acceleration to run it.
- This is a small 350-million-parameter model. It is much less capable than ChatGPT and the model publisher says it is not intended for knowledge-intensive tasks or programming. Check important answers.
- Chat history is stored in local browser storage on each visitor's device. It is not shared across devices.

## Files

- `index.html` — complete NOVA AI site and chat interface.
- `README.md` — these publishing and usage instructions.
- `.nojekyll` — tells GitHub Pages not to process the repository with Jekyll.
