# Configuring WordPress With AWS

## Create The Database Schema

```sql
# create the new schema
CREATE SCHEMA cybertooth_io;
# create a new user for any host with the supplied password
CREATE USER 'cybertooth_io'@'%' IDENTIFIED BY '[SOME_PASSWORD]';
# grant all privileges on the new schema for the new user
GRANT ALL PRIVILEGES ON cybertooth_io.* TO 'cybertooth_io'@'%';
```

## Create Certbot Certificate

Before you even run the following command you must have the appropriate
DNS records in place so that Certbot can verify the common name that
you supply.

```bash
sudo /usr/local/bin/certbot-auto --authenticator standalone --installer apache --pre-hook "service httpd stop" --post-hook "service httpd start"
```

1. You'll be asked for the common name you want on the certificate.  Make
sure it matches your DNS name for the server.
1. When asked what to do with the `ssl.conf`, have everything redirect to
https (the second option at time of writing this).

## Open Website In Browser

## `wp_config.php` Changes

```bash
cd /var/www/html

# this configuration constant prevents WordPress from auto-magically updating
wp config set --type=constant --raw AUTOMATIC_UPDATER_DISABLED true

# these configuration constants are for the "WP Mail SMTP"; puts our AWS SMTP
# password into a filesystem configuration file rather than the database in plaintext
# these credentials belong to the AWS IAM user named `aws_ses_mail_user`
wp config set --type=constant --raw WPMS_ON true
wp config set --type=constant WPMS_SMTP_PASS [AWS_SMTP_SECRET_ACCESS_KEY]

# these configuration constants are used to access the S3 bucket for media asset uploads
# these credentials come from the AWS IAM user named `wordpress-s3`
wp config set --type=constant DBI_AWS_ACCESS_KEY_ID [S3_ACCESS_KEY]
wp config set --type=constant DBI_AWS_SECRET_ACCESS_KEY [S3_SECRET_ACCESS_KEY]
```

## Install Some Useful Plugins

```bash
cd /var/www/html
wp plugin delete akismet hello
wp plugin install wp-mail-smtp velvet-blues-update-urls ga-google-analytics wordpress-seo amazon-web-services amazon-s3-and-cloudfront merge-minify-refresh
```

Make sure to reset permissions on the `wp-content` folder:

```bash
sudo chown -R apache:apache /var/www/html/wp-content
sudo chmod 2775 /var/www/html/wp-content
find /var/www/html/wp-content -type d -exec sudo chmod 2775 {} \;
```
