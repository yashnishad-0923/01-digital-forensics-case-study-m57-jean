# Digital Forensics Concepts Handbook

This handbook contains the forensic concepts, artifacts, and methodologies learned while investigating the M57-Jean case.

---

# 1. E01 (Expert Witness Format)

## Definition

The Expert Witness Format (E01) is one of the most widely used forensic disk image formats.

## Features

- Bit-by-bit acquisition
- Compression
- Metadata storage
- Hash verification
- Multi-segment support
- Court accepted

---

# 2. Hash Verification

## Purpose

Hash verification ensures that forensic evidence has not been modified after acquisition.

## Common Algorithms

- MD5
- SHA1
- SHA256

Even a one-bit modification changes the hash value.

---

# 3. Windows User Profiles

Windows XP stores user profiles under:

```
C:\Documents and Settings\
```

Each profile contains user-specific evidence including:

- Desktop
- Cookies
- Favorites
- Local Settings
- Application Data
- NTUSER.DAT

---

# 4. Desktop Artifacts

Desktop folders frequently contain:

- Active documents
- Downloads
- Shortcuts
- Temporary evidence

Desktop contents should always be documented before analysis.

---

# 5. File Slack

File Slack is the unused space remaining at the end of the last cluster allocated to a file.

It may contain remnants of previously stored data and therefore has forensic value.

---

# 6. File Metadata

Important metadata includes:

- File Name
- File Size
- File Type
- Created Time
- Modified Time
- Accessed Time

Metadata should be documented before examining file contents.

---

# 7. Personally Identifiable Information (PII)

Examples:

- Name
- Social Security Number (SSN)
- Passport Number
- Aadhaar Number
- Phone Number
- Email Address

PII is frequently encountered during digital forensic investigations and must be handled carefully.

---

# 8. Browser Artifacts

Common browser artifacts include:

- History
- Cookies
- Cache
- Downloads
- Search History
- index.dat (Internet Explorer)
- places.sqlite (Firefox)

Deleting browser history does not necessarily remove all browsing evidence.

---

# 9. Autopsy Ingest Modules

Autopsy automatically parses forensic artifacts.

Common modules:

- Recent Activity
- File Type Identification
- Keyword Search
- Hash Lookup
- Embedded File Extractor

Automated results should always be verified manually.

---

# 10. Evidence vs Noise

Digital investigations often produce thousands of artifacts.

Most artifacts represent normal system activity.

The investigator's responsibility is to distinguish relevant evidence from background activity.

---

# 11. Windows Shortcut (.LNK) Files

LNK files record recently accessed files and folders.

They may contain:

- Original path
- MAC timestamps
- Volume information
- Network information

LNK files remain valuable even when the original file has been deleted.

---

# 12. NTUSER.DAT

NTUSER.DAT is the Windows per-user Registry hive.

It stores:

- Recent Documents
- MRU Lists
- Explorer settings
- Application settings
- User-specific configuration

It is one of the most valuable Registry artifacts.

---

# 13. USB Artifacts

Windows records connected USB devices in multiple locations.

Examples:

- USBSTOR
- MountedDevices
- SetupAPI
- ShellBags
- RecentDocs

The presence of a USB device does **not** prove that files were copied.

---

# 14. Timeline Analysis

Timeline analysis reconstructs user activity using timestamps from multiple artifacts.

Common timeline sources include:

- File metadata
- Browser history
- Registry
- LNK files
- Email
- USB artifacts
- Event Logs

A timeline should never rely on a single timestamp.

---

# 15. Email Forensics

Email investigations may reveal:

- Sender
- Recipient
- Subject
- Attachments
- MIME Type
- Timestamps
- Message headers

Email attachments frequently provide direct evidence of data exfiltration.

---

# 16. Evidence Correlation

Evidence correlation is the process of combining multiple independent artifacts to reconstruct events.

Example:

```
Spreadsheet

↓

Recent Documents

↓

Email Attachment

↓

Recipient Confirmation

↓

Supported Finding
```

Independent artifacts increase confidence in forensic conclusions.

---

# 17. Hypothesis Testing

Every investigation begins with one or more hypotheses.

Example:

- Insider leaked the file.
- Browser upload.
- USB copy.
- External compromise.

Evidence is collected to support or reject each hypothesis.

Investigators should avoid drawing conclusions before sufficient evidence exists.

---

# 18. Confidence Levels

Each finding should be assigned a confidence level.

High : Supported by multiple independent artifacts.

Medium : Supported by a single reliable artifact.

Low : Requires additional corroboration.

---

# 19. Digital Forensic Reporting

A professional forensic report should include:

- Executive Summary
- Scope
- Evidence
- Methodology
- Findings
- Timeline
- Evidence Correlation
- Conclusion
- Limitations

Reports should describe facts supported by evidence rather than opinions.

---

# 20. Lessons Learned from the M57-Jean Case

- Evidence correlation is stronger than individual artifacts.
- Browser history alone rarely proves data exfiltration.
- USB device presence does not prove file copying.
- Email artifacts can directly demonstrate data transmission.
- A forensic examiner should distinguish facts, inferences, and conclusions.
- Every finding should be supported by documented evidence.