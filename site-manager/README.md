---
description: All about Site Manager and how to use it.
---

# Site Manager

Site Manager is a Drupal module that provides a CMS for your websites.

In addition to URLs, Site Manager stores properties about the site such as Last Cron, Install Time, PHP and Drupal Versions.

Site Manager has an API that allows it to receive site entities from remote sites.

This means that any Drupal site, running anywhere, can post information about itself back to any Site Manager instance, including sites running in CI or behind firewalls.

### Features

#### Site Entities

Site entities are Drupal content entities that store properties such as PHP and Drupal version as fields.

This means that you can use any Drupal site building API to create your own Site Manager Dashboard.

#### Site Entity Revisions

Site entities have revisions for tracking site information over time. Event handlers can trigger a site revision, including a log message. This provides a history of changes over time, including what configuration changes occured.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

#### Remote Site Entities

Site Manager uses Drupal's JSON:API to receive site entities from remote locations.

Drupal sites with Site.module installed can do this out of the box using the Site Manager URL and an API key.

Non-Drupal systems can also post site information to a Site Manager via JSON:API. See the [Drupal.org JSON:API documentation](https://www.drupal.org/docs/core-modules-and-themes/core-modules/jsonapi-module/creating-new-resources-post) for general information.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption><p>Manage sites like content. Add site.module to give a site the ability to post itself back to a Site Manager.</p></figcaption></figure>

