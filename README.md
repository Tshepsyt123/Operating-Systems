 Operating System Internals, User & File Management Practical – Windows
 Overview

This practical task demonstrates knowledge and hands-on application of operating system internals, user and group management, file system permissions, and package management using Microsoft Windows. All tasks were completed using Command Prompt and PowerShell with Administrator privileges.

The objective of this exercise was to apply system administration skills through command-line tools to manage users, configure access control, and install software.

1️⃣ Operating System Internals

To examine system-level information and understand the operating system environment, the following command was executed:

systeminfo

The systeminfo command provides detailed information about the operating system, including OS version, system architecture (32-bit or 64-bit), installed memory (RAM), processor details, and system boot time. This confirms the internal configuration and environment of the machine.

To verify the currently logged-in user, the following command was executed:

whoami

The whoami command displays the username of the active session, confirming which account is performing administrative actions.

2️⃣ User and Group Management

All user and group management tasks were performed using Command Prompt as Administrator.

A new local user account was created using:

net user student1 Password123 /add

The net user command manages user accounts in Windows. The /add parameter creates a new user, while the username and password are specified during the command. This successfully created a new local account named student1.

Next, a new local group was created using:

net localgroup interns /add

The net localgroup command is used to manage local security groups. This created a group named interns, which can be used to assign permissions collectively.

The user was then added to the group using:

net localgroup interns student1 /add

This command added student1 to the interns group, allowing the user to inherit permissions assigned to that group.

To confirm group membership, the following command was executed:

net localgroup interns

This displayed all users within the group, confirming that student1 was successfully added.

3️⃣ File System and Permission Management (NTFS)

Windows uses the NTFS file system, which supports advanced access control and permission management.

A new directory was created on the C drive using:

mkdir C:\ProjectFolder

The mkdir command creates a new folder named ProjectFolder.

To view the default NTFS permissions assigned to the folder, the following command was used:

icacls C:\ProjectFolder

The icacls command displays access control lists (ACLs), showing which users and groups have permissions and what level of access they possess.

To grant full control permissions to the interns group, the following command was executed:

icacls C:\ProjectFolder /grant interns:F

The /grant parameter assigns permissions, and F stands for Full Control. Full Control allows reading, writing, modifying, executing, and deleting files within the folder.

Permissions were verified again using:

icacls C:\ProjectFolder

The output confirmed that the interns group was assigned full control access.

4️⃣ Package Management Using Chocolatey

Windows does not include a built-in package manager like Linux (apt), so Chocolatey was used for software installation through the command line.

First, Chocolatey installation was verified using:

choco --version

If not installed, it was installed via PowerShell with administrative privileges.

To install software using Chocolatey, the following command was used:

choco install googlechrome -y

or

choco install vlc -y

The choco install command downloads and installs software packages from the Chocolatey repository. The -y parameter automatically confirms installation prompts. The successful launch of the installed application verified correct installation.

 Screenshots Included

Screenshots were captured as evidence of:

systeminfo output

whoami output

User creation

Group creation

Adding user to group

Group membership verification

Folder creation

Folder permissions before modification

Permission assignment using icacls

Updated permissions verification

Chocolatey installation

Software installation process

Installed application running

 Conclusion

In conclusion, this practical exercise provided hands-on experience with core Windows operating system administration tasks. I successfully examined system internals, created and managed user accounts and groups, implemented access control using NTFS permissions, and installed software using a command-line package manager.

This task reinforced key concepts such as user authentication, group-based access control, file system security, and automated software deployment. The practical knowledge gained from this exercise strengthens foundational skills required in IT support, system administration, and cybersecurity roles.
