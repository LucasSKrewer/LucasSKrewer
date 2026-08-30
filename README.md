<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/banner-a-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/banner-a-light.svg">
  <img alt="LucasSKrewer — IT Analyst, Python/Flask, infrastructure to application; game mods, C++, reverse engineering, netcode" src="assets/banner-a-light.svg" width="100%">
</picture>

IT analyst at a metalworking company, covering everything from infrastructure to the
application layer. The part I like most is **building the internal systems the company
runs on every day**.

My work almost always starts the same way: someone losing hours to a spreadsheet.
It ends with a web tool that does the same thing in seconds.

Outside work, game mods — where I get to touch C++, reverse engineering and netcode.

### Daily stack

- **Python** — Flask, SQLite, pandas, routine automation
- **Web** — HTML/CSS/JS with no framework, server-side rendering
- **Windows** — PowerShell, Waitress, on-premise server deployment
- **Data** — fiscal and financial reconciliation, NF-e XML, spreadsheet ETL

### Public projects

**[dnc_micro_toolkit](https://github.com/LucasSKrewer/dnc_micro_toolkit)** — transfers
G-code programs to CNC machines over three transports (Fanuc FOCAS, RS-232, WiFi DNC box),
with no proprietary DNC software. The box's protocol — TFTP over UDP/69 but with its own
opcodes and packet format — was mapped by reverse engineering the vendor's .NET installer,
running its packet constructors via reflection and capturing the real bytes. Documented
byte by byte in the repo.

**[conciliador_nfe](https://github.com/LucasSKrewer/conciliador_nfe)** — compares the
SEFAZ NF-e spreadsheet against what was actually entered in the internal system and reports
what's missing. Flask + SQLite.

**[lsk_backup](https://github.com/LucasSKrewer/lsk_backup)** — 3-2-1 backup for the small
businesses I support: a PySide6 tray app over rclone, built so a non-technical user can
check that last night's backup actually ran.

**[cripto-backtester](https://github.com/LucasSKrewer/cripto-backtester)** — backtests
trading strategies against real Binance history, with no API key and no order sent anywhere.
It's careful not to use the current candle's own price in the decision, which is the mistake
that makes backtests lie.

**[forja-video](https://github.com/LucasSKrewer/forja-video)** — faceless video production
kit for Claude Code: the agents, skills and scripts that take an episode from research to
a finished Short. ffmpeg + edge-tts + Wikimedia, no paid API.

**[musicgen-local](https://github.com/LucasSKrewer/musicgen-local)** — instrumental tracks
generated offline with MusicGen, stitching segments together to get past the model's 30 s limit.

**[jlpt-estudos](https://github.com/LucasSKrewer/jlpt-estudos)** — Japanese vocabulary study
for JLPT N5 and N4, with a roadmap by topic and per-word progress.

Most of what I write is internal and stays at the company. What's here is the slice I can open up.

### Game mods

**DayZ** — a suite of my own mods for a modded server (Chernarus, BR), written in Enforce
Script: trading with a **Brazilian Real currency across 7 banknotes** and exact change,
keycards that lock rooms full of loot, territory with a plot pole and rent, retextured
clothing and a digital lock. A custom PBO build/signing toolchain and a **headless asset
pipeline** (Blender + Pillow) that generates models and textures without opening an editor.

**[dz-testbench](https://github.com/LucasSKrewer/dz-testbench)** — an assertion/runner test
framework for DayZ mods (Enforce Script), running at server boot and writing results to JSON.
Nothing like it existed in the community. MIT.

**[KenshiCoop](https://github.com/LucasSKrewer/KenshiCoop/tree/experimento-3-jogadores)** —
experimental fork of [nhoral](https://github.com/nhoral/KenshiCoop)'s co-op mod (AGPL-3.0, all
credit for the mod goes to them). I wanted to see whether the sync architecture could hold 3
players: a peer-to-peer relay, per-peer state cleanup, and a real per-sender monotonic `seq`
bug — the [FORK-NOTES](https://github.com/LucasSKrewer/KenshiCoop/blob/experimento-3-jogadores/FORK-NOTES.md)
list what's still missing.
