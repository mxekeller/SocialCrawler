### Install ###
The controller is dependent on the *[Google Analytics Measurement Protocol library for PHP](https://github.com/theiconic/php-ga-measurement-protocol)* 
, installed via (Composer)[https://getcomposer.org]: `php composer.phar install`

Install and configure **MariaDB** and **TokuDB** storage engine. Create a database an populate it with the schema from `bootstrap/bare.sql`. Add a user that has access permissions for the schema. 

Don't forget to set all variables in `bootstrap/config.default.php` and save it as `./config.php`.

Disable IPv6 if you plan to run the controller and the agent on the same machine. Otherwise pulling posts from the controller will fail, as the controller uses __INET_ATON(agent_ip)__ to generate a number from the client IP and saves it under the attribute __who__ into the the table __post__ of database. This won't work with an IPv6 address, as the result isn't compatible to the type of the attribute. 

