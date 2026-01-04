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
- **Instance ID:** `4a6c6e36-544d-49ca-992f-67a79ba914a0` (destroyed to save costs)
- **Snapshot ID:** `a2fd2438-2521-41d4-8863-ebf63c0a4e64`
- **Snapshot Name:** "Ubuntu with VS Code and VNC - Jan 4 2026"

## Quick Commands

### Restore Instance from Snapshot
```bash
# Check snapshot status
curl -H "Authorization: Bearer SBT7CM7CXAY7CAL6UTSVHQMLHUZN6LG6NTHQ" \
  "https://api.vultr.com/v2/snapshots/a2fd2438-2521-41d4-8863-ebf63c0a4e64"

# Create new instance from snapshot
curl -X POST -H "Authorization: Bearer SBT7CM7CXAY7CAL6UTSVHQMLHUZN6LG6NTHQ" \
  -H "Content-Type: application/json" \
  -d '{"region":"ord","plan":"vc2-4c-8gb","snapshot_id":"a2fd2438-2521-41d4-8863-ebf63c0a4e64"}' \
  "https://api.vultr.com/v2/instances"
```

### Destroy Instance
```bash
curl -X DELETE -H "Authorization: Bearer SBT7CM7CXAY7CAL6UTSVHQMLHUZN6LG6NTHQ" \
  "https://api.vultr.com/v2/instances/YOUR_INSTANCE_ID"
```

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
