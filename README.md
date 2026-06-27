# Obli Server Manager

Obli Server Manager is a Windows desktop application for managing dedicated game servers from one control panel. It is designed to help install, update, start, stop, monitor, repair, back up, and organize multiple server instances without having to manually run every SteamCMD command or batch file yourself.

This app was built for game server owners who want a cleaner way to manage servers such as ARK: Survival Ascended, Evolve, Arma 3, and other SteamCMD-based dedicated servers.

---

## Features

- Manage multiple dedicated game servers
- Add and edit server profiles
- Start and stop servers
- Install and update servers with SteamCMD
- View server logs and event history
- Monitor CPU, RAM, network usage, and player counts
- Run repair and preflight checks
- Manage Workshop mods
- Use per-game mod install rules
- Create and restore backups
- Create server templates and presets
- Configure Discord or webhook alerts
- Set resource alerts for high CPU, RAM, or other usage
- Manage app permissions
- Enable a local API for mobile app or dashboard connections
- Pair with mobile tools using QR code/token connection
- Use a first-run setup wizard
- Configure app-wide settings in the control center
- Support app updates through an update manifest/release system

---

## Requirements

### Required

- Windows 10 or Windows 11
- .NET Desktop Runtime matching the app build
- SteamCMD
- Enough storage space for game server files
- Network access for SteamCMD downloads and server hosting

### Recommended

- Windows 11
- 16 GB RAM minimum
- 32 GB RAM or more for multiple game servers
- SSD storage
- Wired Ethernet connection
- Dedicated server machine or always-on PC
- Static local IP address for hosting
- Proper firewall and port forwarding rules

---

## First-Time Setup

When you open Obli Server Manager for the first time, use the first-run setup wizard.

The wizard helps configure:

1. SteamCMD location
2. Default server install folder
3. Backup folder
4. App settings
5. Local API settings
6. Update settings
7. Basic server manager preferences

If SteamCMD is not found automatically, download SteamCMD from Valve and place it somewhere simple, such as:

```text
C:\SteamCMD\steamcmd.exe
```

Then open the app settings/control center and set the SteamCMD path.

---

## Recommended Folder Layout

A clean folder setup makes the app easier to manage.

```text
C:\ObliServerManager\
├── SteamCMD\
│   └── steamcmd.exe
├── Servers\
│   ├── ASA-PVE-TheIsland\
│   ├── ASA-PVP-Fibercraft\
│   ├── Evolve-Server-1\
│   └── Arma3-Server-1\
├── Backups\
│   ├── ASA-PVE-TheIsland\
│   └── Evolve-Server-1\
└── Logs\
```

You can use your own folder structure, but keeping SteamCMD, servers, backups, and logs separated is recommended.

---

## Adding a Server

To add a server:

1. Open Obli Server Manager.
2. Click **Add Server**.
3. Choose the game/profile type.
4. Enter a server name.
5. Set the install folder.
6. Set ports, query port, RCON port, and other game-specific settings.
7. Save the server profile.

After the profile is saved, you can install, update, start, stop, back up, and monitor the server from the main window.

---

## Installing or Updating a Server

To install or update a server:

1. Select the server from the server list.
2. Click **Install/Update**.
3. The app will run SteamCMD using the configured game/server App ID.
4. Watch the log output for progress.
5. When the update is finished, check the result message.

If SteamCMD fails, review the event log and troubleshooting section below.

---

## Starting a Server

To start a server:

1. Select the server.
2. Review its launch settings.
3. Click **Start**.
4. Check the status and logs.

The server should show as running after the process starts successfully.

---

## Stopping a Server

To stop a server:

1. Select the running server.
2. Click **Stop**.
3. Wait for the process to close.
4. Check logs if the server does not stop correctly.

For best results, avoid force-closing servers unless they are frozen or not responding.

---

## Logs and Event History

The app includes logs and event history so you can see what happened recently.

Useful things to check:

- Server start command
- SteamCMD output
- Install/update result
- Error messages
- Backup result
- Restore result
- Repair result
- Resource alerts
- Webhook/Discord alert attempts

Logs are especially useful when a server fails to start or SteamCMD exits with an error code.

---

## Preflight Checks and Repairs

The repair/preflight system helps catch common problems before starting or updating a server.

It may check for things such as:

- Missing install folder
- Missing executable
- Bad SteamCMD path
- Missing server files
- Invalid ports
- Bad configuration values
- Missing backup path
- Workshop/mod configuration issues
- Permissions or access problems

Use this before assuming the server itself is broken.

---

## Workshop Mod Manager

The Workshop mod manager allows you to add, enable, disable, and update Steam Workshop mods for supported games.

Each mod entry can include:

- Display name
- Workshop ID
- Enabled/disabled state
- Last update time
- Last update result
- Update message

To update enabled mods:

1. Open the server.
2. Go to the Workshop/mod manager.
3. Set the Workshop App ID if needed.
4. Add Workshop IDs.
5. Enable the mods you want active.
6. Click **Update Enabled Mods**.

SteamCMD will download/update each enabled Workshop item.

---

## Per-Game Mod Install Rules

Some games handle mods differently. The per-game mod install rules feature is used to support those differences.

For example, one game may only need Workshop files downloaded, while another game may need files copied into a specific server folder after download.

Use this system when a game requires special handling after SteamCMD downloads the Workshop item.

---

## Backups

The backup system helps protect your server files and profiles.

You can use backups before:

- Updating a server
- Installing new mods
- Editing important configuration files
- Changing maps
- Testing new launch arguments
- Making major server changes

### Create a Backup

1. Select a server.
2. Click **Backup**.
3. Choose/create the backup.
4. Wait for the backup to complete.
5. Confirm the backup appears in the backup list.

### Restore a Backup

1. Select a server.
2. Open the backup list.
3. Select the backup.
4. Click **Restore**.
5. Confirm the restore.
6. Restart the server if needed.

Always stop the server before restoring a backup.

---

## Server Templates and Presets

Templates and presets are used to quickly create servers with saved settings.

Good use cases:

- ASA PvE template
- ASA PvP Fibercraft template
- Test server template
- Event server template
- High-performance server template
- Low-resource server template

Templates can save time when creating multiple similar servers.

---

## Resource Alerts

Resource alerts help warn you when a server or machine is under heavy load.

Possible alert types:

- High CPU usage
- High RAM usage
- High network usage
- Server offline
- Server process not responding
- Player count threshold
- Disk space warning

Use resource alerts to catch problems before players report them.

---

## Discord and Webhook Notifications

The app can send alerts to Discord or another webhook endpoint.

Common notifications:

- Server started
- Server stopped
- Server crashed
- Server update completed
- Server update failed
- Backup completed
- Backup failed
- High resource usage
- Player count alerts

To use Discord webhooks:

1. Create a webhook in your Discord server.
2. Copy the webhook URL.
3. Open app settings/control center.
4. Paste the webhook URL.
5. Enable the alert types you want.

Do not share your webhook URL publicly.

---

## Permissions

The permissions system controls access to sensitive features.

Possible permission areas:

- Start server
- Stop server
- Install/update server
- Edit server profile
- Delete server
- Create backups
- Restore backups
- Change app settings
- Manage webhooks
- Manage templates
- Enable local API

Use permissions if multiple people will use the manager.

---

## Local API and Mobile Pairing

The local API allows another tool, mobile app, or dashboard to connect to the Server Manager on your local network.

Possible uses:

- View server status from a phone
- View CPU/RAM/network usage
- View server list
- Start or stop servers remotely if enabled
- Pair a mobile app using a QR code/token

### Enable Local API

1. Open app settings/control center.
2. Enable **Local API**.
3. Confirm the port.
4. Save settings.
5. Use the QR/pairing option to connect a mobile app or tool.

Only enable the local API on a network you trust.

---

## App Settings / Control Center

The control center is where global app settings are managed.

Common settings:

- SteamCMD path
- Default install folder
- Default backup folder
- Local API enabled/disabled
- Local API port
- Alert settings
- Discord/webhook URL
- Update channel
- Update manifest URL
- Permission settings
- Theme or UI preferences

After changing important settings, restart the app if something does not update immediately.

---

## Updating Obli Server Manager

If the app was published with the updater system, updates may come from a manifest file such as `latest.json`.

Typical update flow:

1. The app checks the update manifest.
2. If a newer version exists, it downloads the release package.
3. The updater applies the new files.
4. The app restarts or asks you to reopen it.

If an update fails, the app may revert to the previous version.

---

## Common SteamCMD Notes

SteamCMD is used to download and update dedicated server files.

Common SteamCMD issues:

- SteamCMD path is wrong
- SteamCMD is blocked by antivirus
- Internet connection failed
- Not enough disk space
- Wrong App ID
- Steam servers are temporarily unavailable
- Folder permissions are blocking installation
- Server files are locked because the server is still running

Make sure the server is stopped before updating.

---

## Troubleshooting

### SteamCMD was not found

Check the SteamCMD path in app settings.

Recommended path:

```text
C:\SteamCMD\steamcmd.exe
```

Also make sure the file exists.

---

### Server will not start

Check:

- Server executable exists
- Launch arguments are correct
- Ports are not already in use
- Required files are installed
- Server is not already running
- Antivirus is not blocking the executable
- The install/update finished successfully

---

### Server shows offline but is running

Check:

- Query port is correct
- Firewall allows the query port
- Port forwarding is correct
- The game server actually supports query status
- The public IP/domain is correct
- The server has fully finished booting

---

### Workshop mods fail to update

Check:

- Workshop App ID is set
- Workshop ID is numeric
- SteamCMD path is correct
- SteamCMD can access the internet
- The mod still exists on Steam Workshop
- The game supports anonymous Workshop downloads
- The server is stopped before applying mod files

---

### Backup fails

Check:

- Backup folder exists
- There is enough disk space
- The app has permission to write to the backup folder
- The server files are not locked
- The path is not too long
- The server is stopped before backup if required

---

### Local API does not connect

Check:

- Local API is enabled
- The port is correct
- Windows Firewall allows the app
- Phone and PC are on the same network
- The pairing token/QR code is current
- You are using the correct local IP address

---

## Safety Tips

- Back up before major updates.
- Stop servers before updating files.
- Keep SteamCMD in a simple path.
- Do not publicly share local API tokens.
- Do not publicly share Discord webhook URLs.
- Use strong permissions if other users access the manager.
- Keep your server ports documented.
- Keep old working backups before testing new mods.

---

## Suggested Workflow

A good daily workflow:

1. Open Obli Server Manager.
2. Check resource usage.
3. Check server status.
4. Review alerts or event logs.
5. Back up important servers.
6. Update servers or mods if needed.
7. Start/restart servers.
8. Confirm player/query status.
9. Check Discord/webhook alerts.

---

## Project Notes

Obli Server Manager was created by Oblistudios LLC as a dedicated server management tool for organizing and controlling game servers from a cleaner desktop interface.

The goal is to make server hosting easier by reducing manual file editing, command-line usage, and repeated setup work.

---

## Support

If something breaks, collect the following information before troubleshooting:

- App version
- Windows version
- Game/server type
- Server install path
- SteamCMD path
- Error message
- SteamCMD exit code, if shown
- Recent log output
- What action was being performed

This makes it much easier to find the problem quickly.
