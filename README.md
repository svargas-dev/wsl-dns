# WSL Update/Revert DNS servers

## Background
Due to the way WSL is configured by default some DNS resolutions may fail e.g. [using a VPN](https://github.com/microsoft/WSL/issues/1350) or using Node [dns.resolveMX()](https://stackoverflow.com/questions/65637723/why-is-dns-resolvemx-failing-with-gmail-com)

This repo provides scripts to manually update and revert the DNS server to resolve these issues based on [Microsoft Docs: WSL has no network connectivity once connected to a VPN](https://learn.microsoft.com/en-us/windows/wsl/troubleshooting#wsl-has-no-network-connectivity-once-connected-to-a-vpn) for the default Ubuntu 22.04 on WSL2.

Disclaimer: Use at your own risk! Make sure your read and understand any scripts before running them!

## How to use

There are two scripts:

- `updatedns <IPv4 address e.g. 192.168.0.1>`
   - To get the DNS server open a PowerShell and type `ipconfig.exe /all` and look for the line `DNS Servers . . . . . . . . . . . : x.x.x.x` on the adapter in use
- `revertdns`


One way to use these would be to

```bash
$ mkdir ~/.local/bin && cd ~/.local/bin
$ git clone <url repo> .
$ chmod +x updatedns revertdns
```

Then add the scripts' path to your shell PATHS
