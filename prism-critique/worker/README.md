# Prism Critique AI Backend

This is the secure backend for the automatic AI design reviewer.

## Deploy on an iPad without a computer
1. Open https://dash.cloudflare.com/ and sign in.
2. Go to Workers & Pages > Create application. Choose to import a Git repository or create a Worker and paste `index.mjs` from this folder.
3. When importing GitHub, use repository `Caaaaaity/the-image-codex` and project root `prism-critique/worker` where Cloudflare allows a root directory. Deploy the Worker.
4. Open the deployed Worker, select Settings > Variables and Secrets. Add the following as **Secret** (never plain text):
   - `OPENAI_API_KEY`: your own OpenAI API key.
   - `REVIEWER_ACCESS_TOKEN`: a long, unique private passcode that you invent.
5. (Optional) Set `OPENAI_MODEL` to `gpt-4.1` and `ALLOWED_ORIGINS` to the exact HTTPS origin of your website. Both are ordinary non-secret variables.
6. Copy the deployed `.workers.dev` URL. In Prism Critique, open **Connect AI Service**, enter the backend URL and the same access passcode, then choose **Test Connection**.
7. Upload your image and select **Analyze Image with AI**. Scores, notes, technical findings, improvement prompt and saved review populate automatically.

Do not put `OPENAI_API_KEY` inside HTML, browser local storage, a GitHub repository or a ChatGPT message.

The service is not live until the Worker is deployed with a valid OpenAI key and passcode. Set billing alerts and appropriate rate controls to protect your budget.
