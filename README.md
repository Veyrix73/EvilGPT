# Evil GPT

A dark, purple neon chat UI for an AI with a sharp, villain-style personality. Evil GPT is a frontend that uses Groq's OpenAI-compatible chat-completions API by default.

## Features

- Responsive dark-mode interface with a purple/pink neon theme.
- Snarky, direct “Evil GPT” personality prompt.
- Groq connection defaults, with editable endpoint and model fields.
- Conversation history for the current page session.
- API key stays in browser memory only; it is not written to local storage or included in the repo.
- API endpoint and model preferences are saved locally in your browser.

## Run it with Groq

1. Open `index.html` in a modern browser, or serve this folder with a local static server.
2. Create an API key in your GroqCloud account.
3. Open **AI connection settings** (gear icon).
4. Use these settings:
   - **API base URL:** `https://api.groq.com/openai/v1`
   - **Model ID:** `openai/gpt-oss-20b`
   - **API key:** your own Groq API key
5. Save, then send a message.

The default model is listed in Groq's supported-models documentation. You can change the model ID in settings to another model available to your account. Models, limits, and pricing can change.

## Publish with GitHub Pages

1. Open the repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch `main` and folder `/ (root)`, then save.
4. Open the Pages URL GitHub provides.

## Security notes

- **Never put an API key in source code or commit it to GitHub.**
- The key entered in the settings dialog lives in browser memory and clears when the page is refreshed. Requests go directly to the Groq API URL you configured.
- Only enter a key for a provider you trust. A public site visitor needs their own key to use the app; a static GitHub Pages app does not hide a key from its owner.
- Because this is a static page, browser requests require the provider to allow them (CORS). If a browser connection fails due to CORS, use a small backend proxy and keep the key in a server-side environment variable.
- Evil GPT's “evil” persona is a writing style, not a promise to bypass a provider's safeguards. What it can answer also depends on the model and provider.

## Customization

Edit the `SYSTEM_PROMPT` constant in the bottom script of `index.html` to change Evil GPT's voice. The UI is plain HTML, CSS, and JavaScript; there is no build step.
