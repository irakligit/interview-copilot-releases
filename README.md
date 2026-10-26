# Interview Copilot — Releases

Public download host for the Interview Copilot (PointerAI) desktop app installers.

No source code lives here — this repo exists only so the website can link to a
publicly downloadable `.dmg`/`.exe`, since the real source repo is private and
private-repo release assets aren't downloadable by anonymous visitors.

## Publishing a new release

1. Build a signed, notarized installer in the main repo:
   ```
   npm run dist:mac   # produces dist/Interview Copilot-<version>-arm64.dmg
   ```
2. Create a release here and upload the file as a release asset:
   ```
   gh release create v<version> "path/to/Interview Copilot-<version>-arm64.dmg" \
     --repo irakligit/interview-copilot-releases \
     --title "v<version>" \
     --notes "..."
   ```
3. The direct download URL (no GitHub page shown, downloads immediately) is:
   ```
   https://github.com/irakligit/interview-copilot-releases/releases/download/v<version>/Interview%20Copilot-<version>-arm64.dmg
   ```
   Set that as `NEXT_PUBLIC_MAC_DOWNLOAD_URL` in pointerai-web's production env (Vercel).
