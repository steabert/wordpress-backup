# backup-wordpress
Backup script for a WordPress site

## installation
Simply place the script in a directory of your choice
(preferably one that is in the PATH variable).

## configuration
Configuring the script requires setting a few variables in the beginning.
Below is a simple example for an Amazon EC2 server:

    SSH_USER="ec2-user"
    SSH_HOST="ec2-xx-xx-xxx-xxx...amazonaws.com"
    SSH_KEY="$HOME/.ssh/ec2.pem"
    SRC_DIR="/var/www/html/wordpress-site"
    WP_USER="wordpress_user"
    WP_PASS="wordpress_password"
    WP_DB="wordpress_database"
    BINLOG_DIR="/path/to/mysql-binlog"

    BACKUP_DIR="/backups/wordpress"

## usage

    backup-wordpress [-h] [options]

    options:
      -v           verbose output
      -n           perform a dry-run, no backup is made
      -l level     level of the backup: 0 = full backup,
                   higher levels hardlink unchanged files
                   agains the most recent level that was
                   1 lower (default = 0)
