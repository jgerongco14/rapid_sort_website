# Privacy and Security Notes for Website and Google Play

## Purpose

This document summarizes what the app appears to collect or process based on the current codebase and what you should prepare before publishing or marketing the app.

This is a product and implementation summary, not legal advice. You should still review it with your legal or compliance contact before publishing a Privacy Policy or Play Store Data safety form.

## Data the App Appears to Handle

### Account and identity data
Based on the authentication and user sync code, the app may process:
- Google account sign-in
- Display name
- Email address
- Profile photo URL
- Authentication provider
- Firebase user ID

### Gameplay and progress data
The app stores and/or syncs:
- Level
- XP
- Coins
- High score or streak points
- Collected words
- Claimed rewards
- Inventory and card quantities
- Theme/customization choices
- Daily chest state

### Social or community data
The app may publish or read:
- Leaderboard display name
- Leaderboard level
- Leaderboard score or streak points

### Support data
When submitting a support ticket, the app may collect:
- Subject
- Description
- Issue type
- Player ID
- App version
- Device model
- Operating system

### Device and operational signals
The app also references:
- Connectivity status
- Device information APIs
- Local storage through SharedPreferences

### Ads-related data
The app integrates Google Mobile Ads. Depending on your ad configuration and SDK behavior, Google AdMob may process device and ad-related identifiers or usage signals. You should verify the exact Play Store Data safety disclosures required for your final production configuration.

## What This Means for the Website

Your website should at minimum link to:
- Privacy Policy
- Terms of Use
- Support / Contact page
- Account deletion or data request instructions

## Recommended Privacy Policy Sections

### 1. Information we collect
Include:
- Account information from Google sign-in
- Gameplay progress and cloud save data
- Leaderboard profile and score data
- Support ticket details
- Device/app diagnostic details when support is requested

### 2. How we use information
Include:
- To authenticate users
- To save and restore progress
- To power leaderboard features
- To respond to support requests
- To improve app stability and user experience
- To serve ads if ads are enabled

### 3. Data storage
Include:
- Local device storage for settings and gameplay state
- Firebase services for account, leaderboard, support, and cloud data

### 4. Third-party services
List at least:
- Firebase Authentication
- Cloud Firestore
- Google Sign-In
- Google Mobile Ads / AdMob

### 5. User rights
Include:
- How users can request support
- How users can delete their account
- How users can request data deletion or review

### 6. Children
State clearly whether the app is directed to children, general audience, or mixed audience. This affects your Play Store disclosures and ad handling requirements.

## Recommended Security Statement for the Website

You can safely say:
- User progress and account-related features are handled through trusted cloud services
- Access to support tools and account-linked features is tied to authenticated user sessions
- The team reviews and improves app security and stability over time

Avoid saying:
- End-to-end encrypted
- Fully anonymous
- No data collected
- Military-grade security

unless you can verify those claims technically and legally.

## Google Play Preparation Checklist

### Required or strongly recommended
- Privacy Policy URL
- Data safety form completed accurately
- Account deletion path if the app supports account creation/sign-in
- Clear contact/support method
- Signed release build

### Strongly recommended website/legal pages
- Privacy Policy
- Terms of Service
- Support page
- Delete Account / Data Removal page

## Account Deletion Requirement

Because the app includes account functionality and account deletion logic, you should provide:
- In-app delete account access
- A public webpage explaining how to request account deletion or confirming in-app deletion availability

Suggested website copy:

`You can delete your account from the in-app Account Settings screen. If you need help, contact support and include your player email or account details.`

## Data Safety Form Guidance

Before filling Google Play Data safety, verify at least these categories:
- Personal info
- App activity
- Device or other IDs
- User-generated content
- Diagnostics

You should answer based on the final production build and your real backend behavior, not only current UI intentions.

## Security Improvements Recommended Before Release

- Review Firestore security rules for leaderboard, user data, and support tickets
- Restrict write access to only the authenticated user or admins where appropriate
- Validate support ticket inputs server-side where possible
- Minimize stored personal data to only what the feature needs
- Document retention and deletion practices
- Confirm that support ticket data is only readable by authorized staff
- Review ad configuration and consent flow for the target regions

## Suggested Public-Facing Privacy Summary

`PANTS: Rapid Sort may use account information, gameplay progress, leaderboard data, and support details to operate core features such as sign-in, cloud save, support, and rankings. The app may also use trusted third-party services such as Firebase and AdMob. For full details, please review the Privacy Policy.`

## Codebase Signals Used for This Summary

- `lib/services/auth_service.dart`
- `lib/services/data_manager.dart`
- `lib/services/leaderboard_service.dart`
- `lib/services/support_ticket_service.dart`
- `lib/screens/profile_screen.dart`
- `lib/screens/support_ticket_screen.dart`
- `lib/services/ad_service.dart`

## Next Recommended Deliverables

If you want, the next useful step is to create:
- a real Privacy Policy page draft
- a Terms of Use draft
- a website homepage copy draft
- a simple Delete Account page draft
