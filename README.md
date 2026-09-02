# WII-U-RPC

The definitive way to display your Wii U games in Discord. 🎮

[![Wails](https://img.shields.io/badge/built%20with-Wails-red)](https://wails.io)
[![SolidJS](https://img.shields.io/badge/frontend-SolidJS-blue)](https://solidjs.com)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-lightgrey)]()

## Introduction

WII-U-RPC is a Wails app for Windows and macOS that lets you share what you're
playing on your Wii U to Discord as a proper Rich Presence, just like a PC game.

Pick your game from the list, set a custom status, and your Discord profile
shows it off — big cover art, game title, and whatever status message you
want, all updated live.

Built with [Wails](https://wails.io) (Go + native WebView) and
[SolidJS](https://solidjs.com) for the frontend.

![WII-U-RPC's design](https://i.imgur.com/FRbQwzC.png)

> This project is a fork of [Da532/NS-RPC](https://github.com/Da532/NS-RPC)
> (originally built for the Nintendo Switch), re-tooled for the Wii U library
> by [LaxyDev64](https://github.com/LaxyDev64) / Lax Studios. All credit for
> the original app architecture goes to Da532 — this fork just swaps the
> game catalog, branding, and Discord app over to Wii U.

### With WII-U-RPC you can...

- Display that you're playing on your Wii U across all of Discord
- Pick from a growing list of Wii U games, complete with cover art
- Set a custom status message so people know exactly what you're up to
- Pin your favourite games into a quick-access list
- Reconnect to Discord with one click if it ever drops

## Prerequisites

All you need is the [Discord app](https://discord.com/download) installed
and running on the same machine.

Users on Windows 10 or earlier *may* run into issues due to Wails' use of
**Microsoft WebView2**. If the app won't launch, install WebView2 from
[Microsoft's site](https://developer.microsoft.com/microsoft-edge/webview2/)
and try again.

## Installing

Grab the latest build for Windows or macOS from the
[Releases](https://github.com/LaxyDev64/WII-U-RPC/releases) page.

No release yet? See [Building from source](#building-from-source) below.

## Adding or updating games

The game list lives in [`games.json`](./games.json) at the root of this repo
and is pulled live by the app, so no rebuild is needed to add a title —
just:

1. Add an entry with a `title` and an `img` key
2. Upload matching cover art to this app's **Rich Presence → Art Assets** in
   the [Discord Developer Portal](https://discord.com/developers/applications),
   using the exact same string as the `img` value
3. Commit and push — the app fetches the updated list next time it starts

## Building from source

```bash
git clone https://github.com/LaxyDev64/WII-U-RPC.git
cd WII-U-RPC

# install the Wails CLI if you don't have it
go install github.com/wailsapp/wails/v2/cmd/wails@latest

wails build
```

You'll need your own Discord Application ID — create one at the
[Developer Portal](https://discord.com/developers/applications) and drop it
into the `clientID` constant in `app.go`.

## Rewrite history

Long time NS-RPC users may recognise this app's bones! The original codebase
was an Electron app — Da532's first JavaScript project. It was later rewritten
in Wails (Go + native WebView) with a SolidJS frontend for speed and a much
lighter footprint. This Wii U fork builds on that rewrite rather than the
original Electron version.

## Anything else?

Got a feature suggestion, found a bug, or want to contribute a Wii U game to
the list? Open an [issue](https://github.com/LaxyDev64/WII-U-RPC/issues) or a
pull request.

Have a good one!

Not as of yet. If you have feature suggestions or need support, head over to this handy [Discord server](https://discord.gg/StDcdMu) and talk to us.

Have a good one!
