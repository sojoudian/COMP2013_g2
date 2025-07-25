# Nginx Configuration for Bridge Network Assignment

This repository contains a predefined `nginx.conf` file for use in your **Debian VM bridge networking assignment**.

## 📌 Purpose

The provided configuration is designed to:

- Serve content from `/var/www/html`
- Listen on port 80
- Add a custom HTTP header: `X-Served-By: bridge_net`
- Work seamlessly with Nginx on Debian-based systems

## 📥 Download Instructions

To use this configuration on your Debian virtual machine:

1. **Install Nginx**:
   ```bash
   sudo apt update
   sudo apt install nginx -y
   ```

2. **(Optional)** Backup the existing configuration:
   ```bash
   sudo cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup
   ```

3. **Download the custom configuration**:
   ```bash
   https://raw.githubusercontent.com/sojoudian/COMP2013_g2/refs/heads/master/nginx.conf
   ```

   > 🔁 Replace `<your-username>` with your actual GitHub username.

4. **Restart Nginx**:
   ```bash
   sudo systemctl restart nginx
   ```

## 📱 Verify on Mobile

1. Ensure your VM is configured with **Bridged Networking** and your host system is connected to your **mobile hotspot**.
2. Access the VM’s IP address from your **phone’s browser**.
3. You should see the default Nginx page or your custom content from `/var/www/html`.

## ✅ Notes

- Hostname must be set to `bridge_net`:
  ```bash
  sudo hostnamectl set-hostname bridge_net
  ```
- Make sure your firewall allows port 80, or disable it temporarily for testing:
  ```bash
  sudo ufw disable
  ```

---

**Instructor**: Maziar Sojoudian  
**Course**: Cloud, Virtualization, or Networking Fundamentals  
**Institution**: Seneca Polytechnic | George Brown College | Humber Polytechnic  
