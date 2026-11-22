# Personal homepage (static)

Single-page static site for GitHub Pages. No build step, no framework.

```
index.html   the whole page (HTML + CSS inline)
photo.jpg    profile photo (400 px, compressed)
cv.pdf       public CV = ../../个人简历/Resume.tex compiled WITHOUT the phone line,
             with a compressed photo (served at https://wzjeh.github.io/cv.pdf)
.nojekyll    tells GitHub Pages to serve files as-is
```

The old Astro site in the parent folder is kept untouched as a backup.

## Deploy to GitHub Pages (once)

1. On GitHub, create a **public** repository named `wzjeh.github.io`.
2. Upload the three files above (repo page → Add file → Upload files), or:
   ```sh
   cd site
   git init -b main && git add . && git commit -m "Homepage"
   git remote add origin https://github.com/wzjeh/wzjeh.github.io.git
   git push -u origin main
   ```
3. Repo → Settings → Pages → Source: *Deploy from a branch*, `main` / `(root)`.
4. The site is live at https://wzjeh.github.io within a minute or two.

## Retire the Netlify site

Optional: in Netlify, replace the deploy with a page that redirects to
https://wzjeh.github.io (a `_redirects` file containing
`/*  https://wzjeh.github.io  301!`), so old links keep working.
Then update the URL in the CV header.

## Updating

Edit `index.html` directly and push. Update the "Last updated" line in the footer.
Pending: ORCID / Google Scholar links (commented out in the header);
Chem. Sci. volume and pages once assigned.
