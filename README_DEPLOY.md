# মিষ্টি খান v22 — GitHub ও Vercel সেটআপ

বাংলাদেশি ৩০ দিনের ব্যঙ্গ-গেমের source এবং static hosting files। গেমের মূল source হলো `index.html`; প্রকাশিত files `dist/`-এ আছে।

## GitHub-এ প্রথমবার push

1. GitHub-এ একটি নতুন, খালি repository তৈরি করুন। README, license বা `.gitignore` যোগ করবেন না—ZIP-এ সেগুলো থাকবে না।
2. ZIP unzip করে `mishti-khan-v22` ফোল্ডারে terminal খুলুন।
3. নিচের command চালান। `YOUR_USERNAME` ও `REPO_NAME` আপনার GitHub তথ্য দিয়ে বদলাবেন।

```bash
git init -b main
git add .
git commit -m "Publish Mishti Khan v22"
git remote add origin https://github.com/YOUR_USERNAME/REPO_NAME.git
git push -u origin main
```

## Vercel-এ live hosting

1. Vercel-এ **Add New → Project** বেছে GitHub repository import করুন।
2. **Framework Preset:** Other
3. **Root Directory:** `.`
4. **Build Command:** ফাঁকা রাখুন।
5. **Output Directory:** `dist`
6. Deploy চাপুন।

এটি plain HTML/CSS/JavaScript project, তাই build বা install step লাগে না। Vercel-এর Git integration চালু থাকলে পরেরবার `main`-এ push করলেই নতুন deployment হবে।

## ভবিষ্যৎ পরিবর্তন ও push

গেমের source `index.html` সম্পাদনা করে প্রকাশিত copy আপডেট করুন:

```bash
cp index.html dist/index.html
git add index.html dist/index.html
git commit -m "Describe your game update"
git push
```

`dist/404.html` এবং `dist/favicon.svg`-ও প্রকাশিত folder-এ রাখবেন।

## Local preview

Project folder থেকে চালান:

```bash
python3 -m http.server 4173 --directory dist
```

তারপর `http://localhost:4173` খুলুন।

## বর্তমান public preview

https://mishti-khan-bangladesh.mahfuz085-cuet.chatgpt.site

## Vercel docs

- Static project/build settings: https://vercel.com/docs/builds
- Importing a Git repository: https://vercel.com/docs/git
