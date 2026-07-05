# Investigation Timeline

## Case Information

| Field | Value |
|--------|-------|
| Case ID | DF-001 |
| Case Name | M57-Jean Insider Data Exfiltration Investigation |
| Objective | Reconstruct the sequence of events leading to the disclosure of confidential employee information. |

---

# Timeline Methodology

The timeline was reconstructed by correlating timestamps recovered from multiple independent forensic artifacts including:

- File System Metadata
- Windows Shortcut (LNK) Files
- Recent Documents
- Outlook PST Email Messages
- Email Attachments
- USB Device Artifacts

Only events supported by forensic evidence are included.

---

# Chronological Timeline

| Date & Time | Event | Evidence Source | Confidence |
|--------------|-------------------------------|-------------------------|------------|
|20 Jul 2008 01:28:03|Confidential spreadsheet (`m57biz.xls`) present on Jean's Desktop.|FTK Imager – File Metadata|High|
|20 Jul 2008 02:23:00|Alison requested employee names, salaries, and SSNs from Jean.|Outlook PST|High|
|20 Jul 2008 06:56:18|Flash Disk (256 MB) detected on the system.|USB Artifacts|Medium|
|20 Jul 2008 06:57:42|Spreadsheet accessed through Microsoft Excel.|Recent Documents (`m57biz.LNK`)|High|
|20 Jul 2008 06:58:04|Windows recorded updated Desktop activity.|Desktop.LNK|Medium|
|20 Jul 2008 06:58:XX|Jean replied to Alison stating that the requested information had been attached.|Outlook PST|High|
|20 Jul 2008 06:58:XX|Email contains one Microsoft Excel attachment.|Outlook PST|High|
|20 Jul 2008 10:33:XX|Alison acknowledged successful receipt of the file.|Outlook PST|High|

---

# Evidence Correlation

## Event 1

### Confidential Spreadsheet Located

Evidence

- Desktop
- File Metadata

Result

Spreadsheet recovered successfully.

---

## Event 2

### Spreadsheet Access

Evidence

- m57biz.LNK
- NTUSER.DAT

Result

Spreadsheet was opened using Microsoft Excel.

---

## Event 3

### Request for Confidential Information

Evidence

Email from Alison requesting:

- Employee Names
- Salaries
- Social Security Numbers

Result

Recipient explicitly requested confidential company information.

---

## Event 4

### Spreadsheet Transmission

Evidence

Jean replied:

> "I've attached the information that you have requested to this email message."

Result

Outgoing email indicates transmission of requested information.

---

## Event 5

### Attachment Verification

Evidence

Email Attachment

MIME Type

```
application/vnd.ms-excel
```

Attachment Size

```
291,840 bytes
```

Recovered Spreadsheet Size

```
291,840 bytes
```

Result

Attachment characteristics match the spreadsheet recovered from Jean's Desktop.

---

## Event 6

### Recipient Confirmation

Evidence

Alison replied:

> "Thanks for the file."

> "I'll handle it from here."

Result

Recipient confirmed successful receipt of the transmitted document.

---

# Timeline Analysis

The reconstructed timeline demonstrates the following sequence of events:

1. The confidential spreadsheet existed on Jean's Desktop.

2. Alison requested confidential employee information.

3. Jean accessed the spreadsheet.

4. Jean replied by attaching the requested information.

5. The attachment matched the spreadsheet recovered from the forensic image.

6. Alison confirmed successful receipt of the file.

No events identified during the examination support browser-based upload or unauthorized external compromise.

---

# Timeline Confidence Assessment

| Event | Confidence |
|---------|------------|
| Spreadsheet Recovery | High |
| Spreadsheet Access | High |
| Email Request | High |
| Email Reply | High |
| Excel Attachment | High |
| Recipient Confirmation | High |
| USB Device Presence | Medium |
| Browser Upload | Not Supported |
| External Hack | Not Supported |

---

# Timeline Conclusion

The chronological reconstruction demonstrates a consistent sequence of events supported by multiple independent forensic artifacts.

The recovered evidence indicates that the confidential spreadsheet was transmitted through an email attachment following a direct request from Alison.

No forensic evidence identified during the examination supports the hypothesis that the spreadsheet left the system through browser upload, removable media, or unauthorized external access.