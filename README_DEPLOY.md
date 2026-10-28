# UniAi — deployment package

## Deploy to Render

This project can be deployed as a Node.js web service. Keep your OpenAI API key out of GitHub and out of this ZIP. Set it as the `OPENAI_API_KEY` environment variable in Render.

### Option A — Render Blueprint (uses render.yaml)
1. Put these files at the root of a GitHub repository. Do not upload a ZIP as the only repository file.
2. In Render, choose **New > Blueprint** and connect the repository.
3. Enter your OpenAI API key when Render prompts for `OPENAI_API_KEY`.
4. Deploy; Render supplies the public `onrender.com` URL.

### Option B — Web Service manually
- Runtime: Node
- Build command: `npm install`
- Start command: `npm start`
- Environment variables: `OPENAI_API_KEY` = your API key, `OPENAI_MODEL` = `gpt-5` (or another model ID enabled for your API project), `NODE_ENV` = `production`

## Security
- Never commit `.env` or expose your API key in frontend code. `.gitignore` excludes `.env`.
- API usage may be billed separately from your ChatGPT subscription.
- The free Render web service may sleep after 15 minutes of inactivity, so the first visit after idle can take about a minute to wake.

## Local run
1. Copy `.env.example` to `.env`, then set `OPENAI_API_KEY` in `.env`.
2. Run `npm install` and `npm start`.
3. Open `http://localhost:3000`.
