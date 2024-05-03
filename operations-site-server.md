---
description: Simple hosting with DDEV and Git Runners.
---

# Operations Site Server

Ansible roles for bootstrapping a server to run DDEV sites using GitHub runners.

{% embed url="https://github.com/operations-platform/site-server/" %}

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
