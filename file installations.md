**Linux command cheat sheet** 
for updating, upgrading, installing, removing files/packages, and other common terminal tasks. These commands mainly use **Ubuntu/Debian Linux** syntax.

### 🔄 Update & Upgrade

```bash
sudo apt update
```

Updates the package list.

```bash
sudo apt upgrade
```

Upgrades installed packages.

```bash
sudo apt update && sudo apt upgrade
```

Update + upgrade together.

```bash
sudo apt full-upgrade
```

Performs a more complete upgrade, including handling dependency changes.

```bash
sudo apt autoremove
```

Removes unnecessary packages.

```bash
sudo apt autoclean
```

Removes old package files from the local cache.

---

### 📦 Install Software

```bash
sudo apt install package-name
```

Example:

```bash
sudo apt install git
```

Install multiple packages:

```bash
sudo apt install git curl wget
```

Search for a package:

```bash
apt search package-name
```

Show package information:

```bash
apt show package-name
```

---

### 🗑️ Remove Software

Remove a package:

```bash
sudo apt remove package-name
```

Remove package + configuration files:

```bash
sudo apt purge package-name
```

Then remove unused dependencies:

```bash
sudo apt autoremove
```

---

### 📁 Files & Directories

List files:

```bash
ls
```

Detailed list:

```bash
ls -l
```

Show hidden files:

```bash
ls -la
```

Create a file:

```bash
touch file.txt
```

Create a directory:

```bash
mkdir folder
```

Create nested directories:

```bash
mkdir -p folder1/folder2
```

Copy a file:

```bash
cp file.txt backup.txt
```

Copy a directory:

```bash
cp -r folder1 folder2
```

Move/rename a file:

```bash
mv old.txt new.txt
```

Move a file:

```bash
mv file.txt /home/user/Documents/
```

Delete a file:

```bash
rm file.txt
```

Delete an empty directory:

```bash
rmdir folder
```

Delete a directory and its contents:

```bash
rm -r folder
```

Force delete:

```bash
rm -rf folder
```

⚠️ **Be very careful with `rm -rf`**, especially when using `sudo`.

---

### 📥 Download Files

Using `wget`:

```bash
wget https://example.com/file.zip
```

Using `curl`:

```bash
curl -O https://example.com/file.zip
```

---

### 📦 Install `.deb` Files

Install a downloaded `.deb`:

```bash
sudo apt install ./package.deb
```

Alternative:

```bash
sudo dpkg -i package.deb
```

Fix dependency problems:

```bash
sudo apt --fix-broken install
```

---

### 🗜️ Compress & Extract

Create `.tar.gz`:

```bash
tar -czvf archive.tar.gz folder/
```

Extract `.tar.gz`:

```bash
tar -xzvf archive.tar.gz
```

Extract `.zip`:

```bash
unzip file.zip
```

Install unzip if needed:

```bash
sudo apt install unzip
```

---

### 📂 Navigate Directories

Show current location:

```bash
pwd
```

Go into a directory:

```bash
cd folder
```

Go back one directory:

```bash
cd ..
```

Go to home:

```bash
cd ~
```

Go to root:

```bash
cd /
```

---

### 👤 User & Permission Commands

Show current user:

```bash
whoami
```

Change file permissions:

```bash
chmod +x script.sh
```

Run a script:

```bash
./script.sh
```

Change file owner:

```bash
sudo chown user:user file.txt
```

Run command as administrator:

```bash
sudo command
```

---

### 💻 System Information

Check Linux version:

```bash
uname -a
```

Check distribution:

```bash
lsb_release -a
```

Check disk space:

```bash
df -h
```

Check directory size:

```bash
du -sh folder
```

Check memory:

```bash
free -h
```

Check running processes:

```bash
ps aux
```

Live process monitor:

```bash
top
```

---

### 🌐 Network Commands

Show IP address:

```bash
ip addr
```

Show routing table:

```bash
ip route
```

Test internet:

```bash
ping google.com
```

Show network connections:

```bash
ss -tuln
```

Download using `curl`:

```bash
curl https://example.com
```

---

### 🔍 Find Files

```bash
find /home -name "file.txt"
```

Find directories:

```bash
find /home -type d -name "folder"
```

Locate a command:

```bash
which python
```

---

### 📝 Read & Edit Files

Display a file:

```bash
cat file.txt
```

Read page by page:

```bash
less file.txt
```

Edit with Nano:

```bash
nano file.txt
```

Edit with Vim:

```bash
vim file.txt
```

---

### ⭐ Most Important Commands to Memorize

| Task              | Command                    |
| ----------------- | -------------------------- |
| Update packages   | `sudo apt update`          |
| Upgrade packages  | `sudo apt upgrade`         |
| Install           | `sudo apt install package` |
| Remove            | `sudo apt remove package`  |
| Completely remove | `sudo apt purge package`   |
| Unused packages   | `sudo apt autoremove`      |
| List files        | `ls`                       |
| Change directory  | `cd`                       |
| Current directory | `pwd`                      |
| Create file       | `touch file`               |
| Create folder     | `mkdir folder`             |
| Copy              | `cp source destination`    |
| Move/Rename       | `mv source destination`    |
| Delete file       | `rm file`                  |
| Delete folder     | `rm -r folder`             |
| Permissions       | `chmod`                    |
| Administrator     | `sudo`                     |
| Download          | `wget` / `curl`            |
| Disk space        | `df -h`                    |
| Memory            | `free -h`                  |
| IP address        | `ip addr`                  |

**Basic update routine:**

```bash
sudo apt update
sudo apt upgrade
sudo apt autoremove
```
