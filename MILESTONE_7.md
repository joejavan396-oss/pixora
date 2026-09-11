# Pixora — Milestone 7

This milestone adds the discovery and social layer:

- Explore feed/grid
- User search
- Rich public profiles
- Follower/following counts
- Follow/unfollow
- Notification history
- Notification read state
- Improved post/profile navigation

## Supabase

The existing database tables `profiles`, `posts`, `follows`, and `notifications` are used.

Before production launch, notification creation should be moved to trusted database triggers or server-side functions so clients cannot forge notifications.

## Remaining production work

- Followers/following list screens
- Report/block UI
- Moderation workflow
- Privacy settings
- Password reset and email verification
- Account deletion
- Pagination
- Image compression/limits
- Push notifications
- Rate limiting
- Private storage/signed URLs
