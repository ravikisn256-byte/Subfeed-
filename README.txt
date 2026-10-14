SUBFEED — mobile-friendly YouTube subscriptions-only website
============================================================

WHAT IT DOES
- Google sign-in using OAuth (it never asks for or stores your Google password).
- Reads the signed-in YouTube account's subscriptions.
- Shows recent uploads from subscribed channels only, using each channel's uploads playlist.
- Includes channel uploads such as regular videos, Shorts, and public livestream uploads when present in the uploads playlist.
- Tapping a video opens its standard YouTube URL; Android usually opens the original YouTube app if supported links are enabled.
- Responsive layout for mobile screens.

IMPORTANT LIMITS
- This is an independent website, not an official YouTube product.
- YouTube API quotas apply. If you subscribe to a very large number of channels, loading every channel can use quota and take time.
- This initial version loads the newest page (up to 50 uploads) per subscribed channel, then the Load more button asks for another page across channels.
- YouTube Data API does not guarantee every kind of recommendation or private/restricted item is available. The page intentionally does not use YouTube's recommendation feed, search results, or unrelated channels.
- This is a client-side starter. Do not publish an unrestricted API key. Restrict it to YouTube Data API v3 and your website domain.

SETUP (one-time)
1. Open https://console.cloud.google.com/ and create/select a Google Cloud project.
2. In APIs & Services > Library, enable YouTube Data API v3.
3. In APIs & Services > Credentials, create an API key.
   Restrict the key to YouTube Data API v3 and your deployed website's HTTP referrers.
4. Create an OAuth Client ID of type Web application.
   Add the deployed website origin under Authorized JavaScript origins (for local testing, use a local HTTP server origin).
5. Configure the OAuth consent screen. Add your Google account as a test user while the app is in testing mode.
6. Edit index.html and replace:
   PASTE_YOUTUBE_DATA_API_KEY_HERE
   PASTE_GOOGLE_OAUTH_WEB_CLIENT_ID_HERE
   with your actual credentials.
7. Deploy index.html on an HTTPS static host. OAuth sign-in will not work by simply opening the file as file://.

SECURITY
- Never share your OAuth client secret (this browser app does not need one).
- Keep the API key restricted.
- Sign out revokes the current access token where supported.
- Only grant access on your own device and to the intended website.

OPENING VIDEOS IN THE YOUTUBE APP
The site navigates to https://www.youtube.com/watch?v=VIDEO_ID. On Android, ensure YouTube is installed and supported links are enabled in Android app settings. If Android is configured to open links in a browser, the link may open in the browser instead.

FILES
- index.html: complete website
- README.txt: setup guide
