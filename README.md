# Mod Uploader by Nevermore

A standalone Windows tool for publishing **Project Zomboid** mods to Steam Workshop without launching the game.

![Mod Uploader](assets/overview.png)

## Download

Open this repository's **Releases** page and download `ModUploader.exe`. No installer or ZIP is required. `SHA256SUMS.txt` is provided alongside each release.

This is a **closed-source release repository**. Application source code and development history are not included. GitHub's automatically generated “Source code” downloads contain this repository's documentation, not the application source. Download the attached EXE to use the tool.

## Features

- Dark interface with a choice to update an existing mod or create a new Workshop listing.
- Dev-project selection, configurable preparation scripts and file-integrity checks.
- Steam BBCode changelog editor.
- Independent description and preview toggles for existing listings. When off, those values are preserved in Steam.
- New listing title, description, preview and visibility, with private visibility by default.
- Saved Workshop IDs, progress feedback and detailed error logs.
- Uses your running Steam account and verifies ownership before updates.

## Requirements

- Windows x64 with .NET Framework 4.8 or newer.
- An installed Steam copy of Project Zomboid and the Steam client running under your own account. The game can stay closed.
- Your mod's dev files and Workshop folder. Set paths in **Проект и пути**.
- PowerShell 7 when using a preparation script. Java, Python or other build tools are only needed if your chosen project's script requires them.

The current UI is in Russian. The tool is for Project Zomboid, not a universal uploader for unrelated Steam games.

## Use

Choose **Обновить мод** to select an existing project and enter a changelog. **Подготовить файлы** only prepares the local Workshop folder; **Опубликовать** also sends it to Steam.

Choose **Новая публикация** to prepare a local draft from your dev folder. Fill in the listing details and use **Создать и опубликовать** to allocate a Workshop ID and upload. If Steam requests the Workshop legal agreement, accept it on the item page. If creation times out with an uncertain result, inspect your Workshop items before retrying; the tool blocks blind duplicate creation.

The description/preview switches apply to updates of existing items. A new listing requires these fields. Avoid editing payload files while publishing.

## Signature and local data

The EXE is Authenticode-signed with a **self-signed Nevermore certificate** and a timestamp. This provides a verifiable signature under that key; it is not a publicly trusted publisher certificate. Windows/SmartScreen warnings may still appear. No certificate installation or changes to Windows trust settings are required by this tool.

No Steam credentials or signing private keys are embedded in the EXE. Settings and logs are stored under `%LOCALAPPDATA%/WorkshopPublisher`. Mod signing keys remain part of each author's own build setup. Branding and support links do not restrict uploads to the tool author's account.

## Status

Offline checks, UI state checks, cryptographic signature verification and read-only Steam connectivity have passed. Actual Steam item creation and update were not exercised during automated validation.

## Author and support

[Nevermore on Steam](https://steamcommunity.com/profiles/76561198179591723/) · [Buy Me a Coffee](https://buymeacoffee.com/nnevermore)
