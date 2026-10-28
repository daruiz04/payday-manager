# Payday Splitter

A one-page budgeting tool for hourly paychecks. Enter your hours and it works out your take-home pay, then tells you where every dollar goes: bills first, then groceries, then a savings/spending split of whatever is left.

It's a single `index.html` file with no build step and no dependencies.

## Features

- **First-time setup.** Name, hourly pay, normal hours, pay schedule, a payday, and local tax rate.
- **Paycheck picker.** Weekly, every 2 weeks, twice a month, or monthly. Extra paychecks in a month (a 3rd biweekly or 5th weekly check) are detected automatically.
- **Hours → take-home.** Estimates gross pay, federal tax (2026 single brackets), Social Security + Medicare, Kentucky tax, local occupational tax, and net pay. You can type the real amount from your bank instead.
- **Bill checklist.** Each check covers its share of next month's rent, its share of monthly bills, and any card payment due before the next payday. Tick items off as you pay them.
- **Bills by month.** Switch any bill on or off for a given month. Add, edit, or remove bills.
- **Leftover split.** A slider splits what's left between savings and spending money, with a "Goal pace" button.
- **Spending tracker.** Log purchases and see what's left until the next payday.
- **Card balances.** Track each card's balance as payments are ticked off.
- **Moving fund and cost list.** Track savings toward a goal by May 1, 2027, based on real moving costs.
- **Back up or restore.** Download everything as a file, or restore it in another browser.

## Privacy

The page has no personal information built into it. Everything a person enters is saved in their own browser's local storage on their own computer. It's never sent anywhere, and nobody on another computer can see it.

Personal setup files (`*-setup.json`) and backups (`payday-backup-*.json`) are ignored by git, so they stay off GitHub.

## Updating without losing data

Saved data is tied to the browser and to where the page is opened from (the file's location, or the website address).

- Replacing `index.html` with a newer version in the same place keeps everything.
- Opening it from a new location or a new website address starts empty. Use **Back up or restore** to carry data over.
- Code changes must keep the existing storage key names (`settings4`, `bills4`, `off4`, `done2`, `pays`, `splits`, `hours`, `spends`, `balances`, `costs`, `useCosts`, `moved`, `folds`, `saved`, `sel`, `bmonth`). Renaming one makes that data look lost.

## Setup files

A setup file is a `payday-setup` JSON file that fills in a person's starting info (name, pay, bills). Restoring one only adds what hasn't been entered yet. It never overwrites anything.

A backup file (`payday-backup`) replaces everything saved in that browser. The page asks before doing that.

## Tax figures

2026 estimates for a single filer: federal brackets after the $16,100 standard deduction, 7.65% FICA, and Kentucky's flat 3.5% rate with a $3,360 standard deduction. The local occupational rate comes from Settings (for example, Louisville Metro is 1.45% for people who live outside Jefferson County and 2.2% for residents). Check the numbers against a real pay stub.
