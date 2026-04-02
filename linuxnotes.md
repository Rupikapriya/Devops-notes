Linux over Windows

Cost-Effectiveness
Free and Open Source
Performance and Efficiency
Better Resource Utilization
Security and Reliability
Less Vulnerable to Malware

Core components of a Linux Machine

+----------------------------------------------------+
| User Applications (Vim, Docker, Apache, etc.)     |
+----------------------------------------------------+
| Shell (Bash, Zsh, Fish, etc.)                     |  <-- Part of the OS
+----------------------------------------------------+
| System Libraries (glibc, libc, OpenSSL, etc.)     |  <-- Part of the OS
+----------------------------------------------------+
| System Utilities (ls, grep, systemctl, etc.)      |  <-- Part of the OS
+----------------------------------------------------+
| Linux Kernel (Process, Memory, FS, Network)       |  <-- Core of the OS
+----------------------------------------------------+
| Hardware (CPU, RAM, Disk, Network, Peripherals)   |
+----------------------------------------------------+


(a) Hardware Layer

🔹 The physical components of the computer (CPU, RAM, disk, network interfaces, etc.).
🔹 The OS interacts with hardware using device drivers.
(b) Kernel (Core of Linux OS)

🔹 The Linux Kernel is responsible for directly managing system resources, including:

    Process Management – Schedules processes and handles multitasking.

    Memory Management – Allocates and deallocates RAM efficiently.

    Device Drivers – Acts as an interface between software and hardware.

    File System Management – Manages how data is stored and retrieved.

    Network Management – Handles communication between systems.

(c) Shell (Command Line Interface - CLI)

🔹 A command interpreter that allows users to interact with the kernel.
🔹 Examples: Bash, Zsh, Fish, Dash, Ksh.
🔹 Converts user commands into system calls for the kernel.
(d) User Applications

🔹 End-user programs like web browsers, text editors, DevOps tools, etc.
🔹 Applications interact with the OS using system calls via the shell or GUI.

Linux Distributions
Linux distributions (distros) are different versions of Linux that package the Linux kernel with various software, system utilities, and package managers. Each distro is designed for different use cases, such as personal computing, server management, or security.
ex: ubuntu, fedora, debian..

Package Managers in Linux

A package manager is a tool that automates the process of installing, updating, configuring, and removing software in a Linux system. It ensures that software and its dependencies are managed efficiently.

How Does a Package Manager Work?

Repositories (Repos):

A package manager fetches software from official repositories (online storage of packages).
Example: Ubuntu gets packages from archive.ubuntu.com.
Installing Software:APT for ubuntu and debian
sudo apt install <packege name>

When you install software, the package manager: ✅ Downloads the package from the repository. ✅ Resolves dependencies (installs additional required software). ✅ Installs and configures the software automatically.
Updating Software: 
sudo apt update         # Update package lists
sudo apt upgrade -y     # Upgrade installed packages

A single command updates all installed packages to the latest version.
Removing Software:sudo apt remove <package name>

The package manager also removes software cleanly without leaving unnecessary files.

Always update your package list before installing software:
sudo apt update && sudo apt upgrade -y
✅ Use autoremove to clean up unused dependencies:
sudo apt autoremove
✅ Enable automatic security updates (Ubuntu):
sudo apt install unattended-upgrades

Understanding the Folder Structure

Directory	Description
/sbin -> /usr/sbin	System binaries for administrative commands (linked to /usr/sbin).
/bin -> /usr/bin	Essential user binaries (linked to /usr/bin).
/lib -> /usr/lib	Shared libraries and kernel modules (linked to /usr/lib).

Important System Directories
Directory	Description
/boot	Stores files needed for booting the system (not relevant in containers).
/usr	Contains most user-installed applications and libraries.
/var	Stores logs, caches, and temporary files that change frequently.
/etc	Stores system configuration files.

User & Application-Specific Directories
Directory	Description
/home	Default location for user home directories.
/opt	Used for installing optional third-party software.
/srv	Holds data for services like web servers (rarely used in containers).
/root	Home directory for the root user.

Temporary & Volatile Directories
Directory	Description
/tmp	Temporary files (cleared on reboot).
/run	Holds runtime data for processes.
/proc	Virtual filesystem for process and system information.
/sys	Virtual filesystem for hardware and kernel information.
/dev	Contains device files (e.g., /dev/null, /dev/sda).

Mount Points
Directory	Description
/mnt	Temporary mount point for external filesystems.
/media	Mount point for removable media (USB, CDs).
/data	Likely your mounted volume from Windows (C:/ubuntu-data).

User Management in Linux
