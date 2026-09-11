# Pixora — Milestone 8: Security, Performance & Reliability

Implemented:
- Input sanitisation for captions/comments/search
- Upload size protection
- Post-upload cleanup when database insertion fails
- Feed pagination support
- Report-post and block/unblock services
- More defensive authentication checks
- Reduced feed payload and bounded result sets

## Security work still required before public launch

1. Apply strict Supabase RLS policies to every table.
2. Prevent clients from creating their own notifications; use trusted database triggers or Edge Functions.
3. Use private storage and signed URLs where appropriate.
4. Add server-side rate limiting.
5. Add moderation and abuse detection.
6. Add email verification/password recovery.
7. Add account deletion.
8. Review database indexes and query plans.
9. Add production error monitoring.
10. Test with real Android, iOS and web builds.

## Performance

The feed now supports bounded pagination through `limit` and `offset`. The next UI pass should connect this to FlatList `onEndReached`, cache images, and avoid loading unnecessary profile data.

## Important

Security cannot be guaranteed by client-side code alone. Supabase RLS, database constraints, server-side functions and storage policies must be configured correctly before deployment.
