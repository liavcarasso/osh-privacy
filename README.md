# OSH — Google Play Data Safety form answers

Transcribe these into **Play Console → App content → Data safety**. Answers are
derived from `PRIVACY_POLICY.md`. Two items are judgment calls — flagged ⚠️.

## Section 1 — Overview questions

| Question | Answer |
|---|---|
| Does your app collect or share any of the required user data types? | **Yes** |
| Is all of the user data collected by your app encrypted in transit? | **Yes** (all traffic to Firebase uses TLS) |
| Do you provide a way for users to request that their data be deleted? | **Yes** (in-app *Settings → Delete Account*, plus the deletion web page) |

> Deletion URL to provide: your hosted copy of `account-deletion.html`
> (e.g. `https://liavcarasso.github.io/osh-privacy/account-deletion.html`).

## Section 2 — Data types collected

For **every** row below: **Collected = Yes**, **Shared = No** (other users seeing
your status/earnings inside the app is app functionality, NOT "sharing" with a
third party in Data Safety terms), **Processed ephemerally = No**,
**Required (not optional)** unless noted.

Purposes are limited to **App functionality** and **Account management** for all
rows (no Analytics, no Ads, no third-party sharing).

| Data type (Console category → item) | Collected | Linked to user? | Purpose | Notes |
|---|---|---|---|---|
| Personal info → **Email address** | Yes | Linked | App functionality, Account management | Firebase Auth login |
| Personal info → **Name** | Yes | Linked | App functionality | Display name shown to friends/groups |
| Personal info → **User IDs** | Yes | Linked | App functionality, Account management | Firebase UID + friend code |
| Photos and videos → **Photos** | Yes | Linked | App functionality | **Optional** — only if user uploads a profile photo |
| App activity → **Other user-generated content** | Yes | Linked | App functionality | Shift records, job profiles, monthly stats |
| Device or other IDs → **Device or other IDs** | Yes | Linked | App functionality | Expo/FCM/APNs push token (notifications) |

### ⚠️ Judgment calls — decide before submitting

1. **Earnings figures.** OSH stores earnings the user types in. This is *not*
   payment/banking data, but the Console has **Financial info → Other financial
   info**. Two defensible options:
   - Treat earnings as **App activity / user-generated content** (already listed
     above) — recommended, since they are self-entered tracking numbers, not real
     financial account data.
   - Or additionally declare **Financial info → Other financial info** to be
     maximally conservative. Either is acceptable; pick one and be consistent
     with the privacy policy.

2. **Approximate/precise location.** Answer **No** — OSH does not collect GPS or
   IP-based location (confirmed in privacy policy §2.4).

## Section 3 — Things to answer "No / not collected"

- Location (approximate or precise) — **No**
- Financial info → payment info, purchase history, credit score — **No**
- Health & fitness — **No**
- Messages (emails, SMS, in-app) — **No**
- Contacts — **No**
- Calendar — **No**
- Web browsing history — **No**
- Installed apps / search history — **No**
- Audio (voice/sound recordings) — **No** (RECORD_AUDIO is blocked in the build)

## Section 4 — Security practices

- Data encrypted in transit: **Yes**
- Users can request data deletion: **Yes**
- Committed to Play Families Policy: **No** (target audience is 13+, not children)
- Independent security review: **No** (leave unchecked unless you have one)
