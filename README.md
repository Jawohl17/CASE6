### Виконав самостійно Шевченко Артем РПЗ-23А

# WORK-CASE-6

# Task 1: Installing Additional Shells

![image](https://github.com/user-attachments/assets/a427d79a-a433-4311-9194-a2807424f572)

Deploying Additional Shell Environments
In this task, the default terminal interface provided by Linux (Bash) was expanded by integrating two more advanced command-line interpreters: Zsh (Z Shell) and Fish (Friendly Interactive Shell). These were installed using the system’s package management tool.

Bash remains the default and is widely used for scripting and automation in Linux systems.

Zsh offers an extensive plugin system, enhanced autocompletion, and custom theming capabilities—ideal for developers.

Fish stands out for its interactive design, real-time syntax highlighting, and intuitive suggestions, making it beginner-friendly.

After installation, these shells were tested individually to ensure proper configuration and compatibility with the system.



# Task 2: Creating Users and Groups
### Commands Used:
### Create groups
for group in techsupport developers financiers founders guests; do
    sudo groupadd $group
done

# Add users with group and shell
sudo useradd -m -s /bin/bash -G techsupport tech1
sudo useradd -m -s /bin/bash -G techsupport tech2

sudo useradd -m -s /usr/bin/zsh -G developers dev1
sudo useradd -m -s /usr/bin/zsh -G developers dev2

sudo useradd -m -s /usr/sbin/nologin -G financiers fin1
sudo useradd -m -s /usr/sbin/nologin -G financiers fin2

sudo useradd -m -s /usr/bin/fish -G founders ceo1
sudo useradd -m -s /usr/bin/fish -G founders ceo2

sudo useradd -m -s /usr/sbin/nologin -G guests guest1
sudo useradd -m -s /usr/sbin/nologin -G guests guest2

![image](https://github.com/user-attachments/assets/cf5f48e1-520c-43ff-920f-9abcd2677e3c)


### To simulate a typical enterprise environment, five user groups were created, representing various departments:

Technical Support

Developers

Financiers

Founders

Guests

Each group was populated with two users. These accounts were set up with designated home directories and added to their respective groups. The creation process also included specifying each user's shell environment (where applicable).
# Task 3: Assigning Default Shells
User Group	Default Shell
Tech Support	/bin/bash
Developers	/usr/bin/zsh
Financiers	/usr/sbin/nologin (Access Denied)
Founders	/usr/bin/fish
Guests	/usr/sbin/nologin (Access Denied)

![image](https://github.com/user-attachments/assets/bf6c505c-fe70-4eb4-ac31-a4b86f3e2a48)


### Each group received a shell type according to their operational requirements:

Group	Shell Assigned	Purpose
Technical Support	/bin/bash	Standard operations and support tasks
Developers	/usr/bin/zsh	Advanced shell tools for development needs
Financiers	/usr/sbin/nologin	Interactive shell disabled for security
Founders	/usr/bin/fish	User-friendly interface for executive use
Guests	/usr/sbin/nologin	Access blocked to limit system exposure

Users from restricted groups (Financiers and Guests) were intentionally prevented from logging into the system by assigning them the nologin shell.

# Task 4: Demonstration of User Capabilities
Example Commands Executed by Group Members:
### Tech Support (tech1, tech2) using bash:

uname -a            # Display system info
df -h               # Disk space usage
whoami              # Current user
pwd                 # Print working directory

###  Developers (dev1, dev2) using zsh:
neofetch            # Display system information (if installed)
ls -la              # List files
echo "Dev user active"

### Founders (ceo1, ceo2) using fish:

date                # Show system date
hostname            # Show machine hostname
pwd                 # Current directory

### Financiers & Guests (nologin):
### These users are restricted from logging in. Any login attempt will result in:
This account is currently not available.

![image](https://github.com/user-attachments/assets/d8484d09-8a03-4762-a6f0-3b5cba89daef)


### To confirm correct shell behavior, authorized users were logged in and prompted to execute simple commands such as:

Viewing system information (uname, neofetch)

Checking the current user (whoami)

Displaying disk usage or directories (df -h, pwd)

Showing system time and hostname (date, hostname)

Users assigned nologin received an error message upon login attempts, confirming that their accounts were effectively restricted.

# Conclusion 
This work demonstrated the configuration of a multi-user Linux system with customized shell environments based on user roles. By installing additional shells (Zsh and Fish), we expanded the flexibility and user experience of the terminal. Users were organized into functional groups reflecting a real organizational structure, and their shell access was tailored to match their responsibilities. Technical and developer roles received interactive shells, while access was intentionally restricted for non-technical groups for security purposes. The successful execution of commands by permitted users and blocked access for restricted users confirmed the system’s correct setup. Overall, this case highlights effective system administration practices in managing user roles, permissions, and terminal environments.
