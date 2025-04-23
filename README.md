<h1> Configuring Linux System Administration & Troubleshooting Toolkit</h1>
This project show cases Linux command-line proficiency by demonstrating file management, process control, log analysis, and system maintenance tasks. It highlights the ability to troubleshoot and maintain a Linux system effectively.

<h2>Environments and Technologies Used</h2>
- Google Cloud
- Bash

<h2>Operating Systems Used </h2>
- Linux

<h2>High-Level Deployment and Configuration Steps</h2>

- Access a Linux virtual machine
- Create, Modify and Remove Files and Folders 
- Change permissions within a file and folder
- Installing and removing software 
- Terminate a specific process and multiple processes
- Use Logs to Help You Track Down an Issue in Linux

<h2>File & Folder Management</h2>

In this Linux virtual machine, directory /home/user/Desktop contains a file called "colors". We'll open the file, and for every line listed in it, we'll create a new folder with that name in the directory /home/user/Documents

(Image) 

Step 1: Change into working directory.

(Image) 

Step 2: Show the contents of the file "colors" within the "Desktop" directory.

(Image) 

Step 3: Create the directories.


Let's see how to copy, move, and rename files by going through a few examples. In the directory /home/user/Pictures, we'll take all the hidden files and move them into the directory /home/user/Documents/Hidden

(Image) 
Step 1: Change into the Pictures directory.

(Image) 
Step 2: Show the directory contents, including hidden files.

(Image) 
Step 3: Move the hidden files into the target directory.


Some files in the directory /home/user/Music need to be cleaned up. We'll see an example of removing files and directories by removing-:

(Image) 
Step 1: Navigate to the Music folder.

(Image) 
Step 2: Remove files.


In the directory /home/user/Downloads of your virtual machine, a number of files exist. We'll find the files that have the word "vacation" in them, and move them to /home/user/Documents

(Image) 
Step 1: Find files.

(Image) 
Step 2: Move the directories that match into the target directory.



<h2>Files & Permissions</h2>

(Image)
Step 1: Checking permissions - Before you can even begin changing the permission of a file or folder, you need to first check the permissions of the specific file/folder. To display ownership and permissions for a file, you can use ls with the -l flag and the name of the file you're interested in with the command ls -l [FILENAME]

(Image)
Step 2: Changing file permissions  - Now, change the permissions of "important_document" (from the previous step) so that the owner has execute permissions on top of their current permissions. To do this, you'll use the chmod command, with the argument 700. 

(Image)
Step 3: Changing folder permissions - In this directory there's a folder called "secret_folder". View its current permissions using ls, this time with the -ld flag rather than -l because you're viewing a directory instead of a normal file:

(Image)
Step 4: Changing owners - Now you'll change the owner of a file. In your current directory, there's a folder called "taco". Use ls to examine its permissions and see who the owner of the file is and after that You can see from this that the root user currently owns this file. There's another user account on the machine called "cook". Go ahead and make "cook" the owner of the file, using the chown command like this:



<h2>Software Instillation & Archiving</h2>

(Image)
Step 1: Installing Sublime Text - First, use dpkg to install a text editor, called Sublime Text. A .deb file is located at "/home/qwiklab/downloads/sublime-text_build-3211_amd64.deb", which you can install using this command:

(Image)
Step 2: Extracting an archive - Next, you will extract a .tar archive. The archive "extract_me.tar" is located in "/home/qwiklab/downloads/". Move to that directory, using this command:

(Image)
Step 3: Archiving files - First, move back to the original directory. You can also use the tar command to do the reverse operation, creating an archive. There are three files in your /home/qwiklab/documents folder named "Earth", "Mercury", and "Venus". Use tar to archive them into the file "Planets.tar" using this command (one line):

(Image) 
Step 4: Installing 7-Zip - You can also install programs on Linux, using apt too, which handles dependencies for you to simplify the installation process. You can install the program 7-Zip, using apt, with a simple one-line command:

(Image)
Step 5: Uninstalling GIMP - Uninstallation can also be handled by apt by using "remove" instead of "install" as the argument. GIMP, an image-editing program, is already installed on your machine. Uninstall it now, using apt with this command:

<h2>Process Management & System Monitoring</h2> 

(Image)
Step 1: Terminating a specific process - The ps -aux command allows you to list all currently running processes on a Linux machine. However, the list of processes is often super long, which makes finding a specific process pretty tough. To filter the processes you're interested in, you can pipe the output of ps through grep.

(Image)
Step 2: Terminating multiple processes - There are also multiple processes running on your computer containing the word "razzle". You can find them in the same way that you found the previous process using ps. Because grep doesn't look for full matches, it can be used to find any process that contains a specific substring:


<h2>Log Analysis & Troubleshooting</h2> 

(Image)
Step 1: Viewing logs on Linux - On Linux machines, logs are stored in the /var/log directory. There are lots of log files in this directory, and you can view them with this command:

(Image)
Step 2: Low disk space - You can see that the largest file in your home directory is /home/lab/storage/ultra_mega_large.txt, at about 5GB. This isn't an important file, but it's taking up a lot of space, so you can delete it to fix the disk space error:

(Image)
Step 3: Remove corrupted file - First, navigate to the file’s location. It is in lab folder in the home directory. Next, use the sudo command along with the command to remove files to delete the file named corrupted_file.

(Image)
Step 4: Update VLC - Before you get started on this step, go back to the home directory. Next, use the sudo command along with the apt-get package manager to identify and install missing dependencies that are required by other installed packages. Finally, use the command to display the status of a specific package. In this case, you will check the status of the VLC media player package.

(Image)
Step 5: End malicious processes - First, use the command used to list processes with -aux with the pipe symbol followed by the command that searches for text patterns within a file or stream of data and the process name totally_not_malicious. Next, kill the command using sudo and the process ID. Finally, use the command you started with again to make sure that the totally_not_malicious process has been ended.

(Image)
Step 6: Change Permission to file - The file that you need to change the permissions to is titled super_secret_file.txt. Use the sudo command along with the command used to change permissions followed by the permission mode that grants read, write, and execute permissions.
