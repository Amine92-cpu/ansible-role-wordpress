# WordPress Ansible Role

Ce rôle installe un serveur WordPress complet avec MariaDB et Apache sur Ubuntu (Debian) et Rocky Linux (RedHat).

## Prérequis

- Ansible 2.9+
- Privilèges `sudo` ou `root` sur les hôtes cibles.
- Module `mysql-python` ou `pymysql` installé sur les hôtes cibles pour la configuration MariaDB.

## Variables du rôle

| Variable | Description | Par Défaut |
|----------|-------------|------------|
| `wp_db_name` | Nom de la base de données | `wordpress` |
| `wp_db_user` | Utilisateur de la base de données | `example` |
| `wp_db_password` | Mot de passe de l'utilisateur DB | `examplePW` |
| `wp_db_root_password` | Mot de passe root MariaDB | `examplerootPW` |
| `wp_version` | Version de WordPress à installer | `latest` |
| `wp_install_dir` | Répertoire d'installation | `/var/www/html` |

## Fonctionnalités

- **Multi-plateforme** : Supporte Debian/Ubuntu et Rocky Linux.
- **Idempotence** : Le rôle peut être exécuté plusieurs fois sans effets de bord.
- **Templates** : Utilisation de templates Jinja2 pour `wp-config.php` et la config Apache.
- **Handlers** : Redémarrage intelligent des services.

## Exemple de Playbook

```yaml
---
- name: Deploy WordPress
  hosts: all
  become: yes
  roles:
    - wordpress
```

## Publication sur Ansible Galaxy

Pour publier ce rôle sur Galaxy :
1. Créez un compte sur [Ansible Galaxy](https://galaxy.ansible.com).
2. Liez votre compte GitHub.
3. Importez le dépôt contenant ce rôle.
