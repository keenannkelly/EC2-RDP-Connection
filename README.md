# Connecting to AWS EC2 Windows Instance via RDP

# 🎯 Project Overview

This project documents the complete process of establishing a secure RDP connection to an AWS EC2 Windows instance, showcasing knowledge of AWS security practices, Windows Server administration, and remote access protocols.

# 🎥 Watch Me Build This Lab

See the complete RDP connection process in action:
[![Watch Me Build This Lab](https://cdn.loom.com/sessions/thumbnails/46b966a0feb347198e716365c2c33f90-with-play.gif)](https://www.loom.com/share/46b966a0feb347198e716365c2c33f90)

**[▶️ Click here to watch the full video demonstration](https://www.loom.com/share/46b966a0feb347198e716365c2c33f90)**

# 📋 Steps Performed

### Step 1: Select EC2 Instance
- Navigated to AWS EC2 Console
- Located target Windows Server instance
- Selected instance for connection
- Verified instance state: **Running**
<img width="2290" height="552" alt="Instances(11) -" src="https://github.com/user-attachments/assets/90ef9378-459a-4fb9-ad74-8511255c005e" />

### Step 2: Access RDP Client Configuration
- Clicked **"Connect"** button on instance details page
- Selected **"RDP Client"** tab
- Chose connection type: **"Connect using RDP Client"**
- Downloaded **Remote Desktop file** (.rdp)
<img width="1003" height="475" alt="Connect we" src="https://github.com/user-attachments/assets/e9064ab5-0884-47bc-9905-8fa07925599e" />

### Step 3: Retrieve Administrator Password
- Clicked **"Get Password"** button
- Prepared to decrypt Windows administrator credentials
- Initiated password retrieval process
<img width="278" height="132" alt="Password" src="https://github.com/user-attachments/assets/13deb8da-31ae-403e-9d75-693e497a31eb" />

### Step 4: Upload Private Key
- Clicked **"Upload private key file"** or **"Browse"**
- Selected the `.pem` key pair file created during instance launch
<img width="152" height="114" alt="Certifica" src="https://github.com/user-attachments/assets/6f00631d-97e4-43fe-9f19-a9a1c8de77b5" />

- Uploaded private key for password decryption
<img width="1065" height="528" alt="bet Windows password wo" src="https://github.com/user-attachments/assets/e6c6dfa9-0b94-4ed1-8219-19a9e3c48a1a" />


**Security Note:** The private key never leaves your local machine during this process.

### Step 5: Decrypt Password
- AWS decrypted the administrator password using uploaded key
- Password displayed in plaintext (temporarily)
- Copied decrypted password to clipboard
<img width="1637" height="661" alt="Pasted Graphic 9" src="https://github.com/user-attachments/assets/ee2809d7-8036-4a2d-9590-990622a16ed8" />
<img width="352" height="72" alt="Password" src="https://github.com/user-attachments/assets/1d2636d7-eaaa-480c-856d-9a9566dd2ca3" />

**Technical Process:**
```
Encrypted Password + Private Key → Decrypted Administrator Password
```

### Step 6: Launch RDP Connection
- Opened downloaded `.rdp` file in Remote Desktop application
- System prompted for credentials
- Pasted decrypted administrator password
- Username: **Administrator** (default Windows admin account)
<img width="542" height="271" alt="Enter Your Credentials" src="https://github.com/user-attachments/assets/b7cf0b27-a448-4f79-84d5-2e7873ae1d17" />

### Step 7: Successful Connection
- ✅ RDP connection established
- ✅ Windows Server desktop displayed
- ✅ Full remote access achieved
- ✅ Ready for server configuration and management
<img width="1309" height="1051" alt="Pasted Graphic 13" src="https://github.com/user-attachments/assets/4dd9d459-1103-4e60-a0ec-aa01323ac1c3" />


## 📈 Skills Demonstrated

### AWS Cloud Services
- ✅ EC2 instance management
- ✅ Key pair authentication
- ✅ AWS Console navigation
- ✅ Password decryption process

### Windows Server Administration
- ✅ Remote Desktop Protocol (RDP)
- ✅ Windows authentication
- ✅ Remote server access

## 👨‍💻 Author

**Keenan Kelly**

This project demonstrates practical AWS cloud infrastructure access and Windows Server remote administration capabilities.
