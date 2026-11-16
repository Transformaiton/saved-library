# Reading from Instagram: exactly what happens

## What the code does
`scripts/collector.js` runs inside an instagram.com tab where the person is already logged in. It asks the site for the list `api/v1/feed/saved/posts`, the same list Instagram itself loads when you scroll the Saved folder, page after page (about 21 posts per page), with a random pause of 2.5 to 5.5 seconds between pages. It then shrinks each post's image to 120 by 150 pixels, so the library still works offline, and downloads one JSON file.

## What it does not do
- There is no request that changes anything: only read requests (GET). No like, save, unsave, follow, comment, or message.
- It does not click any Instagram button. The download itself is a link the code creates.
- It does not send the information to any server. The code contains no address other than Instagram and Instagram's image servers.
- It does not read messages, followers, the password, or cookies.

## What is in the file
For each post: an id, a link, a kind (reel, photo, carousel), the creator's username, whether the account is private, the caption (up to 2,200 characters), the date posted, likes, comments, plays, duration, and a small image. The order is the save order: the first row is the one saved most recently.

## The bookmark (start.html)
- The button on the page is a bookmark that contains this same code. Drag it to the bookmarks bar, and click it while you are on instagram.com.
- **Safari:** dragging does not always work. In the Develop menu, turn on "Allow JavaScript from Smart Search field". It is easier to open this page in Chrome.
- **Firefox:** it works. If nothing happens, check that the bookmark was saved with an address that starts with `javascript:`.
- **A workplace that blocks bookmarks containing code:** use Claude with the Chrome extension, or use another computer.
- **Phone:** not supported.

## More than 3,000 saved posts
Before the run, in the Instagram tab: `window.SAVED_LIMIT = 6000` (on the browser-connection path, add that line at the start of the code). Above 3,000 the run is long, and you should say so.

## If Instagram asks to slow down
The code waits one minute and tries again, up to three times, then stops with `rate_limited`. Do not shorten the pauses and do not run two reads at once. Wait 10 minutes and run again from the start.

## The path with no extension and no bookmark
Instagram's official download ("Download your information" in Settings, JSON format) includes the saved list, but only a link and a creator name, with no captions. You cannot summarize posts or build shelves by subject from that, so this skill does not use it.
