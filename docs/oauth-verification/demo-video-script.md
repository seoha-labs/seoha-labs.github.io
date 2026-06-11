# Demo Video Script (for Google Verification Center)

Google reviewers require an English-language video showing the full OAuth
flow and how each sensitive scope is actually used. Upload to YouTube as
**Unlisted** and paste the link in the verification form.

## Preparation (before recording)

- Set Chrome UI language and the Google account language to **English**
  (the consent screen must appear in English).
- Use the **production OAuth client** (the same client ID as the published
  extension), not a test client.
- Have a CLOVA Note account with at least one transcription result ready.
- Have a second email account open (recipient inbox) to prove delivery.
- Sign out of the Google account in the extension beforehand so the video
  captures the full consent flow.
- Record the entire browser window; do not cut or speed up the OAuth part.

## Recording sequence

1. **Show the extension identity** (~10s)
   - Open `chrome://extensions`, show Clova2Mail installed, its name and ID.
   - Optionally show the Chrome Web Store listing page.

2. **Start OAuth sign-in** (~30s)
   - Open the extension and click the sign-in button.
   - When the Google consent screen appears, pause briefly so the reviewer
     can read: the **app name (Clova2Mail)**, the requested permission
     "Send email on your behalf" (`gmail.send`), and the account email.
   - Make sure the URL bar with the `client_id` parameter is visible at
     least once.
   - Click through and complete consent.

3. **Demonstrate gmail.send usage** (~60s)
   - Open CLOVA Note and show a transcription result.
   - Use the extension to compose an email from that transcript
     (show the generated subject/body and the recipient field).
   - Click **Send** — narrate or caption that this is the explicit user
     action that triggers `gmail.send`.

4. **Prove the email was sent** (~20s)
   - Switch to the recipient inbox and open the received email, showing
     the sender address matches the account that granted consent.

5. **Demonstrate userinfo.email usage** (~10s)
   - Show where the extension displays the connected account's email
     address (e.g., settings or popup header).

## Checklist before uploading

- [ ] Consent screen shown in English
- [ ] App name on consent screen matches the OAuth consent screen config
- [ ] `client_id` visible in the URL during OAuth
- [ ] Full flow uncut: sign-in -> consent -> feature use -> email delivered
- [ ] Each requested scope demonstrated in actual use
- [ ] Uploaded as YouTube Unlisted, link copied
