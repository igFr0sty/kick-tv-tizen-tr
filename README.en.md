# Kick TV TR

[Türkçe](README.md) · **English**

An unofficial Kick client for Samsung Smart TVs running Tizen. It adds a Following screen and Turkish support to [Kick TV by corekill](https://github.com/corekill/kick-tv-tizen).

> This project is not affiliated with or endorsed by Kick, 7TV or Samsung. It is a community fork.

## What this fork adds

- **Following screen:** opens first and shows only channels that are live, sorted by viewer count.
- **Account sync (optional):** loads your follows from your Kick account and refreshes them automatically.
- **Local list:** without an account, add channels yourself with **+ Follow**.
- **Turkish interface:** Turkish when the TV language is Turkish, English otherwise.
- **Turkish browse filter:** added to the language options and selected by default on Turkish TVs.
- **Automatic focus:** the first live channel is selected on launch.

Playback, quality selection, search, live chat and 7TV emotes come from the original project.

## Differences from the original

- It installs as a separate app (`KckTvTr001.KickTVTR`), so it can sit next to the original.
- The original's account sign-in, usage counter and diagnostics are removed, because they use the original author's server. This fork does not talk to any server of its own.

## Install

1. Open **Apps** on the TV, press **123**, and enter `12345`.
2. Turn on **Developer Mode** and set **Host PC IP** to your computer's local IP address.
3. Restart the TV by holding the power button until the Samsung logo appears.
4. Download `KickTV.wgt` from [Releases](../../releases/latest).
5. In [Apps2Samsung](https://github.com/Apps2Samsung/Apps2Samsung), choose **Custom WGT File**, select the file, select your TV, and press **Download & Install**.

## Connect your Kick account (optional)

**Read this first.** Kick's official API has no followed-channels list ([open request](https://github.com/KickEngineering/KickDevDocs/issues/87)). Account sync therefore uses an undocumented Kick address and your browser session key.

- The session key gives full access to your Kick account. Never share it, and never paste it into a website or send it to anyone.
- The key is stored as plain text on your TV. It is sent only to `kick.com`.
- Kick can change this address at any time, and sync would stop until the app is updated.
- This is not a method Kick officially supports. Use it at your own risk.

To connect:

1. Sign in on kick.com in a desktop browser.
2. Press `F12`, then go to **Application → Cookies → https://kick.com**.
3. Copy the **Value** of `session_token`.
4. In the app, press **Edit**, enter the key in **Kick session key**, and press **Connect account**.

A USB keyboard makes this much easier. Before giving the TV to someone else, press **Disconnect**.

## Build

```bash
./scripts/build.sh
```

The package is written to `dist/KickTV.wgt` and must be signed for your TV, which Apps2Samsung does during installation.

## Credits and license

Based on [corekill/kick-tv-tizen](https://github.com/corekill/kick-tv-tizen) by corekill and its contributors. Please support the original project.

MIT License; see [LICENSE](LICENSE). Kick, 7TV and Samsung names and trademarks belong to their owners and are not covered by this license.
