# CyberPAMZero Trust Network Access

TLDR: No more VPNs, just use Cloudflare Access to access your CyberPAM instance. Hosts no longer need to be in the same network, or have <b>any open ports.</b>

> Yes, CyberPAM and the host do NOT need to be in the same network.

![ZTDrawing](media/drawing.png)


## Setup Requirements

- Assumes you have a CyberPAM instance running already.
- Assumes you have a Cloudflare account and a domain. (free tier is fine)

## Settings Panel Fully Configured

When you having it it all setup, you should see something like this, notice the green globes.  This setup takes less than 15 minutes to complete.

> 💣 Notice red panel, once you set your domain, if you change it you will need to re-register the agents.

![ZT Settings Panel](media/ztsettings.png)



## Cloudflare ZTNA



>*The ZTNA module here works amazing well, however the setup isn't foolproof. Fill in the values and press save, then enable and the engine will start.*


### Add Catchall Policy

You need this policy to secure your hosts, and allow access to your CyberPAM instance.

![alt text](media/ztaddapp.png)
![ztadd](media/ztself.png)
![ztdomain](media/ztdomain.png)
![ztserver](media/ztservice.png)
![ztcatch](media/zt-catchall.png)

### Get your Service Token

You'll need to strip off the CF-Header and CF-Key from the token, and then paste it into the CyberPAM settings panel.

![Get your service token](media/zttoken.png)

### Setup API Access
Take note of the API key, account id, and email, you'll need to paste them into the CyberPAM settings panel. Your permissions should match these here.

![Example API token](media/ztapi.png)

You'll know its working when you see the green globe and your domains populate.

> If you don't see the green globes or the domains don't populate, you'll need to check your API key, account id, and email.

![API Verified](media/ztverifyapi.png)

![List of domains](media/ztlist.png)


## Add Hosts

Lets add a host to our CyberPAM instance.

![zerotrust add host](media/ztadd.png)

![system token](media/systoken.png)

Run the CyberPAM agent on the host, and provide this token. Within a few minutes you should see the host will be added to the list and the tunnel will show it's health under "expanded" view.

https://github.com/RamboRogers/cyberpamagent

### 🐧 Linux & 🍎 macOS

```bash
curl -L https://raw.githubusercontent.com/RamboRogers/cyberpamagent/main/install.sh | sh
```

### 🪟 Windows PowerShell
> *Admin Powershell*
```powershell
iwr -useb https://raw.githubusercontent.com/RamboRogers/cyberpamagent/main/install.ps1 | iex
```

![ZT Install](media/ztinstall.png)

That's it, the agent will install and run as a service. You can uninstall it with `cyberpamagent -uninstall`.

## Lots of Hosts

A example instance with some hosts added.

![Home](media/home.png)


<div align="center">

## ⚖️ License

<p>
CyberPAM is licensed under a restricted license.<p><i> (c)Matthew Rogers 2024. All rights reserved. No Warranty. No Support. No Liability. No Refunds.</p<br>
</i><p>
<em>Free Demo Software</em>
</p>

### Connect With Me 🤝

[![GitHub](https://img.shields.io/badge/GitHub-matthewrogers-181717?style=for-the-badge&logo=github)](https://github.com/matthewrogers)
[![Twitter](https://img.shields.io/badge/Twitter-@rogerscissp-1DA1F2?style=for-the-badge&logo=twitter)](https://x.com/rogerscissp)
[![Website](https://img.shields.io/badge/Web-matthewrogers.org-00ADD8?style=for-the-badge&logo=google-chrome)](https://matthewrogers.org)

![Matthew Rogers](media/ramborogers.png)

</div>