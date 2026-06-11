# GCP Console Checklist (click-by-click)

Work through these in order. All steps use https://console.cloud.google.com
with the Google account that **owns the GCP project** for Clova2Mail.

## 0. Prerequisite — Search Console domain verification

1. Go to https://search.google.com/search-console
2. Add property -> **URL prefix** -> `https://seoha-labs.github.io/`
3. Choose the **HTML tag** method. The tag is already deployed on the site:
   `sRIt4sf45b1XXyYl94mnMp287YGVUDaQ_cWcX8Cewtc` — just click **Verify**.
4. Must be verified with the same account as the GCP project owner.

## 1. Branding (OAuth consent screen)

Navigation: **APIs & Services -> OAuth consent screen** (newer consoles:
**Google Auth Platform -> Branding**)

- [ ] App name: `Clova2Mail` (must match the name shown in the extension
      and the demo video)
- [ ] User support email: `niceweather94@gmail.com`
- [ ] App logo: upload 120x120 px logo (uploading a logo is what triggers
      brand verification — required anyway for full verification)
- [ ] Application home page: `https://seoha-labs.github.io/clova2-mail/`
- [ ] Application privacy policy link:
      `https://seoha-labs.github.io/clova2-mail/privacy.html`
- [ ] Application terms of service link:
      `https://seoha-labs.github.io/clova2-mail/terms.html`
- [ ] Authorized domains: `seoha-labs.github.io`
      (github.io is on the Public Suffix List, so your subdomain counts as
      your own domain)
- [ ] Developer contact information: `niceweather94@gmail.com`
- [ ] Save

## 2. Data Access (scopes)

Navigation: **Google Auth Platform -> Data Access** (or "Edit app" ->
Scopes step)

- [ ] Add scope `https://www.googleapis.com/auth/userinfo.email`
- [ ] Add scope `https://www.googleapis.com/auth/gmail.send`
      (appears under Gmail API — enable the Gmail API first if it is not
      listed: APIs & Services -> Library -> Gmail API -> Enable)
- [ ] Confirm NO other scopes are listed
- [ ] IMPORTANT: scopes here must exactly match what the extension
      requests in `manifest.json` / `chrome.identity`. Changing scopes
      after submission resets verification — freeze them now.

## 3. Audience / publishing status

Navigation: **Google Auth Platform -> Audience**

- [ ] User type: External
- [ ] Publishing status: click **Publish app** -> confirm
      (status becomes "In production")

## 4. Verification Center — submit

Navigation: **Google Auth Platform -> Verification Center** (or the
"Prepare for verification" banner)

- [ ] Confirm branding info is complete (it pre-checks home page, privacy
      policy, authorized domain ownership)
- [ ] Declare all scopes in use (`gmail.send`, `userinfo.email`)
- [ ] Paste the gmail.send justification from
      `docs/oauth-verification/scope-justification.md`
- [ ] Paste the YouTube Unlisted demo video link
- [ ] Submit and watch `niceweather94@gmail.com` for replies — Google's
      trust & safety team replies by email, often with follow-up questions.
      Typical turnaround: a few days to a few weeks for sensitive scopes.

## Notes

- gmail.send is a **sensitive** (not restricted) scope: no CASA security
  assessment is required as long as the app does not store Gmail data
  server-side. If Google's reply asks about data handling, answer that all
  processing is local in the browser with no backend server.
- Until verification completes, users see the "unverified app" warning;
  the 100-user cap does not apply to apps only using sensitive (non
  restricted) scopes in production, but the warning stays until approval.
- Do NOT change scopes, app name, or the OAuth client while verification
  is pending — it restarts the review.
