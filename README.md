Imran's Finances

A privacy-first personal finance tracker for Android that reads your bank SMS, automatically categorises transactions, tracks your tolls, and never sends your data anywhere. Everything stays on your phone.

---

What it does

Imran's Finances turns the hundreds of bank SMS and payment notifications cluttering your inbox into a clean, searchable ledger of what you spent, earned, and owed — with category detection, payee grouping, toll tracking, and export to PDF or CSV.

No account, no server, no sign-up. The app reads SMS and notifications directly on your device, stores everything in a local SQLite database, and never uploads anything.

---

Features

📩 Automatic transaction import

· SMS scanner — reads your bank SMS from the last N days, extracts amount, merchant, UPI ID, date, reference number, and balance
· Notification listener — captures payment notifications from UPI apps (Paytm, PhonePe, GPay, Amazon Pay, Mobikwik, Jio Payments, etc.)
· Duplicate detection — deduplicates on SMS key, ref number + account, and fuzzy match (time ± 5 min, same amount, same merchant, same day)
· Rescan anytime — incremental scan picks up only new SMS since last scan

🏦 Multi-bank, multi-channel

· Detects 40+ Indian banks (HDFC, SBI, ICICI, Axis, Kotak, IDFC, PNB, Canara, Union, Federal, Jupiter, Fi, and more) from SMS sender headers
· Handles UPI, IMPS, NEFT, RTGS, ATM, FASTag, Credit Card, Cash, and CDM (Cash Deposit Machine) deposits
· Differentiates debit vs credit correctly, and pulls out your available balance when the SMS has it

🧠 UPI & Mobile intelligence (v12.3+)

· UPI ID extraction — pulls the VPA out of Federal Bank-style UPIOUT/…/vpa@handle/… messages, cleans stray spaces, validates the handle
· Mobile number detection — recognises 10-digit Indian mobiles (6/7/8/9 first digit) inside UPI usernames
· Brand recognition — 150 built-in brand → category mappings (Clovia → Shopping, Swiggy → Food, Airtel → Bills, IRCTC → Travel, LIC → Insurance, Bajaj Finserv → Loan, etc.)
· Machine Learning review screen — the app proposes display names and categories for new UPI/mobile merchants. You get a review screen with tick boxes to accept or reject each suggestion. Original SMS is never altered — only the display name on the transaction.
· Contacts screen — two tabs (UPI / Mobile) listing every UPI ID and mobile number the app has seen, with per-contact txn count, total in, and total out. Tap any row to see all its transactions.

📒 Ledger

· Year-grouped, collapsible transaction list
· Search by merchant, body, sender, tag, or >amount
· Filter by All / Sent / Received, by category, by tag, or by date range (Today / Week / Month / custom year-month)
· Bulk select to delete, re-categorise, or move to Tolls in one go
· Long-press any txn for Edit / View raw SMS / Delete / Categorize / Move to tolls
· Tag transactions and filter by tag (#food, #trip-ooty)

🚗 Travel & Tolls

· FASTag toll detection — matches toll SMS to known plazas by name/amount
· Date-grouped toll list — one collapsible section per day, showing time, plaza name, and amount
· Map view — routes drawn via OSRM, going vs returning trips coloured differently
· Move to tolls — one-tap from any txn, bulk-select in Ledger, or "Move ALL" for a whole payee
· Remove from tolls — long-press any toll row (or select mode) to remove a wrongly-classified entry; the transaction itself stays in the ledger
· Export toll list to PDF or long screenshot

👥 Payees

· Auto-grouped by merchant / UPI ID
· Merge duplicate payees into one survivor, with undo
· Add aliases — "Add & merge" another UPI/name into an existing payee
· Recurring detection — flags payees that look like subscriptions (monthly, similar amount)
· Per-payee view — total sent, total received, full transaction history with Newest/Oldest sort
· Export to PDF (colour-coded red/green with In/Out/Net totals) or long screenshot

💰 Accounts & Net Worth

· Grouped by Bank / Wallet / Card / FASTag / Loan / Insurance
· Icon per provider — banks, wallets, telecoms, insurers, and lenders show their own icon
· Duplicate cleanup — spot and remove duplicate account rows
· Reclassify any account (tap to move Bank → Wallet, or Bank → Loan, etc.)
· Net worth = assets − liabilities, computed from latest balance per account

📊 Dashboard

· Month picker with prev/next navigation
· Spend vs income with month-over-month delta
· Projected month-end spend based on current run rate
· Category donut with per-category row (tap to filter ledger, long-press to set a budget)
· Spending heatmap by hour of day
· Cash (ATM) tracker
· Latest 5 transactions with quick access to full ledger
· Per-month PDF report — share via any app

📈 Charts

· Monthly category breakdown with animated donut
· Month navigation

💸 Bills & Budgets

· Bills — add recurring bills with amount, due day, category, frequency (monthly/weekly/yearly). Mark paid (auto-creates txn). Last-paid date tracked.
· Budgets — set a monthly limit per category. Dashboard shows progress bar and remaining. Notification fires when you exceed it (once per category per month).

🏷️ Categories & Rules

· 14 built-in categories (Grocery, Fuel, Food, Travel, Shopping, Bills & Recharge, Entertainment, Health, Cash, EMI/Loan, Transfer, Salary/Income, Received, Other) plus unlimited custom categories
· Rules screen groups learned rules by category, shows match count, allows per-rule or clear-all deletion
· Learn from corrections — when you change a txn's category, the app learns it. You get a confirmation dialog showing similar transactions (same payee / UPI / exact name) with tick boxes so you decide which to update too.

🏦 Loans

· Auto-detected from SMS mentioning loan, EMI, LAN, or loan account numbers
· Shows last EMI amount, next estimated EMI date, total paid
· Tap a loan to see every linked transaction

💳 Auto-categorisation

· Keyword rules matched against merchant and body (300+ keywords across Indian banks, UPI apps, billers)
· Learned rules from your manual corrections, with weight-based matching
· Brand dictionary for UPI handles (Clovia, Swiggy, Netflix, Airtel, Bajaj Finserv, etc.)

🔐 Privacy & security

· All data is local — SQLite on your device. No cloud sync, no telemetry, no ads.
· FLAG_SECURE — blocks screenshots and screen recording of sensitive screens
· Biometric lock — optional fingerprint/face unlock, re-prompts after 60 seconds in background
· No internet required for core features (only optional: OSRM map routes, OSM tiles)

🎨 Interface

· Material 3 design — soft cards, ripple feedback, hairline borders
· 7 colour palettes — Purple, Teal, Amber, Indigo, Rose, Green, Navy
· Light / Dark / System theme
· Hinglish language option (English + Hindi mix for common labels)
· Bottom navigation with active-tab pill
· Quick-add FAB — cash entry, add bill, set budget
· Long screenshot — capture any screen as a full-length PNG via the camera icon
· Drawer with all screens (Dashboard, Ledger, Travel, Payees, Accounts, UPI & Mobile, Machine Learning, Bills, Budgets, Categories, Rules, Loans, Settings)

💾 Backup & data portability

· CSV backup — every table exported to Downloads/ImransFinances/, plus a .rules.json sidecar with learned rules
· Restore — tolerant of old v11 backups, skips malformed rows without rolling back the whole restore
· CSV bank statement import — upload a bank-exported CSV with column mapping preview
· Toll JSON import — upload toll plaza data (NHAI format)
· Clean DB + restore — wipe and restore from a backup in one action
· Rules JSON — export/import learned category rules separately

📤 Export

· PDF reports — monthly summary, per-payee transaction list with colour-coded totals, per-loan list, toll list grouped by date
· Long screenshots — any screen, full content, shareable

---

Supported formats

UPI SMS:

```
UPIOUT/600427023116 /9999999999@axl/UPI/0000
UPI IN/610829760319 /jamesbond000@oksbi/UP/0000
```

ATM SMS:

```
TO ATM/55555555555/BERLINGTON ROAD \
→ "ATM Withdrawal on Burlington Road", Cash
```

CDM (Cash Deposit Machine):

```
BY CDM/3878/FBL-KANPUR \24/1
→ "CDM Deposit · FBL-KANPUR", Transfer (money in)
```

Bank SMS formats — tested against HDFC, SBI, ICICI, Axis, Kotak, IDFC, PNB, Canara, Federal Bank, and more. If a bank's format isn't recognised, the raw SMS is preserved so you can still find and edit it.

---

Privacy

· No analytics — the app doesn't phone home
· No ads — no ad SDK
· No third-party tracking — no Firebase, no Sentry, no Crashlytics
· No cloud — your SMS, transactions, and rules never leave your device
· Network used only for: OpenStreetMap tiles (map view) and OSRM routing (toll trips). These requests contain no personal data.

---

Technical

· Language: Kotlin
· Min SDK: 30 (Android 11)
· Target SDK: 33
· Size: ~5 MB APK
· Data store: SQLite (fintrack.db, version 15)
· Build: GitHub Actions → debug APK → GitHub Release on every push
· Dependencies: AppCompat, Core-KTX, Biometric, osmdroid, Material 3, SwipeRefreshLayout

---

Getting started

1. Install the latest APK from Releases
2. Grant SMS read permission when prompted
3. Tap Rescan SMS on first run — the app imports transactions from your inbox
4. (Optional) Grant Notification access in Settings → Notification access for live transaction capture
5. (Optional) Set a biometric lock in Settings
6. Open Machine Learning from the drawer to review UPI and mobile suggestions
7. Open UPI & Mobile from the drawer to browse by contact

---

What's coming

· Improved SMS parser for more banks
· Cloud-free encrypted backup
· Recurring transaction alerts
· Split transaction support
· Tax-year report export

---

License

Personal project, shared as-is. Not affiliated with any bank, UPI provider, or financial institution. Use at your own discretion.
