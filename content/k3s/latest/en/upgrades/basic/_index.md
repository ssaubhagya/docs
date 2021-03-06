---
title: "Upgrade Basics"
weight: 10
---

You can upgrade K3s by using the installation script, or by manually installing the binary of the desired version.

>**Note:** When upgrading, upgrade server nodes first one at a time, then any worker nodes.

### Upgrade K3s Using the Installation Script

To upgrade K3s from an older version you can re-run the installation script using the same flags, for example:

```sh
curl -sfL https://get.k3s.io | sh -
```

If you want to upgrade to specific version you can run the following command:

```sh
curl -sfL https://get.k3s.io | INSTALL_K3S_VERSION=vX.Y.Z-rc1 sh -
```

### Manually Upgrade K3s Using the Binary

Or to manually upgrade K3s:

1. Download the desired version of the K3s binary from [releases](https://github.com/rancher/k3s/releases)
2. Copy the downloaded binary to `/usr/local/bin/k3s` (or your desired location)
3. Stop the old k3s binary
4. Launch the new k3s binary

### Restarting K3s

Restarting K3s is supported by the installation script for systemd and OpenRC.

**systemd**

To restart servers manually:
```sh
sudo systemctl restart k3s
```

To restart agents manually:
```sh
sudo systemctl restart k3s-agent
```

**OpenRC**

To restart servers manually:
```sh
sudo service k3s restart
```

To restart agents mantually:
```sh
sudo service k3s-agent restart
```
