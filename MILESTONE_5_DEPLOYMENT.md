# Pixora — Milestone 5 Deployment Kit

This milestone prepares Pixora for Android, iPhone and Web builds.

## 1. Create the real Expo project

If you have not already done so:

```bash
npx create-expo-app@latest pixora
cd pixora
```

Copy the Pixora source files from this package into the project.

Install the dependencies from `package-additions.txt`.

## 2. Configure Supabase

Create your `.env` file:

```env
EXPO_PUBLIC_SUPABASE_URL=YOUR_SUPABASE_PROJECT_URL
EXPO_PUBLIC_SUPABASE_ANON_KEY=YOUR_SUPABASE_ANON_KEY
```

Never put a Supabase service-role key in the mobile/web app.

Run `supabase/schema.sql` in the Supabase SQL editor and create:
- `post-images`
- `avatars`

## 3. Test locally

```bash
npx expo start
```

For web:

```bash
npx expo start --web
```

## 4. Install EAS CLI

```bash
npm install -g eas-cli
eas login
```

Then configure the project:

```bash
eas build:configure
```

The included `eas.json` provides development, preview and production profiles.

## 5. Android build

For a testable Android package, use the preview profile:

```bash
eas build --platform android --profile preview
```

For a Google Play release build:

```bash
eas build --platform android --profile production
```

A real Google Play release also requires an eligible Google Play developer account and store setup.

## 6. iPhone build

```bash
eas build --platform ios --profile production
```

Apple signing and App Store distribution require an eligible Apple Developer account.

## 7. Web build

```bash
npx expo export --platform web
```

This creates a `dist` folder that can be deployed to a compatible static hosting provider.

## 8. Before public launch

Pixora should NOT be considered production-ready until these are completed:
- Email verification and password recovery
- Account deletion
- Stronger privacy/security rules
- Pagination/infinite feed loading
- Content reporting and moderation
- Rate limiting and abuse protection
- Image optimisation and size limits
- Private storage/signed URLs where appropriate
- Error monitoring
- Backup/recovery plan
- Privacy policy and terms
- App Store/Play Store metadata and screenshots
- Final testing on real Android, iPhone and web browsers

## Milestone 5 goal

At the end of this milestone, the project has a clear path to:
Android build → iPhone build → Web build → store/web deployment.

The exact build commands can vary slightly with the Expo SDK version used by the final project, so use the Expo/EAS CLI output as the authority if it asks for an SDK-specific change.
