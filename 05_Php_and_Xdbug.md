# Php & Xdebug

[<== Retour](../../)

## PHP

### Configuration du Php.ini

Le fichier `php.ini` se trouve dans le dossier `/usr/local/etc/php/<votre_version>`.

### Configuration

```
[mail function]
; For Win32 only.
; https://php.net/smtp
SMTP = <serveur_smtp_hote>
; https://php.net/smtp-port
smtp_port = <serveur_smtp_port>

; For Win32 only.
; https://php.net/sendmail-from
sendmail_from = <serveur_smtp_mail_envoi>

; For Unix only.  You may supply arguments as well (default: "sendmail -t -i").
; https://php.net/sendmail-path
;sendmail_path = <adresse_de_outil>

; Force the addition of the specified parameters to be passed as extra parameters
; to the sendmail binary. These parameters will always replace the value of
; the 5th parameter to mail().
;mail.force_extra_parameters =

; Add X-PHP-Originating-Script: that will include uid of the script followed by the filename
mail.add_x_header = Off

; The path to a log file that will log all mail() calls. Log entries include
; the full path of the script, line number, To address and headers.
;mail.log =
; Log mail to syslog (Event Log on Windows).
;mail.log = syslog
```

### Gestion du service

1. Démarrer le service Php :

    ```
    apachectl start
    ```
2. Stopper le service Php :

    ```
    apachectl stop
    ```

3. Redémarrer le service Php :

    ```
    apachectl restart
    ```
    
## Xdebug

Si besoin, la doc. **Xdebug** se trouve ici : [https://xdebug.org/docs/install#pecl](https://xdebug.org/docs/install).

### Installation

Afin de pouvoir installer **Xdebug** sur macOS, il est nécessaire d'avoir **Homebrew** et **PECL** d'installer.

> **NB : PECL** est nativement installé sur macOS, tel que **PHP**.

Vérifions cela :

##### ==> **Hombrew** avec la commande `brew`.

```
~ % brew

Example usage:
  brew search TEXT|/REGEX/
  brew info [FORMULA|CASK...]
  brew install FORMULA|CASK...
  brew update
  brew upgrade [FORMULA|CASK...]
  brew uninstall FORMULA|CASK...
  brew list [FORMULA|CASK...]

Troubleshooting:
  brew config
  brew doctor
  brew install --verbose --debug FORMULA|CASK

Contributing:
  brew create URL [--no-fetch]
  brew edit [FORMULA|CASK...]

Further help:
  brew commands
  brew help [COMMAND]
  man brew
  https://docs.brew.sh
```

##### ==> **PECL** avec la commande `pecl `

```
~ % pecl

Commands:
build                  Build an Extension From C Source
bundle                 Unpacks a Pecl Package
channel-add            Add a Channel
channel-alias          Specify an alias to a channel name
channel-delete         Remove a Channel From the List
channel-discover       Initialize a Channel from its server
channel-info           Retrieve Information on a Channel
channel-login          Connects and authenticates to remote channel server
channel-logout         Logs out from the remote channel server
channel-update         Update an Existing Channel
clear-cache            Clear Web Services Cache
config-create          Create a Default configuration file
config-get             Show One Setting
config-help            Show Information About Setting
config-set             Change Setting
config-show            Show All Settings
convert                Convert a package.xml 1.0 to package.xml 2.0 format
cvsdiff                Run a "cvs diff" for all files in a package
cvstag                 Set CVS Release Tag
download               Download Package
download-all           Downloads each available package from the default channel
info                   Display information about a package
install                Install Package
list                   List Installed Packages In The Default Channel
list-all               List All Packages
list-channels          List Available Channels
list-files             List Files In Installed Package
list-upgrades          List Available Upgrades
login                  Connects and authenticates to remote server [Deprecated in favor of channel-login]
logout                 Logs out from the remote server [Deprecated in favor of channel-logout]
makerpm                Builds an RPM spec file from a PEAR package
package                Build Package
package-dependencies   Show package dependencies
package-validate       Validate Package Consistency
pickle                 Build PECL Package
remote-info            Information About Remote Packages
remote-list            List Remote Packages
run-scripts            Run Post-Install Scripts bundled with a package
run-tests              Run Regression Tests
search                 Search remote package database
shell-test             Shell Script Test
sign                   Sign a package distribution file
svntag                 Set SVN Release Tag
uninstall              Un-install Package
update-channels        Update the Channel List
upgrade                Upgrade Package
upgrade-all            Upgrade All Packages [Deprecated in favor of calling upgrade with no parameters]
Usage: pecl [options] command [command-options] <parameters>
Type "pecl help options" to list all options.
Type "pecl help shortcuts" to list all command shortcuts.
Type "pecl help version" or "pecl version" to list version information.
Type "pecl help <command>" to get the help for the specified command.
```

Une fois **PECL** et **HomeBrew** installés, il faut est maintenant possible d'installer **Xdebug** grâce à **PECL**

```
pecl install xdebug

ou

pecl install xdebug-<version>
```

> Pour **PHP** 7.1.33, la version 2.9.8 de **Xdebug** est bien compatible.
> Nécessaire pour **Valet** non compatible avec **PHP** 7.2 ou +.

L'installation devrais se terminée avec le message ci-dessous :

```
Build process completed successfully
Installing '/usr/local/Cellar/php/8.1.5/pecl/20210902/xdebug.so'
install ok: channel://pecl.php.net/xdebug-3.1.4
Extension xdebug enabled in php.ini
```