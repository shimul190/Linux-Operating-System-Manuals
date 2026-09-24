#### Section 1: Process Management

##### **Viewing Processes**

* **`ps`**: Displays a snapshot of currently running processes for the current shell session.
* **`ps aux`**: Displays detailed information about all running processes across all users on the system.
* **`ps aux | grep nginx`**: Filters the process list to display only processes matching the keyword `nginx`.
* **`top`**: Displays real-time, dynamic information about active system processes.
* **`htop`**: An interactive, user-friendly process viewer (provides more detailed visual feedback than `top`).

##### **Interactive Shortcuts inside `top` and `htop**`

* **`P`** *(in `top`)*: Sorts processes by CPU usage.
* **`M`** *(in `top`)*: Sorts processes by memory usage.
* **`F6`** *(in `htop`)*: Opens the menu to select a column for sorting processes.
* **`k`**: Prompts you to enter a PID to kill a specific process directly from the interface.
* **`Esc`**: Cancels the current prompt or action (e.g., exiting the process kill prompt).
* **`q`**: Exits `top` or `htop` and returns to the command prompt.

##### **Terminating Processes**

* **`PID`**: Stands for **Process ID** (a unique numerical identification number assigned to every running process).
* **`kill 1250`**: Sends a default termination signal (`SIGTERM`) to graceful stop process `1250` (e.g., a Python process).
* **`kill -9 1250`**: Forcefully terminates (`SIGKILL`) process `1250` immediately. Use this if a process refuses to stop gracefully.
* **`pkill python`**: Kills all processes running under the name `python`. *(Note: Use with caution, as it will kill all matching processes system-wide).*

---

#### Section 2: Managing Services (`systemd` / `systemctl`)

> **Note:** Service management commands usually require administrator privileges, so prefix them with **`sudo`**.

* **`sudo systemctl status nginx`**: Checks the current operational status (active, inactive, failed) of the `nginx` service.
* **`sudo systemctl start nginx`**: Starts the `nginx` service.
* **`sudo systemctl stop nginx`**: Stops (deactivates) the running `nginx` service.
* **`sudo systemctl restart nginx`**: Completely stops and then restarts the `nginx` service.
* **`sudo systemctl reload nginx`**: Reloads the service configuration files without interrupting active connections. *(Note: Not all services support reload; if unsupported, use `restart`).*
* **`sudo systemctl enable nginx`**: Configures the `nginx` service to start automatically upon system boot.
* **`sudo systemctl disable nginx`**: Prevents the `nginx` service from starting automatically upon system boot.
