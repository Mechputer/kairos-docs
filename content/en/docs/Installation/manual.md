---
title: "Manual installation"
linkTitle: "Manual installation"
weight: 1
date: 2022-11-13
description: >
  Install Kairos manually
---

To install manually, follow the [quickstart]({{< relref "../Getting started" >}}). When the QR code is prompted at the screen, you will be able to log in via SSH to the box with the password `kairos` as `kairos` user.

{{% alert title="Note" %}}

After the installation, the password login is disabled, users, and SSH keys to log in must be configured via cloud-init.

{{% /alert %}}


## Installation

To start the installation, run the following command from the console:

```bash
sudo kairos-agent manual-install --device "auto" $CONFIG
```

Where the configuration can be a `cloud-init` file or a URL to it:

```yaml
#cloud-init

p2p:
  network_token: ....
# extra configuration
```

The token `p2p.network_token` is a base64 encoded string which
contains an [`edgevpn` token](https://github.com/mudler/edgevpn/blob/master/docs/content/en/docs/Concepts/Token/_index.md). For more information, [check out the architecture section]({{< relref "../architecture/network" >}}).

**Note**: 
- The command is disruptive and will erase any content on the drive.
- The parameter **"auto"** selects the biggest drive available in the machine.
