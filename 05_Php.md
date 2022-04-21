# Php

[<== Retour](../../)

## Configuration du Php.ini

Le fichier `php.ini` se trouve dans le dossier `/usr/local/etc/php/<votre_version>`.

## Configuration

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

## Gestion du service

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