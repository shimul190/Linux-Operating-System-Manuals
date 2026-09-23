## 1. Groups & User Management

### Creating Groups & Users

* **Create a group named `developers`:**
```bash
sudo groupadd developers

```


(Note: Original note had `developers` misspelled in some places).


* **Create users with home directories:**
```bash
sudo useradd -m rifat
sudo useradd -m sudip

```


(The `-m` flag creates the home directory under `/home/<username>`).


* **Set password for a user:**
```bash
sudo passwd rifat

```


(If you do not set a password, the user account remains locked).


* **View all home directories (user profiles):**
```bash
cd /home && ls

```



### Adding Users to Groups

* **Add existing users to the `developers` group:**
```bash
sudo usermod -aG developers rifat
sudo usermod -aG developers sudip

```


(Note: Always use `-aG` together to **append** the group. Using `-G` alone will remove the user from all other groups).


* **Check groups assigned to a user:**
```bash
groups rifat

```



---

## 2. File Ownership & Permissions Structure

### Viewing Directory Details

* **List files/directories with details:**
```bash
ls -l

```


* **Switch user account:**
```bash
su username

```



### Directory Permission Output Breakdown

Example command:

```bash
mkdir devs
ls -l

```

Example output:

```text
drwxrwxr-x 2 root root 4096 Sep 24 10:00 devs

```

Breakdown of `drwxrwxr-x`:

* `d` $\rightarrow$ Indicates a **Directory**.


* `rwx` (1st triplet) $\rightarrow$ **User/Owner** permissions (read, write, execute).


* `rwx` (2nd triplet) $\rightarrow$ **Group** permissions (read, write, execute).


* `r-x` (3rd triplet) $\rightarrow$ **Others/General** permissions (read, execute, no write).


* `root` (1st instance) $\rightarrow$ File Owner (User).


* `root` (2nd instance) $\rightarrow$ File Group.


* `4096` $\rightarrow$ File/Directory size in bytes.


* `devs` $\rightarrow$ Directory name.



---

## 3. Changing Ownership & Permissions (Symbolic Method)

### Changing Ownership (`chown` / `chgrp`)

* **Change owner of directory/file to `sudip`:**
```bash
sudo chown sudip devs

```


(Now user `sudip` owns the directory, but group remains `root`).


* **Change group ownership to `developers`:**
```bash
sudo chgrp developers devs

```


(Now user `sudip` and group `developers` hold ownership over `devs`).



### Symbolic Permission Modifications (`chmod`)

* **Grant group write permission:**
```bash
chmod g+w devs

```


* **Common symbolic flags:**
* **Targets:** `u` (user), `g` (group), `o` (others), `a` (all).


* **Operations:** `+` (add permission), `-` (remove permission).


* **Permissions:** `r` (read), `w` (write), `x` (execute).




* **Examples:**
* Add write to user/others: `chmod u+w,o+w devs`

* Add full access for all: `chmod a+rwx devs`

* Remove permissions: `chmod g-w,u-r,o-x devs`




(Note: Directories with full read, write, and execute permissions for everyone usually display in **green** in terminal output).

---

## 4. Numeric Permissions (Absolute Method)

Permissions are calculated using positional values:

* **Read ($r$)** = `4`

* **Write ($w$)** = `2`

* **Execute ($x$)** = `1`


### Permission Value Reference Table

| Target | Read (4) | Write (2) | Execute (1) | Total Value | Resulting Notation |
| --- | --- | --- | --- | --- | --- |
| **User (Owner)** | Yes (4) | Yes (2) | No (0) | **6** | `rw-`<br> |
| **Group** | Yes (4) | No (0) | No (0) | **4** | `r--`<br> |
| **Others** | No (0) | No (0) | Yes (1) | **1** | `--x`<br> |

### Command Examples

* **Set `641` permissions (`rw-r-----x`):**
```bash
chmod 641 devs

```


* **Full permissions for everyone (`rwxrwxrwx`):**
```bash
chmod 777 devs

```


* **Remove all permissions (`---------`):**
```bash
chmod 000 devs

```
