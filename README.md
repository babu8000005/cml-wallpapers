# CML LiveDesk — GitHub Pages wallpaper package

এই package-এ `AURA OFF BOYS.jpg` wallpaper, optimized thumbnail, `manifest.json`, এবং GitHub Pages-এর জন্য GitHub Actions workflow প্রস্তুত আছে।

## GitHub-এ upload ও publish

1. ZIP-টি কম্পিউটারে download করে **Extract All** করুন। ZIP-টি GitHub repository-তে একক file হিসেবে upload করবেন না; GitHub সেটি নিজে থেকে extract করবে না।
2. GitHub-এ নতুন repository তৈরি করুন। Free plan-এ Pages ব্যবহার করতে repository-টি **Public** রাখুন। Pages-এ publish হওয়া file-গুলো public URL-এ দেখা যাবে।
3. Extract করা package-এর ভেতরের সব content repository-র root-এ দিন। `.github/workflows/deploy-pages.yml` path-টি হুবহু ঠিক রাখুন; `.github` folder-টি যেন বাদ না পড়ে। GitHub Desktop বা Git command line দিয়ে upload করাই সবচেয়ে নির্ভরযোগ্য।
4. GitHub repository-তে **Settings → Pages → Build and deployment → Source** থেকে **GitHub Actions** বেছে নিন।
5. `main` branch-এ files commit/push করুন। তারপর **Actions** tab-এ `Deploy wallpaper library to GitHub Pages` workflow সফল হওয়া পর্যন্ত অপেক্ষা করুন।
6. **Settings → Pages**-এ website URL পাবেন। `https://<username>.github.io/<repository>/manifest.json` খুলে manifest এবং তার image paths পরীক্ষা করুন।

## Folder structure

```text
.github/
  workflows/
    deploy-pages.yml
README.md
public/
  manifest.json
  thumbnails/
    AURA OFF BOYS-thumb.jpg
  wallpapers/
    AURA OFF BOYS.jpg
```

Manifest-এর image path-গুলো relative রাখা হয়েছে; তাই repository-based Pages URL-এ `/repository/` অংশটিও ঠিকভাবে কাজ করবে। নতুন wallpaper যোগ করতে `public/wallpapers/` ও `public/thumbnails/`-এ file যোগ করে `public/manifest.json`-এ নতুন entry দিন।

## Free plan ও ব্যবহারের সীমা

GitHub Pages-এর published site সর্বোচ্চ 1 GB হতে পারে; bandwidth-এর soft limit 100 GB/month। GitHub Pages commercial SaaS বা online business host করার জন্য নয়। তাই এটিকে ছোট personal/test wallpaper catalog-এ ব্যবহার করুন; app commercial হলে বা download traffic বেড়ে গেলে GitHub Pages-এর policy ও limits যাচাই করে hosting বদলান। [GitHub Pages limits](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits)

## App integration

এই package GitHub Pages hosting ও manifest প্রস্তুত করে। CML LiveDesk app-এ remote manifest fetch, gallery mapping, download ও cache feature আলাদা করে implement করতে হবে; package একা app source code পরিবর্তন করে না।

Wallpaper-গুলো publicভাবে বিতরণের আগে source/license অনুযায়ী share করার অনুমতি নিশ্চিত করুন।
