# Vestates HR Desk

HR Desk is the group HR records app and dashboard for 365 Energy, Apex Restaurant, Vestates, Zbom Home and Farm2Table. It shows headcount, salary cost, exits, gender, and contract and probation status, and staff records can be edited by the people who have access.

**App:** https://bdavestates.github.io/hr-desk/

## How it works

- Everyone signs in with their email and a password.
- The staff records are kept in Firebase (project `vestates-hr-desk`). Everyone with access sees the same live data.
- What each person can do depends on their role:

| Role | Can do |
|---|---|
| **Admin** | Everything: see and edit each person's salary, delete records, import and export, invite people and change their access, and see the activity log |
| **Editor** (e.g. assistant HR) | Add staff, edit details, record exits and renew contracts. Sees salary totals by company, not individual salaries |
| **Viewer** | Sees the dashboard and staff list. Cannot change anything |

These limits are enforced by the database rules in `firestore.rules`, not only by the app, so they can't be bypassed.

## Giving someone access

1. An admin opens **Access** and invites the person's email address with a role.
2. The person opens the app, chooses **Create your account**, and uses that exact email.
3. They confirm their email from the message Firebase sends them, then click **I've confirmed**.

To remove someone, an admin clicks **Remove** next to their name on the **Access** page.

## Importing and exporting

- **Import / export → Choose Excel file** (admin only) loads staff from the Database sheet of the employee database workbook. This replaces all the current records.
- **Download Excel** exports the records. The export includes salaries only when an admin downloads it.

## Files

| File | Purpose |
|---|---|
| `index.html` | The app |
| `firebase-config.js` | The Firebase project's connection settings (these are not secret) |
| `firestore.rules` | The database security rules, also published in the Firebase console |
| `manifest.webmanifest`, `sw.js`, `icons/` | Installing the app and opening it offline |

When you change `index.html`, also bump `VERSION` in `sw.js` (for example `hrdesk-v3` to `hrdesk-v4`) so installed copies update.
