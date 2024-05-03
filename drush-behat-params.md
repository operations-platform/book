---
description: Zero-config behat command using Drush.
---

# Drush Behat Params

{% embed url="https://github.com/operations-platform/drush-behat-params" %}

To use behat, you have to tell it where your code is and what URL it's running under.

This is very difficult when you have dynamic environments, such as when running pull requests.

This package provides a `drush behat` command that automatically sets the `BEHAT_PARAMS` environment variable to use the file path and URL that Drush itself is using.

With this command, you can even run behat tests remotely using drush aliases, including on hosted platforms like pantheon.

<figure><img src=".gitbook/assets/image.png" alt=""><figcaption><p>Behat tests running in CI environments using GitHub runners.</p></figcaption></figure>

