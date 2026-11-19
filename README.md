# Johnny Manziel Fact File

A one-page site about Johnny Manziel with a live search. Each search is answered by Claude using the site's library of reliable sources. Each fact is checked again, and it's marked **Verified** only when 3 separate outlets back it.

## What's in this folder

| File | What it does |
| --- | --- |
| `index.html` | The whole page: design, photos, chapters, bio, FAQ and sources. |
| `api/ask.js` | A small server function that sends searches to Claude. |
| `lib/library.json` | The source library the search checks facts against (95 sources). |
| `package.json` | Tells Vercel this is a Node project. Nothing to install. |

## Put it on Vercel

### Option A: through GitHub (no coding tools needed)

1. Make a free account at github.com and create a new repository (for example `johnny-manziel`).
2. On the repository page click **Add file → Upload files**. Drag in **everything inside this folder**: `index.html`, `package.json`, `README.md`, and the `api` and `lib` folders. Click **Commit changes**.
3. Go to vercel.com, sign in with GitHub, click **Add New → Project**, and import the repository.
4. Leave the settings as they are (Framework Preset: **Other**). Click **Deploy**.

### Option B: with the Vercel command line

Open a terminal in this folder and run `npx vercel`, then follow the prompts.

## Turn on live answers (optional)

Without this step the site still works, but the search only shows matches from the page.

1. Create an API key at console.anthropic.com (you need to add billing there). **Set a monthly spending limit** in the console so a busy day can't run up a bill.
2. In Vercel, open your project → **Settings → Environment Variables**. Add:
   - Name: `ANTHROPIC_API_KEY`
   - Value: your key
3. Go to **Deployments**, open the latest one, and click **Redeploy** so the key takes effect.

The key stays on Vercel's server. Visitors never see it.

### Optional settings (also environment variables)

| Name | Default | What it changes |
| --- | --- | --- |
| `MODEL_ANSWER` | `claude-sonnet-5-5` | Model that writes the answers |
| `MODEL_AUDIT` | `claude-haiku-5-5` | Faster model that double-checks citations |
| `SEARCHES_PER_10_MIN` | `20` | Searches allowed per visitor every 10 minutes (best effort) |

## Images

Every graphic on the page is an original illustration drawn in code: the money-sign hands, the plain team-colored helmets (no logos), the bottle, money bag, gavel and heart. There are no photos, team logos or brand labels, so the site is safe to share publicly. Team and show names appear only as text, the normal way to refer to them.
