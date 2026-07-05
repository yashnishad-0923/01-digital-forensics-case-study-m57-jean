# Investigation Board

## Case Information

| Field | Value |
|--------|-------|
| Case ID | DF-001 |
| Case Name | M57-Jean Insider Data Exfiltration Investigation |
| Examiner | Yash Nishad |
| Status | Investigation Closed |

---

# Investigation Question

**How did the confidential employee spreadsheet leave Jean's laptop, and does the available evidence support Jean's claim that she was hacked?**

---

# Initial Case Information

## Incident Summary

A confidential Microsoft Excel spreadsheet containing employee names, salaries, and Social Security Numbers (SSNs) belonging to M57.Biz was discovered on a competitor's website.

Jean claimed that she had no knowledge of how the spreadsheet left her computer and stated that she believed her system had been compromised.

A forensic examination was initiated to determine the method of disclosure.

---

# Confirmed Facts

| ID | Fact | Status |
|----|------|--------|
| F-01 | Forensic image successfully verified | ✓ |
| F-02 | Windows XP operating system identified | ✓ |
| F-03 | Jean user profile recovered | ✓ |
| F-04 | Confidential spreadsheet recovered | ✓ |
| F-05 | Spreadsheet contains employee names, salaries and SSNs | ✓ |
| F-06 | Spreadsheet accessed through Microsoft Excel | ✓ |
| F-07 | Outlook PST recovered | ✓ |
| F-08 | Email attachment recovered | ✓ |
| F-09 | Recipient acknowledged receiving the file | ✓ |

---

# Investigation Hypotheses

## H1 – Intentional Disclosure by Jean

### Status

Supported [✓]

### Supporting Evidence

- Alison requested confidential employee information.
- Jean replied stating the requested information was attached.
- Email contained one Microsoft Excel attachment.
- Attachment matched the recovered spreadsheet.
- Recipient confirmed successful receipt.

### Confidence

High

---

## H2 – External Compromise (Hacking)

### Status

Not Supported [✕]
 
### Findings

- No malware evidence identified.
- No suspicious browser activity indicating unauthorized disclosure.
- No evidence of unauthorized transmission.

### Confidence

Low

---

## H3 – Browser-Based Exfiltration

### Status

Not Supported [✕]

### Findings

- Browser artifacts examined.
- Keyword searches returned no relevant results.
- No upload evidence identified.

### Confidence

Medium

---

## H4 – USB-Based Exfiltration

### Status

Not Supported [✕]

### Findings

- USB devices were connected.
- No evidence demonstrated copying of the spreadsheet to removable media.

### Confidence

Medium

---

## H5 – Email-Based Exfiltration

### Status

Supported [✓]

### Supporting Evidence

- Email requesting confidential information.
- Jean's reply with attachment.
- Microsoft Excel attachment identified.
- Attachment size matched recovered spreadsheet.
- Recipient confirmed receipt.

### Confidence

High

---

# Evidence Correlation

```text
Confidential Spreadsheet
        │
        ▼
Spreadsheet Metadata
        │
        ▼
m57biz.LNK
        │
        ▼
NTUSER.DAT
        │
        ▼
Email Request
        │
        ▼
Jean's Reply
        │
        ▼
Excel Attachment
        │
        ▼
Recipient Confirmation
```

---

# Evidence Summary

| Evidence | Result | Confidence |
|----------|--------|------------|
| Confidential Spreadsheet | Identified | High |
| Spreadsheet Content | Verified | High |
| Spreadsheet Access | Confirmed | High |
| Browser Artifacts | No supporting evidence | Medium |
| USB Devices | Connected but unrelated | Medium |
| Outlook PST | Examined | High |
| Email Request | Verified | High |
| Email Attachment | Verified | High |
| Recipient Confirmation | Verified | High |

---

# Investigation Decision Matrix

| Question | Answer | Evidence |
|----------|--------|----------|
| Was the spreadsheet present? | Yes | Desktop |
| Was it confidential? | Yes | Spreadsheet Contents |
| Was it opened? | Yes | LNK + Registry |
| Was confidential information requested? | Yes | Email |
| Did Jean send a reply? | Yes | Outlook PST |
| Was an attachment included? | Yes | Outlook PST |
| Was the attachment Excel? | Yes | MIME Type |
| Did the attachment match the spreadsheet? | Yes | Size Comparison |
| Did the recipient receive it? | Yes | Reply Email |
| Was browser upload identified? | No | Browser Analysis |
| Was USB copying demonstrated? | No | USB Analysis |
| Was hacking supported? | No | No supporting evidence |

---

# Final Assessment

The investigation identified multiple independent forensic artifacts supporting the same sequence of events.

Evidence demonstrated that:

- The confidential spreadsheet existed on Jean's Desktop.
- The spreadsheet was opened using Microsoft Excel.
- Alison requested confidential employee information.
- Jean replied with an attached Microsoft Excel document.
- The attachment matched the recovered spreadsheet.
- Alison confirmed successful receipt of the file.

No forensic evidence examined during this investigation supports the hypothesis that the confidential spreadsheet left the system because of browser upload, USB exfiltration, or unauthorized external compromise.

---

# Case Outcome

| Hypothesis | Final Status |
|------------|--------------|
| Intentional Disclosure | ✓ Supported |
| Email Exfiltration | ✓ Supported |
| Browser Upload | ✕ Not Supported |
| USB Exfiltration | ✕ Not Supported |
| External Compromise | ✕ Not Supported |

---

# Investigation Status

**Case Status:** Closed

**Evidence Status:** Correlated

**Documentation Status:** Complete

**Report Status:** Completed

**Portfolio Status:** Ready for Publication