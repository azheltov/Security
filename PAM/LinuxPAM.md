# Creating a Linux and PAM-related cheat sheet as a text document
linux_cheat_sheet = """
# Linux and PAM Cheat Sheet

## 1. Linux Basics
### Navigation and File Management
# List files and directories
ls -l

# Change directory
cd <directory_path>

# Create a new directory
mkdir <directory_name>

# Copy a file
cp <source_file> <destination_file>

# Move or rename a file
mv <source_file> <destination_file>

# Delete a file
rm <file_name>

### Permissions
# View file permissions
ls -l

# Change file permissions
chmod 755 <file_name>

# Change file owner
chown <user>:<group> <file_name>

### Processes
# View running processes
ps aux

# Kill a process
kill <process_id>

# View system resource usage
top

## 2. PAM-Related Commands and Concepts
### Common PAM Files
# Location of PAM configuration files
/etc/pam.d/

# Default PAM authentication configuration
/etc/pam.d/common-auth

# PAM access control configuration
/etc/security/access.conf

### PAM Modules
# Lock account after 3 failed login attempts
auth required pam_tally2.so deny=3 unlock_time=600

# Enable multi-factor authentication (e.g., Google Authenticator)
auth required pam_google_authenticator.so

# Execute custom scripts during authentication
auth required pam_exec.so /path/to/script

### SSH and Privileged Access
# Generate SSH key pair
ssh-keygen -t rsa -b 2048 -f ~/.ssh/id_rsa

# Copy SSH public key to a server
ssh-copy-id user@hostname

# Restrict SSH access to specific users
vim /etc/ssh/sshd_config
# Add:
AllowUsers user1 user2

# Restart SSH service
sudo systemctl restart sshd

### PAM Logs and Troubleshooting
# View authentication logs
cat /var/log/auth.log

# Test PAM configuration
pamtester <service> <username> authenticate

### User Management
# Add a new user
sudo useradd -m -s /bin/bash <username>

# Set user password
sudo passwd <username>

# Add user to sudo group
sudo usermod -aG sudo <username>

# Lock or unlock a user account
sudo passwd -l <username>
sudo passwd -u <username>

## 3. Useful PAM Commands
# Check PAM version
pam --version

# List installed PAM modules
ls /lib/security/

# Verify PAM configuration syntax
pamtester <service_name> <username> authenticate
"""

# Saving the content to a text file
file_path = "/mnt/data/Linux_and_PAM_Cheat_Sheet.txt"
with open(file_path, "w") as file:
    file.write(linux_cheat_sheet)

file_path 
'/mnt/data/Linux_and_PAM_Cheat_Sheet.txt'
