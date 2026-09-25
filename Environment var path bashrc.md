# Environment Variables, PATH, and `.bashrc`

## 1. Basic Environment Variables & Shell Usage

```bash
# View the HOME variable
echo $HOME

# Display all environment variables
printenv

# View the current active shell
echo $SHELL

# View the current logged-in user
echo $USER

```

### Creating Shell Variables

```bash
# Define a local shell variable (temporary for the current session)
name="shell_name"

# Display the variable value
echo $name

```

---

## 2. Managing Environment Variables & Files

### Creating Environment Variables

To make a variable accessible to subprocesses in the shell, use `export`:

```bash
export friend="shell_name"

```

### File Operations

```bash
# Create a new empty file
touch filename

# Open or edit a file using the Vim editor
vim filename

# Make a file executable
chmod +x filename

# Move a file into another folder
mv filename foldername/filename

```

---

## 3. Adding Directories to `PATH`

Adding a folder to your `PATH` variable allows you to run executables located inside that directory from anywhere in the system.

```bash
# Add a directory (e.g., /home/duvai77/devs) to your PATH
export PATH="$PATH:/home/duvai77/devs"

# Verify updated PATH entries
echo $PATH

# Locate the path of an executable or file
which filename

```

> **Note:** Adding a directory to `PATH` allows files inside folders like `devs/` to be accessed from any location, including the home directory.
> 
> 

---

## 4. Understanding and Using `.bashrc`

### Why use `.bashrc`?

When you define variables or update `PATH` directly in the terminal, those changes are temporary and lost when the terminal closes. The `.bashrc` file automatically runs whenever a new terminal session starts, saving your settings permanently.

### Editing and Reloading `.bashrc`

1. **Open `.bashrc` in Vim:**
```bash
vim ~/.bashrc

```


2. **Add your custom configurations/variables (inside Vim):**
```bash
export friend="Sudip"

```


3. **Save, exit Vim, and reload `.bashrc` without restarting the terminal:**
```bash
source ~/.bashrc

```


4. **Verify the change:**
```bash
echo $friend

```



> **Result:** Even if you log out and log back in, running `echo $friend` will consistently output `Sudip`. This same persistent behavior applies to `PATH` additions, folder configurations, and custom aliases.
> 
>
