## theme-coredrive for ownCloud

### Use the theme-coredrive App

To use the `theme-coredrive` app, clone this repository to the `/var/lib/univention-appcenter/apps/owncloud/data/custom` folder on your server. Please note that the Apache user needs access rights to the folder and its content. As an example, use the following command to adjust the permissions: `chown -R www-data:www-data theme-coredrive`.

### Change values
Please have a look at the file `defaults.php` if you want to change texts. The copyright text on the start page and other texts are well documented there.

### Integrity check

Since files in the theme must be changeable, it has not been signed by us. Therefore an `integrity check warning` appears in your ownCloud instance. You can deactivate it for the `theme-coredrive` app by adding following config parameter to `config/config.php`. You can find the config directory in the root folder of your instance.

```
'theme' => 'theme-coredrive',
'integrity.ignore.missing.app.signature' => [
      'theme-coredrive',
 ],
```

### Enable theme

```
univention-app shell owncloud
occ app:enable theme-coredrive
exit
```

## OwnCloud - Important configurations

### Requirements

#### Windows
  - Windows 7+
  - x86 with 32-bit or x86-64 with 64-bit
  - Native WinVFS available for Windows 10 version 1709 or later
#### macOS
  - macOS 10.12+
  - x86-64 or Apple M in Rosetta 2 emulation; unsupported legacy builds for Mac OS X 10.10 & 10.11 available
  - M1 native support planned for Q4 2022 - no issues in regard to performance or otherwise known at this time!
#### Linux
  - CentOS 7.x with minimum version x=8 (x86-64)
  - Debian 10 & 11 (x86-64)
  - Fedora 34 & 35 (x86-64)
  - openSUSE Leap 15.3 (x86-64)
  - Ubuntu 20.04 & 21.10 & 22.04 (x86-64)

### Types to evaluation

- [CLIENT DEFINE] Limit upload size files (default 250MB)
- [CLIENT DEFINE] Time to clen up the trash (default 30 days if the system need more space)
- [CLIENT DEFINE] Connect using LPDA
- [CLIENT DEFINE] Create Users group
- [CLIENT DEFINE] Limit user quoat
- [CLIENT DEFINE] Allow users to share by link
                  - Allow public uploads
                  - Enforce password protection for read-only links
                  - Enforce password protection for read & write links
                  - Enforce password protection for upload-only (File Drop) links
                  - Set default expiration date
                  - Allow users to send mail notification for shared files
                  - Allow users to share file by social media
- [CLIENT DEFINE] Automatically accept new icoming local user shares
- [CLIENT DEFINE] Allow resharing
- [CLIENT DEFINE] Allow sharing with groups
- [CLIENT DEFINE] Restrict users to only share with users in their groups
- [CLIENT DEFINE] Restrict users to only share with groups they are mamber of
- [CLIENT DEFINE] Exclude groups from sharing
- [CLIENT DEFINE] Default user and group share permission (create:default, change, delete, share)
- [CLIENT DEFINE] Crypt files. (It make all files more big than before uploaded)
- [CLIENT DEFINE] Timeout to lockfile (Default: 30 minutes)
- [CLIENT DEFINE] Timeout to versioning (default)
  - LAST UP TO DATE --> QTD. VERSION
  - 1 second --> 1
  - 10 seconds --> 5
  - 1 minute --> 6
  - 1 hour --> 59
  - 1 day --> 23
  - 30 days --> 30
- [CLIENT CONFIG] Restrict subfolders to share
- [CLIENT INFORM] You can only copy up to 2500 files at one time.
- [CLIENT INFORM] Restrict invalide names and size directories and files
  - Filenames cannot end in a space or dot
  - Windows reserved names:q
    - CON, PRN, AUX, NUL COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3,
      LPT4, LPT5, LPT6, LPT7, LPT8, LPT9
- [OUR MISSION] Config e-mail templates
- [OUR MISSION] Config log to make little disk use
- [OUR MISSION] Monitoring SSL certified. If expiries the system down
