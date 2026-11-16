# Install Saved Library by Transformaiton.com

Saved Library reads the posts you have already saved on Instagram, sorts them onto shelves, and builds a page on your computer. You need one assistant you already use: Claude Code, Codex, or ChatGPT.

## What you need

- A computer. This does not run on a phone.
- A desktop browser logged in to Instagram. Chrome is the simplest. Edge, Brave, Arc, and Firefox also work.
- Python 3.9 or newer. On a Mac it is usually already there. Check with `python3 --version`. On Windows, `py --version`. If it is missing, install it from [python.org](https://www.python.org/downloads/) and come back. Nothing else has to be installed: the scripts use only Python's standard library.
- One of:
  - [Claude Code](https://claude.com/claude-code), on a Claude Pro plan or higher
  - [Codex](https://chatgpt.com/codex), included with paid ChatGPT plans
  - ChatGPT with file upload. The free plan has a daily limit.

On a Mac, the first Python run can ask to install the command-line developer tools, and the browser can ask for access to the Downloads folder. Approve both.

## Claude Code

1. Install [Claude Code](https://claude.com/claude-code).
2. Open it and paste this:

> Install the skill "Saved Library by Transformaiton.com" from https://github.com/Transformaiton/saved-library : download the repo into your skills folder, ~/.claude/skills/saved-library (if git is not installed, download the repository zip and extract it there). Then read SKILL.md in that folder and follow it to sort my saved Instagram posts. Talk to me in English.

3. If it asks for permission to download or to run a command, approve it.
4. If you also have the Claude in Chrome extension, the skill can read Saved itself. Without the extension, it opens `start.html` and you drag one bookmark. See [Usage](USAGE.md).

The next time, open a new chat and write `Sort my saved posts`.

## Codex

Paste the same request, with Codex's skills folder:

> Install the skill "Saved Library by Transformaiton.com" from https://github.com/Transformaiton/saved-library : download the repo into your skills folder, ~/.agents/skills/saved-library (if git is not installed, download the repository zip and extract it there). Then read SKILL.md in that folder and follow it to sort my saved Instagram posts. Talk to me in English.

Approve the download and any command it asks to run. Codex has no browser extension, so the first run uses the bookmark on `start.html`.

The next time, open a new chat and write `Sort my saved posts`.

## ChatGPT only

This path does not install a skill. You attach two files to a new chat.

1. On GitHub, open [Transformaiton/saved-library](https://github.com/Transformaiton/saved-library), choose **Code**, then **Download ZIP**. Double-click the zip. You get a `saved-library` folder.
2. Open `start.html` in that folder and read your saved posts with the button (steps 1 and 2 on the page). A file named `instagram-saved-....json` lands in Downloads.
3. Start a new ChatGPT chat. Attach that JSON file and `chatgpt/saved-library-chatgpt.py`. Paste the prompt from the button on `start.html`, or the same text from `chatgpt/prompt.txt`.
4. ChatGPT runs the steps and gives you `library.html` to download. Open that file in your browser. It works later with no network.

## Install by hand

If you prefer to place the files yourself:

```bash
git clone https://github.com/Transformaiton/saved-library.git
```

- Claude Code: move the folder to `~/.claude/skills/saved-library`
- Codex: move the folder to `~/.agents/skills/saved-library`

Then open a new chat and write `Sort my saved posts`.

## Confirm it is in place

The folder should contain `SKILL.md`, `start.html`, `scripts/`, `assets/`, `reference/`, and `chatgpt/`. You do not need an API key.
