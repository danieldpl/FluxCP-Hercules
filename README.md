# FluxCP - Hercules Version

FluxCP is a **web-based control panel** for managing [Hercules](https://github.com/HerculesWS/Hercules) servers.
It allows players to register accounts, view server stats, rankings, and provides administrative tools for GMs.

---

## 📋 Requirements

- **PHP 7.0+**
- **MySQL 5.x+**
- **PHP extensions**:
  - `PDO` and `PDO_MYSQL`
  - `GD2` (optional – for displaying guild emblems and CAPTCHA)
  - `Tidy` (optional – for cleaner HTML output)
- **Apache (recommended)** with:
  - `mod_rewrite` enabled (optional – for UseCleanUrls feature)

---

## ⚙️ Installation Guide

1. **Download and extract FluxCP** to your web server directory (e.g. `public_html/`, `www/` or `htdocs`):

```bash
git clone https://github.com/HerculesWS/FluxCP.git
```

2. **Create a database** for your control panel (separate from your main RO databases, optional but recommended).

3. **Edit the application configuration**:

   Open the file `config/application.php` and configure the following:
```php
  'ServerAddress'      => 'mysite.com',
  'BaseURI'            => '',
  'InstallerPassword'  => 'InstallPasswordHere',
```
   - `ServerAddress` with your domain, e.g., `mysite.com`
   - `BaseURI` only if the files are not in the web server root, e.g., `/site` or `/painel`
   - `InstallerPassword` with a secure password for the installation page
   - `ThemeName` (optional) if using custom themes; add your theme to the array

   **PayPal setup (optional):**
   - `DonationCurrency` with the currency code, e.g., `USD` for US dollars
   - `AcceptDonations` must be set to `true`
   - `PayPalBusinessEmail` with your PayPal account email

4. **Configure the server and database connection**:

   Open the file `config/servers.php` and set:
```php
'ServerName'     => 'FluxRO',
'DbConfig'       => array(
     ...
    'Hostname'   => '127.0.0.1',
    'Username'   => 'ragnarok',
    'Password'   => 'ragnarok',
    'Database'   => 'ragnarok',
     ...
'LogsDbConfig'   => array(
     ...
    'Username'   => 'ragnarok_log',
    'Password'   => 'ragnarok_log',
    'Database'   => 'ragnarok_log',
    ...
```
   - `ServerName` with the name of your server
   - Under `DbConfig` and `LogsDbConfig`, set `hostname`, `username`, `password`, and `database` with the correct access credentials. If FluxCP uses the same database as your emulator, the values will likely be similar.
   - In `LoginServer`, update `Address` and `Port` with the correct login server details
   - In `CharMapServers`, update:
     - `ServerName` with your server's name
     - `Renewal` to `true` and `PreRenewal` to `false`
     - `ExpRates` and `DropRates` if using FluxCP's web database
     - `CharServer` and `MapServer` with the correct `Address` and `Port`

5. **Point your browser** to the folder where FluxCP is installed and follow the web-based installer steps.

6. **Done!** You should now be able to access your FluxCP panel.

---

## 👥 Contributors

The following people have contributed to the development of FluxCP over the years.
Thank you for your hard work and dedication!

|# |# |# |
|---|---|---|
| Boooo        | Byteflux86   | Gepard     |
| hemagx       | jaBote       | Mumbles    |
| Mysterious   | Paradox924X  | shugotenshi |
| Streusel     | Xantara      |            |


---

## 📄 License

FluxCP is released under the terms of the LGPL-3.0 License.