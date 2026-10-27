# Getver

A lightweight static landing page deployed to Vercel by GitHub Actions.

## Run locally

Open `index.html` in a browser, or start a local server from this folder:

```sh
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Enable continuous deployment

1. Create a Vercel project and set its framework preset to **Other**. The project root is this repository's root.
2. Create a GitHub repository and push these files to its `main` branch.
3. In the GitHub repository, open **Settings → Secrets and variables → Actions** and add these repository secrets:
   - `VERCEL_TOKEN`: a token created in your Vercel account settings.
   - `VERCEL_ORG_ID`: the Vercel team or account ID.
   - `VERCEL_PROJECT_ID`: the ID of the Vercel project created in step 1.
4. The workflow in `.github/workflows/deploy.yml` deploys the site to production on each push to `main`. You can also start it manually from the repository's **Actions** tab.

The workflow requires all three secrets. It does not expose the token in the repository.
