<p align="center">
<table align="center">
  <tr>
    <td align="center" width="50%"><strong>Session Recording</strong></td>
  </tr>
  <tr>
    <td align="center"><img src="media/cyberpam.gif" width="100%" alt="Session Recording Demo"></td>
  </tr>
</table>

<div align="center">
  <h1>CyberPAM</h1>
  <p><strong>Zero Trust Privileged Access Management</strong></p>
  <p>🔐 Zero Trust | 🎥 Session Recording | 🌐 Multi-Protocol | 🔒 ABAC Security | 🎨 Beautiful UI</p>
  <p>
    <img src="https://img.shields.io/badge/version-0.4.0c-blue.svg" alt="Version 0.4.0c">
    <img src="https://img.shields.io/badge/platform-linux%20%7C%20macos-brightgreen.svg" alt="Platform Support">
  </p>
</div>

CyberPAM is a comprehensive Zero Trust Privileged Access Management solution designed for secure access to Windows, UNIX systems, and web applications. With its beautiful dark-themed interface and robust security features, it provides enterprise-grade access control and session monitoring capabilities.

I made CyberPAM for my own use, but I'm happy to share it with the community. I've been working with PAM products for years and CyberPAM is the culmination of my experience.  Session recording is a must have for any PAM product, and CyberPAM is the best I've seen from an Admin perspective, and user experience. Often implementations of PAM products take a long time to get to production, but not CyberPAM.



<p align="center">
<b> ⚡️ v0.4.0c Setup Zero Trust Network Access for CyberPAM Targets/Hosts ⚡️</b>
<table>
<tr>
<td>
<img src="media/tagsdrawing.png" width="100%" alt="Tag Flow">
</td>
<td>
<img src="media/tags.png" width="100%" alt="Tags">
</td>
</tr>
</table>

</p>



<p align="center">
<a href="ZEROTRUST.md"><b> ⚡️ v0.3.0c Setup Zero Trust Network Access for CyberPAM Targets/Hosts ⚡️</b></a>
<table>
<tr>
<td>
<img src="media/pam.png" width="100%" alt="Tag Flow">
</td>
<td>
<img src="media/drawing.png" width="100%" alt="Tags">
</td>
</tr>
</table>
</p>

What is PAM? <a href="https://en.wikipedia.org/wiki/Privileged_access_management">PAM</a> is the process of managing access to resources. It is a critical component of any security architecture.

<p align="center"> <b>⚡️ This is a SINGLE CONTAINER (Docker or Kubernetes) and can go from pull to production in 5 minutes and is PERFECT for a SaaS Product 🚀</b> </p>


## 🚀 Quick Start

CyberPAM is distributed as a Docker container for easy deployment and a 5 minute setup:

### Docker
 *You can just copy paste this into your terminal 🖥️ to deploy or upgrade*
```bash
# Pull the latest image
docker pull mattrogers/cyberpam:latest

docker stop cyberpam
docker rm cyberpam

# Run with basic configuration
docker run -d \
  --name cyberpam \
  -v cyberpamdb:/data \
  -v cyberpamrecordings:/recordings \
  -p 8080:8080 \
  mattrogers/cyberpam:latest

docker logs cyberpam
```

### Kubernetes

```bash
kubectl apply -f kubernetes/deployment-cyberpam.yaml
```

## ⚡️NOTICE - GET YOUR ADMIN PASSWORD👋

Access the web interface at `http://localhost:8080` after starting the container. The initial admin credentials will be displayed in the container logs:

```bash
# View initial admin credentials
docker logs cyberpam
```

![CyberPAM Login](media/password.png)



## 🌟 Features

<table style="width:100%; border-collapse: collapse;">
  <tr>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">Security & Access Control</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>🔒 Zero Trust Architecture with ABAC</li>
        <li>🔑 Multi-factor authentication with mandatory TOTP</li>
        <li>🔍 Granular access control with 4 security levels</li>
        <li>📝 Comprehensive audit logging for compliance</li>
        <li>🎥 Session recording with video playback</li>
        <li>🔐 Password complexity enforcement</li>
        <li>🔍 Tag-based access control</li>
      </ul>
    </td>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">Protocol Support with Session Recording</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>🖥️ RDP (Remote Desktop Protocol)</li>
        <li>🔗 SSH (Secure Shell)</li>
        <li>🌐 HTTP/HTTPS (planned)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">Session Recording</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>📹 Full video recording of all sessions</li>
        <li>🔄 Automatic video conversion</li>
        <li>🔒 Secure storage management</li>
        <li>⏱️ Playback controls with timeline</li>
        <li>⬇️ Download capabilities</li>
        <li>🔐 Access control based on ABAC levels</li>
      </ul>
    </td>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">User Management</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>👤 Local user authentication</li>
        <li>🔑 Role-based access control</li>
        <li>🔒 TOTP (2FA) requirement</li>
        <li>🔐 Password complexity rules</li>
        <li>🕒 Session management</li>
        <li>🚫 Failed attempt tracking</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">Beautiful Interface</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>🌑 Dark-themed modern UI</li>
        <li>🖥️ Matrix-style animations</li>
        <li>📱 Responsive design</li>
        <li>🔗 Protocol-based grouping</li>
        <li>🔑 Role-based navigation</li>
        <li>🖼️ Enhanced modals</li>
      </ul>
    </td>
    <td style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
      <h3 style="margin-top: 0;">Cloudflare Zero Trust Support Built in</h3>
      <ul style="list-style-type: none; padding-left: 0;">
        <li>🔒 Enhanced security with identity-based access</li>
        <li>🌐 Secure access to internal applications without VPN</li>
        <li>🛡️ Protection against data breaches and cyber threats</li>
        <li>🔍 Continuous monitoring and logging of user activity</li>
        <li>🔑 Multi-factor authentication (MFA) enforcement</li>
        <li>📊 Detailed access control policies and reporting</li>
        <li>🚀 Simplified user experience with seamless access</li>
      </ul>
    </td>
  </tr>
</table>

## 🔧️ Security Notice

CyberPAM is designed to be deployed behind a reverse proxy that handles SSL/TLS termination and additional security controls. We recommend:

### SSL/TLS Termination
Use a reverse proxy like Caddy (recommended), Nginx, or Traefik to handle HTTPS:

```bash
# Example Caddyfile configuration
cyberpam.yourdomain.com {
    reverse_proxy localhost:8080
}
```

### Zero Trust Network Access INTO CyberPAM

It's easy to setup a tunnel with Cloudflare Zero Trust into CyberPAM.

<table style="width:100%; border-collapse: collapse;">
<tr>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>1. Navigate to Tunnels</strong><br>
<img src="media/zerotrust.png" alt="Tunnel" width="400"/>
</td>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>2. Add a New Tunnel</strong><br>
<img src="media/addtunnel.png" alt="Add Tunnel" width="400"/>
</td>
</tr>

<tr>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>3. Create Your Tunnel</strong><br>
<img src="media/createtunnel.png" alt="Create Tunnel" width="400"/>
</td>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>4. Copy Your Token</strong><br>
<img src="media/copytoken.png" alt="Get Token" width="400"/>
</td>
</tr>

<tr>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>5. Save Token Details</strong><br>
<img src="media/notepad.png" alt="Extract Token" width="400"/>
</td>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>6. Configure Tunnel</strong><br>
<img src="media/addtoken.png" alt="Add Tunnel" width="400"/>
</td>
</tr>

<tr>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>7. Verify Tunnel Status</strong><br>
<img src="media/configuretunnel.png" alt="Tunnel Added" width="400"/>
</td>
<td align="center" width="50%" style="border: 1px solid #ddd; padding: 10px;">
<strong>8. Set Access Policies</strong><br>
<img src="media/policy.png" alt="Tunnel Status" width="400"/>
</td>
</tr>
</table>

We strongly recommend placing CyberPAM behind a Zero Trust solution such as:
- Cloudflare Zero Trust
- Zscaler Private Access
- Palo Alto Prisma Access

This ensures:
- Identity-based access control
- DDoS protection
- WAF capabilities
- Additional authentication layer
- Network isolation

### Example Architecture
```
Internet -> Cloudflare Zero Trust -> Reverse Proxy (TLS/Cloudflared) -> CyberPAM Container
```

## 🔒 First Time Setup



1. Start CyberPAM
2. Note the initial admin credentials displayed
3. Log in as admin
4. Change password and set up TOTP
5. Begin adding systems and users

## 🎯 Use Cases

- **Privileged Access Management**: Secure access to critical systems
- **Session Monitoring**: Record and audit all user sessions
- **Compliance**: Meet regulatory requirements with comprehensive logging
- **Zero Trust Implementation**: Enforce least-privilege access
- **Remote Access**: Secure remote system management

### Screenshots

<div align="center">
  <table>
    <tr>
      <td><img src="media/welcome.png" alt="Login Screen" width="400"/></td>
      <td><img src="media/systems.png" alt="Systems Dashboard" width="400"/></td>
    </tr>
    <tr>
      <td><img src="media/recordings.png" alt="Session Recordings" width="400"/></td>
      <td><img src="media/users.png" alt="User Management" width="400"/></td>
    </tr>
    <tr>
      <td><img src="media/playback.png" alt="Settings" width="400"/></td>
      <td><img src="media/audit.png" alt="Settings" width="400"/></td>
    </tr>
    <tr>
<td colspan="2"><img src="media/session.png" alt="Session Recording Demo" width="800"/>
</td>
    </tr>
  </table>
</div>

## Version CyberPam 0.4.0c
### Major Features
- **Advanced Tagging System**
  - Tag-based access control for systems and users
  - Hierarchical system organization
  - Improved system grouping and filtering
  - Tag-based search functionality
  - Admin-controlled tag management

- **Enhanced Security**
  - Automatic HTTPS configuration
  - Improved password handling and security
  - Enhanced logging with sensitive data redaction
  - Strengthened error handling and security feedback

- **Usability Improvements**
  - Streamlined connection workflow
  - Improved error messages with modal dialogs
  - Enhanced system card management
  - Better session handling and state management
  - Refined dark theme and UI consistency

- **System Management**
  - Advanced system filtering and organization
  - Improved system card layout and interactions
  - Enhanced system editing capabilities
  - Better protocol-specific configurations

- **Authentication Enhancements**
  - Improved password management workflow
  - Better SSH key handling
  - Enhanced multi-protocol authentication
  - Streamlined connection process

## Version CyberPam 0.3.0c
- ***Added Zero Trust Network Access from Cloudflare Support***
- Added ZTNA Agent https://github.com/RamboRogers/cyberpamagent
- GUI Refactoring and improvements

## Version CyberPam 0.2.0c
- Added Zero Trust Network Access from Cloudflare Support
- Added many missing features, like user reset
- Reworkeded more GUI styling inconsistencies
- Enhanced audit log interface with improved readability and filtering
- Added CSV export functionality for audit logs
- Improved system management interface with expanded/compact views
- Added cyberpunk-themed confirmation dialogs and modals
- Enhanced system deletion process with animated feedback
- Added system name display in recordings view
- Improved date/time formatting in recordings view
- Added version display in settings page
- Enhanced navbar consistency across all pages
- Improved admin status handling and security checks
- Added Cloudflare IP support for better security logging
- Enhanced error handling and user feedback
- Improved mobile responsiveness across all views
- Removed sensitive data from the audit log

## Version CyberPam 0.1.1c

***Please keep the issues and enhancement requests coming!***

- New Recording UI (with status and storage)
  - Fixes issues with transcoding (was scripted)
  - Event driven transcoding with nice UI
- Added SSH Key Authentication
- Added more fonts (bugfix)
- Reworked container storage (db persistence)
  - Allows for easier upgrades and backups
- GUI Improvements and Refactoring

![New Recording](media/recordings2.png)

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


