# BitLocker Recovery Key Finder

**Digital forensics coursework**

A Python desktop tool for locating candidate BitLocker recovery passwords in files and memory dumps, with reporting and optional live-memory acquisition.

Python · Tkinter · ReportLab · document parsers

> Academic prototype. Features below are grounded in the source; validation limits are recorded below.

## What it does

- Directory scanning with parsers for text, Office documents, PDFs, and other formats.
- Memory-dump scanning with byte offsets and configurable scan ranges.
- Recovery-password pattern and checksum checks.
- Case information, result export, and PDF reporting modules.
- Optional WinPmem acquisition and Volatility integration hooks.

## Getting started

Commands below use Windows PowerShell.

```powershell
git clone https://github.com/xxKHAN313/BitLocker-Key-Finder-main.git
cd BitLocker-Key-Finder-main/BitLocker-Key-Finder-main
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe main.py
```

Use Python with Tkinter installed. Live acquisition requires Windows, administrator privileges, and a separately obtained compatible WinPmem executable at `assets/winpmem.exe`. It is not included in the published repository. Optional Volatility functionality requires a compatible installation and plugins.

Use only authorized test data. Pattern and checksum matches are candidate findings, not proof that a key unlocks a particular volume. Recovery depends on what data is actually present; no recovery rate or forensic admissibility claim is made.

## Code map

`main.py` — entry point; `ui` — Tkinter interface; `modules/partition_scan.py` — file scanning; `modules/live_ram.py` — acquisition and dump scanning; `modules/pdf_reporter.py` — PDF reports.

Browse the [application source](BitLocker-Key-Finder-main/).

## Validation and limitations

All tracked Python files passed syntax parsing. GUI operation, live acquisition, and key recovery were not exercised. No recovery-key samples or acquisition executable are tracked in the reviewed checkout.

## Credits and license

The existing project credits name Irtaza Zahid, Muhammad Ammar Shahid, Usman Khan, and Shaheer Shaban. The original README attributes dump loading, browse dialogs, and text export to Usman Khan. These credits are preserved.

The original project README includes educational-use conditions. Review those terms before reuse; this documentation does not replace them.
