# Audit trails and proving what happened

**Covers:** audit trail

## When "trust us" is not enough {#overview}
In some fields, a team must be able to prove what was done, by whom and when. Banks, hospitals, aircraft makers and anyone handling personal data are examples. An inspector or a court may ask months later: who approved this change, and why? If the answer exists only in someone's memory, the organization is in trouble. A record that answers these questions automatically is called an audit trail.

## audit trail {#audit-trail}
An audit trail is a traceable record of past decisions and actions, such as a log that shows who approved a change, who made it and when. It is kept so that anyone with the right to check can reconstruct what happened later.

A good trail has a few features:
- **Complete:** it covers every relevant action, not just some.
- **Time-stamped and attributed:** each entry says when it happened and who did it.
- **Tamper-evident:** nobody can quietly change or delete past entries. Often entries are only ever added, never edited.
- **Retained:** it is kept for as long as the rules require, often several years.
- **Searchable:** you can find the relevant entries quickly.

In software, the trail often combines the version control history, the review approvals, the build and release logs and the records of who accessed sensitive data. The same idea applies inside the application, for example a log of who viewed or changed a customer record.

Rules that require such records include financial reporting laws such as the Sarbanes-Oxley Act, healthcare privacy rules such as HIPAA in the United States and data-protection law such as the GDPR in Europe. Teams must check which apply to them.

## Why it also helps without regulation {#why}
An audit trail is useful even when no law demands it. It helps in an incident, because you can see what changed just before things broke. It makes onboarding easier and helps to settle disagreements about who decided what. The cost is storage and some discipline.

## A worked example {#example}
A payroll system lets staff change an employee's salary. A manager, Lena, asks to raise Omar's pay. Here is what the trail records:

| Time | Who | Action | Detail |
|---|---|---|---|
| 09:12 | Lena | Requested change | Omar Hadid, salary 50,000 to 54,000 |
| 09:40 | Priya (HR) | Approved | Reason: annual review, ticket HR-204 |
| 09:41 | System | Applied change | Old value 50,000, new value 54,000 |
| 09:41 | System | Notified | Payroll team |

Six months later, an auditor asks why Omar's pay rose. The answer takes one minute and does not need anyone's memory.

Now check the arithmetic: 54,000 minus 50,000 is 4,000, and 4,000 divided by 50,000 is 8 percent. The record shows both the numbers and the person who approved them.

To make it tamper-evident, the system never edits a row. If Priya had made an error, a new row would record the correction and refer to the earlier one.

## A common mistake {#mistake}
Logging too little ("a change was made") or too much (every keystroke). The first cannot answer the auditor's questions. The second buries them and may store private data that should not be kept. Decide what the key questions are: who, what, when and why, and record exactly that. Another mistake is letting administrators edit their own logs.

## Key points {#key-points}
- An audit trail is a record that shows who did what, when and why.
- A good trail is complete, attributed, tamper-evident, retained and searchable.
- Regulated fields often require one, but any team benefits from one in an incident.
- Record the key questions precisely, and never allow quiet edits.
