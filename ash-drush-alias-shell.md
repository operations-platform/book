---
description: >-
  The ASH CLI is a simple PHP CLI tool for managing and controlling sites and
  servers via CLI.
---

# ash: Drush Alias Shell

You create an alias file, and use `ash @alias $COMMAND` to run anything you want remotely.

See [https://github.com/jonpugh/ash](https://github.com/jonpugh/ash).

```sh
$ ash @live drush status
                                                                                                                              12:48:01
Drupal version   : 10.2.3                                     
Site URI         : http://thinkdrop.live.ci.thinkdrop.net     
DB driver        : mysql                                      
DB hostname      : db                                         
DB port          : 3306                                       
DB username      : db                                         
DB name          : db                                         
Database         : Connected                                  
Drupal bootstrap : Successful                                 
Default theme    : openingday                                 
Admin theme      : claro                                      
PHP binary       : /usr/bin/php8.2                            
PHP config       : /etc/php/8.2/cli/php.ini                   
PHP OS           : Linux                                      
PHP version      : 8.2.18                                     
Drush script     : /var/www/html/bin/drush                    
Drush version    : 12.4.3.0                                   
Drush temp       : /tmp                                       
Drush configs    : /var/www/html/vendor/drush/drush/drush.yml 
                   /var/www/html/drush/drush.yml              
Install profile  : standard                                   
Drupal root      : /var/www/html/web                          
Site path        : sites/default                              
Files, Public    : sites/default/files                        
Files, Temp      : /tmp                          
```

```sh
$ ash @live ddev composer info                                                                                                                         12:50:29
asm89/stack-cors                               2.2.0
behat/behat                                    3.14.0
behat/gherkin                                  4.9.0
behat/mink                                     1.11.0
                          
```
