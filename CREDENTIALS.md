# Vultr Server Access Credentials

## Server Information
- **IP Address:** 45.76.29.60
- **OS:** Ubuntu 25.10 x64
- **Region:** ORD (Chicago)
- **Specs:** 4 vCPU, 8GB RAM, 160GB Disk

## Access Methods

### 1. SSH Access
```bash
ssh root@45.76.29.60
```
- **Password:** `}4yYHe(*m(F4qMC)`

### 2. VS Code (Browser)
- **URL:** http://45.76.29.60:8080
- **Password:** `ac2bc305a9480589a3aeb2fb`

### 3. VNC Access (Remote Desktop)
- **Address:** `45.76.29.60:5901`
- **Password:** `vultr2026`
- **Resolution:** 1920x1080
- **Desktop:** XFCE4

**VNC Clients:**
- Windows: RealVNC, TightVNC, UltraVNC
- Mac: RealVNC Viewer, Screen Sharing (vnc://45.76.29.60:5901)
- Linux: Remmina, TigerVNC

### 4. Vultr API
- **API Key:** `SBT7CM7CXAY7CAL6UTSVHQMLHUZN6LG6NTHQ`
- **Instance ID:** `4a6c6e36-544d-49ca-992f-67a79ba914a0`

## Quick Commands

### Restart VNC Server
```bash
vncserver -kill :1
vncserver :1 -geometry 1920x1080 -depth 24
```

### Restart Code-Server
```bash
systemctl restart code-server@root
```

### Check Services Status
```bash
systemctl status code-server@root
vncserver -list
```

## Notes
- VNC password is limited to 8 characters by design
- Code-server auto-starts on boot
- VNC server needs manual restart after reboot
- All services are running as root user

---
**Created:** January 4, 2026
