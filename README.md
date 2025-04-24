<h1> Configuring Linux System Administration & Troubleshooting Toolkit</h1>
This project show cases Linux command-line proficiency by demonstrating file management, process control, log analysis, and system maintenance tasks. It highlights the ability to troubleshoot and maintain a Linux system effectively.

<h2>Environments and Technologies Used</h2>
-Google Cloud

-Bash

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

<img width="467" alt="image" src="https://github.com/user-attachments/assets/750f88e2-eed6-4952-8b99-656d560d2e69" />

#1 Creating Directories - In this Linux virtual machine, directory /home/user/Desktop contains a file called "colors". We'll open the file, and for every line listed in it, we'll create a new folder with that name in the directory /home/user/Documents. First change into working directory using the cd /home/user/Documents command. Then show the contents of the file "colors" within the "Desktop" directory using cat /home/user/Desktop/colors. Then create the directories using mkdir for the 4 directorieds called red blue green yellow magenta.



<img width="464" alt="image" src="https://github.com/user-attachments/assets/4fa51f31-0832-451c-9ad6-a3ac2aa9eaf5" />

#2 Copy, Moving & Renaming Files - Let's see how to copy, move, and rename files by going through a few examples. In the directory /home/user/Pictures, we'll take all the hidden files and move them into the directory /home/user/Documents/Hidden. Change into the Pictures directory using cd, next show the directory contents, including hidden files using the ls -a command. Last move the hidden files into the target directory using mv .apple .banana .broccoli .milk /home/user/Documents/Hidden

<img width="463" alt="image" src="https://github.com/user-attachments/assets/810daeed-81f2-4107-96a4-e7ce41204b60" />

<img width="458" alt="image" src="https://github.com/user-attachments/assets/11174350-7310-4992-99c2-dc17579d9f61" />

#3 Removing Files - Some files in the directory /home/user/Music need to be cleaned up. We'll see an example of removing files and directories by removing-. Navigate to the Music folder. Then remove files.


<img width="460" alt="image" src="https://github.com/user-attachments/assets/dd8dc140-dc87-4f01-af58-8366fc785980" />

#4 Searching In Directories - In the directory /home/user/Downloads of your virtual machine, a number of files exist. We'll find the files that have the word "vacation" in them, and move them to /home/user/Documents. Find files the files using the commands used eariler. Lastly move the directories that match into the target directory.



<h2>Files & Permissions</h2>

(Image)
#1 Checking permissions - Before you can even begin changing the permission of a file or folder, you need to first check the permissions of the specific file/folder. To display ownership and permissions for a file, you can use ls with the -l flag and the name of the file you're interested in with the command ls -l [FILENAME] There's a file named "important_document" on your machine in the "/home/qwiklab/documents" directory. You can change to this directory from your current one using cd/qwiklab/documents. The to check out its current permissions do ls -l important_document

(Image)
#2 Changing file permissions  - Now, change the permissions of "important_document" (from the previous step) so that the owner has execute permissions on top of their current permissions. To do this, you'll use the chmod command, with the argument 700. Keep in mind that because the file is owned by "root" you'll need to use sudo chmod 700 important_document. You can check the permissions using ls -l important_document 

(Image)
(Image)
(Image)
#3 Changing folder permissions - Now you'll do a similar process, this time on a directory. First, move up one directory using cd. In this directory there's a folder called "secret_folder". View its current permissions using ls, this time with the -ld flag rather than -l because you're viewing a directory instead of a normal file. Use the ls -ld secret_folder/ command. You can check the permissions again to see that the group now has only write permissions, and the owner has the same permissions as before. Use ls -ld secret_folder/ to do this.Finally, you can remove read permissions from everyone else using sudo chmod o-r secret_folder/. You can see that all the criteria for this file are now met using ls -ld secret_folder/. Using chmod this way is easier to remember, but takes lots more commands. All the previous steps could also have been done using the numerical notation. Type it like this sudo chmod 720 secret_folder/.

(Image)
#4 Changing owners - Now you'll change the owner of a file. In your current directory, there's a folder called "taco". Use ls to examine its permissions and see who the owner of the file is using ls -ld taco/. After that You can see from this that the root user currently owns this file. There's another user account on the machine called "cook". Go ahead and make "cook" the owner of the file, using the chown command like this "sudo chown cook /home/qwiklab/taco". Now you can use ls -ld taco/ again.



<h2>Software Instillation & Archiving</h2>

(Image)
#1 Installing Sublime Text - First, use dpkg to install a text editor, called Sublime Text. A .deb file is located at "/home/qwiklab/downloads/sublime-text_build-3211_amd64.deb", which you can install using sudo dpkg -i /home/qwiklab/downloads/sublime-text_build-3211_amd64.deb. You can remedy this by using apt to fix the missing dependencies, using sudo apt install -f. You'll be prompted to confirm your decision to continue with the operation by typing "Y" (for "Yes"), midway through the process. Now Sublime Text is successfully installed, which you can verify using dpkg -s sublime-text

(Image)
#2 Extracting an archive - Next, you will extract a .tar archive. The archive "extract_me.tar" is located in "/home/qwiklab/downloads/". Move to that directory, using cd /home/qwiklab/downloads. You can use the Linux tar command to extract it using sudo tar -xvf extract_me.tar. The contents of the archive (the file named "great_job") are then extracted

(Image)
#3 Archiving files - First, move back to the original directory. You can also use the tar command to do the reverse operation, creating an archive. There are three files in your /home/qwiklab/documents folder named "Earth", "Mercury", and "Venus". Use tar to archive them into the file "Planets.tar" using tar -cvf Planets.tar --absolute-names /home/qwiklab/documents/Earth /home/qwiklab/documents/Mercury /home/qwiklab/documents/Venus. "Planets.tar" will then be added to your current directory, and will contain the three planet files

(Image) 
#4 Installing 7-Zip - You can also install programs on Linux, using apt too, which handles dependencies for you to simplify the installation process. You can install the program 7-Zip, using apt. sudo apt install p7zip-full. When it's finished, 7-Zip will be installed as you see in the screenshots. You'll be prompted to confirm your decision midway through the installation process. Confirm this by typing Y. Then, 7-Zip will be installed. Verify the installation using dpkg -s p7zip-full.

(Image)
#5 Uninstalling GIMP - Uninstallation can also be handled by apt by using "remove" instead of "install" as the argument. GIMP, an image-editing program, is already installed on your machine. Uninstall it now, using apt with sudo apt remove gimp. You'll be prompted to confirm your decision midway through the uninstallation process. Confirm this by typing Y. Then, GIMP will be uninstalled. You can verify this using dpkg -s gimp

<h2>Process Management & System Monitoring</h2> 

(Image)
#1 Terminating a specific process - The ps -aux command allows you to list all currently running processes on a Linux machine. However, the list of processes is often super long, which makes finding a specific process pretty tough. To filter the processes you're interested in, you can pipe the output of ps through grep. You can run ps and grep to find them, using ps -aux | grep "totally_not_malicious" To stop a process, you can use the kill command. You need to use sudo to have permission to stop them. Type the commmand sudo kill [PROCESS ID]. After killing the processes, you can verify that they're no longer running by running ps -aux | grep "totally_not_malicious".

(Image)
#2 Terminating multiple processes - There are also multiple processes running on your computer containing the word "razzle". You can find them in the same way that you found the previous process using ps. Because grep doesn't look for full matches, it can be used to find any process that contains a specific substring.  Type the commmand ps -aux | grep "razzle". To kill each of the processes, you can use sudo kill [PROCESS ID]. To verify that the processes were successfully stopped, you can use ps -aux | grep "razzle". You should only see the process for the grep command, indicating that the other processes are no longer running as seen above.


<h2>Log Analysis & Troubleshooting Example</h2> 

(Image)
#1 Viewing logs on Linux - On Linux machines, logs are stored in the /var/log directory. There are lots of log files in this directory, and you can view them with ls /var/log. The logs on Linux can be viewed like any text file; you can use sudo cat /var/log/syslog.

(Image)
#2 Low disk space - The command below uses du, sort, and head to show the top five largest files, starting from your /home directory. Type the command sudo du -a /home | sort -n -r | head -n 5. You can see that the largest file in your home directory is /home/lab/storage/ultra_mega_large.txt, at about 5GB. It's taking up a lot of space, so you can delete it to fix the disk space error. Run the command sudo rm /home/lab/storage/ultra_mega_large.txt. You can see that the log entry is still present in the log file; logs aren't deleted once the errors that caused them are resolved.
