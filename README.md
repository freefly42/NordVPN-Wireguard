# [Wireguard](https://www.wireguard.com) configuration file generator for a [NordVPN](https://nordvpn.com)

A `bash` scripts that generates [Wireguard](https://www.wireguard.com) configuration file for a [NordVPN](https://nordvpn.com) connection.

## INSTALL

This guide assumes the use of [Ubuntu](https://ubuntu.com). A similar install procedure will work on other distros.

### Clone this project

First let's clone this project so that you'll have the script on your target [Ubuntu](https://ubuntu.com) system.

### Install required packages

```bash
sudo apt install wireguard curl jq net-tools
```

### Install [NordVPN](https://nordvpn.com) client

Execute the following command and follow the on screen instructions:

```bash
sh <(curl -sSf https://downloads.nordcdn.com/apps/linux/install.sh)
```

## Login to your [NordVPN](https://nordvpn.com) account

Use `legacy` username and password to login.

> Note: This will NOT work if you have `Multi Factor Authentication` enabled. If you have `MFA` enabled, please disable it, proceed with the login, then re-enable it.

```bash
nordvpn login --legacy​
```

## Change protocol to NordLynx

After a successful login, please set [NordVPN](https://nordvpn.com) to use `NordLynx` protocol.

```bash
sudo nordvpn set technology nordlynx
```

## Generate [Wireguard](https://www.wireguard.com) configuration files

The script is quite simple and can be run without parameters to generate a config file for the recommended server:

```bash
$ ./NordVpnToWireguard.sh
```

Requesting a specific country:

```bash
$ ./NordVpnToWireguard.sh Canada
```

Requesting a specific country and city

```bash
$ ./NordVpnToWireguard.sh Hungary Budapest
```

Requesting a specific server type

```bash
$ ./NordVpnToWireguard.sh Onion_Over_VPN
```

Getting help:

```bash
$ nordvpn connect --help
Usage: NordVpnToWireguard [OPTIONS]
```

## Use the generated [Wireguard](https://www.wireguard.com) configuration files

Import the file/s with the  [Wireguard](https://www.wireguard.com) client in any platform and activate the `VPN`.
