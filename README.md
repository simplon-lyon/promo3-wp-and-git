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
