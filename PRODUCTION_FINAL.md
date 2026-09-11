# Pixora — Final Production Handoff

Pixora is now packaged as the final source/release handoff.

## Included
- Expo React Native application
- Android, iOS and Web configuration
- Supabase integration
- Authentication
- Profiles
- Posts and image uploads
- Likes
- Comments
- Saved posts
- Follows
- Search and Explore
- Notifications
- Report/block services
- Release build scripts
- Production checklist
- Database hardening migration

## Local verification

```bash
npm install
npm run typecheck
npx expo start
```

Web:

```bash
npm run web
```

Web production export:

```bash
npm run build:web
```

## Native release

```bash
npm install -g eas-cli
eas login
eas build --platform android --profile preview
eas build --platform android --profile production
eas build --platform ios --profile production
```

## Before publishing

1. Configure the production Supabase URL and anonymous/publishable key.
2. Never place a Supabase service-role key in the Expo application.
3. Apply and test database RLS policies.
4. Apply the release hardening migration.
5. Test Storage policies.
6. Test authentication recovery and email verification.
7. Test report/block and moderation workflows.
8. Test account deletion.
9. Add privacy policy and terms.
10. Test on physical Android and iPhone devices.
11. Test the web build on major browsers.
12. Create final store screenshots and metadata.

## Important

A source package cannot itself prove store acceptance or production reliability. Those require real-device testing, a production backend, platform signing and the relevant store review process.
