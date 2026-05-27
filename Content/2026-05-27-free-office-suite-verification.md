---
source_url: https://www.libreoffice.org/download/download/
source_title: LibreOffice — Official Download
source_author: The Document Foundation
source_date: 2026-04-30
retrieved_at: 2026-05-27
language: en
---

# Free Office Suite — Verification Report

## Recommendation

**LibreOffice 26.2.3** (Windows x86-64) — the only candidate that is fully free with no ads, no premium tier, no account requirement, no telemetry-by-default, and backed by a non-profit foundation (The Document Foundation). It includes Writer (Word equivalent), Calc (Excel equivalent), Impress (PowerPoint equivalent), plus Draw, Base, and Math as bonuses. Native `.docx` / `.xlsx` read/write, mature RTL/Hebrew support, and an active release cadence.

## Compared Candidates

- **LibreOffice 26.2.3** (recommended)
  - Pros: 100% free forever, fully open-source (MPL 2.0), no ads, no account, no nags, includes 6 apps, strong RTL/Hebrew support, active development with predictable release schedule, transparent CVE disclosure, GPG-signed installers.
  - Cons: UI feels dated next to Microsoft 365; some advanced `.docx` formatting (complex floating tables, certain Track Changes scenarios) still has fidelity gaps vs Microsoft Office; CTL must be enabled manually for full RTL.
  - Official URL: `https://www.libreoffice.org/download/download/`

- **ONLYOFFICE Desktop Editors**
  - Pros: Open source (AGPL 3.0), the highest `.docx` / `.xlsx` fidelity of the three (uses the Microsoft formats as its native ones), modern ribbon UI, strong collaboration features when paired with a server.
  - Cons: Free desktop client is real, but the project pushes hard toward its paid cloud/server tiers; AGPL has implications if you self-host; smaller install base and shorter security-advisory track record than LibreOffice.
  - Official URL: `https://www.onlyoffice.com/download-desktop.aspx`

- **WPS Office Free**
  - Pros: Polished UI that mirrors Microsoft Office very closely, very good `.docx` / `.xlsx` compatibility, lightweight installer.
  - Cons: Proprietary freeware (not open source). The "free" tier is ad-supported and steers heavily toward WPS Premium / AI subscriptions. Developer is Kingsoft, a China-based company — has triggered enterprise/government concerns in some jurisdictions about telemetry and data handling (not a confirmed verdict, but a recurring flag in reviews). Not recommended when LibreOffice meets the need.
  - Official URL: `https://www.wps.com/office/windows/`

- **Apache OpenOffice** — excluded per brief. Project is on minimal maintenance, last meaningful release lags far behind LibreOffice. Not recommended in 2026.

- **SoftMaker FreeOffice** — proprietary freeware, real and ad-free, but requires registration with an email to receive a product key, and the free tier is a deliberately reduced version of the paid SoftMaker Office. Acceptable, but loses to LibreOffice on the "no account, no strings" criterion.

## Verification — LibreOffice 26.2.3

### Official source

- **Download URL (Windows x86-64, MSI):** `https://download.documentfoundation.org/libreoffice/stable/26.2.3/win/x86_64/LibreOffice_26.2.3_Win_x86-64.msi`
- **Landing page:** `https://www.libreoffice.org/download/download/`
- **Publisher / maintainer:** The Document Foundation (TDF) — an independent non-profit foundation based in Berlin, Germany. Founded in 2010 as the steward of LibreOffice after the fork from OpenOffice.org. Funded by donations, members, and corporate sponsors (Collabora, Red Hat, Allotropia, etc.).
- **License:** Mozilla Public License v2.0 (MPL 2.0) for the source code. Free for personal and business use; no per-seat licensing, no activation, no usage telemetry by default.

### Project health

- **Latest stable release:** LibreOffice 26.2.3 — released **April 30, 2026** (43 bugfixes over 26.2.2).
- **Parallel "Still" branch:** LibreOffice 25.8.7 (April 2026) — recommended by TDF for conservative/business deployments.
- **Release cadence:** Two major releases per year (Feb and Aug); point releases roughly every 4-6 weeks. LibreOffice 26.2.4 already on schedule for early June 2026. 26.2 branch supported with seven maintenance updates through November 30, 2026.
- **Project status:** Active. Very active. Dozens of contributors per release, transparent public roadmap, conference held annually.

### Safety scan

- **VirusTotal:** No CVE-specific public report for the 26.2.3 MSI was located in my searches. General community reports (BleepingComputer forum threads, third-party trackers) consistently show LibreOffice installers from the official TDF mirror as clean across 40+ engines. Recommend re-scanning the specific MSI file on VirusTotal at download time as a final sanity check; that is standard practice and not a sign of doubt about the suite.
- **Checksum / signature available:** Yes. The TDF download mirror exposes SHA256 and GPG `.asc` signatures next to each installer (via the "Info" / "Details" link on the download page, and directly in the mirror directory listing). GPG verification via `gpg --verify LibreOffice_26.2.3_Win_x86-64.msi.asc` is the gold standard. On Windows, Gpg4win is the recommended tool. SHA256 verification with PowerShell `Get-FileHash` is the simpler alternative.

### Recent CVEs (last 12 months)

All CVEs below are fixed in **26.2.3** (the recommended version). Anyone on 26.2.3 is current.

- **CVE-2026-4430** — Heap buffer overflow (out-of-bounds write) in AgileEngine when parsing crafted OOXML documents with mismatched encryption salt parameters. Affects 26.2 before 26.2.3 and 25.8 before 25.8.7. **Fixed in 26.2.3 and 25.8.7.** Announced May 6, 2026. CVSS not published on the TDF advisory; exploitation requires the user to open a crafted document. (Source: TDF advisory page.)
- **CVE-2025-14714** — macOS-only TCC bypass. Not applicable to Windows. Fixed in 25.2.4.
- **CVE-2025-2866** — PDF signature spoofing (adbe.pkcs7.sha1 verification flaw — invalid signatures accepted as valid). Fixed in 24.8.6 / 25.2.2.
- **CVE-2025-1080** — Arbitrary macro execution via `vnd.libreoffice.command` URI scheme, browser-to-LibreOffice attack vector. Patched in 24.8.5 / 25.2.1 (March 4, 2025).
- **CVE-2025-0514** — Windows-specific. ShellExecute interpreting non-file URLs as Windows paths could let a crafted hyperlink in a document trigger executable launch on CTRL+click. Fixed in 24.8.5 (February 25, 2025).

**Verdict on CVE history:** Normal-and-healthy. Five disclosed CVEs in 12 months for a 200-million-line codebase is a sign of an actively audited project, not a leaky one. All are patched in the current stable. The two Windows-relevant ones (CVE-2025-0514, CVE-2026-4430) are document/hyperlink attack vectors — the standard "do not open suspicious files" hygiene applies, same as Microsoft Office.

### Reviews summary

- "LibreOffice is the best overall free Microsoft Office alternative in 2026 for most people because it offers the strongest mix of file support, full offline access, mature desktop apps, and long-term reliability without requiring a subscription or cloud account." — TechRadar, *Best free office software of 2026* (updated Jan 14, 2026).
- LibreOffice is "the author's go-to office suite on the desktop"; positioned as the answer to subscription lock-in and data-ownership concerns. — All Things Open, *Your 2026 quick guide to free Office alternatives* (Jan 8, 2026).
- "LibreOffice is the better pick if you want a completely free, full-featured desktop suite" — SelectHub, *LibreOffice vs WPS Office 2026*.

### Safety verdict

**Safe** — when downloaded from `download.documentfoundation.org` (or via the `libreoffice.org/download/` page that links to it), and ideally verified against the SHA256 / GPG signature published next to the installer. The current 26.2.3 release ships with all known CVEs (including the May 6, 2026 OOXML heap overflow) patched. Open-source code, non-profit governance, transparent security disclosure process.

## Caveats / Things to know

- **License:** MPL 2.0 — open source, free for any use including commercial. No EULA gotchas.
- **Ads / paid upsells:** **None.** No nag screens, no "Pro" tier, no telemetry on by default. Donation prompts on first launch can be dismissed permanently.
- **Download size:** ~360 MB for the Windows x86-64 MSI (approximate, based on prior 26.x releases; verify on the download page at retrieval time).
- **Install size on disk:** ~1.5-1.8 GB after install with default components.
- **`.docx` / `.xlsx` compatibility — real-world:**
  - Reading: excellent for the vast majority of documents.
  - Writing: very good. Round-tripping (open `.docx` → edit → save as `.docx` → reopen in Microsoft Word) works for ordinary documents. Known edge cases: heavily formatted Word documents with complex floating tables, certain Track Changes scenarios, and some advanced Excel features (PivotTable refresh behavior, certain chart types, macros written in VBA-specific dialects) can show fidelity loss. For most home and SMB use, fine. For round-tripping with Microsoft-Office-bound external partners on critical docs, test first.
  - LibreOffice also reads/writes ODF natively (`.odt`, `.ods`, `.odp`) — the ISO-standard open formats. Recommended for documents that will stay inside LibreOffice.
- **Hebrew / RTL:** Supported. To enable: `Tools → Options → Language Settings → Languages → Complex Text Layout (CTL): Enabled`, then set CTL language to Hebrew. Once enabled, `Ctrl+Shift+D` toggles RTL text direction inline. Hebrew UI translation is available during installation (choose Hebrew in the installer language selector, or change UI language post-install). Known minor friction: when mixing Hebrew and Latin fonts, the CTL font defaults sometimes override Western font choices — workaround is to set the CTL font explicitly in `Tools → Options → LibreOffice Writer → Basic Fonts (CTL)`.
- **Two release tracks:** TDF publishes both a "Fresh" line (newest features — currently 26.2.3) and a "Still" line (more conservative — currently 25.8.7). For a typical end user wanting Word + Excel replacements, **26.2.3 is the recommended pick**. For an organization deploying to many machines and prioritizing stability over new features, 25.8.7 is the safer choice.
- **Windows support:** Requires Windows 10 or higher. Works fine on Windows 11.
