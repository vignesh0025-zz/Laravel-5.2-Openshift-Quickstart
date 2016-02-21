# Laravel-5.2-Openshift-Quickstart
This adds Laravel 5.2 Support in Openshift. 

### Credits 

- [Warnar Boekkooi (For NGINX Cartridge)](https://github.com/boekkooi/openshift-cartridge-nginx)
- [Warnar Boekkooi (For PHP Cartridge)](https://github.com/boekkooi/openshift-cartridge-php)
- [Djordje Kovacevic (For the actual procedure)](http://djordjekovacevic.com/articles/run-laravel-5.1-on-openshift)
- [luciddreamz (For Laravel Openshift action hooks)](https://github.com/luciddreamz/laravel)

### Procedure

- Login to http://www.openshift.com
- Refer the following https://github.com/luciddreamz/laravel#laravel-50-on-openshift for information on setting up __.env__ for the application
- Press the below Deploy Link to go to Application Creation Page. Just fill the name and Scaling options and create. Simple as that. Enjoy. 

#[DEPLOY](https://openshift.redhat.com/app/console/application_type/custom?name=Laravel52&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-nginx&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-php&cartridges[]=mysql-5&initial_git_url=https://github.com/vignesh0025/Laravel-5.2-Openshift-Quickstart)
