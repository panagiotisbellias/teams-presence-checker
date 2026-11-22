# Teams Presence Checker

A static, read-only Microsoft Teams presence checker for personal use.

## Features
- Microsoft sign-in with MSAL Browser.
- Reads `GET https://graph.microsoft.com/v1.0/me/presence`.
- Requests delegated `Presence.Read` only.
- Refreshes every 15 minutes while the page is open, plus manual refresh.
- Stores the Entra client and tenant IDs in this browser's local storage, not in the repository.

## Entra app registration
- Platform: Single-page application (SPA).
- Redirect URI: `https://panagiotisbellias.github.io/teams-presence-checker/`
- API permission: Microsoft Graph > Delegated > `Presence.Read`.
- Do not add a client secret or `Presence.ReadWrite`.

## Publish with GitHub Pages
1. Upload all files in this folder to the repository root.
2. In repository Settings > Pages, select Deploy from a branch.
3. Select branch `main` and folder `/ (root)`, then Save.
4. Wait for the Pages deployment to complete.

## First use
1. Open the GitHub Pages URL.
2. Enter the Application (client) ID and Directory (tenant) ID from Entra.
3. Select Save configuration.
4. Sign in with the same work account used in Graph Explorer.

The IDs are identifiers, not credentials, but this app keeps them out of the public source repository by asking for them on the device.

## Limitations
- This is a browser shortcut, not a background Android service.
- The 15-minute refresh runs only while the page is open and active. Android may suspend browser tabs.
- MSAL caches authentication data in browser local storage. Use only on a device you control, and sign out on shared devices.
