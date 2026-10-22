# KRUNCH Café Recipe Guide

Tablet-first private recipe guide for KRUNCH Café.

## Status
- Frontend: index.html committed.
- Database: tables `krunch_categories`, `krunch_recipes`, `krunch_admins` created in the existing 171 Cafe Timesheet Supabase project.
- Four categories and six **illustrative** recipes seeded.
- Supabase RLS restricts recipe reads to authenticated users, and writes to authorised administrators.

## Complete setup
1. In Supabase Authentication → Users, create an email/password account for the café tablet. Use a strong password and do not share it publicly.
2. Create a separate administrator email/password account.
3. Copy the admin user's UUID, then in Supabase SQL Editor run:
   `insert into public.krunch_admins(user_id) values ('REPLACE_WITH_ADMIN_UUID');`
4. In GitHub repository Settings → Pages, select Deploy from a branch, `main`, `/(root)`, and Save.
5. Open the published GitHub Pages URL on the tablet and sign in once. Supabase normally remembers the session but it may require occasional reauthentication.
6. Verify sign-in, recipe viewing, admin editing and that unauthenticated users cannot fetch recipe rows.

**Important:** All recipes are sample data and must be checked for food safety, allergens, ingredients, quantities and kitchen procedures before actual use. The GitHub repository is public, but recipe data is not publicly readable. Do not store secret API keys in index.html.

## Future enhancements
Recipe photography, offline caching, dedicated tablet kiosk mode, allergen labels and recipe version history.
