# VPN Share

**VPN Share** shares your phone's active VPN connection with other devices
connected via Mobile Hotspot or USB tethering — so your laptop, tablet or
second phone browses through the same VPN, even if it has no VPN of its own.

- Package: `com.ddk.vpnshare`
- Current version: **3.7** (versionCode 11)
- Requires: Android 8+ (min SDK 26), target SDK 34

## What you can do with it

- **Share your VPN over hotspot** — turn on your VPN, turn on your hotspot,
  and every device connected to the hotspot goes through the VPN.
- **Root Mode (Transparent NAT)** — clients need zero setup. The app sets
  up iptables NAT + policy routing, so connected devices work exactly
  like a standard hotspot, but all their traffic goes through your VPN.
  Shows connected clients, a packets-routed counter and diagnostics.
- **Non-Root Mode (Local Proxy)** — no root needed. The app runs an
  embedded HTTP proxy (port 8080) and SOCKS5 proxy (port 1080) on your
  phone; clients set a manual Wi-Fi proxy. Includes a built-in
  "Test proxy on this phone" self-test, optional proxy username/password
  and step-by-step guides for Android, Windows, iOS and macOS.
- **USB tethering** — works over USB tethering too, not just Wi-Fi hotspot.

## How it works

Pick a mode on first launch. Root Mode uses iptables rules and a routing
table to send hotspot traffic into the VPN tunnel. Non-Root Mode runs a
local proxy server on the phone; the client's traffic goes to the proxy,
and the proxy forwards it through the VPN (the device default route).
Your real VPN connection and your phone's own traffic are untouched.

## Install

1. Download **VPN-Share-v3.7.apk** from
   [Releases](https://github.com/SnzLabs/vpn-hotspot-share/releases) and install it.
2. Connect your VPN.
3. Open VPN Share, pick **Root Mode** (rooted phone) or **Non-Root Mode**,
   and turn it on.
4. Connect the other device to your hotspot (Root Mode: nothing else to
   set up; Non-Root Mode: set the manual Wi-Fi proxy to your phone's IP,
   HTTP port 8080 or SOCKS5 port 1080, as shown in the app).

## License

MIT — see [LICENSE](LICENSE).

## Disclaimer

VPN Share is a connectivity tool. It only routes traffic from devices
you connect to your own hotspot through your own VPN. Do not use it to
bypass network policies you are bound by, and keep your proxy
credentials private if you enable proxy authentication.
