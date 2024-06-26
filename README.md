---
description: >-
  The Operations Experience Project is a collection of tools and practices to
  improve operator and developer experience.
---

# Operations Experience Project

This started in Drupal, but many tools and principles can be applied elsewhere.&#x20;

[What is OX?](ox-operator-experience/)

{% embed url="https://github.com/operations-project" %}

### Components

1. Drupal Modules
   1.  [Site.module](operations-tools/site-module-and-site-manager.md) - [https://www.drupal.org/project/site](https://www.drupal.org/project/site)&#x20;

       _Drupal module for tracking and reporting site state._
   2.  [Site Manager](operations-tools/site-module-and-site-manager.md) - [https://www.drupal.org/project/site\_manager](https://www.drupal.org/project/site\_manager)

       _CMS for your websites._
2. Hosting Solutions
   1.  [Site Server](operations-site-server/)

       _Simple web server powered by DDEV and self-hosted GitHub Runners._
   2.  [Site Server GitHub Action](operations-site-server/)

       _GitHub Action for running sites on Site Server._
3. Developer Tools
   1.  [Ash CLI](operations-tools/ash-drush-alias-shell.md) - [https://github.com/jonpugh/ash](https://github.com/jonpugh/ash)

       _The Alias Shell._

       * Replacement for global drush.
       * Runs commands on remote servers and sites.
   2.  Drush Behat Params - [https://github.com/operations-platform/drush-behat-params](https://github.com/operations-platform/drush-behat-params)

       _Simplified Behat config._
   3.  OperationsDrupalContext (TODO).

       _Better behat test failure reporting._&#x20;
4. Composer Packages
   1.  Operations Scripts - [https://github.com/operations-platform/scripts](https://github.com/operations-platform/scripts)

       _Simple bash scripts to make scripting prettier._
   2.  Composer Project Bin Scripts - [https://github.com/operations-platform/composer-project-bin-scripts](https://github.com/operations-platform/composer-project-bin-scripts)

       _Add scripts to bin dir of composer projects._
   3.  Composer Remote Bin Scripts - [https://github.com/operations-platform/composer-project-bin-scripts](https://github.com/operations-platform/composer-project-bin-scripts)

       _Install remote scripts to bin dir._
   4.  Drupal Settings - [https://github.com/operations-platform/drupal-settings](https://github.com/operations-platform/drupal-settings)

       _Universal settings.php. NEEDS WORK! PRs for different hosting platforms are welcome._
   5.  Git Split - [https://github.com/operations-platform/git-split](https://github.com/operations-platform/git-split)

       _Simple tool for pushing sub packages from a monorepo._

Created by Jon Pugh.