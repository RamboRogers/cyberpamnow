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
    <img src="https://img.shields.io/badge/version-0.1.0c-blue.svg" alt="Version 0.1.1c">
    <img src="https://img.shields.io/badge/go-%3E%3D1.21-00ADD8.svg" alt="Go Version">
    <img src="https://img.shields.io/badge/platform-linux%20%7C%20macos-brightgreen.svg" alt="Platform Support">
    <img src="https://img.shields.io/badge/license-GPLv3-green.svg" alt="License">
  </p>
</div>

CyberPAM is a comprehensive Zero Trust Privileged Access Management solution designed for secure access to Windows, UNIX systems, and web applications. With its beautiful dark-themed interface and robust security features, it provides enterprise-grade access control and session monitoring capabilities.

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
    <td colspan="2" style="vertical-align: top; padding: 10px; border: 1px solid #ddd;">
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
  </tr>
</table>

## 🚀 Quick Start

CyberPAM is distributed as a Docker container for easy deployment and a 5 minute setup:

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

> *As of 0.1.1c, the container was designed to user docker volumes for persistence. You could also use a bind mount to the same effect.*

## ⚡️NOTICE - GET YOUR ADMIN PASSWORD👋

Access the web interface at `http://localhost:8080` after starting the container. The initial admin credentials will be displayed in the container logs:

```bash
# View initial admin credentials
docker logs cyberpam
```

![CyberPAM Login](media/password.png)


### 📂 External Recordings Storage

```
# Run with external recordings storage
docker run -d \
  --name cyberpam \
  -p 8080:8080 \
  -v /your/local/path:/recordings \
  mattrogers/cyberpam:latest
```

The `/recordings` volume binding is optional but recommended for:
- Persistent storage of session recordings outside the container
- Easy access to recording files for backup
- Sharing recordings between container recreations
- Integration with external video processing tools



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

### Zero Trust Network Access
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
  </table>
</div>

## 🔜 Roadmap

1. HTTP Protocol Support
   - Browser isolation
   - Security controls
   - Recording support

2. Enhanced Security
   - External authentication
   - Certificate management
   - Enhanced audit
   - Security scanning

3. Performance Optimization
   - Connection pooling
   - Load balancing
   - Resource management
   - Cache implementation

4. Advanced Features
   - Search functionality
   - Advanced filtering
   - Batch operations
   - Report generation

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

![Matthew Rogers](media/ramborogers.gif)

</div>
