# CLAUDE.MD - Project Context for AI Assistants

## Project Overview

**YOINK!** (Your Observables Instantly Nabbed & Kategorized) is a single-file HTML cybersecurity tool for extracting, managing, and exporting Indicators of Compromise (IOCs) from raw text.

### Key Characteristics
- **Zero dependencies** - entirely self-contained in one HTML file
- **Offline-first** - designed to run on air-gapped systems
- **Security focus** - built for incident response and threat intelligence workflows
- **Defensive security tool** - extracts and processes IOCs for defensive purposes only

## Architecture

### File Structure
```
/YOINK/
├── yoink.html              # Main production file (~125KB)
├── defanger.html           # Development/testing versions
├── defanger copy*.html     # Backup/iteration files
├── README.md               # User-facing documentation
├── linkedin-post.md        # Marketing content
├── screenshots/            # UI screenshots for documentation
└── CLAUDE.MD              # This file
```

### Technology Stack
- Pure HTML5, CSS3, and vanilla JavaScript
- No frameworks, no build tools, no external libraries
- Embedded IANA TLD list (~1500 entries) for domain validation
- LocalStorage for theme and language preferences

## Core Functionality

### Supported IOC Types (8 total)
1. **IPv4 addresses** - regex with octet validation
2. **URLs** - HTTP/HTTPS/FTP/FTPS protocols
3. **Domains** - validated against IANA TLD list
4. **Email addresses** - standard pattern matching
5. **File names** - extension-based classification
6. **MD5 hashes** - 32-char hex
7. **SHA-1 hashes** - 40-char hex
8. **SHA-256 hashes** - 64-char hex

### Key Features
- **Auto-refang**: Converts defanged input (`hxxps`, `[.]`, etc.) to valid IOCs
- **Defang output**: Safely neutralize IOCs for sharing in reports/chat
- **Source viewer**: Click any IOC to see highlighted occurrences in original text
- **Inline editing**: Edit, copy, or delete extracted IOCs
- **Move between categories**: Long-press domains/files to reclassify
- **3 export formats**: CSV, JSON, STIX 2.1
- **STIX 2.1 bundles**: Full-featured with Identity, SCOs, Indicators, Relationships, Report, TLP markings
- **Bilingual**: English and Dutch UI
- **Dark/Light themes**: User preference stored locally

### Domain vs File Classification Logic
| TLD valid? | File extension? | Result | Priority |
|:-:|:-:|---|---|
| ✓ | ✗ | Domain | TLD validation |
| ✓ | ✓ | Domain | TLD takes priority |
| ✗ | ✓ | File | Extension match |
| ✗ | ✗ | Discard | No match |

This eliminates false positives like `window.location` while correctly handling ambiguous cases like `archive.zip` (TLD) vs `malware.zip` (file).

## Development Guidelines

### Code Style
- **Simplicity first**: No premature optimization or abstraction
- **Self-contained**: All functionality in one file
- **Readable**: Clear variable names, logical structure
- **Comments**: Document complex regex patterns and validation logic

### Security Considerations
- **Defensive use only**: This tool is for defenders (SOC, IR teams, threat intel analysts)
- **No active connections**: IOCs are extracted and displayed, never connected to
- **Safe by default**: Defanged output prevents accidental clicks on malicious URLs
- **Privacy-focused**: No telemetry, no external calls, no data leaves the browser

### Testing Workflow
- Test with various defanged input formats
- Validate IANA TLD edge cases (`.zip`, `.cab`, `.mov`, `.com`)
- Verify hash deduplication (MD5 shouldn't match within SHA-256)
- Test STIX 2.1 export with TIP platforms
- Check both dark/light themes and EN/NL languages

## Use Cases

1. **Incident Response**: Extract IOCs from phishing emails, malware reports, sandbox output
2. **Threat Intelligence**: Parse advisories and export as STIX for threat intelligence platforms
3. **SOC Operations**: Defang IOCs before sharing in tickets, Slack, email
4. **Malware Analysis**: Extract hashes, C2 domains, and URLs from analysis notes
5. **Training/CTF**: Teach IOC handling and STIX formatting

## Export Formats

### CSV
Simple two-column format: `Type, Value`

### JSON
Structured object with arrays per category:
```json
{
  "ips": [...],
  "urls": [...],
  "domains": [...],
  "emails": [...],
  "files": [...],
  "md5": [...],
  "sha1": [...],
  "sha256": [...]
}
```

### STIX 2.1
Full bundle including:
- Identity SDO (organization)
- SCOs (ipv4-addr, url, domain-name, email-addr, file)
- Indicator SDOs (STIX patterns)
- Relationship SROs (18 relationship types supported)
- Report SDO (ties indicators together)
- TLP markings (CLEAR, GREEN, AMBER, AMBER+STRICT, RED)

## Future Enhancement Ideas

- [ ] IPv6 support
- [ ] CIDR notation detection
- [ ] CVE identifier extraction
- [ ] MITRE ATT&CK technique ID extraction
- [ ] Additional language support
- [ ] Browser extension wrapper
- [ ] Bulk file processing (drag-and-drop multiple files)
- [ ] Export to additional formats (MISP, OpenIOC)

## Important Notes for AI Assistants

### What You Should Do
✓ Help analyze the extraction logic and regex patterns
✓ Improve domain/file classification accuracy
✓ Enhance STIX 2.1 export functionality
✓ Add new IOC types (CVE, ATT&CK IDs, etc.)
✓ Improve UI/UX and accessibility
✓ Fix bugs in extraction or export logic
✓ Optimize performance for large text inputs
✓ Add new defensive security features

### What You Should NOT Do
✗ Add features that could be used offensively (e.g., auto-scanning live URLs)
✗ Implement credential extraction or harvesting capabilities
✗ Add functionality that connects to or validates IOCs against live infrastructure
✗ Create features for reconnaissance or active exploitation
✗ Suggest or implement malicious uses of the tool

### Code Modification Approach
- Always read the entire HTML file before suggesting changes
- Maintain the single-file architecture
- Test changes don't break existing functionality
- Preserve the zero-dependency constraint
- Keep the file size reasonable (<200KB)
- Ensure offline functionality remains intact

## Credits

Created by **Mike Meerkat** ([Datasafari.org](https://datasafari.org)) and **Claude** ([Anthropic](https://anthropic.com)).

---

**Last Updated**: 2026-02-02
**File Version**: 1.0
**Project Status**: Active Development
