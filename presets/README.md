# AutomationZ Scheduler (FTP/FTPS)

AutomationZ Scheduler is a lightweight desktop app that **automatically uploads files to remote servers (FTP/FTPS) on a weekly schedule** (days + hour + minute).

It was built for DayZ server owners who need things like **weekend raid switches**, **daily loadout rotations**, and **event config changes** to happen *even when they are offline* — but it also works for **websites, VPS configs, and any FTP-based workflow**.

**Created by Danny van den Brande**

---

## Why this exists (the problem it solves)

Many server owners manage changes like:
- Turn raids ON Friday evening and OFF Sunday night
- Rotate loadouts per weekday
- Swap messages / notifications during events
- Enable maintenance mode automatically

Doing this manually means you must be present at the exact time, every week.  
AutomationZ Scheduler removes that requirement by running tasks for you.

---

## What it automates (FAQ-friendly)

**Is this really automation if I still configure it manually?**

Yes. The **setup is manual once**, but the **execution is automatic**.

- Manual step: create profiles, mappings, tasks (your “intent”)
- Automatic step: the scheduler watches the clock and runs tasks **without you clicking anything**

If the app is running, tasks will execute at the configured day/time.

---

## How it works (4 simple building blocks)

### 1) Profiles (servers)
A Profile is one server connection: host, port, username/password, optional FTPS, and a **remote root** folder.

You can add **as many profiles as you want**, which is perfect if you manage multiple servers.

### 2) Presets (local folders)
A Preset is a local folder that contains the files you want to upload (examples: `raid_on`, `raid_off`, `DZB_NEW_Loadouts`).

### 3) Mappings (local -> remote rules)
A Mapping defines exactly which **local file** overwrites which **remote file**.

Example mapping:
- local: `BBP_raid_on.json`
- remote: `config/BaseBuildingPlus/BBP_Settings.json`

Mappings can be enabled/disabled and can optionally download a backup before overwriting.

### 4) Tasks (the schedule)
A Task ties it all together:
- which Profile to use
- which Preset folder to upload from
- which day(s) to run
- hour + minute
- which mappings it is allowed to run (global enabled mappings or selected ones)

---

## Screenshots
See the wiki for screenshots.
---

## Quick Start (recommended order)

1. **Create a Profile**
   - Add your FTP/FTPS host, user, password
   - Set your remote root (e.g. `/dayzstandalone` on Nitrado)
2. **Create Mappings**
   - Define what file should overwrite what remote target
   - Turn on “Backup before overwrite” if you want safety backups
3. **Create Presets**
   - Put your preset files inside `presets/<PresetName>/`
4. **Create Tasks**
   - Pick the Profile + Preset + day/time
   - Choose global mappings or specific mappings
5. **Start the Scheduler**
   - Leave it running for true automation (or enable auto-start)

---

## Typical DayZ examples

### Weekend raids
- Task: Raid ON -> Friday 18:00
- Task: Raid OFF -> Sunday 23:59

### Daily loadouts
- Task: Loadout Monday -> Monday 00:00
- Task: Loadout Tuesday -> Tuesday 00:00
- ...

### Messages / notifications
Schedule different `messages.xml` or Expansion notification configs depending on weekday or event.

---

## Safety features

- **Exact path mapping** (no guessing, no bulk syncing)
- **Optional backup** before overwrite (downloads the current remote file first)
- **Dry run** option on tasks (log only, no upload)

---

## License
Pick a license that matches your goal:
- **MIT**: simplest and most permissive (recommended for adoption)
- **GPLv3**: forces derivatives to remain open-source
- **Apache-2.0**: permissive + explicit patent terms

Most small utility tools like this use **MIT**.

---

## Credits
DayZ AutomationZ Scheduler
Created by Danny van den Brande

This project is developed in free time and provided
completely free of charge.

If AutomationZ helps you manage your servers,
saves you time, or replaces manual work,
consider supporting development with a donation.

Donations are optional but appreciated and help
keep the project alive and improving.

Support development: https://ko-fi.com/dannyvandenbrande
