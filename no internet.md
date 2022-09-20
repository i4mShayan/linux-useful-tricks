# Wifi/Lan connected but no Internet connection

<h2>Solution #1 (ProtonVPN)</h2>
This problem mostly happen after using VPNs specially ProtonVPN


If ProtonVPN is the case you can try disconnecting using cli version:

```bash
protonvpn-cli disconnect
```


<h2>Solution #2</h2>
If that didn't work try editing /etc/resolv.conf.

firstly we make a backup of that!
```bash
sudo cp /etc/resolv.conf /etc/resolv.conf.backup
```

then we obviously will open it!

```bash
sudo nano /etc/resolv.conf
```

now clear it up and put these lines into it: 

```text
nameserver 8.8.8.8
nameserver 8.8.4.4
```

and save it!
Done!


<h2>Solution #3 (OpenVPN)</h2>

If this happend after using OpenVPN do this:

```bash
sudo killall openvpn
```
If that didn't work do this:

```bash
pgrep openvpn | xargs sudo kill -9
```

