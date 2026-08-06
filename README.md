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

Modding gives me the kind of problem work doesn't: someone else's code, no documentation,
no game source, and a 2010 compiler as a hard requirement.

**[KenshiCoop](https://github.com/LucasSKrewer/KenshiCoop/blob/experimento-3-jogadores/FORK-NOTES.md)**
— experimental fork. The original mod is by [nhoral](https://github.com/nhoral/KenshiCoop)
(AGPL-3.0) and takes Kenshi from single-player to two-player co-op; all credit for the mod
goes to them.

I wanted to know whether the synchronization architecture could hold a larger group — a
direction the author deliberately doesn't pursue, so it became a fork rather than an issue.
On the [`experimento-3-jogadores`](https://github.com/LucasSKrewer/KenshiCoop/tree/experimento-3-jogadores)
branch:

- **Peer-to-peer relay** — the host now forwards state authored by one peer to the *other*
  peers, through a single chokepoint, with an explicit per-packet-type policy and 42
  assertions pinning the table down. A no-op with two players.
- **Per-peer state cleanup** — one player leaving used to sweep the entire session, tearing
  down the proxies of everyone who stayed. Each peer is now swept individually.
- **Per-sender sequence guard** — this one is a real bug, not an N-player change: the docs
  promise a monotonic `seq` *per sender*, but the line kept a single scalar. Two senders with
  independent counters would starve each other out.

It isn't N-ready yet, and the [FORK-NOTES](https://github.com/LucasSKrewer/KenshiCoop/blob/experimento-3-jogadores/FORK-NOTES.md)
list honestly what's still missing.
