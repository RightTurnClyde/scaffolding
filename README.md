Scaffolding
===========

Boilerplate for starting my CF - FW/1 - DI/1 projects

I often being new projects with the same basic structure and got tired of creating it manually. This configuration
assumes the entire application needs password protected (the most likely scenario for my purposes), starts with
2 basic subsystems (home, admin). 

Authentication is performed against the local LDAP server. If the user is authenticated with LDAP they have access
to the application. If we need to limit the user to only those who have permission to the current application, then need to
write code for that after successful LDAP authentication. This will need to be done in home/services/security.cfc.

Code in this project is designed for ColdFusion 11.

### Before Starting New Project
* Run "bower install" to download front-end dependencies
* Run "npm install" to download/install dev dependencies
    * When developing on Windows the paths in the node_modules folder may be too long to function properly. A fix is to install
"rimraf" package - npm install -g rimraf 
* Run "grunt" to create initial distribution files and folders
* Change the reload password in application.cfc for the production environment
* Change the application.projectName variable in application.cfc
* Change the "name" value in bower.json and package.json files
* Change/add any necessary information in the /config JSON files (change adminEmail is important to receive error reports)
* Run the db.sql script to create the userLog and failedLogins tables. This file can then be removed from the project
