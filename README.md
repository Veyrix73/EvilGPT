# Evil GPT

A dark, purple neon chat UI for an AI with a sharp, villain-style personality. Evil GPT is a frontend: it connects to an OpenAI-compatible chat-completions API that you configure.

## Features

- Responsive dark-mode interface with a purple/pink neon theme.
- Snarky, direct “Evil GPT” personality prompt.
- Connect any provider that supports the OpenAI-compatible `/chat/completions` endpoint.
- Conversation history for the current page session.
- API key stays in browser memory only; it is not written to local storage or included in the repo.
- API endpoint and model preferences are saved locally in your browser.

## Run it

1. Open `index.html` in a modern browser, or serve this folder with a local static server.
2. Open **AI connection settings** (gear icon).
3. Enter your provider's API base URL, model ID, and API key.
4. Save, then send a message.

Example OpenRouter settings:

- API base URL: `https://openrouter.ai/api/v1`
- Model ID: `openai/gpt-4o-mini` (change it to a model available in your provider account)
- API key: your own key from your provider

The model ID above is only an example; provider offerings and prices change. Use a model that is actually available to your account.

## Publish with GitHub Pages

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then save.
4. Open the Pages URL GitHub provides.

## Security notes

- **Never put an API key in source code or commit it to GitHub.**
- The key entered in the settings dialog lives in browser memory and clears when the page is refreshed. Requests go directly to the API URL you configured.
- Only enter a key for a provider you trust. A public site visitor needs their own key to use the app.
- Because this is a static page, your chosen API provider must allow requests from the browser (CORS). If not, use a small backend proxy and keep the key in a server-side environment variable.
- Evil GPT's “evil” persona is a writing style, not a promise to bypass a provider's safeguards. What it can answer also depends on the model and provider.

## Customization

Edit the `SYSTEM_PROMPT` constant in the bottom script of `index.html` to change Evil GPT's voice. The UI is plain HTML, CSS, and JavaScript; there is no build step.
