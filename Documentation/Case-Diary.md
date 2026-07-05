# Case DF-001 – M57-Jean Investigation

# Examiner

Yash Nishad

# Case ID

DF-001

# Investigation Objective

Determine whether the confidential employee salary spreadsheet was intentionally disclosed or whether it left the system as a result of unauthorized access.

# Evidence

Image Name: nps-2008-jean.E01 / nps-2008-jean.E02

Image Type: Expert Witness Format (E01)

Tools Used:

- FTK Imager 8.2
- Autopsy 4.23.1
- HxD

---

# Investigation Log

---

## Entry 1 – Evidence Verification

### Activity

Loaded the forensic image into FTK Imager and verified the evidence properties.

### Observations

- Image Format: E01
- Evidence Type: Forensic Disk Image
- File System: NTFS
- Partition Layout:
  - NTFS Partition
  - Unpartitioned Space
- Bytes/Sector: 512
- Total Sectors: 20,971,520
- Approximate Disk Size: 10 GiB
- MD5 Hash:
  78a52b5bac78f4e711607707a0ce3f93

### Conclusion

The evidence image loaded successfully and integrity information was available for examination.

---

## Entry 2 – Operating System and User Profiles

### Activity

Examined the filesystem structure and identified user profiles.

### Observations

Windows XP directory structure identified.

User Profiles:

- Administrator
- All Users
- Default User
- Devon
- Jean
- LocalService
- NetworkService

### Conclusion

The primary user profile relevant to the investigation is Jean. Other user accounts were documented for completeness.

---

## Entry 3 – Desktop Examination

### Activity

Examined Jean's Desktop.

### Observations

The following files were identified:

- AIM Tunes.url
- m57biz.xls
- m57biz.xls.FileSlack

### Conclusion

The spreadsheet m57biz.xls corresponds to the file referenced in the investigation scenario and was selected for further examination.

---

## Entry 4 – Spreadsheet Metadata

### Activity

Examined file metadata.

### Observations

File Name:
m57biz.xls

File Size:
291,840 bytes

Created:
20 July 2008 01:28:03

Modified:
20 July 2008 01:28:03

Accessed:
20 July 2008 01:28:03

### Conclusion

The spreadsheet is an allocated file. Metadata was documented prior to content examination.

---

## Entry 5 – Spreadsheet Content Examination

### Activity

Examined the spreadsheet contents.

### Findings

The spreadsheet contains:

- Employee Names
- Positions
- Salaries
- Social Security Numbers

### Conclusion

The recovered spreadsheet contains confidential employee information and is considered primary evidence.

---

## Entry 6 – Browser Artifact Review

### Activity

Examined browser artifacts manually using FTK Imager.

### Observations

Located:

- Cookies
- History
- index.dat
- Temporary Internet Files

### Conclusion

Browser artifacts were identified for later examination.

---

## Entry 7 – Autopsy Processing

### Activity

Imported the evidence into Autopsy and completed ingest processing.

### Artifacts Extracted

- Web History
- Cookies
- Downloads
- Search History
- Email Messages
- Recent Documents
- Shell Bags
- USB Devices
- Installed Programs

### Conclusion

Artifact extraction completed successfully.

---

## Entry 8 – Browser History Examination

### Activity

Reviewed browser history artifacts.

### Findings

Autopsy identified:

5339 browser history records.

Keyword searches for:

- m57
- m57biz
- xls
- salary
- spreadsheet

returned no relevant results.

### Conclusion

No browser evidence supporting data disclosure was identified.

---

## Entry 9 – Recent Documents

### Activity

Reviewed Recent Documents artifacts.

### Findings

Recovered:

- m57biz.LNK

Registry reference:

NTUSER.DAT

Program:

Microsoft Excel

### Conclusion

Independent artifacts demonstrate that m57biz.xls was opened through Microsoft Excel.

---

## Entry 10 – USB Device Examination

### Activity

Examined USB artifacts.

### Findings

Removable devices identified:

- CBM2090 Flash Drive Controller
- Flash Disk 256 MB
- Apple iPhone

### Conclusion

External devices were connected.

No evidence demonstrates that the spreadsheet was copied to removable media.

---

## Entry 11 – Timeline Correlation

### Activity

Correlated timestamps from multiple forensic artifacts.

### Artifacts Used

- Spreadsheet Metadata
- LNK File
- Recent Documents
- USB Artifacts

### Conclusion

A preliminary investigation timeline was established for later correlation.

---

## Entry 12 – Email Examination

### Activity

Reviewed Outlook PST messages.

### Findings

Recovered an email from Alison requesting:

- Employee Names
- Salaries
- Social Security Numbers

Jean replied:

"I've attached the information that you have requested to this email message."

The email contained:

Attachments: 1

### Conclusion

The email conversation strongly suggested transmission of confidential information and required attachment verification.

---

## Entry 13 – Attachment Verification

### Activity

Examined the email attachment.

### Findings

The attachment was: Microsoft Excel

MIME Type: application/vnd.ms-excel

Size: 291,840 bytes

The attachment size matched m57biz.xls recovered from Jean's Desktop.

### Conclusion

The attached file is consistent with the confidential spreadsheet recovered during the examination.

---

## Entry 14 – Email Correlation

### Activity

Correlated the complete email conversation.

### Findings

Sequence identified:

1. Alison requested employee names, salaries and SSNs.

2. Jean replied with an attached spreadsheet.

3. Alison acknowledged receipt by replying:

"Thanks for the file."

"I'll handle it from here."

### Conclusion

The complete email conversation demonstrates successful transmission of the requested confidential information.

---

## Entry 15 – Final Evidence Correlation

### Activity

Correlated all significant forensic artifacts recovered during the investigation.

### Correlated Evidence

✓ Spreadsheet recovered from Desktop

✓ Spreadsheet contains requested employee information

✓ Spreadsheet opened through Microsoft Excel

✓ Email requesting confidential information

✓ Jean replied with one Excel attachment

✓ Attachment size matches m57biz.xls

✓ Recipient confirmed successful receipt

### Conclusion

Multiple independent forensic artifacts support the same sequence of events and collectively demonstrate that the confidential spreadsheet was transmitted through email.

No evidence supporting browser upload, USB-based exfiltration, or external compromise was identified during this examination.

---

# Final Investigator Assessment

The forensic examination identified a confidential spreadsheet containing employee names, salaries, and Social Security Numbers on Jean's Desktop.

Email analysis demonstrated that Alison requested this information, Jean replied with an Excel attachment, and the recipient subsequently acknowledged successful receipt of the file.

The attachment matched the spreadsheet recovered during the examination.

Based on the available evidence, the confidential spreadsheet was transmitted through email.

No forensic evidence examined during this investigation supports the hypothesis that the spreadsheet left the system because of an external hacking incident.

The conclusions presented in this diary are based solely on the supplied forensic disk image and associated artifacts.

--------------------------------------------

Examiner:
Yash Nishad

Case ID:
DF-001

Date Completed:
05/07/2026

Status:
Investigation Closed