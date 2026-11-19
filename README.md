# Apple Passwords for Alfred (apw)

Search your Apple Passwords (iCloud Keychain) logins and 2FA codes from Alfred and use them in any app.

## Keywords
- **pw site** – list logins. Add a word to filter accounts: `pw github work`
  - ↩ copy password · ⌘↩ copy username · ⌥↩ copy 2FA code · ⌃↩ paste password into the front app · ⇧↩ open site
- **otp site** – list 2FA codes. ↩ copy · ⌃↩ paste
- **pwauth** – start apw and pair (macOS shows a PIN; enter it in the dialog). `pwauth 123456` also works.

## Prerequisites

- Alfred with Powerpack.
- [Homebrew](https://brew.sh/). Install it first and follow its Terminal instructions to add `brew` to your shell path. Confirm with `brew --version`.
- A browser supported by [apw](https://github.com/bendews/apw), with Apple’s iCloud Passwords extension installed and enabled. Chrome is one option.

## Setup

1. In Terminal, run `brew install bendews/homebrew-tap/apw`.
2. Import the `.alfredworkflow` file into Alfred.
3. In Terminal, run `apw start` and leave that tab open. If automatic browser selection fails and Chrome has the extension, try `apw start --browser chrome`.
4. In Alfred, type `pw example.com` using a site you have saved. If Alfred shows **Connect to Apple Passwords**, press Return, enter the macOS PIN, then repeat the search. Pair again whenever apw restarts.

The workflow checks the standard Homebrew binary paths on Apple Silicon and Intel. If your installation uses a different path, run `command -v apw` in Terminal and enter the result in **Configure Workflow → apw path**.

## Privacy
Passwords are never shown in Alfred's results. They are fetched only when you act on a result, put on the clipboard marked transient/concealed (Alfred's clipboard history skips them), and cleared after `clear_after` seconds unless you copied something else meanwhile. Only site names are remembered, for autocomplete (turn off in Configure Workflow).

## Development disclosure
This workflow was built with help from Claude and updated with OpenAI Codex.
