# Laravel-5.2-Openshift-Quickstart
This adds Laravel 5.2 Support in Openshift. 

### Credits 

- [Warnar Boekkooi (For NGINX Cartridge)](https://github.com/boekkooi/openshift-cartridge-nginx)
- [Warnar Boekkooi (For PHP Cartridge)](https://github.com/boekkooi/openshift-cartridge-php)
- [luciddreamz (For Laravel Openshift action hooks)](https://github.com/luciddreamz/laravel)
- [Djordje Kovacevic (For the actual procedure)](http://djordjekovacevic.com/articles/run-laravel-5.1-on-openshift)

### Configuration
- see __.openshift/nginx.conf.erb__ for nginx server configuration
- Refer the following https://github.com/luciddreamz/laravel#laravel-50-on-openshift for information on setting up __.env__ for the application
- In short, .env in laravel root is used only for local environment.
- When pushed to openshift, .env in root is overwritter with .openshift/.env file (__Database and Application Environment variables are setup already for Production in openshift environment in .openshift/.en file__)
- If at all any additional variable to be setup for __production, add it to .openshift/.env__. 
- Read the README at the link above for detailed Information 

### Installation 

- Login to http://www.openshift.com
- Press the below Deploy Link to go to Application Creation Page. Just fill the name and Scaling options and create. Simple as that. Enjoy. 

<center>
<h1>
<a href="https://openshift.redhat.com/app/console/application_type/custom?name=Laravel52&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-nginx&cartridges[]=http://cartreflect-claytondev.rhcloud.com/github/boekkooi/openshift-cartridge-php&cartridges[]=mysql-5&initial_git_url=https://github.com/vignesh0025/Laravel-5.2-Openshift-Quickstart" target="_blank">DEPLOY</a>
</h1>
</center>
