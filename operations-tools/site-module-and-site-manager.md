---
description: All about Site Manager and how to use it.
---

# Site Module & Site Manager

### Site Module

Site.module is a Drupal module that provides a way to track the state of your website over time.

<figure><img src="../.gitbook/assets/image (1).png" alt="" width="245"><figcaption><p>Site state indicator.</p></figcaption></figure>

In addition to URLs, Site entities store properties about the site such as Last Cron, Install Time, PHP and Drupal Versions.&#x20;

It uses Drupal status report & Site Audit module to determine an overall state of your Drupal site. Create your own simple plugins for storing properties and affect state.&#x20;

Site entity properties are Drupal fields. This means that you can use any Drupal site building API to create your own Site Manager Dashboard.

<figure><img src="../.gitbook/assets/image (2).png" alt="" width="375"><figcaption><p>Site entity teaser. Field and Layout API compatible.</p></figcaption></figure>

Site entities have revisions for tracking site information over time. Event handlers can trigger a site revision, including a log message. This provides a history of changes over time, including what configuration changes occured.

<figure><img src="../.gitbook/assets/image (3).png" alt="" width="375"><figcaption></figcaption></figure>

### Site Manager

Site Manager is used for storing information on many sites in one place. It has an API that allows it to receive site entities from remote sites.

<figure><img src="../.gitbook/assets/image (4).png" alt="" width="375"><figcaption><p>Projects dashboard. Site Manager has entities for Projects and environments</p></figcaption></figure>

Since site.module lets a Drupal site post out from itself, any site hosted anywhere can send updates to a Site Manager. This includes CI environments, even ephemeral ones running in git runners or ones protected from behind a firewall.

<figure><img src="../.gitbook/assets/image (5).png" alt="" width="352"><figcaption></figcaption></figure>

#### Site API

Site Manager uses Drupal's JSON:API to send and receive site entities from remote locations.

Drupal sites with Site.module installed can post information to a Site Manager or any other URL.

Non-Drupal systems can also post site information to a Site Manager via JSON:API. See the [Drupal.org JSON:API documentation](https://www.drupal.org/docs/core-modules-and-themes/core-modules/jsonapi-module/creating-new-resources-post) for general information.





<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption><p>Manage sites like content. Add site.module to give a site the ability to post itself back to a Site Manager.</p></figcaption></figure>

