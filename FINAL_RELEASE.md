# Pixora — Milestone 9 Final Release Kit

Milestone 9 is the release-preparation stage. It does not automatically publish the app to stores.

## A. Install and verify

From the Expo project directory:

```bash
npm install
npx expo start
```

Test:
- Login/signup
- Profile editing
- Photo upload
- Feed
- Likes
- Comments
- Saves
- Explore/search
- Follow/unfollow
- Notifications
- Web navigation

## B. Web release

```bash
npx expo export --platform web
```

Deploy the generated `dist/` directory to a compatible static host.

## C. Android release

Log in to EAS:

```bash
npm install -g eas-cli
eas login
eas build:configure
```

Test build:

```bash
eas build --platform android --profile preview
```

Production build:

```bash
eas build --platform android --profile production
```

Google Play publishing requires an eligible developer account and store configuration.

## D. iPhone release

```bash
eas build --platform ios --profile production
```

Apple signing and App Store distribution require an eligible Apple Developer account.

## E. Final security gate

Do not publish until:
- Supabase RLS has been reviewed and tested
- Storage policies are restrictive
- Service-role secrets are never shipped to the client
- Notification creation is trusted/server-side
- Report/block flows are connected to moderation
- Account recovery and deletion work
- Rate limits are implemented
- User-generated content is moderated
- Privacy policy and terms are available
- Backups and monitoring are configured

## F. Store assets

Prepare:
- App icon
- Splash screen
- Android screenshots
- iPhone screenshots
- Web preview
- App description
- Privacy policy URL
- Terms URL
- Support contact
- Age/content rating information

## G. Versioning

For the first public release use:
- Version: 1.0.0
- Android versionCode: 1
- iOS buildNumber: 1

Increment the platform build number for subsequent submissions.

## Important

This kit prepares the project for release, but a real store submission requires developer accounts, signing, store metadata, testing and acceptance by the relevant platform.
