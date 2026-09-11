# Pixora — Social Photo Sharing App

Pixora is an Expo/React Native + Supabase social photo-sharing app targeting Android, iOS and Web.

## 1. Create the Expo project

The safest setup is to create a fresh Expo project, then copy the files in this archive over it:

```bash
npx create-expo-app@latest pixora
cd pixora
```

Install dependencies:

```bash
npx expo install @supabase/supabase-js @react-native-async-storage/async-storage react-native-url-polyfill expo-image-picker
```

## 2. Configure Supabase

Create a Supabase project. In the SQL editor, run:

`supabase/schema.sql`

Then create two Storage buckets:

- `post-images`
- `avatars`

For the MVP, these buckets can be public. The database policies still protect database records. For a production deployment, private buckets with signed URLs are preferable.

## 3. Environment variables

Create `.env`:

```env
EXPO_PUBLIC_SUPABASE_URL=YOUR_SUPABASE_PROJECT_URL
EXPO_PUBLIC_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY
```

Do NOT put a Supabase service-role/secret key in the app.

## 4. Start

```bash
npx expo start
```

Press:
- `a` for Android
- `i` for iOS (macOS/Xcode required)
- `w` for web

## Current features

- Email/password registration
- Login/logout
- Persistent authentication session
- User profiles
- Edit profile
- Avatar upload
- Photo upload
- Captions
- Chronological home feed
- Likes/unlikes
- Comments
- Follow/unfollow
- User search
- Notifications
- Saved posts
- Basic reporting and blocking database support

Messaging, stories, video/reels, advanced recommendations and admin UI are planned for later milestones.


## Milestone 3 upgrades

This version adds a more polished Pixora experience:
- Refreshed home feed UI with loading and empty states
- Improved post cards and profile presentation
- Optimistic likes
- Save/unsave posts
- Better create-post screen
- Character counter for captions
- Safer local UUID generation for post uploads
- Shared theme constants for consistent styling

### Supabase
The existing `supabase/schema.sql` already includes the `saved_posts` table and its RLS policies.

### Important
Create these Storage buckets in Supabase:
- `post-images`
- `avatars`

For a production release, use private storage/signed URLs, add moderation, pagination, rate limiting, account recovery/deletion, and stronger privacy controls.


## Milestone 5
Deployment configuration and launch documentation are included in `eas.json`, `MILESTONE_5_DEPLOYMENT.md`, and `LAUNCH_CHECKLIST.md`.


## Milestone 6
Production social features include post details, comments, and saved posts. See `MILESTONE_6_PRODUCTION.md`.


## Milestone 7
Discovery, public profiles, follow state/counts, user search and notification screens are included. See `MILESTONE_7.md`.


## Milestone 8
Security, input validation, upload protection, feed pagination support and report/block services are included. See `MILESTONE_8.md`.


## Milestone 9
Final release preparation for Android, iOS and Web. See `FINAL_RELEASE.md` and `RELEASE_CHECKLIST.md`.


## Final production handoff
See `PRODUCTION_FINAL.md` and `supabase/migrations/0002_pixora_release_hardening.sql`.
