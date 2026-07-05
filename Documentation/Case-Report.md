# Digital Forensic Examination Report

---

# Case Information

| Field | Value |
|--------|-------|
| Case ID | DF-001 |
| Case Name | M57-Jean Insider Data Exfiltration Investigation |
| Examiner | Yash Nishad |
| Evidence | nps-2008-jean.E01 / E02 |
| Examination Tools | FTK Imager 8.2, Autopsy 4.23.1, HxD |
| Operating System | Microsoft Windows XP |
| File System | NTFS |

---

# 1. Executive Summary

A forensic examination was conducted on the supplied Expert Witness (E01) disk image belonging to Jean, an executive at M57.Biz.

The purpose of the examination was to determine how confidential employee information appeared on a competitor's website and to evaluate Jean's claim that the disclosure resulted from unauthorized access to her computer.

The examination identified multiple independent forensic artifacts demonstrating that the confidential spreadsheet was transmitted through email.

No evidence supporting the hypothesis of external compromise was identified within the supplied forensic image.

---

# 2. Scope

The examination included:

- Evidence Verification
- File System Examination
- User Profile Analysis
- Spreadsheet Examination
- Browser Artifact Analysis
- Recent Document Analysis
- USB Device Analysis
- Outlook Email Examination
- Timeline Reconstruction
- Evidence Correlation

The examination was limited to the supplied forensic image.

No live memory, network captures, firewall logs, or mail server logs were available.

---

# 3. Evidence Summary

## Evidence Image

Image Name : nps-2008-jean.E01

Image Format : Expert Witness Format (E01)

File System : NTFS

Approximate Size : 10 GiB

MD5 Verification Hash : 78a52b5bac78f4e711607707a0ce3f93

---

# 4. Examination Methodology

The investigation followed the following sequence:

1. Verify evidence integrity.
2. Examine filesystem.
3. Identify user profiles.
4. Examine Desktop.
5. Recover spreadsheet.
6. Review spreadsheet metadata.
7. Examine spreadsheet contents.
8. Parse artifacts using Autopsy.
9. Review browser artifacts.
10. Review Recent Documents.
11. Review USB artifacts.
12. Examine Outlook PST.
13. Correlate artifacts.
14. Produce findings.

---

# 5. Findings

## Finding 1

### Confidential Spreadsheet Located

The spreadsheet m57biz.xls was recovered from Jean's Desktop.

Evidence Source : FTK Imager

Confidence : High

---

## Finding 2

### Spreadsheet Contains Confidential Information

The spreadsheet contains:

- Employee Names
- Positions
- Salaries
- Social Security Numbers

Confidence : High

---

## Finding 3

### Spreadsheet Was Accessed

Artifacts identified:

- m57biz.LNK
- NTUSER.DAT Recent Document entry

These artifacts indicate that the spreadsheet was opened using Microsoft Excel.

Confidence : High

---

## Finding 4

### Browser Examination

Browser artifacts were recovered including:

- Cookies
- index.dat
- Browser History
- Temporary Internet Files

Keyword searches did not identify evidence supporting browser-based disclosure of the spreadsheet.

Confidence : Medium

---

## Finding 5

### USB Examination

Several removable storage devices were identified including:

- CBM2090 Flash Drive Controller
- Flash Disk 256 MB
- Apple iPhone

No evidence demonstrated that the spreadsheet was copied to removable media.

Confidence : Medium

---

## Finding 6

### Email Request

Email analysis identified a message from Alison requesting:

- Employee Names
- Salaries
- Social Security Numbers

Confidence : High

---

## Finding 7

### Email Reply

Jean replied:

"I've attached the information that you have requested to this email message."

The email contained one attachment.

Confidence : High

---

## Finding 8

### Attachment Verification

The attachment was identified as : Microsoft Excel

MIME Type : application/vnd.ms-excel

Attachment Size : 291,840 bytes

The attachment size matched the spreadsheet recovered from the Desktop.

Confidence : High

---

## Finding 9

### Recipient Confirmation

Alison replied:

"Thanks for the file."

"I'll handle it from here."

This confirms successful receipt of the transmitted document.

Confidence : High

---

# 6. Timeline

| Date & Time | Event | Evidence |
|--------------|-------------------------------|------------|
|20 Jul 2008 01:28|Spreadsheet exists|FTK|
|20 Jul 2008 06:57|Spreadsheet opened|LNK|
|20 Jul 2008 06:58|Jean replies with attachment|Outlook PST|
|20 Jul 2008 06:58|Excel attachment identified|Outlook PST|
|20 Jul 2008 10:33|Recipient acknowledges receipt|Outlook PST|

---

# 7. Evidence Correlation

The following independent artifacts support one another:

- Spreadsheet recovered from Desktop.
- Spreadsheet contains requested confidential information.
- Recent Document artifact.
- Microsoft Excel Registry reference.
- Email requesting confidential information.
- Reply containing Excel attachment.
- Attachment size matching recovered spreadsheet.
- Recipient confirmation email.

The combination of these artifacts establishes a consistent sequence of events.

---

# 8. Conclusion

The forensic examination identified a confidential spreadsheet containing employee names, salaries, positions, and Social Security Numbers on Jean's Desktop.

Email analysis demonstrated that Alison requested this information, Jean replied with an attached Microsoft Excel document, and the recipient acknowledged successful receipt of the file.

The attachment matched the spreadsheet recovered during the examination.

Based on the available evidence, the confidential spreadsheet was transmitted through email.

No forensic evidence examined during this investigation supports the hypothesis that the spreadsheet left the system because of an external hacking incident.

---

# 9. Limitations

The examination was limited to the supplied forensic image.

The following evidence sources were unavailable:

- Live memory
- Firewall logs
- Mail server logs
- Network packet captures
- Cloud storage logs

The conclusions presented are based solely on the available evidence.

---

# 10. Recommendations

- Review corporate email security policies.
- Restrict transmission of confidential employee information.
- Implement Data Loss Prevention (DLP) controls.
- Conduct employee awareness training.
- Audit outbound email attachments containing sensitive information.

---

# 11. Final Assessment

| Hypothesis | Status |
|------------|--------|
| Browser Upload | Not Supported |
| USB Exfiltration | Not Supported |
| Email Transmission | Supported |
| External Compromise | No Supporting Evidence |

---

# Examiner

Yash Nishad
Case Status : Closed