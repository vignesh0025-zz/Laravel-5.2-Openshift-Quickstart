# Laravel-5.2-Openshift-Quickstart
This adds Laravel 5.2 Support in Openshift. 
[Laravel](http://laravel.com/) is a free, open source PHP web application framework, 
designed for the development of model–view–controller (MVC) web applications.

This QuickStart was created to make it easy to get started with Laravel 5.2 on
OpenShift.

### Credits 

Almost all credits goes to [luciddreamz (For Laravel Openshift action hooks)](https://github.com/luciddreamz/laravel). I just configured NGINX and PHP(5.6.16) and Laravel 5.2 Support.

- [Warnar Boekkooi (For NGINX Cartridge)](https://github.com/boekkooi/openshift-cartridge-nginx)
- [Warnar Boekkooi (For PHP Cartridge)](https://github.com/boekkooi/openshift-cartridge-php)
- [luciddreamz (For Laravel Openshift action hooks)](https://github.com/luciddreamz/laravel)
- [Djordje Kovacevic (For the actual procedure)](http://djordjekovacevic.com/articles/run-laravel-5.1-on-openshift)

## OpenShift Considerations ##
These are some special considerations you may need to keep in mind when
running your application on OpenShift.

### NGINX Configuration
- see __.openshift/nginx.conf.erb__ for nginx server configuration

### Local .env file
Copy paste .env.example to .env and make your changes to it. __.env__ file will not be included in GIT. Also make sure to include the variables to be mentioned in __.env.example__ file, incase you work in team. 

### Local vs. Remote Development ###
This Laravel QuickStart provides separate `.env` configuration files for both local and 
remote development, found at `.env` and `.openshift/.env` respectively. When the local 
repo is pushed to OpenShift `.env` is overwritten with the `.openshift/.env` file.

### Remote Development ###
Your application is configured to automatically use your OpenShift MySQL or PostgreSQL 
database in when deployed on OpenShift using [OpenShift Environment Variables](https://developers.openshift.com/en/managing-environment-variables.html).

Additionally, your `APP_ENV`, `APP_URL`, and `APP_KEY` will be set automatically in 
production on OpenShift.

The Laravel `CACHE_DRIVER` is set to use [APC opcode caching](http://php.net/manual/en/book.apc.php)
and the `SESSION_DRIVER` is set to use the local file system for storage. Feel 
free to update these settings in `.openshift/.env`.

### Laravel Migrations ###
When the application is pushed to OpenShift, `php artisan migrate --force` is automatically executed.

### Composer ###
When the application is pushed, `composer install` is automatically executed over the root directory. See [PHP Markers](https://developers.openshift.com/en/php-markers.html) for more details on the 'use_composer' marker.

### 'Development' Mode ###
When you develop your Laravel application in OpenShift, you can also enable the
'development' environment by setting the `APPLICATION_ENV` environment variable,
using the `rhc` client, like:

```
$ rhc env set APPLICATION_ENV=development -a <app-name>
```

Then, restart your application:

```
$ rhc app restart -a <app-name>
```

If you do so, OpenShift will run your application under 'development' mode.
In development mode, your application will:

* Set Laravel's `APP_ENV` to 'development' and `APP_DEBUG` to 'true'
* Ignore your composer.lock file
* Show more detailed errors in browser
* Display startup errors
* Enable the [Xdebug PECL extension](http://xdebug.org/)
* Enable [APC stat check](http://php.net/manual/en/apc.configuration.php#ini.apc.stat)

Set the variable to 'production' and restart your app to deactivate error reporting 
and resume production PHP settings.

Using the development environment can help you debug problems in your application
in the same way as you do when developing on your local machine. However, we strongly 
advise you not to run your application in this mode in production.

### Log Files ###
Your application is configured to use the OpenShift log directory. You can use the 
`rhc tail` command to stream the latest log file entries:

```
rhc tail -a <APP_NAME>
```

To stop tailing the logs, press *Ctrl + c*.

### Installation 

- Login to http://www.openshift.com
- Press the below Deploy Link to go to Application Creation Page. Just fill the name and Scaling options and create. Simple as that. Enjoy. 

<center>
<h2>
<a href="https://openshift.redhat.com/app/console/application_type/custom?name=Laravel52&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-nginx&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-php&cartridges[]=mysql-5&initial_git_url=https://github.com/vignesh0025/Laravel-5.2-Openshift-Quickstart" target="_blank">DEPLOY</a>
</h2>
</center>

## Additional Resources ##
Documentation for the Laravel framework can be found on the [Laravel website](http://laravel.com/docs). Check 
out OpenShift's [Developer Portal](https://developers.openshift.com/en/php-overview.html) for help running PHP on OpenShift.
