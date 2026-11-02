# PANCREANOID — personal research website

Static, single-page research portfolio for Md Abu Talha Siddique.
No build step, no frameworks to install, no paid services. Everything the visitor sees is in `index.html`.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole website: content, styles and scripts in one file. The only file you normally edit. |
| `favicon.svg` | The small icon in the browser tab. |
| `og-image.png` | The preview image shown when the link is shared on LinkedIn, X, Slack, etc. |
| `404.html` | Shown if someone types a wrong address on your site. |
| `robots.txt`, `sitemap.xml` | Help search engines index the site. |
| `.nojekyll` | Tells GitHub Pages to serve the files exactly as they are. Keep it. |

External resources loaded at view time (both free, both allow hotlinking): Google Fonts (Manrope, Newsreader) and three.js r128 from cdnjs for the 3D organoid. If either fails to load the page still works; the organoid falls back to a soft glowing sphere.

## Publishing for free on GitHub Pages (first time)

You need a free GitHub account. Nothing is ever charged; GitHub Pages has no paid tier for personal sites.

1. Go to https://github.com/signup and create an account. **Choose the username `pancreanoid`** if it is available — the site address becomes `https://pancreanoid.github.io`. (If it is taken, pick another; the address becomes `https://<username>.github.io`.)
2. Once signed in, click the **+** in the top-right corner → **New repository**.
3. Repository name: type exactly `<username>.github.io` (for example `pancreanoid.github.io`). Keep it **Public**. Do not tick any of the "initialize" boxes. Click **Create repository**.
4. On the empty repository page click **uploading an existing file**.
5. Drag all the files from this folder into the upload area: `index.html`, `favicon.svg`, `og-image.png`, `404.html`, `robots.txt`, `sitemap.xml`, `.nojekyll`. (If your computer hides `.nojekyll`, upload the others; the site still works.)
6. Click the green **Commit changes** button.
7. Wait one to two minutes, then open `https://<username>.github.io` in your browser. HTTPS is on automatically.

If the page does not appear after five minutes: open the repository → **Settings** → **Pages**, make sure "Source" says *Deploy from a branch* and the branch is `main` with folder `/ (root)`, then **Save**.

## Updating the site later (new paper, award, link)

1. Open `index.html` in any plain-text editor (Notepad on Windows, TextEdit in plain-text mode on Mac, or VS Code).
2. Search for the word `EDIT`. Every place you are likely to change is marked with an `<!-- EDIT: ... -->` comment.
3. Make the change. For example, to add a publication copy one `<li class="pub"> ... </li>` block, paste it below, and replace the text. Change its status label from `Placeholder` to `Published` once it is a peer-reviewed article:
   ```html
   <li class="pub">
     <span class="year">2027</span>
     <div>
       <h3>Full article title</h3>
       <p class="meta">Siddique MAT, Co-author A, Co-author B · Journal Name, 12(3), 100–110 · <a href="https://doi.org/10.xxxx/yyyy">doi:10.xxxx/yyyy</a></p>
     </div>
     <span class="status">Published</span>
   </li>
   ```
   Status labels you can use: `status` (published), `status ongoing` (in preparation / ongoing), `status placeholder` (unconfirmed).
4. Save the file.
5. On GitHub, open your repository, click `index.html`, click the pencil icon (**Edit this file**), select all, paste the new contents, and click **Commit changes**. Or use **Add file → Upload files** and drop the new `index.html` on top of the old one.
6. The live site updates within a minute or two. Refresh the page (hold Shift while reloading if you still see the old version).

Things to replace before sharing the site widely:
- `your.email@ufl.edu` → your real address (search for `emailText`).
- The five contact links (`href="#"`) → your Google Scholar, ORCID, LinkedIn, GitHub and ResearchGate pages. Delete any line you do not use.
- The three placeholder publication entries.
- If your address is not `https://pancreanoid.github.io/`, replace that address everywhere it appears in `index.html`, `robots.txt` and `sitemap.xml` (search for `pancreanoid.github.io`).

## Alternatives, also free

- **Cloudflare Pages** (`https://pancreanoid.pages.dev`): sign in at https://dash.cloudflare.com, Workers & Pages → Create → Pages → **Upload assets**, name the project `pancreanoid`, drag the folder in. Unlimited bandwidth on the free plan.
- **Netlify** (`https://pancreanoid.netlify.app`): https://app.netlify.com → Add new site → Deploy manually, drag the folder in, then Site settings → Change site name to `pancreanoid`. Free plan is credit-metered, generous enough for a portfolio.

The site files are identical for all three. GitHub Pages is recommended because its free tier has never had a pricing change and a `.github.io` address is widely recognised in academia.

## A custom domain (optional, costs money)

`pancreanoid.ai`, `pancreanoid.com` or similar is a *registered domain* and always has an annual fee (`.ai` is one of the more expensive endings). All three hosts above will attach a custom domain for free if you ever buy one, but the site does not need it: the free subdomain is permanent, has HTTPS, and can be cited on a CV.

## Scientific-integrity notes baked into the page

- Every research area carries an "Ongoing research" label; the legend explains the labels.
- The machine-learning section states that methods are in development, not peer-reviewed, not validated, and not a diagnostic tool.
- Publication entries are placeholders until you replace them with verified citations.
- The ADM schematic notes that the marker behaviour shown reflects the general literature, not your own results.
