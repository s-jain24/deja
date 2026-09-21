# Deja — Gemini edition

## Deploy
1. Create a GitHub repository and upload the CONTENTS of this folder. index.html, api/, fonts/, and vercel.json must be at the repository root.
2. In Vercel choose Add New Project and import that repository.
3. Framework preset: Other. No build command. Output directory: leave default (root).
4. Add environment variable GEMINI_API_KEY with your Google AI Studio key.
5. Deploy. If adding the key after deployment, redeploy.
6. Open the deployed site, add one outfit photo, wait for analysis, and upload an inspiration photo.

Optional GEMINI_MODEL defaults to gemini-2.5-flash. Model access and free-tier quotas depend on your Google project.

## Behavior
Original design and local wardrobe storage are preserved. Gemini analyzes wardrobe photos once and ranks outfits against the inspiration. Photos are sent through the Vercel function to Google for analysis; the app does not store them on the server. Browser IndexedDB retains photos locally. Previously uploaded photos from Claude will need uploading again on this new site.

The sample demo remains available without API access. Without a configured key, written-description matching remains available. API quota/errors are shown honestly.

## Verification and limits
Client/server syntax and mocked endpoint checks pass. Live Gemini calls and Vercel deployment require the owner's key and have not yet been tested. Endpoint rate limiting is best-effort per running instance, not a durable account-wide limit. This is a hackathon prototype, without user authentication; use Vercel access protection for a private demo if available. Do not commit API keys. Google free-tier data handling terms apply to submitted photos.
