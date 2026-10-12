# Money Orbit — Privacy (Android beta)

**Last updated:** 12 October 2026

Money Orbit is a personal, offline-first financial tracking application that is still in active beta development. Its current financial database is **not encrypted at rest**. Please do not use the beta as the sole or authoritative store of sensitive financial records.

## Optional Gmail credit-alert reader

If you enable **More → Gmail bank credits**, Money Orbit asks Google for `gmail.readonly` OAuth authorization. This is a **read-only, restricted Google permission**, granted through Google's own account-selection and consent screens. Money Orbit does not ask for your Gmail password.

Only when you initiate a scan does Money Orbit communicate directly with Google's Gmail API over HTTPS to search recent bank-credit alerts (up to 65 matching messages from the last 60 days). It analyzes potential deposits on your phone, shows short previews, and lets you approve or dismiss suggested transactions. No email automatically changes your bank account balance or financial records.

Raw email bodies and OAuth access tokens are **not intentionally persisted to the app's ledger, backup, GitHub repositories, or a Money Orbit server**. Locally saved settings may include the connected Google email address and identifiers of emails already imported. Transactions you explicitly approve are kept in the local SQLite ledger with amount, date, category, selected account and a generic source note. Google, your network service provider, Android and the device's system software remain subject to their own security/data practices.

## Disconnect

You can select **Disconnect and revoke Gmail access** to revoke the OAuth grant and clear locally tracked Gmail message markers. Previously approved ledger entries are retained until you remove them yourself. You can also inspect/remove a third-party authorization in your Google Account security settings.

## Other local finance data

Financial spaces, accounts, transaction entries, budgets, reminders and savings plans are stored on your Android device. External export features are initiated by the user. Backups saved through Money Orbit's portable export are AES-GCM encrypted using a user-selected backup password, while ordinary CSV exports are plaintext and must be protected by the user. Optional local LLM files and generation stay on the device unless you deliberately share text to an external service.

## Distribution

Only signed APKs and checksums are made public in this release repository. No financial records or Gmail credentials are published to it. Installing updates requires Android user approval. Public source code is kept separate.

For questions about private beta usage, contact the repository owner through GitHub.
