# The Rich Life — Monthly Report

Mobile-first web app for org leaders to submit monthly numbers.
Built with Supabase (auth + database) and hosted on GitHub Pages.

## Live URL
https://empowercouple24.github.io/richlife-report

## Setup

### 1. Run the database schema
- Go to your Supabase project → SQL Editor
- Paste and run `supabase/schema.sql`

### 2. Make yourself admin
After creating your account in the app, run this in Supabase SQL Editor:
```sql
update public.profiles
set is_admin = true
where id = (select id from auth.users where email = 'your@email.com');
```

### 3. Deploy to GitHub Pages
- Push this repo to GitHub as `richlife-report`
- Go to repo Settings → Pages → Deploy from branch → main → / (root) → Save
- Site goes live at `https://empowercouple24.github.io/richlife-report`

### 4. Configure Supabase Auth redirect
- Go to Supabase → Authentication → URL Configuration
- Add to "Redirect URLs": `https://empowercouple24.github.io/richlife-report`

## Inviting org leaders
1. Sign in as admin
2. Click "Admin" in the top bar
3. Enter their email → Send invite
4. They receive a branded email from team@myclubtracker.com
5. They click the link, set a password, complete the wizard

## Swapping the domain later
When you have therichlife.com:
1. Update `RESEND_FROM` in index.html
2. Update Supabase redirect URLs
3. Point your domain DNS to GitHub Pages (CNAME record)
