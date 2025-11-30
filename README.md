# Connecting to AWS EC2 Windows Instance via RDP

A step-by-step guide demonstrating secure Remote Desktop Protocol (RDP) connection to an AWS EC2 Windows Server instance using key pair authentication.

## 🎯 Project Overview

This project documents the complete process of establishing a secure RDP connection to an AWS EC2 Windows instance, showcasing knowledge of AWS security practices, Windows Server administration, and remote access protocols.

## 🎥 Watch Me Build This Lab

See the complete RDP connection process in action:

[![Watch Me Build This Lab](https://cdn.loom.com/sessions/thumbnails/46b966a0feb347198e716365c2c33f90-with-play.gif)](https://www.loom.com/share/46b966a0feb347198e716365c2c33f90)

**[▶️ Watch Me Build This Lab - Full Video Walkthrough](https://www.loom.com/share/46b966a0feb347198e716365c2c33f90)**

*This video demonstrates the complete EC2 RDP connection process from instance selection to successful remote desktop access.*

## 🔐 Security Highlights

- **Key Pair Authentication** - Secure password decryption using private key
- **Encrypted Credentials** - AWS-encrypted administrator password
- **Remote Access Protocol** - Industry-standard RDP connection
- **Best Practices** - Proper key management and secure connection methods

## 📋 Connection Process

### Step 1: Select EC2 Instance
- Navigated to AWS EC2 Console
- Located target Windows Server instance
- Selected instance for connection
- Verified instance state: **Running**

### Step 2: Access RDP Client Configuration
- Clicked **"Connect"** button on instance details page
- Selected **"RDP Client"** tab
- Chose connection type: **"Connect using RDP Client"**
- Downloaded **Remote Desktop file** (.rdp)

**What this does:**
- Pre-configures connection settings
- Includes public IP/DNS automatically
- Simplifies connection process

### Step 3: Retrieve Administrator Password
- Clicked **"Get Password"** button
- Prepared to decrypt Windows administrator credentials
- Initiated password retrieval process

### Step 4: Upload Private Key
- Clicked **"Upload private key file"** or **"Browse"**
- Selected the `.pem` key pair file created during instance launch
- Uploaded private key for password decryption

**Security Note:** The private key never leaves your local machine during this process.

### Step 5: Decrypt Password
- AWS decrypted the administrator password using uploaded key
- Password displayed in plaintext (temporarily)
- Copied decrypted password to clipboard

**Technical Process:**
```
Encrypted Password + Private Key → Decrypted Administrator Password
```

### Step 6: Launch RDP Connection
- Opened downloaded `.rdp` file in Remote Desktop application
- System prompted for credentials
- Pasted decrypted administrator password
- Username: **Administrator** (default Windows admin account)

### Step 7: Successful Connection
- ✅ RDP connection established
- ✅ Windows Server desktop displayed
- ✅ Full remote access achieved
- ✅ Ready for server configuration and management

## 🖥️ Connection Details

### RDP Configuration
```
Protocol:          Remote Desktop Protocol (RDP)
Port:              3389 (default)
Username:          Administrator
Authentication:    Password (decrypted via key pair)
Connection File:   .rdp (pre-configured)
```

### Security Group Requirements
```
Type:              RDP
Protocol:          TCP
Port Range:        3389
Source:            Your IP address (recommended)
                   or 0.0.0.0/0 (less secure)
```

## 🔧 Technical Components

### AWS Services Used
- **Amazon EC2** - Virtual machine hosting
- **AWS Key Management** - Secure password encryption/decryption
- **Security Groups** - Network access control
- **VPC** - Virtual private cloud networking

### Client Requirements
- **Remote Desktop Client** - Built-in on Windows, downloadable for Mac/Linux
- **Private Key File** - `.pem` format from EC2 key pair
- **Network Access** - Internet connection to AWS region

## 💻 Platform-Specific RDP Clients

### Windows
```
Built-in: Remote Desktop Connection (mstsc.exe)
Location: Start Menu → "Remote Desktop Connection"
```

### macOS
```
Download: Microsoft Remote Desktop from Mac App Store
Free application with full RDP support
```

### Linux
```
Options:
- Remmina (recommended)
- Vinagre
- FreeRDP (command-line)

Install: sudo apt-get install remmina
```

## 🔐 Security Best Practices

### Key Management
- ✅ Store private keys securely (encrypted storage)
- ✅ Never share private key files
- ✅ Use appropriate file permissions (chmod 400 on Linux/Mac)
- ✅ Keep backup of key pair in secure location

### Network Security
- ✅ Restrict RDP access to specific IP addresses
- ✅ Use VPN for additional security layer
- ✅ Enable Network Level Authentication (NLA)
- ✅ Consider AWS Systems Manager Session Manager as alternative

### Password Security
- ✅ Change default administrator password after first login
- ✅ Use strong, complex passwords
- ✅ Enable Windows Firewall
- ✅ Keep Windows Server updated

## 🚀 Alternative Connection Methods

### AWS Systems Manager Session Manager
```
Advantages:
- No open inbound ports required
- No key pair management needed
- Full audit trail in CloudTrail
- Browser-based access

Connection:
AWS Console → Systems Manager → Session Manager → Start Session
```

### AWS Client VPN
```
Benefits:
- Secure VPN tunnel to VPC
- Private IP access
- Enhanced security
- Multi-instance access
```

### Bastion Host / Jump Server
```
Architecture:
Your Computer → Bastion Host → Target EC2 Instance
Provides additional security layer
```

## 📊 Troubleshooting Guide

### Cannot Connect to Instance

**Issue**: Connection timeout or refused

**Solutions:**
```
1. Verify instance is running
   - Check instance state in EC2 console

2. Check Security Group rules
   - Ensure port 3389 is open
   - Verify source IP is allowed

3. Verify Network ACLs
   - Check VPC network ACL settings

4. Confirm public IP/DNS
   - Use correct connection endpoint
```

### Password Decryption Failed

**Issue**: Cannot decrypt administrator password

**Solutions:**
```
1. Verify correct key pair file
   - Must match key pair used at launch

2. Check instance age
   - Password available 4-5 minutes after launch

3. Ensure Windows is fully initialized
   - Wait for instance status checks to pass
```

### RDP Client Issues

**Issue**: RDP application errors

**Solutions:**
```
1. Update RDP client to latest version
2. Check local firewall settings
3. Verify network connectivity
4. Try alternative RDP client
```

## 📈 Skills Demonstrated

### AWS Cloud Services
- ✅ EC2 instance management
- ✅ Security group configuration
- ✅ Key pair authentication
- ✅ AWS Console navigation
- ✅ Password decryption process

### Windows Server Administration
- ✅ Remote Desktop Protocol (RDP)
- ✅ Windows authentication
- ✅ Remote server access
- ✅ Administrator account management

### Security Practices
- ✅ Public key cryptography understanding
- ✅ Secure credential management
- ✅ Network security configuration
- ✅ Access control implementation

### Technical Documentation
- ✅ Step-by-step process documentation
- ✅ Troubleshooting guides
- ✅ Security best practices
- ✅ Professional presentation

## 🎓 Learning Outcomes

This project demonstrates:
- **Cloud Infrastructure Access** - Secure remote connection methods
- **AWS Security Model** - Key-based authentication
- **Windows Server Management** - Remote administration capabilities
- **Network Protocols** - RDP configuration and usage
- **Problem Solving** - Troubleshooting connection issues

## 📸 Visual Documentation

### Recommended Screenshots
1. **EC2 Console** - Instance selection and Connect button
2. **RDP Client Tab** - Download RDP file option
3. **Get Password** - Password decryption interface
4. **Key Upload** - Private key file selection
5. **Decrypted Password** - Password display (blur sensitive info)
6. **RDP Client** - Connection dialog
7. **Windows Desktop** - Successfully connected session

## 🔄 Post-Connection Tasks

### Initial Configuration
```
1. Change Administrator password
2. Enable Windows Firewall
3. Install Windows Updates
4. Configure Windows Defender
5. Set up user accounts (if needed)
6. Install required software
7. Configure backup strategy
```

### Server Hardening
```
1. Disable unnecessary services
2. Configure audit policies
3. Enable BitLocker (if applicable)
4. Set up monitoring/logging
5. Configure automatic updates
```

## 💰 Cost Considerations

### RDP Connection Costs
```
RDP Connection:     FREE (no additional charge)
Data Transfer:      Standard AWS data transfer rates
Instance Hours:     Charged while instance is running
Elastic IP:         Free while attached to running instance
```

### Cost Optimization
- Stop instances when not in use
- Use appropriate instance sizing
- Monitor data transfer usage
- Consider Reserved Instances for long-term use

## 🛠️ Useful Commands

### Windows PowerShell (from RDP session)
```powershell
# Check system information
Get-ComputerInfo

# View network configuration
Get-NetIPConfiguration

# Check Windows version
systeminfo | findstr /B /C:"OS Name" /C:"OS Version"

# List installed software
Get-ItemProperty HKLM:\Software\Microsoft\Windows\CurrentVersion\Uninstall\* | Select-Object DisplayName, DisplayVersion

# Check disk space
Get-PSDrive -PSProvider FileSystem
```

### AWS CLI (from local machine)
```bash
# Get instance details
aws ec2 describe-instances --instance-ids i-xxxxxxxxxxxxx

# Get Windows password
aws ec2 get-password-data --instance-id i-xxxxxxxxxxxxx --priv-launch-key /path/to/key.pem

# Check security group rules
aws ec2 describe-security-groups --group-ids sg-xxxxxxxxxxxxx
```

## 📚 Additional Resources

- [AWS EC2 Windows Instances Documentation](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/)
- [Remote Desktop Protocol (RDP) Overview](https://docs.microsoft.com/windows-server/remote/remote-desktop-services/)
- [AWS Security Best Practices](https://aws.amazon.com/architecture/security-identity-compliance/)
- [Windows Server Administration Guide](https://docs.microsoft.com/windows-server/)

## 👨‍💻 Author

**Keenan Kelly**

This project demonstrates practical AWS cloud infrastructure access and Windows Server remote administration capabilities.

## 📄 Related Projects

- [Creating a VM on AWS](https://github.com/keenannkelly/Creating-VM-on-AWS) - EC2 instance deployment
- [AWS S3 Bash Lab](https://github.com/keenannkelly/aws-s3-bash-lab) - AWS automation scripting

---

*Demonstrating secure remote access to AWS cloud infrastructure and Windows Server administration*