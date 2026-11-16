# Use Saved Library by Transformaiton.com

After [install](INSTALL.md), one request is enough.

## Start a run

Open a new chat with Claude Code or Codex and write one of these:

- `Sort my saved posts.`
- `What did I save on Instagram?`
- `Build my Saved Library.`
- `/saved-library`

With ChatGPT, attach `instagram-saved-....json` and `chatgpt/saved-library-chatgpt.py`, then paste `chatgpt/prompt.txt`. See [Install](INSTALL.md).

The assistant tells you what it is about to do, then asks you to confirm you are logged in to Instagram on this computer.

## What you do, and what it does

**If Claude in Chrome is connected**, you only stay logged in. The assistant reads Saved itself. About 4 to 6 minutes for 1,000 posts. It will say things like "Read 340 so far".

**If there is no browser connection**, it opens `start.html`.

1. Drag the blue **My saved posts** button to the bookmarks bar. Show the bar with Ctrl+Shift+B (Mac: Cmd+Shift+B).
2. Go to [instagram.com](https://www.instagram.com/) while logged in, and click the bookmark.
3. Wait until the panel says **Ready**. The file `instagram-saved-YYYY-MM-DD.json` is in Downloads.
4. Tell the assistant `ready`.

It then sorts the posts, writes one sentence for each, and opens `library.html`.

A short trial, if you want to see the shape before a full library, is to ask for a run of the first 200 posts. The assistant passes `--limit 200`.

## What the page gives you

The page is `saved-library-output/YYYY-MM-DD/library.html` in the folder where the chat was working. Open it any time, including offline.

| What you get | What it looks like |
|---|---|
| A wall of every saved post that breaks apart onto a bookcase | About 6 seconds. You can film it and share it |
| Search across every saved post | Matching books light up on the bookcase |
| Worth doing | Up to 15 practical actions, with a checkmark that stays on this computer |
| A shelf for each subject | One sentence per post, and a link to the original |
| A share card | An image ready for a story |

Click **Replay the sort** to watch the wall again. Click **Share card**, then **Download image**, for the story image. Click a shelf name to jump to those posts. Check off an action when you have done it.

## How to read the list

The assistant closes with:

1. How many saved posts, how many shelves, and the biggest shelf.
2. The first five things worth doing.
3. The path to `library.html`.
4. How to film the sort, or download the share card.
5. A reminder that the summaries were written by AI.

Scores, if you want to know how the list was chosen:

- **3**: specific, and you could do it in under an hour.
- **2**: worth doing, but it takes longer or needs the right moment.
- **1**: interesting, nothing to do.
- **0**: entertainment, or the caption was empty.

Only scores 2 and 3 appear under Worth doing.

## Examples

A bakery owner who saves a lot of marketing ideas might see shelves such as Offers, Content ideas, Email, and Local ads, then a Worth doing line like "Rewrite this week's offer as a three-line caption and post it Thursday."

Useful follow-ups in the same chat:

- "Which of these could I do this week?"
- "Read me only the email shelf."
- "I already did the first two. What is next?"

The page itself is the record. The chat does not have to stay open.

## If something stops

| What you see | What to do |
|---|---|
| Not logged in | Log in at instagram.com in the same browser, then try again |
| Instagram asked to slow down | Wait 10 minutes and run again. Do not start a second read |
| No saved posts | Confirm it is the account you meant |
| The bookmark does nothing | You may have dragged the page instead of the blue button, or the browser blocks bookmark code. Details are in `reference/collect.md` |
| The file did not download | Check the downloads bar. Tell the assistant the full path and it will pass `--src` |
| Safari will not take the drag | Open `start.html` in Chrome |

More than 3,000 saved posts: the read stops at 3,000 unless you set `window.SAVED_LIMIT` first. See `reference/collect.md`.

## A note on the summaries

The assistant reads the caption, not the words spoken in a reel. A deleted post, or a post whose account turned private, can show up with no image, and its link may not open. Before you spend money or change an offer, open the original post.
