# Scope Justification (for Google Verification Center)

Copy-paste the texts below into the verification request form.

## App functionality summary (if asked)

> Clova2Mail is a Chrome extension that integrates Naver CLOVA Note (a
> speech-to-text transcription service) with Gmail. Users select a
> transcription result in CLOVA Note, and the extension composes an email
> from it and sends it through the user's Gmail account when the user
> explicitly clicks "Send".

## Justification for `https://www.googleapis.com/auth/gmail.send`

> Clova2Mail's core and only feature is sending emails composed from the
> user's CLOVA Note transcription results. When the user selects a
> transcript and clicks "Send" in the extension, the extension creates an
> email message from that content and sends it via the Gmail API on the
> user's behalf. Sending happens only as a direct result of an explicit
> user action.
>
> We request `gmail.send` because it is the narrowest scope that allows
> sending email. We deliberately do not request `gmail.compose`,
> `gmail.modify`, or `gmail.readonly`: the extension never reads, modifies,
> deletes, or stores any existing Gmail messages.
>
> All processing happens locally in the user's browser. The extension has
> no backend server, and no Gmail data or user data is transmitted to or
> stored on any external server. Google user data is not used for any
> purpose other than this user-facing feature, in compliance with the
> Google API Services User Data Policy, including the Limited Use
> requirements.

## Justification for `https://www.googleapis.com/auth/userinfo.email`

> The extension uses the signed-in user's email address solely to display
> which Google account is connected and will be used as the sender, so the
> user can confirm they are sending from the intended account. The address
> is not stored on any server or shared with any third party.
