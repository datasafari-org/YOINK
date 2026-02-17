# YOINK! - Future Features & Enhancement Ideas

This document tracks potential enhancements and feature requests for YOINK!. These ideas are collected from user feedback, development insights, and cybersecurity best practices.

## 🎯 High Priority

### Additional IOC Types
- [ ] **Bitcoin/Crypto Addresses** - Support for BTC, ETH, and other cryptocurrency wallet addresses
- [ ] **User Agents** - Extract suspicious or malicious user agent strings
- [ ] **Registry Keys** - Windows registry path extraction for malware analysis
- [ ] **Mutex Names** - Extract mutex identifiers commonly used by malware

### Enhanced Hash Support
- [ ] **SSDEEP/Fuzzy Hashes** - Context-triggered piecewise hashing for similarity matching
- [ ] **Imphash** - Import hash extraction for PE file analysis

### Export Format Enhancements
- [ ] **MISP JSON Export** - Native export to MISP (Malware Information Sharing Platform) format
- [ ] **OpenIOC Format** - Support for Mandiant's OpenIOC XML format
- [ ] **YARA Rules** - Auto-generate basic YARA rules from IOCs
- [ ] **Sigma Rules** - Generate Sigma rules for SIEM detection (complement existing SIEM queries)
- [ ] **CybOX Export** - Cyber Observable eXpression format for threat intelligence
- [ ] **PDF Report Generation** - Create formatted PDF reports with IOC tables and metadata

## 🔧 User Experience Improvements

### UI/UX Enhancements
- [ ] **Drag & Drop File Input** - Bulk processing of multiple text files at once
- [ ] **Browser Extension** - Chrome/Firefox extension for right-click "YOINK from page"
- [ ] **Auto Theme** - Add system preference detection (`prefers-color-scheme`) for automatic dark/light switching
- [ ] **Keyboard Shortcuts** - Add hotkeys for common actions (Ctrl+E to extract, etc.)
- [ ] **Column Sorting** - Click headers to sort IOCs alphabetically or by type
- [ ] **Bulk Actions** - Select multiple IOCs and perform actions (delete, copy, export)
- [ ] **IOC Statistics Dashboard** - Visual summary of extracted IOC counts per type
- [ ] **Search/Filter IOCs** - Real-time filtering of extracted IOCs by keyword
- [ ] **Undo/Redo Functionality** - Revert accidental deletions or edits

### Data Management
- [ ] **Session Persistence** - Save/load extraction sessions to LocalStorage
- [ ] **Import from CSV/JSON** - Load previously exported IOCs back into the tool
- [ ] **Merge Sessions** - Combine multiple extraction sessions
- [ ] **IOC Deduplication Across Types** - Smarter cross-category duplicate detection
- [ ] **IOC Tagging System** - Add custom tags/labels to IOCs for organization
- [ ] **IOC Notes/Comments** - Add contextual notes to specific indicators

## 🌍 Internationalization

### Additional Languages
- [ ] **German (Deutsch)** - Add German language support
- [ ] **French (Français)** - Add French language support
- [ ] **Spanish (Español)** - Add Spanish language support
- [ ] **Japanese (日本語)** - Add Japanese language support
- [ ] **Portuguese (Português)** - Add Portuguese language support

## 🔒 Security & Validation

### IOC Enrichment
- [ ] **TLD Update Mechanism** - Option to refresh IANA TLD list (with offline fallback)
- [ ] **Private IP Detection** - Flag RFC1918 private IPs separately
- [ ] **Bogon IP Detection** - Identify reserved/unroutable IP addresses
- [ ] **Disposable Email Detection** - Flag temporary/throwaway email domains
- [ ] **URL Scheme Validation** - Better handling of custom protocols (ftp://, file://, etc.)
- [ ] **Punycode/IDN Support** - Handle internationalized domain names
- [ ] **Base64 Encoded IOCs** - Detect and decode base64-encoded indicators

### False Positive Reduction
- [ ] **Whitelist Management** - User-defined whitelist for common false positives
- [ ] **Context Awareness** - Smarter extraction based on surrounding text
- [ ] **Confidence Scoring** - Assign confidence levels to extracted IOCs
- [ ] **Machine Learning Classifier** - Optional ML-based IOC validation

## 🤝 Integration & Interoperability

### API & Connectivity
- [ ] **VirusTotal API Lookup** - Optional hash/IP/domain reputation checks
- [ ] **AbuseIPDB Integration** - Check IP reputation scores
- [ ] **URLhaus Lookup** - Cross-reference malicious URLs
- [ ] **MISP Integration** - Push/pull IOCs directly to/from MISP instances
- [ ] **REST API Mode** - Run YOINK as a local API service
- [ ] **CLI Version** - Command-line interface for scripting/automation

### SIEM Integration
- [x] **Microsoft Sentinel Queries** - KQL wildcard queries *(Completed)*
- [x] **Splunk Queries** - SPL search syntax *(Completed)*
- [x] **Elastic/ELK Queries** - Lucene query syntax *(Completed)*
- [ ] **QRadar Queries** - AQL (Ariel Query Language) support
- [ ] **Chroniclesecurity Queries** - Google Chronicle UDM search syntax
- [ ] **LogRhythm Queries** - LogRhythm search syntax
- [ ] **Sumo Logic Queries** - Sumo Logic query syntax

## 📊 Analysis & Reporting

### Advanced Features
- [ ] **Timeline Visualization** - Plot IOC appearance over time (if timestamps present)
- [ ] **Relationship Mapping** - Visual graph of IOC relationships
- [ ] **IOC Frequency Analysis** - Highlight most common indicators
- [ ] **Diff/Compare Mode** - Compare two extraction sessions
- [ ] **Regex Custom Extractor** - User-defined regex patterns for custom IOCs
- [ ] **Template System** - Save export templates with preferred settings

### Malware Analysis Tools
- [ ] **Defang/Refang Presets** - Multiple defanging formats (hXXp, [.]com, etc.)
- [ ] **C2 Pattern Detection** - Identify common C2 communication patterns
- [ ] **Packer Detection** - Identify common malware packers from strings
- [ ] **String Entropy Calculator** - Detect obfuscated/encrypted strings
- [ ] **Hex/Binary Input Support** - Extract IOCs from hex dumps

## 🎨 Customization

### Personalization
- [ ] **Custom Color Schemes** - User-defined accent colors
- [ ] **Layout Presets** - Compact/Detailed/Analyst view modes
- [ ] **Export Templates** - Customizable CSV/JSON export formats
- [ ] **Column Visibility** - Show/hide specific IOC categories
- [ ] **Font Size Adjustment** - Accessibility improvements for visually impaired users

## 🧪 Experimental Features

### Cutting Edge
- [ ] **AI-Powered IOC Extraction** - LLM-based context-aware extraction
- [ ] **Natural Language Analysis** - Extract IOCs from narrative threat reports
- [ ] **OCR Support** - Extract IOCs from screenshots/images
- [ ] **Audio Transcription** - Extract IOCs from security podcast transcripts
- [ ] **Live Paste Monitor** - Watch clipboard for automatic extraction
- [ ] **Browser Automation** - Scrape IOCs from threat intel feeds

## 🐛 Known Issues & Technical Debt

### Bug Fixes
- [ ] **Long Hash Line Wrapping** - Better mobile/small screen handling
- [ ] **Large File Performance** - Optimize for 10MB+ text inputs
- [ ] **Unicode Edge Cases** - Better handling of non-ASCII characters
- [ ] **Modal Scroll Behavior** - Fix scroll issues on iOS Safari

### Code Quality
- [ ] **Modularization** - Split into logical modules (still single-file)
- [ ] **Unit Tests** - Automated testing for regex patterns
- [ ] **Performance Profiling** - Benchmark extraction speed improvements
- [ ] **Accessibility Audit** - WCAG 2.1 AA compliance
- [ ] **Code Comments** - Enhanced inline documentation

## 📝 Documentation

### User Documentation
- [ ] **Video Tutorials** - Walkthrough screencasts for common workflows
- [ ] **Use Case Examples** - Real-world incident response scenarios
- [ ] **API Documentation** - If REST API mode is implemented
- [ ] **Troubleshooting Guide** - Common issues and solutions
- [ ] **FAQ Section** - Frequently asked questions

### Developer Documentation
- [ ] **Architecture Diagram** - Visual overview of code structure
- [ ] **Contribution Guidelines** - How to submit PRs and feature requests
- [ ] **Regex Pattern Library** - Documented extraction patterns
- [ ] **Testing Guide** - How to test new features

---

## 💡 How to Suggest Features

Have an idea not listed here? Open an issue on GitHub or contact:

- **GitHub**: [datasafari-org/YOINK](https://github.com/datasafari-org/YOINK)
- **Website**: [datasafari.org](https://datasafari.org)
- **Email**: Contact via GitHub

---

## 🏆 Completed Features

### v1.1 (2026-02-17)
- [x] **PRISM Design System** — Neutral gray-blue palette, card-based layout, box shadows, unified `rem` border-radius scale
- [x] **System Font Stack** — `-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto` for crisp cross-platform rendering
- [x] **PRISM Component Classes** — `.badge`, `.status-dot`, `.spinner`, `.card`, `.btn-icon`, `.btn-link`
- [x] **Semantic Color Tokens** — `--accent-success`, `--accent-warning`, `--accent-danger-color`, `--accent-info`, `--shadow`
- [x] **Refined All UI Components** — Top bar, IOC section cards, modals, SIEM query boxes, doc tables, textarea, source display

### v1.0 (2026-02-04)
- [x] **IPv6 Address Extraction** — Full and compressed notation with MAC false-positive filtering
- [x] **CIDR Range Extraction** — IPv4 CIDR with validated prefix (0–32)
- [x] **SHA-512 Hash Extraction** — 128-char hex with deduplication chain (SHA-512 → SHA-256 → SHA-1 → MD5)
- [x] **CVE Identifier Extraction** — CVE-YYYY-NNNNN pattern (1999–2029)
- [x] **MITRE ATT&CK ID Extraction** — Technique (`T####`/`T####.###`) and tactic (`TA####`) IDs
- [x] **STIX 2.1 Extended** — `vulnerability`, `attack-pattern`, `ipv6-addr` types with NVD/MITRE external references
- [x] **SIEM Queries Extended** — IPv6, CVE, ATT&CK blocks added to Sentinel, Splunk, and Elastic

### v0.7-beta (initial release)
- [x] IP Address Extraction (IPv4)
- [x] URL Extraction (HTTP/HTTPS/FTP/FTPS)
- [x] Domain Name Extraction with IANA TLD Validation
- [x] Email Address Extraction
- [x] File Name Extraction
- [x] MD5/SHA-1/SHA-256 Hash Extraction
- [x] Auto-Refang Input
- [x] Defang Output
- [x] CSV Export
- [x] JSON Export
- [x] STIX 2.1 Export (with Identity, SCOs, Indicators, Relationships, Report, TLP)
- [x] Source Text Viewer with Highlighting
- [x] Inline IOC Editing
- [x] Individual IOC Selection
- [x] Long-Press Domain/File Reclassification
- [x] English/Dutch Bilingual Support
- [x] Dark/Light Theme Toggle
- [x] LocalStorage Theme/Language Persistence
- [x] Single-File Zero-Dependency Architecture
- [x] Offline-First Design
- [x] SIEM Wildcard Queries (Sentinel, Splunk, Elastic)

---

**Last Updated**: 2026-02-17
**Current Version**: v1.1
**Maintained By**: Mike Meerkat (Datasafari.org) & Contributors
