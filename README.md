# bedtimepassport.com

The landing page for the Bedtime Passport books. It is plain HTML and CSS with no build step, hosted free on Netlify from a free GitHub repository. The only thing you pay for is the domain.

## What's in this folder

| File | What it is |
|---|---|
| `index.html` | The landing page |
| `styles.css` | All the styling |
| `thanks.html` | The page people see after they sign up |
| `free/bedtime-passport-night-1-iceland.pdf` | The free Night 1 story; thanks.html links to it as the sign-up gift |
| `404.html` | Shown for any address that doesn't exist |
| `favicon.svg` | The little icon in the browser tab |
| `netlify.toml` | Netlify settings (no build, redirects, cache) |
| `robots.txt`, `sitemap.xml` | Help search engines find the page |
| `images/` | Put your covers, author photo and share image here (see the note inside) |

## Before you go live: three things to fill in

1. **Pictures.** Add `book1-cover.jpg`, `book2-cover.jpg`, `author.png` and `og-image.jpg` to `images/`. The list with sizes is in `images/PUT-IMAGES-HERE.txt`. Until you add them, the page shows a navy placeholder cover with the title, and the author section shows text only.
2. **Amazon links.** Both buttons go to an Amazon search for "Bedtime Passport Daly Henrikson" for now. Once each book has its own Amazon page, search `index.html` for `amazon.com/s?k=` and paste in the real link for each book. A short link such as `https://www.amazon.com/dp/XXXXXXXXXX` is fine.
3. **Book 2 button text.** It says "Find it on Amazon." Change it to "Pre-order on Amazon" if Book 2 goes up for pre-order too.

## Step 1: Put the files on GitHub (free)

1. Sign in at github.com (or make a free account).
2. Click **New repository**. Name it `bedtimepassport-site`. It can be Public or Private; Netlify works with both. Click **Create repository**.
3. On the new repository page, click **uploading an existing file**.
4. Drag in everything from this folder, including the `images` folder. Click **Commit changes**.

## Step 2: Host it on Netlify (free)

1. Go to netlify.com and sign up **with your GitHub account**.
2. Click **Add new project**, then **Import an existing project**, then **GitHub**. Pick `bedtimepassport-site`.
3. Leave the build command empty and the publish directory as `.`. Click **Deploy**.
4. In a minute you'll have a free address like `something-random.netlify.app`. Open it and check the page.
5. Turn on the sign-up form: go to **Forms** in the project menu and click **Enable form detection**, then go to **Deploys** and click **Trigger deploy**. Netlify only finds the form after a deploy with detection turned on.
6. Get an email for each sign-up: **Project configuration**, then **Notifications**, then **Emails and webhooks**, then **Form submission notifications**, then add your email address.

From now on, any file you change on GitHub goes live by itself a minute later.

### Staying free on Netlify

The free plan gives 300 credits a month and stops your site (it doesn't bill you) if you run out. Form sign-ups are free and unlimited. Each time a change goes live costs 15 credits, so you have room for about 20 updates a month, with credits left over for visitors. To save credits, make several changes at once and commit them together instead of one at a time.

## Step 3: The domain (the only cost, about $10 a year)

If you don't own `bedtimepassport.com` yet, buy it at **Cloudflare Registrar** (about $10.46 a year, the same price every year, privacy included) or Porkbun. Avoid registrars that discount the first year and raise the renewal.

Then connect it to Netlify:

1. In Netlify, go to **Domain management**, then **Add a domain**. Type `www.bedtimepassport.com` and confirm. Netlify will offer to add the bare `bedtimepassport.com` too; say yes.
2. At your registrar's DNS settings, add these two records. If your registrar is Cloudflare, set each one to **DNS only** (gray cloud, not orange).

| Type | Name | Value |
|---|---|---|
| CNAME | `www` | your Netlify address, such as `something-random.netlify.app` |
| A | `@` | `75.2.60.5` |

3. Back in Netlify, wait for the domain to show as verified, then click **Verify DNS configuration** and **Provision certificate** under HTTPS. The free security certificate (the padlock) can take up to an hour.

Netlify shows its current recommended records on the domain page. If they differ from the table above, use Netlify's.

## Step 4 (optional, free): An email address at your domain

The footer lists `hello@bedtimepassport.com`. If your domain is at Cloudflare, turn on **Email Routing** (free) and forward `hello@` to your personal inbox. Otherwise, change or remove that line in `index.html`.

## The email list

Every sign-up is saved in Netlify under **Forms**, where you can download them all as a spreadsheet (CSV). When you're ready to send an update, import that file into the email tool you use (Substack is free, for example). If you'd rather people sign up for Substack directly, swap the form in `index.html` for Substack's own sign-up form; this page doesn't need anything else changed.

## Changing the page later

Open the file on GitHub, click the pencil icon, edit, and click **Commit changes**. Most edits are plain sentences inside `index.html`. Colors and fonts are at the top of `styles.css`.
