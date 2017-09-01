# Wordpress And Git
A example on how to save a Wordpress project on Github.

## Create A New Wordpress Instance

1. go to https://fr.wordpress.org/ and get the last Wordpress archive
2. download and extract the archive where you want
3. change the perm of the wordpress folder: `chown -R user:www-data wordpress`
4. rename the wordpress folder to math your site name
5. open your website in the browser and configure your Wordpress instance

## Save Your Site In Github

1. create a new repository on Github and make sure to select a `.gitignore` for Wordpress
2. go to your Wordpress folder in the command line:
    - init a git repo: `git init`
    - set the remote: `git remote add origin <your repo>`
    - pull the repo: `git pull origin master`
    - add all the file to git: `git add --all`
    - commit the change: `git commit`
    - push the change to Github: `git push --set-upstream origin master`
3. celebrate!

## Save The Database

1. go to your Wordpress folder in the command line:
    - dump the content of MySQL: `mysqldump -u user -p database > database.sql`
2. commit and push the change

## Restore The Project

1. clone your repostory
2. create a new database for your website: `mysql -u user -p --execute 'CREATE DATABASE name;'`
3. restore the database: `mysql -u user -p < database.sql`
4. copy `wp-config-sample.php`: `cp wp-config-sample.php wp-config.php`
5. edit `wp-config.php`: set the name of the database, your username, your pass, etc...
6. add the following line to `wp-config.php` to tell Wordpress the new URL of your website:

```
define('WP_HOME','http://example.com');
define('WP_SITEURL','http://example.com');
```