# Pixora Runtime Test

The release kit was statically reviewed and corrected for the main integration issues found in the accumulated source:

- Added `package.json` so the project has an npm manifest.
- Aligned comments with the database `content` column.
- Aligned notifications with `recipient_id` and `is_read`.
- Fixed the tab layout import and hidden secondary routes so the main tab bar stays compact.

I could not complete `npm install` in this execution environment because the package download did not finish within the available runtime.

On a computer with internet access, run:

```bash
npm install
npm run typecheck
npx expo start
```

Then test on Android/iOS/Web.
