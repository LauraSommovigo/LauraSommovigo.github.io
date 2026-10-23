# Launch plan: beta → public → first search result

Site address once live: **https://laurasommovigo.github.io**

## Stage 1 — Private beta (now)
Review the private preview link Claude shared. Send it to 1–2 trusted colleagues for comments.
Nothing is on GitHub yet, so nobody can find it.

## Stage 2 — Soft launch (live, but hidden from Google)
The files ship with search engines blocked (`noindex` in index.html and `Disallow: /` in robots.txt).
The site works for anyone holding the link, but Google won't list it.

1. On github.com, click **New repository**. Name it exactly `LauraSommovigo.github.io`, set it to **Public**, and don't add a README.
2. On the new repo page, click **uploading an existing file**. Drag in every file from this folder, including `.nojekyll`. On a Mac, press Cmd+Shift+. in Finder to show hidden files. Then click **Commit changes**.
3. Go to **Settings → Pages**. Set Source to *Deploy from a branch* and the branch to `main` / `(root)`, then save. The site goes live in about a minute.
4. Check it on your phone and laptop. Share the link with your mentors.

(Free GitHub accounts can't serve Pages from a private repo, so this stage is the "private" live step. The link works, but nothing points to it.)

## Stage 3 — Public launch (let Google in)
1. In `index.html`, delete the line `<meta name="robots" content="noindex, nofollow">`.
2. Replace the contents of `robots.txt` with:
   ```
   User-agent: *
   Allow: /
   Sitemap: https://laurasommovigo.github.io/sitemap.xml
   ```
3. Commit both changes.
4. **Google Search Console** (search.google.com/search-console): add a *URL prefix* property for `https://laurasommovigo.github.io/`. Verify it with the *HTML tag* method by pasting the tag into the `<head>` of index.html. Then:
   - Go to Sitemaps and submit `sitemap.xml`.
   - Go to URL Inspection, enter the homepage and click **Request indexing**.
5. Optional: **Bing Webmaster Tools** can import directly from Search Console. This also covers DuckDuckGo.

## Stage 4 — Become the top result for "Laura Sommovigo"
Google ranks a personal page first when trusted sites link to it under your name. In order of impact:
1. **Columbia / LtU people page:** ask for your profile to link to the site.
2. **ORCID:** add the site under *Websites & social links*. (Your ORCID iD isn't in the CV; add it to the site too.)
3. **GitHub profile:** set the *Website* field to the site. Also create a profile README.
4. **NASA ADS / arXiv / Google Scholar:** add the homepage URL where each profile allows it.
5. **Email signature, conference bios, LinkedIn:** include the URL.
6. Keep the site updated (new papers, talks). Fresh pages get recrawled more often.

Expect indexing within days of Stage 3. Reaching the top spot usually takes 2–6 weeks once the links above are in place. Your name is distinctive, which helps.


## Yearly update
Once a year: replace `cv.pdf`, then edit `index.html` to add new first-author papers, talks and roles, and bump the "Updated" date in the footer. Upload the changed files on GitHub with **Add file → Upload files**.
