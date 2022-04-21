# PostFix - Serveur de mail

[<== Retour](../../)

Si tous va bien, PostFix est déjà installer sur MacOS.

## Vérification de la présence de postfix

Avec la commande `postfix` ou `postfix -help`.

On obtiens :

```
postfix: error: to submit mail, use the Postfix sendmail command
postfix: fatal: the postfix command is reserved for the superuser
```

Et, en tant qu'utilisateur `root` : 

```
~ % sudo postfix help
```

On obtiens :

```
postfix: illegal option -- h
postfix: fatal: usage: postfix [-c config_dir] [-Dv] command
```

Postfix est bien présent sur la machine mais n'est pas configuré.

## Configuration

Il faut éditer le fichier `mainc.fr` dans le dossier `/etc/postfix/` de macOS.

Les Lignes a édité sont :

- `myhostname = mailtester`
- `mydomain = ldumay.fr`
- `myorigin = $mydomain`

Afin d'envoyer, les mails à l'adresse type : `<myhostname>@<mydomain>`

Cela donnerais :

```
# INTERNET HOST AND DOMAIN NAMES
# 
# The myhostname parameter specifies the internet hostname of this
# mail system. The default is to use the fully-qualified domain name
# from gethostname(). $myhostname is used as a default value for many
# other configuration parameters.
#
myhostname = mailtester

# The mydomain parameter specifies the local internet domain name.
# The default is to use $myhostname minus the first component.
# $mydomain is used as a default value for many other configuration
# parameters.
#
mydomain = ldumay.fr

# SENDING MAIL
# 
# The myorigin parameter specifies the domain that locally-posted
# mail appears to come from. The default is to append $myhostname,
# which is fine for small sites.  If you run a domain with multiple
# machines, you should (1) change this to $mydomain and (2) set up
# a domain-wide alias database that aliases each user to
# user@that.users.mailhost.
#
# For the sake of consistency between sender and recipient addresses,
# myorigin also specifies the default domain name that is appended
# to recipient addresses that have no @domain part.
#
myorigin = $mydomain
```

## Démarrer (ou redémarrer) PostFix

Une fois la configuration terminé, il faut maintenant le démarré ou le redémarré.

### Redémarrage

```
~ % sudo postfix reload
Password:
postfix/postfix-script: refreshing the Postfix mail system
```

> Si Postfix n'est pas démarrer, vous obtiendrais ce message :
> 
> ```
> postfix/postfix-script: fatal: the Postfix mail system is not running
> ```

### Démarrage

```
~ % sudo postfix start 
Password:
postfix/postfix-script: starting the Postfix mail system
```