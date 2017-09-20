# vpngate.py

This script allows to use the free VPN service provided by [VPNGate](http://www.vpngate.net/en/) in an easy way. The user just needs to provide the desidered output country, and the script automatically chooses the best server.

After this step, OpenVPN is launched with the proper configuration. The VPN can be terminated by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.

# Usage

Run the script by providing the desired output country:
```
     chmod+x vpngate.py
    ./vpngate.py US

```
Both country codes and country names are supported, as listed on the VPNGate website, e.g.:

    vpngate.py "United Kingdom"

Moreover, the script allows to input countries with **any case** (`Italy`, `italy`, `ItALy` all work) and with **partial names**:
- `Korea` will work for `Korea Republic Of`
- `Russia` will work for `Russian Federation`
- ... and so on

# Demo

Here is a short Youtube video showcasing an example usage:

[![YT video](http://i.imgur.com/WxbOiOT.png)](http://youtu.be/3OFwxkxN_HI)

# Requirements

OpenVPN needs to be installed.

The script should run on any Linux distribution with the Python [Requests](python-requests.org) module installed. The user running the script must be able to run `sudo` commands in order to start `openvpn`.


If you are using a distribution of Linux with access to the Arch User Repository, the simplest way to install is by using the
[openvpn-update-systemd-resolved](https://aur.archlinux.org/packages/openvpn-update-systemd-resolved/) AUR package as this will take care of any updates through your package manager.

Alternatively, the package can be manually installed by running the following:

```
git clone https://github.com/jonathanio/update-systemd-resolved.git
cd update-systemd-resolved
make
```

## How to Enable

Make sure that you have `systemd-resolved` enabled and running:

```
systemctl enable systemd-resolved.service
systemctl start systemd-resolved.service
```