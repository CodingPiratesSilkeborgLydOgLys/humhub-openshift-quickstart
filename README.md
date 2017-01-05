# Humhub on openshift

HumHub is a feature rich and highly flexible OpenSource Social Network Kit written in PHP.

Find more information at: http://www.humhub.org

### Install with one click


Create an account at http://openshift.redhat.com/

[![Click to install OpenShift](http://launch-shifter.rhcloud.com/launch/light/Click to install.svg)](https://openshift.redhat.com/app/console/application_types/custom?cartridges[]=php-5.4&cartridges[]=mysql-5.5&initial_git_url=https://github.com/CodingPiratesSilkeborgLydOgLys/humhub-openshift-quickstart&name=humhub)

Note:
Cartridges used:
- php-5.4
- mysql-5.5

TODO:
humhub is added as a dep. git and may not work: find out with first Install with one click
check requirements 
General Requirements:
PHP 5.4+
MySQL
Shell access (e.g. ssh) to server
Apache 2.x
PHP CUrl Extension (w/ SSL Support) http://de1.php.net/manual/en/curl.setup.php
PHP Multibyte String Support http://php.net/manual/en/mbstring.setup.php
PHP PDO MySQL Extension (http://www.php.net/manual/en/ref.pdo-mysql.php)
PHP Zip Extension (http://php.net/manual/en/book.zip.php)
PHP EXIF Extension (http://php.net/manual/en/book.exif.php)
PHP INTL Extension (http://php.net/manual/en/intro.intl.php)
PHP FileInfo Extension (http://php.net/manual/en/fileinfo.installation.php)

### Installing via the command line


Create a PHP application :

	rhc app create humhub php-5.4

You can also use any other custom name instead of 'humhub'. Remember to use that app name in the next command

Add this upstream grav quickstart repo

	cd humhub
	rm php/index.php
	git remote add upstream -m master git://github.com/gautamkrishnar/grav-openshift-quickstart.git
	git pull -s recursive -X theirs upstream master

Push the repo upstream to OpenShift

	git push        

Head to your application at:

	http://humhub-$yourdomain.rhcloud.com

To give your new humhub site a web address of its own, add your desired alias:

	rhc app add-alias -a humhub --alias "$whatever.$mydomain.com"

Then add a cname entry in your domain's dns configuration pointing your alias to $whatever-$yourdomain.rhcloud.com.

