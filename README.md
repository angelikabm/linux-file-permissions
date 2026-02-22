<h1>📁 File Permissions in Linux</h1>

<h2>Project Description</h2>
The research team at my organization needs to update the file permissions for certain files and directories within the projects directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks:
<br />


<h2>Reviewing File and Directory Permissions</h2>

I first used Linux commands to examine the current permission settings for files and directories within the file system.
<p align="center">
<img src="https://i.imgur.com/PYKNCh8.png" height="80%" width="80%" alt="Reviewing File and Directory Permissions"/>
<br />
  
The first line of the screenshot shows the command I executed, while the remaining lines display the output. I used the ls -la command to generate a detailed listing of all contents in the projects directory, including hidden files. The output revealed one directory named drafts, one hidden file named .project_x.txt, and four additional project files. The 10-character string shown in the first column represents the permissions assigned to each file or directory.

<h2>Understanding the Permissions String</h2>

The 10-character permissions string indicates the type of file and the level of access granted to different users. It can be interpreted as follows:

- 1st character: Identifies the file type. A d represents a directory, while a hyphen (-) indicates a regular file.

- 2nd–4th characters: Define the user’s permissions for read (r), write (w), and execute (x). A hyphen (-) indicates that a specific permission is not granted.

- 5th–7th characters: Represent the group’s read, write, and execute permissions.

- 8th–10th characters: Indicate permissions for other users on the system who are not part of the user or group.

For example, the permissions for project_t.txt are -rw-rw-r--. The leading hyphen shows that it is a regular file. The user, group, and others all have read access, while only the user and group have write access. No execute permissions are assigned.

<h2>Modifying File Permissions</h2>

The organization determined that users classified as other should not have write access to any project files. Based on the permissions review, I identified project_k.txt as a file that required adjustment.
<p align="center">
<img src="https://i.imgur.com/DTGgK0O.png" height="80%" width="80%" alt="Modifying File Permissions"/>
<br />
  
Using the chmod command, I removed write permissions for other. After making this change, I ran ls -la again to confirm that the permissions were updated correctly.

<h2>Updating Permissions on a Hidden File</h2>

The research team recently archived project_x.txt and wanted to prevent all users from modifying it, while still allowing the user and group to retain read access.
<p align="center">
<img src="https://i.imgur.com/vsfLL0P.png" height="80%" width="80%" alt="Updating Permissions on a Hidden File"/>
<br />
  
Since .project_x.txt begins with a period, it is considered a hidden file. I removed write permissions from both the user and the group and ensured the group had read access. This was accomplished by removing write permissions with u-w and g-w, and adding read permissions for the group using g+r. I verified the changes using ls -la.

<h2>Changing Directory Permissions</h2>

The organization required that only the researcher2 user have access to the drafts directory and its contents. This meant that execute permissions needed to be restricted so no other users or groups could access the directory.
<p align="center">
<img src="https://i.imgur.com/cM1xFw0.png" height="80%" width="80%" alt="Changing Directory Permissions"/>
<br />
  
After reviewing the existing permissions, I used the chmod command to remove execute permissions from the group. The researcher2 user already had the appropriate access, so no additional permissions were added. The updated permission listing confirmed that only researcher2 retained execute privileges.

<h2>Summary</h2>

In this task, I updated multiple file and directory permissions within the projects directory to align with organizational security requirements. I began by reviewing existing permissions using ls -la, which informed each permission change. I then applied the necessary updates using the chmod command and verified all changes to ensure access levels matched the intended authorization model.
