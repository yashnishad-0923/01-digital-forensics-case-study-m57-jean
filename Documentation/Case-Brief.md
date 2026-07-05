# Case Brief

## Case ID

DF-001

---

# Case Name

M57-Jean Insider Data Exfiltration Investigation

---

# Case Summary

A confidential Microsoft Excel spreadsheet containing employee names, positions, salaries, and Social Security Numbers (SSNs) belonging to M57.Biz was discovered on a competitor's website.

The spreadsheet was known to exist only on the laptop assigned to the company's Chief Financial Officer, Jean.

Jean claimed that she had no knowledge of how the information left her computer and suggested that her laptop had been compromised by an external attacker.

A forensic examination of the supplied disk image was conducted to determine how the confidential information was disclosed and to evaluate the credibility of the hacking claim.

---

# Investigation Objective

The objectives of this investigation were:

- Verify the integrity of the supplied forensic evidence.
- Identify the operating system and user environment.
- Locate and examine the confidential spreadsheet.
- Determine whether the spreadsheet had been accessed.
- Investigate possible methods of data exfiltration, including:
  - Email
  - Browser upload
  - USB devices
  - Other user activity
- Correlate multiple forensic artifacts.
- Determine whether the available evidence supports the claim of external compromise.

---

# Scope of Examination

The examination was limited to the supplied forensic disk image.

The investigation included:

- File System Analysis
- User Profile Analysis
- Spreadsheet Examination
- Browser Artifact Analysis
- Email Analysis
- USB Device Analysis
- Recent Documents Analysis
- Timeline Correlation

The following evidence was **not** available:

- Live memory acquisition
- Network packet captures
- Firewall logs
- Mail server logs
- Cloud storage logs

All conclusions are based solely on the supplied forensic evidence.

---

# Evidence Provided

| Evidence | Description |
|-----------|-------------|
| nps-2008-jean.E01 | Primary forensic disk image |
| nps-2008-jean.E02 | Continuation segment of the E01 image |

---

# Evidence Information

| Field | Value |
|--------|-------|
| Evidence Format | Expert Witness Format (E01) |
| File System | NTFS |
| Operating System | Microsoft Windows XP |
| Partition Layout | One NTFS Partition + Unpartitioned Space |
| Approximate Size | 10 GiB |
| MD5 Verification Hash | 78a52b5bac78f4e711607707a0ce3f93 |

---

# Tools Used

The following forensic tools were used during the investigation:

- FTK Imager 8.2
- Autopsy 4.23.1
- HxD Hex Editor

---

# Examination Methodology

The investigation followed a structured forensic workflow:

1. Evidence Verification
2. File System Examination
3. User Profile Identification
4. Spreadsheet Analysis
5. Browser Artifact Examination
6. USB Artifact Examination
7. Recent Document Analysis
8. Email Analysis
9. Timeline Correlation
10. Evidence Correlation
11. Final Findings

---

# Key Evidence Identified

The investigation identified the following significant artifacts:

- Confidential spreadsheet (`m57biz.xls`)
- Windows Shortcut (`m57biz.LNK`)
- NTUSER.DAT Recent Document reference
- Outlook PST mailbox
- Email requesting confidential employee information
- Reply email containing an Excel attachment
- Recipient acknowledgement confirming receipt
- Browser artifacts
- USB connection history

---

# Final Findings

The forensic examination established that:

- The confidential spreadsheet was present on Jean's Desktop.
- The spreadsheet had been opened using Microsoft Excel.
- Alison requested confidential employee information by email.
- Jean replied with an attached Microsoft Excel document.
- The attachment matched the spreadsheet recovered during examination.
- Alison acknowledged successful receipt of the file.

No forensic evidence examined during this investigation supports the hypothesis that the confidential spreadsheet left the system because of an external compromise or hacking incident.

---

# Investigation Outcome

**Status:** Completed

The available evidence supports the conclusion that the confidential spreadsheet was transmitted through email.

No evidence supporting unauthorized external access was identified within the supplied forensic image.

---

# Examiner

**Name:** Yash Nishad

---

# Case Status

Investigation Completed

---

# Repository

This case was completed as part of a digital forensics learning portfolio demonstrating practical examination techniques, evidence correlation, documentation, and forensic reporting using industry-standard tools.