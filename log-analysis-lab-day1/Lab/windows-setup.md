# 🛠️ Windows Log Collection Setup

## 1. Enable PowerShell Logging

1. Open the Local Group Policy Editor using `gpedit.msc`.
2. Navigate to:

   `Computer Configuration > Administrative Templates > Windows Components > Windows PowerShell`

3. Configure the applicable logging policies:
   - Turn on PowerShell Script Block Logging.
   - Turn on Module Logging, if needed for additional command visibility.

**Note:** Script Block Logging is the relevant setting for Event ID 4104. Logging options may vary by Windows edition.

## 2. Simulate PowerShell Activity

Open PowerShell and execute:

```powershell
Get-LocalUser | Select-Object Name, Enabled
```

This command displays local Windows user accounts and whether each account is enabled.

## 3. Examine the Event Log

1. Press `Windows + R`.
2. Type `eventvwr.msc` and press Enter.
3. Navigate to:

   `Applications and Services Logs > Microsoft > Windows > PowerShell > Operational`

4. Select **Filter Current Log**.
5. Enter Event ID `4104`.
6. Locate the event containing the `Get-LocalUser` command.
7. Examine the event details.

## 4. Document the Evidence

Capture a screenshot showing the PowerShell command in the event details.

Save the screenshot as:

`Images/Log Analysis.png`

## 5. Investigation Note

The command enumerates local user accounts. Although account enumeration can occur during malicious reconnaissance, this activity alone does not establish malicious intent.

Additional evidence and context are necessary before classifying the activity as suspicious or malicious.
