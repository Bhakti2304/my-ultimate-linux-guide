# Understanding the Folder Structure

### Explanation of System Directories

ls -ltr
List all the  files and folders in the particular directory

 `/sbin -> /usr/sbin` | System binaries for administrative commands (for admin commands) (linked to `/usr/sbin`)

 `/lib -> /usr/lib` | Libraries used by kernel for making system call to the Hardware (linked to `/usr/lib`)

 `/boot` | Stores files needed for booting the system (not relevant in containers)

 `/bin -> /usr/bin` | Essential User binaries (for non-admin commands) (linked to `/usr/bin`)

`/usr` | Contains most user-installed applications and libraries

`/srv` | Holds data for services like web servers (rarely used in containers)

`/opt` | Used for installing optional third-party software

 `/mnt` | Temporary mount point for external filesystems(adding/mounting the more temporary storage/volume location)

 `/var` | Stores logs, caches, and temporary files that change frequently

`/home` | Default location for user home directories (ex. /home/ubuntu or /home/user1)

`/data` | Likely your **mounted volume** from Windows (`C:/ubuntu-data`)

`/tmp` | Temporary files (cleared on reboot)

`/root` | Home directory for the root user

`/run` | Holds runtime data for processes

`/etc` | Stores system configuration files (similar to `C:/` drive in Windows)


### **Important System Directories**

| Directory |
|-----------|
| `/boot` |
| `/usr` |
| `/var` |
| `/etc` |

### **User & Application-Specific Directories**
| Directory |
|-----------|
| `/home` |
| `/opt` |
| `/srv` |
| `/root` |

### **Temporary & Volatile Directories**
| Directory |
|-----------|
| `/tmp` |
| `/run` |
| `/proc` |
| `/sys` |
| `/dev` |

### **Mount Points**
| Directory |
|-----------|
| `/mnt` |
| `/media` |
| `/data` |
