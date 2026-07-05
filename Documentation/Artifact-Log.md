# Artifact Log

## Case Information

| Field | Value |
|--------|-------|
| Case ID | DF-001 |
| Case Name | M57-Jean Insider Data Exfiltration Investigation |
| Examiner | Yash Nishad |

---

# Artifact Summary

| Artifact ID | Artifact | Status |
|-------------|----------|--------|
| ART-001 | E01 Evidence Image | Examined |
| ART-002 | NTFS File System | Examined |
| ART-003 | User Profiles | Examined |
| ART-004 | Desktop Files | Examined |
| ART-005 | m57biz.xls | Examined |
| ART-006 | Windows Shortcut (.LNK) | Examined |
| ART-007 | NTUSER.DAT | Examined |
| ART-008 | Browser Artifacts | Examined |
| ART-009 | USB Artifacts | Examined |
| ART-010 | Outlook PST | Examined |
| ART-011 | Email Attachment | Examined |

---

# ART-001 — Evidence Image

## Description

Primary forensic disk image supplied for examination.

### Location

```
nps-2008-jean.E01
nps-2008-jean.E02
```

### Findings

- Successfully mounted.
- Integrity verified.
- NTFS filesystem identified.

### Forensic Value

Primary source of digital evidence.

---

# ART-002 — NTFS File System

### Location

```
Partition 1
```

### Findings

- Windows XP filesystem
- Active partition
- User profiles recovered

### Forensic Value

Provides access to all allocated files and directories.

---

# ART-003 — User Profile

### Location

```
C:\Documents and Settings\Jean
```

### Findings

Jean's user profile contained:

- Desktop
- NTUSER.DAT
- Cookies
- Application Data

### Forensic Value

Primary source of user activity.

---

# ART-004 — Desktop

### Location

```
C:\Documents and Settings\Jean\Desktop
```

### Findings

Recovered:

- AIM Tunes.url
- m57biz.xls
- m57biz.xls.FileSlack

### Forensic Value

Desktop contained the confidential spreadsheet central to the investigation.

---

# ART-005 — Confidential Spreadsheet

### File

```
m57biz.xls
```

### Size

291,840 bytes

### Contents

- Employee Names
- Positions
- Salaries
- Social Security Numbers

### Forensic Value

Primary evidence demonstrating possession of confidential employee information.

---

# ART-006 — Windows Shortcut (.LNK)

### Artifact

```
m57biz.LNK
```

### Findings

Shortcut references:

```
C:\Documents and Settings\Jean\Desktop\m57biz.xls
```

### Forensic Value

Indicates the spreadsheet was accessed through Microsoft Excel.

---

# ART-007 — NTUSER.DAT

### Artifact

Windows User Registry Hive

### Findings

Recovered Recent Document references for:

```
m57biz.xls
```

### Forensic Value

Corroborates user interaction with the spreadsheet.

---

# ART-008 — Browser Artifacts

### Examined

- History
- Cookies
- index.dat
- Temporary Internet Files

### Findings

- Browser activity recovered.
- Keyword searches returned no evidence linking browser activity to disclosure of the spreadsheet.

### Forensic Value

Used to evaluate browser-based exfiltration.

---

# ART-009 — USB Artifacts

### Devices Identified

- CBM2090 Flash Drive Controller
- Flash Disk 256 MB
- Apple iPhone

### Findings

Removable media devices were connected.

No evidence demonstrated that confidential files were copied to removable media.

### Forensic Value

Used to evaluate removable media as a possible exfiltration method.

---

# ART-010 — Outlook PST

### Artifact

```
outlook.pst
```

### Findings

Recovered:

- Incoming emails
- Outgoing emails
- Attachments

### Forensic Value

Primary source of communication evidence.

---

# ART-011 — Email Attachment

### MIME Type

```
application/vnd.ms-excel
```

### Size

```
291,840 bytes
```

### Correlation

Attachment size matched:

```
m57biz.xls
```

### Forensic Value

Direct evidence demonstrating transmission of the confidential spreadsheet.

---

# Evidence Correlation Matrix

| Artifact | Purpose | Result |
|----------|---------|--------|
| E01 Image | Evidence Source | Verified |
| Desktop | Locate confidential file | Success |
| Spreadsheet | Identify confidential information | Success |
| LNK File | User activity | Spreadsheet opened |
| NTUSER.DAT | Registry correlation | Spreadsheet referenced |
| Browser History | Browser upload investigation | No supporting evidence |
| USB Artifacts | USB exfiltration investigation | No supporting evidence |
| Outlook PST | Email investigation | Confidential email recovered |
| Email Attachment | Attachment verification | Excel attachment confirmed |

---

# Artifact Confidence Assessment

| Artifact | Confidence |
|-----------|------------|
| Evidence Image | High |
| Spreadsheet | High |
| LNK File | High |
| NTUSER.DAT | High |
| Outlook PST | High |
| Email Attachment | High |
| Browser Artifacts | Medium |
| USB Artifacts | Medium |

---

# Artifact Log Conclusion

The investigation relied on multiple independent forensic artifacts recovered from the supplied forensic image.

The strongest evidentiary artifacts included:

- Confidential spreadsheet (`m57biz.xls`)
- Windows Shortcut (`m57biz.LNK`)
- NTUSER.DAT Registry references
- Outlook PST email messages
- Microsoft Excel email attachment
- Recipient acknowledgement email

Correlation of these artifacts established a consistent sequence of events demonstrating transmission of the confidential spreadsheet through email.