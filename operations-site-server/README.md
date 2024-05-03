---
description: Simple hosting with DDEV and Git Runners.
---

# Operations Site Server

GitHub workflows for private self-hosted hosting and testing environments.



{% embed url="https://github.com/operations-platform/site-server/" %}
Server installation scripts
{% endembed %}

{% embed url="https://github.com/operations-project/site-server-ddev" %}
GitHub Action for launcing a site with DDEV
{% endembed %}

### Examples

#### Continuously Deploy `main` branch to a live site.

```yaml
# ./github/workflows/deploy.yml
name: Deploy to live
on:
  push:
    branches:
      - main
jobs:
  build:
    name: Deploy site
    runs-on: yourserver.com
    environment:
      name: "live"
      url: "http://www.yoursite.com?${{ github.run_id }}"
    steps:
    - uses: operations-platform/site-server-ddev@main
      with:
        path: projects/yoursite.com/live
        git-reference: main
        ddev-fqdns: yoursite.com,live.yoursite.com
```

#### Deploy Preview Environments

```yaml
# ./github/workflows/pull-request-environment.yml
name: Deploy to Preview
on: [pull_request]
jobs:
  build:
    name: Deploy Site
    runs-on: yourserver.com
    environment:
      name: "pr${{ github.event.number }}"
      url: "http://pr${{ github.event.number }}.ci.yoursite.com?${{ github.run_id }}"
    steps:
    - uses: operations-platform/site-server-ddev@main
      with:
        sync: yes
        ddev-project-tld: ci.yoursite.com
        ddev-project-name: pr${{ github.event.number }}
```

#### Delete Preview Environment

```yaml
name: Delete Pull Request Environment

on:
  pull_request:
    types:
      - closed

env:
  DDEV_PROJECT_PATH_FULL: "/var/platform/Sites/${{ github.repository }}/pr${{ github.event.number }}"
  
jobs:
  delete:
    name: Delete Environment
    runs-on: yourserver.com

    steps:
      - name: Remove site
        working-directory: ${{ env.DDEV_PROJECT_PATH_FULL }}
        run: |
          ddev remove --remove-data --omit-snapshot

      - name: Remove code
        working-directory: ${{ env.DDEV_PROJECT_PATH_FULL }}
        run: |
          rm -rf ${{ env.DDEV_PROJECT_PATH_FULL }}
```

#### Run Cron

```yaml
name: Drupal Cron
on:
  schedule:
    - cron: '45 * * * *'

jobs:
  cron:
    name: Drupal Cron
    runs-on: yourserver.com
    steps:    
      - name: Run cron
        working-directory: projects/yoursite.com/live
        run: |
          ddev drush cron -v
          ddev drush status
```



### Features

#### DDEV powered sites on the internet

<figure><img src="../.gitbook/assets/image (21).png" alt=""><figcaption><p>The <code>ddev list</code> command run on an Operations Site Server.</p></figcaption></figure>

#### GitHub Actions for everything

<figure><img src="../.gitbook/assets/image (16).png" alt=""><figcaption><p>GitHub Repository Actions interface.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (17).png" alt=""><figcaption><p>Deployment task running from private server in GitHub UI.</p></figcaption></figure>

#### Cron runs

Gain transparency into your cron process by using scheduled GitHub actions.

<figure><img src="../.gitbook/assets/image (18).png" alt=""><figcaption><p>Cron runs brought to you by: GitHub Actions!</p></figcaption></figure>

#### Pull Request & Deployments Integration

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>Use the GitHub interface for quickly making changes and submitting a pull request</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (26).png" alt=""><figcaption><p>GitHub users get real-time feedback on the deployment of their code.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (27).png" alt=""><figcaption><p>Immediate and direct access to easy-to-read logs, with links to running sites.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (20).png" alt=""><figcaption><p>GitHub Pull Requests with Commit Checks and Deployments API integration. "View Deployment" is a direct link to the site</p></figcaption></figure>

#### Environments & Deployments

By using GitHub Workflows, integration with Commit Statuses, Deployment API, and Environments is seamless. No custom code, no API integration.

<figure><img src="../.gitbook/assets/image (23).png" alt=""><figcaption><p>GitHub's Environment interface shows every deployment to every environment.</p></figcaption></figure>

#### Secrets

Store all sensitive info in GitHub repository secrets. Allows users to replace values when needed, such as for custom HTTPS certificates.

<figure><img src="../.gitbook/assets/image (22).png" alt=""><figcaption></figcaption></figure>

### Server Install

The repo contains Ansible roles to prepare a server for running sites like this:

1. Users.&#x20;
   * Configures users from GitHub usernames with Sudo and SSH access.
   * Creates a `platform` user for cloning code, running jobs, and launching sites.
2. DDEV.&#x20;
   1. Installs and configures DDEV for "casual hosting".
3. GitHub Runners
   1. Installs and configures GitHub runners as a service.&#x20;

Once installed, your server is ready to react to git pushes, running jobs from GitHub workflow config files as the `platform` user.

With the right GitHub workflow config, PREs will be automatically created for Pull Requests, and environments can be created manually.

### Site Server DDEV Action

GitHub action for deploying sites wtih DDEV.

{% embed url="https://github.com/operations-platform/site-server-ddev" %}
