Linux command cheat sheet for updating, upgrading, installing, removing files/packages, and other common terminal tasks. These commands mainly use Ubuntu/Debian Linux syntax.

🔄 Update & Upgrade
sudo apt update

Updates the package list.

sudo apt upgrade

Upgrades installed packages.

sudo apt update && sudo apt upgrade

Update + upgrade together.

sudo apt full-upgrade

Performs a more complete upgrade, including handling dependency changes.

sudo apt autoremove

Removes unnecessary packages.

sudo apt autoclean

Removes old package files from the local cache.

📦 Install Software
sudo apt install package-name

Example:

sudo apt install git

Install multiple packages:

sudo apt install git curl wget

Search for a package:

apt search package-name

Show package information:

apt show package-name
🗑️ Remove Software

Remove a package:

sudo apt remove package-name

Remove package + configuration files:

sudo apt purge package-name

Then remove unused dependencies:

sudo apt autoremove
📁 Files & Directories

List files:

ls

Detailed list:

ls -l

Show hidden files:

ls -la

Create a file:

touch file.txt

Create a directory:

mkdir folder

Create nested directories:

mkdir -p folder1/folder2

Copy a file:

cp file.txt backup.txt

Copy a directory:

cp -r folder1 folder2

Move/rename a file:

mv old.txt new.txt

Move a file:

mv file.txt /home/user/Documents/

Delete a file:

rm file.txt

Delete an empty directory:

rmdir folder

Delete a directory and its contents:

rm -r folder

Force delete:

rm -rf folder

⚠️ Be very careful with rm -rf, especially when using sudo.

📥 Download Files

Using wget:

wget https://example.com/file.zip

Using curl:

curl -O https://example.com/file.zip
📦 Install .deb Files

Install a downloaded .deb:

sudo apt install ./package.deb

Alternative:

sudo dpkg -i package.deb

Fix dependency problems:

sudo apt --fix-broken install
🗜️ Compress & Extract

Create .tar.gz:

tar -czvf archive.tar.gz folder/

Extract .tar.gz:

tar -xzvf archive.tar.gz

Extract .zip:

unzip file.zip

Install unzip if needed:

sudo apt install unzip
📂 Navigate Directories

Show current location:

pwd

Go into a directory:

cd folder

Go back one directory:

cd ..

Go to home:

cd ~

Go to root:

cd /
👤 User & Permission Commands

Show current user:

whoami

Change file permissions:

chmod +x script.sh

Run a script:

./script.sh

Change file owner:

sudo chown user:user file.txt

Run command as administrator:

sudo command
💻 System Information

Check Linux version:

uname -a

Check distribution:

lsb_release -a

Check disk space:

df -h

Check directory size:

du -sh folder

Check memory:

free -h

Check running processes:

ps aux

Live process monitor:

top
🌐 Network Commands

Show IP address:

ip addr

Show routing table:

ip route

Test internet:

ping google.com

Show network connections:

ss -tuln

Download using curl:

curl https://example.com
🔍 Find Files
find /home -name "file.txt"

Find directories:

find /home -type d -name "folder"

Locate a command:

which python
📝 Read & Edit Files

Display a file:

cat file.txt

Read page by page:

less file.txt

Edit with Nano:

nano file.txt

Edit with Vim:

vim file.txt
⭐ Most Important Commands to Memorize
Task	Command
Update packages	sudo apt update
Upgrade packages	sudo apt upgrade
Install	sudo apt install package
Remove	sudo apt remove package
Completely remove	sudo apt purge package
Unused packages	sudo apt autoremove
List files	ls
Change directory	cd
Current directory	pwd
Create file	touch file
Create folder	mkdir folder
Copy	cp source destination
Move/Rename	mv source destination
Delete file	rm file
Delete folder	rm -r folder
Permissions	chmod
Administrator	sudo
Download	wget / curl
Disk space	df -h
Memory	free -h
IP address	ip addr

Basic update routine:

sudo apt update
sudo apt upgrade
sudo apt autoremove
