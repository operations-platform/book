---
description: >-
  Operator Experience (OX) is how a user interacts with and experiences
  developing and operating a service such as a website. The Operations Project
  is a set of tools and practices to improve OX.
---

# Operator Experience: OX

### Definitions

#### Operator Experience: OX

Operator Experience (OX) is how a user interacts with and experiences developing and operating a service such as a website.&#x20;

OX Design is the application of user experience principles to the tools used in development, testing, deployment, & monitoring services.

#### Operator Experience Platform: OXP

An "Operator Experience Platform" is any tool that is used to operate services.

Examples of OXPs include Jenkins, Aegir, Acquia Cloud, Pantheon Dashboard, GitHub.com.

### Tools

#### Operations Project

The **Operations Project** is a collection of tools to improve operator and developer experience that, combined, can be used as an Operator Experience Platform.

This started in Drupal, but many tools and principles can be applied elsewhere.&#x20;

#### Components

1. Drupal Modules
   1.  [Site.module](site-manager/) - [https://www.drupal.org/project/site](https://www.drupal.org/project/site)&#x20;

       _Drupal module for tracking and reporting site state._
   2.  [Site Manager](site-manager/) - [https://www.drupal.org/project/site\_manager](https://www.drupal.org/project/site\_manager)

       _CMS for your websites._
2. Hosting Solutions
   1.  [Site Server](operations-site-server.md)

       _Simple web server powered by DDEV and self-hosted GitHub Runners._
   2.  [Site Server GitHub Action](operations-site-server.md)

       _GitHub Action for running sites on Site Server._
3. Developer Tools
   1.  [Ash CLI](ash-drush-alias-shell.md) - [https://github.com/jonpugh/ash](https://github.com/jonpugh/ash)

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

