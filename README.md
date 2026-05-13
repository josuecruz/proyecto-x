# Proyecto X — GitHub Pages Deployment Guide

This guide explains how to publish the Proyecto X landing page on GitHub Pages and use it as a credibility asset for VC outreach.

---

## 1. Create the GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Repository name: **`proyecto-x`** (or `proyecto-x-landing` if the org name is taken)
3. Description: _"AI-Native Financial Services for Mexico — Landing Page"_
4. Visibility: **Public** (GitHub Pages requires public repos on the free tier)
5. Do **not** initialize with README, .gitignore, or license
6. Click **Create repository**

## 2. Push the Landing Page

```bash
# Clone the empty repo
git clone https://github.com/<your-username>/proyecto-x.git
cd proyecto-x

# Copy the landing page into the repo root
cp /path/to/landing-page.html ./index.html

# Commit and push
git add index.html
git commit -m "Add landing page"
git push origin main
```

> **Important:** Name the file `index.html` (not `landing-page.html`) so GitHub Pages serves it automatically at the root URL.

## 3. Enable GitHub Pages

1. Go to your repo on GitHub: `https://github.com/<your-username>/proyecto-x`
2. Click **Settings** → **Pages** (left sidebar)
3. Under "Branch", select `main` and save (leave folder as `/ (root)`)
4. Wait 1–2 minutes. Your site will be live at:
   ```
   https://<your-username>.github.io/proyecto-x/
   ```

### Verify it works

Open the URL in a browser. The landing page should render fully with all sections, language toggle, and contact form.

## 4. (Optional) Point a Custom Domain

If you own a domain (e.g., `proyecto-x.com`):

1. In your repo **Settings** → **Pages**, enter your domain under "Custom domain"
2. Check **Enforce HTTPS**
3. Add the following DNS records at your domain registrar:

   | Type  | Name              | Value                          |
   |-------|-------------------|--------------------------------|
   | A     | @                 | `185.199.108.153`              |
   | A     | @                 | `185.199.109.153`              |
   | A     | @                 | `185.199.110.153`              |
   | A     | @                 | `185.199.111.153`              |
   | CNAME | www               | `<your-username>.github.io`    |

   Propagation takes 5–30 minutes.

## 5. FormSubmit.co Configuration

The contact form uses [FormSubmit.co](https://formsubmit.co), a free form-to-email service:

1. The form action is already set to: `https://formsubmit.co/jcvm2089@gmail.com`
2. When the first form submission is received, FormSubmit will send a confirmation email to jcvm2089@gmail.com — click the link in that email to verify.
3. After verification, all form submissions will be forwarded automatically.
4. You can customize the auto-reply, redirect URL, and subject line from the FormSubmit dashboard.

### Optional: Add reCAPTCHA

FormSubmit supports Google reCAPTCHA to prevent spam. To enable:

1. Get a reCAPTCHA v2 site key from [developers.google.com/recaptcha](https://developers.google.com/recaptcha)
2. Add to the form: `<input type="hidden" name="_captcha" value="true">` (already present)
3. Follow FormSubmit docs to add the widget

## 6. Using This as a VC Outreach Asset

A polished, bilingual landing page on a custom domain significantly improves credibility. Here's how to leverage it:

### In Cold Emails

Include the link in your signature:

```
---
Josue Yannick Cruz Sandoval
CEO/Founder, Proyecto X
jcvm2089@gmail.com
https://<your-username>.github.io/proyecto-x/
```

### In Pitch Decks

Add a QR code linking to the landing page on your "Contact" slide.

### In Investor Updates

Reference specific sections:

- _"See our market analysis at proyectox.com/#mexico"_
- _"Our tech moat is detailed at proyectox.com/#tech"_

### For Warm Introductions

When an intro is made, the investor can browse the landing page before the meeting. This pre-qualifies interest and saves meeting time for deeper questions.

### In Grant Applications

Include the URL in INADEM, Impulsora de Innovación, and other grant applications as your "company website" — far more credible than a LinkedIn profile alone.

## 7. Updating the Page

```bash
# Edit index.html locally
vim index.html

# Commit and push
git add index.html && git commit -m "Update content" && git push
```

GitHub Pages deploys automatically within 1–2 minutes of push.

---

## Quick Reference

| Task | Command |
|------|---------|
| Clone repo | `git clone https://github.com/<user>/proyecto-x.git` |
| Copy landing page | `cp landing-page.html proyecto-x/index.html` |
| Commit & push | `git add . && git commit -m "Message" && git push` |
| Deployed URL | `https://<user>.github.io/proyecto-x/` |
| Form service | [FormSubmit.co](https://formsubmit.co) — free tier |
