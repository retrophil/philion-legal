# High Infamy legal pages — release checklist

**Status (18 November 2026): REVIEW DRAFT ONLY — DO NOT PUBLISH OR ENTER ITS URL IN GOOGLE PLAY YET.**

The HTML pages in this branch are intentionally marked as drafts with `noindex`. GitHub Pages is configured to publish the `main` branch, so these changes are **not live** until merged.

## Verified against source

- Client signs in with Firebase Authentication; both anonymous and email-based auth are present.
- Player documents in Cloud Firestore include names, avatars, support IDs, progress, currency, owned items, jobs and game results.
- The backend populates publicly readable leaderboard and activity-feed documents using player name/avatar/activity.
- Planned IAP uses Unity IAP, Google Play/Apple and server-side Firebase purchase fulfilment; live IAP remains disabled.
- A complete account-deletion client UI or backend cascade was **not found** in the inspected Unity and Firebase GitHub repositories.
- No final advertising SDK/integration was positively identified from the inspected GitHub source. The current local Unity project/release build may be newer.

## Blockers before merging a final privacy policy into `main`

1. Identify ALL advertising, attribution, diagnostics and analytics SDKs that will ship in the **actual Android release build**. Record identifiers, collection, sharing, consent and links to vendor policies. Update section 6 accordingly.
2. Confirm the app's account sign-in methods, player profile data, leaderboard visibility, Firebase products, and local diagnostic data processing against the final build.
3. Build an in-app **Delete account** entry point plus a secured server-side deletion service, verify owner authentication and remove all account-associated Firestore data, public leaderboard/activity records and the Firebase Auth user. Define legal retention exceptions and response times.
4. Test the email-based external deletion request channel, including ability to identify a player securely and fulfil a deletion request without requiring game reinstall.
5. Confirm purchase integration and transaction/receipt retention practices at launch (or state clearly that paid bundles are not available in this version).
6. Replace all `Pre-release draft` banners and release-review placeholders with factually accurate final disclosures. Set an effective date; decide whether to allow robots indexing.
7. Test deployed Pages URL in a private/incognito browser, globally accessible with HTTPS. Then link the exact `/philion-legal/privacy.html` URL in Play Console and in the game UI.
8. Complete Google Play Data safety form consistently with the final privacy policy and all third-party SDKs.
9. Complete Google Play account deletion URL using the exact `/philion-legal/delete-account.html` path **only after** the process actually works.

## Policy references

- Google Play User Data: https://support.google.com/googleplay/android-developer/answer/10144311
- Google Play account deletion: https://support.google.com/googleplay/android-developer/answer/13327111
- Google Play privacy policy listing requirements: https://support.google.com/googleplay/android-developer/answer/9859455

**Important:** This checklist is not legal advice. The published disclosures must be reviewed and maintained by the developer.
