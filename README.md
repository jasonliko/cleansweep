# Clean Sweep website

A one-page site for Clean Sweep, a sustainable reverse graffiti company. Everything is in `index.html`, so there's no build step.

## Before you upload: set your contact info

Open `index.html`. Near the bottom, inside the `<script>` tag, edit these two lines:

```js
const CONTACT_EMAIL = "hello@example.com";   // your real email
const FORM_ENDPOINT = "";                     // optional
```

- **CONTACT_EMAIL**: the address the "Book a wall" form sends to. If you leave `FORM_ENDPOINT` empty, the form opens the visitor's email app with their request already filled in.
- **FORM_ENDPOINT** (optional): to receive form messages without an email app, make a free form at https://formspree.io and paste its URL here, for example `"https://formspree.io/f/abcd1234"`.

Also search the file for `[PHONE]` and `[CITY]` and replace them with your own details.

## Put it on GitHub Pages

1. On GitHub, create a new **public** repository, for example `clean-sweep`.
2. Upload `index.html` (and this README) to the repository. You can drag and drop them on the repo page, or use the terminal:
   ```bash
   cd clean-sweep-site
   git init
   git add .
   git commit -m "Clean Sweep website"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/clean-sweep.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**. Under "Build and deployment", set **Source** to *Deploy from a branch*, then pick branch `main` and folder `/ (root)`, and click **Save**.
4. After a minute or two the site is live at `https://YOUR-USERNAME.github.io/clean-sweep/`.

## Connect your own domain

1. In **Settings → Pages → Custom domain**, type your domain (for example `www.cleansweep.com`) and click **Save**. GitHub adds a `CNAME` file to the repo for you.
2. At the company where you bought your domain (GoDaddy, Namecheap, Squarespace, Cloudflare and so on), open the DNS settings and add:
   - **For `www`:** a `CNAME` record with host `www` pointing to `YOUR-USERNAME.github.io`
   - **For the bare domain (`cleansweep.com`):** four `A` records with host `@` pointing to
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
3. DNS changes can take anywhere from a few minutes to a day. Once GitHub shows the domain as verified, tick **Enforce HTTPS**.

GitHub's official guide: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
