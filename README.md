DayZ AutomationZ Scheduler
DayZ AutomationZ Scheduler is a standalone automation application designed to automatically upload files to remote servers using FTP or FTPS based on scheduled tasks.
It was originally created to solve a common problem for DayZ server owners: switching configuration files at specific times (weekend raids, loadouts, events) without needing to be online.
Over time, it became clear this tool is not limited to DayZ — it works for any FTP-based workflow.
What it automates
Once configured, the Scheduler can:
⦁	Automatically upload files on specific days and times
⦁	Run unattended (24/7 or when needed)
⦁	Replace server files exactly when required
⦁	Create backups before overwriting
⦁	Handle multiple servers and profiles
Core concepts
Profiles
Profiles store FTP/FTPS connection details and remote root paths.
You can create unlimited profiles for different servers.
Presets
Presets are local folders containing files to upload.
Examples:
⦁	raid_on
⦁	raid_off
⦁	loadouts_monday
⦁	website_theme_dark
Mappings
Mappings define exact file replacement rules:
Local file → Remote destination
This strict mapping system ensures safety and predictability.
Tasks
Tasks schedule uploads based on:
⦁	Day(s) of the week
⦁	Hour and minute
⦁	Selected profile, preset, and mappings
What it does NOT do
⦁	It is NOT a DayZ mod
⦁	It does NOT change game logic
⦁	It does NOT require server parameters
Who this is for
⦁	Game server owners
⦁	Website owners
⦁	VPS administrators
⦁	Anyone needing scheduled FTP uploads
Author
Created by Danny van den Brande
AutomationZ Project
