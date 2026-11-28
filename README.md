# harmsandhu.com

Personal site. Built with Astro, hosted free on GitHub Pages, published automatically every time you push to `main`.

## Everyday edits

- **Links (LinkedIn, GitHub, email):** fill them in at `src/config.ts`. Empty ones stay hidden.
- **Page text:** `src/pages/index.astro`.
- **Turn on Writing:** set `showWriting: true` in `src/config.ts`.
- **New article:** copy `src/content/articles/example-draft.md`, rename it (the file name becomes the web address), write, and set `draft: false`.

Commit and push: the site updates in about a minute.

To preview on your own computer: `npm install`, then `npm run dev`, and open http://localhost:4321.

## One-time setup

### 1. Put the code on GitHub
1. Create a new repository on GitHub (for example `harmsandhu-site`). Public is fine.
2. From this folder:
   ```
   git remote add origin https://github.com/YOUR-USERNAME/harmsandhu-site.git
   git branch -M main
   git push -u origin main
   ```

### 2. Turn on GitHub Pages
1. In the repository: **Settings > Pages**.
2. Under **Build and deployment > Source**, choose **GitHub Actions**.
3. Open the **Actions** tab and wait for "Deploy to GitHub Pages" to finish (green tick).
4. Back in **Settings > Pages**, under **Custom domain**, enter `harmsandhu.com` and save.

### 3. Point harmsandhu.com at GitHub (GoDaddy)
In GoDaddy: **My Products > harmsandhu.com > DNS**.

1. Delete any existing **A** record for `@` (GoDaddy usually adds a "Parked" one).
2. Add four **A** records, Name `@`, one for each value:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
3. Edit the **CNAME** record named `www` so its value is `YOUR-USERNAME.github.io` (add it if missing).
4. Leave email records (MX, TXT) alone.

DNS can take from a few minutes to 24 hours. Then, in **Settings > Pages**, tick **Enforce HTTPS** once GitHub allows it.

### 4. Send harmsandhu.ca to the .com (GoDaddy)
**My Products > harmsandhu.ca > DNS > Forwarding**: add forwarding to `https://harmsandhu.com`, type **Permanent (301)**.

### 5. Recommended: verify the domain with GitHub
**GitHub profile Settings > Pages > Add a domain**, enter `harmsandhu.com`, and add the TXT record it gives you in GoDaddy DNS. This stops anyone else's GitHub repository from claiming your domain.
