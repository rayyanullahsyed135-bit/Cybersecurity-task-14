# Cybersecurity-task-14- Linux Server Hardening & Secure Configuration
1. Review Default Linux System Settings

Checked existing users using cat /etc/passwd

Reviewed running services using systemctl list-units --type=service

Identified open ports using ss -tuln

2. Remove Unused Users & Restrict Sudo Access

Identified unused accounts

Removed unused users with: sudo deluser username

Restricted sudo access by editing /etc/sudoers using visudo

Applied least privilege principle by allowing only required commands

3. Disable Root Login & Secure SSH

Disabled root login by editing /etc/ssh/sshd_config
PermitRootLogin no

Enabled key-based authentication
PasswordAuthentication no

Restarted SSH service
sudo systemctl restart ssh

4. Update System & Enable Automatic Updates

Updated packages: sudo apt update && sudo apt upgrade -y
Enabled automatic security updates: sudo apt install unattended-upgrades, sudo dpkg-reconfigure unattended-upgrades

5. Configure Firewall
Enabled UFW firewall: sudo ufw enable

Allowed required services only: 
sudo ufw allow ssh
sudo ufw allow http
sudo ufw allow https

Verified firewall status: sudo ufw status 

6. Disable Unnecessary Services

Identified unused services
Disabled them using:
sudo systemctl stop service_name
sudo systemctl disable service_name

7. Secure File Permissions

Checked permissions for sensitive files
Secured important configuration files: 
sudo chmod 600 /etc/shadow
sudo chmod 644 /etc/passwd

8. Review System Logs
Monitored authentication logs: sudo tail -f /var/log/auth.log
Reviewed system activity for anomalies




