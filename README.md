# Disk-Usage-Analyzer





  Disk Usage Analyzer - Linux CLI Tool

            
 


1.	Introduction
The Disk Usage Analyzer is a command-line tool for Linux designed to provide users with an overview of their storage usage. It helps identify large directories and files, provides disk usage summaries, and allows for specific directory analysis. This tool uses basic Linux commands like df, du, and find to gather data, sort it, and display it in a clear, concise format.

2.	Abstract
The Disk Usage Analyzer is a Linux command-line tool designed to provide users with an efficient overview of storage usage on their systems. By leveraging basic Linux commands like df, du, and find, this tool helps users identify large directories and files, analyze specific directories, and view overall disk usage summaries. The script outputs clear and human-readable results, making it accessible for both beginners and advanced users. This tool is ideal for system administrators or anyone needing to optimize storage, as it pinpoints areas consuming the most space, aiding in the management of disk resources on Linux systems.

3.	Objectives
The objective of the Disk Usage Analyzer is to provide Linux users and administrators with a convenient, command-line-based tool to monitor and manage disk space usage efficiently. This tool aims to:
1.	Offer a Disk Usage Overview: Provide a quick summary of the total disk usage across all mounted filesystems, helping users understand overall space consumption.
2.	Identify Largest Storage Consumers: Quickly list the top 10 largest directories and files on the system, enabling users to identify areas with significant storage usage and potentially free up space.
3.	Enable Specific Directory Analysis: Allow users to analyze the disk usage of specific directories, providing insights into their impact on overall disk space.
4.	Streamline Storage Management: Simplify the process of identifying storage-hogging directories and files, making it easier to clean up unnecessary data and optimize disk space.
.
4.	Prerequisites
         Before using the Disk Usage Analyzer script, ensure the following prerequisites are met:
1.	Linux Operating System: The script is designed to run on Linux-based systems with bash shell support.
2.	Basic Knowledge of Command Line: Familiarity with using the terminal and basic command-line operations is helpful for executing the script and interpreting its output.
3.	Sudo or Root Access (Optional): For complete system-wide analysis, root privileges may be required to access certain directories and files. Running the script as a regular user may limit access to certain areas of the filesystem.

4.	Installations: The script relies on standard Linux utilities (df, du, find, sort, and head), which are commonly available on most Linux distributions by default. Ensure these 
5.	utilities are installed on the system.
6.	Script File: Save the provided code as disk_usage_analyzer.sh and make it executable. Use the following command to make the script executable:




5.	Implementation

Here is the implementation of the Disk Usage Analyzer script. You can copy this code into a file, make it executable, and run it to analyze disk usage on your Linux system.



  5.1 Usage Instructions

1.	Save the script as disk_usage_analyzer.sh:

nano disk_usage_analyzer.sh:

2.	Make the script executable:

chmod +x disk_usage_analyzer.sh

3.	Run the script:

./disk_usage_analyzer.sh


6.	Explanation of the Script

1.	find / -type f: Searches for all files (-type f) under the root directory (/).
2.	-exec du -h {} +: For each file found, du -h is executed to display its size in human-readable format.

3.	2>/dev/null: Redirects permission errors to /dev/null, effectively suppressing them, so the script only shows files it has access to.
4.	sort -rh | head -n 10: Sorts the files by size in reverse order and displays the top 10 largest files.
5.	This section is useful for quickly identifying large, individual files that may be taking up unnecessary space.

1.Display Disk Usage Summary
•	Command: df -h --total
	Explanation:
•	df shows the amount of disk space used and available on mounted filesystems.
•	-h makes it human-readable (shows sizes in MB, GB).
•	--total adds a summary line showing the total disk usage across all filesystems.
•	Purpose: Provides an overview of total disk space usage.
2.List the Top 10 Largest Directories
•	Command: du -ah / | sort -rh | head -n 10
	Explanation:
•	du -ah /: Calculates the size of each file and directory from the root (/) directory.
•	-a includes files as well as directories.
•	-h makes it human-readable.
•	sort -rh: Sorts entries by size in reverse order (largest first).
•	head -n 10: Shows only the top 10 entries.
•	Purpose: Identifies the directories and files using the most space.

3.Check Disk Usage for a Specific Directory
 
•	Commands: read, du -sh "$dir"
	Explanation:
•	read -p: Prompts the user to enter a directory path.
•	if [ -d "$dir" ]; then: Checks if the entered path is a valid directory.
•	du -sh "$dir": Calculates and displays the total size of the specified directory.
•	-s gives a summary for the whole directory.
•	-h makes it human-readable.
•	Purpose: Allows the user to analyze a specific directory's storage usage.
4.Find and List the Top 10 Largest Files
 


•	Command: find / -type f -exec du -h {} + 2>/dev/null | sort -rh | head -n 10
	Explanation:
•	find / -type f: Finds all files starting from the root directory.
•	-exec du -h {} +: For each file found, du -h displays its size.
•	2>/dev/null: Suppresses permission errors by redirecting them to /dev/null.
•	sort -rh | head -n 10: Sorts files by size (largest first) and displays the top 10.
•	Purpose: Lists the largest files on the system to help identify space hogs.


7.	How to Run the Script
      Follow these steps to save, make executable, and run the script:

Save the Script:
•	Open a text editor (like nano) and create a file named disk_usage_analyzer.sh
 
•	Copy and paste the script into this file.
•	Save and close the file by pressing Ctrl+X, then Y, then Enter.

Make the Script Executable:
•	Run the following command to grant execute permissions to the script:
 
    
    Run the Script:
•	Execute the script using the following command:
 


Conclusion
The Disk Usage Analyzer script is a straightforward yet powerful tool for managing disk space on Linux systems. By utilizing fundamental commands like df, du, and find, the script provides a comprehensive view of storage usage, making it easier for users to identify the largest directories and files, check specific directory sizes, and ultimately manage storage resources more effectively. The tool is designed with ease of use in mind, offering human-readable outputs and useful summaries without requiring extensive knowledge of Linux commands.
This script is particularly helpful for system administrators and users who need to keep a close eye on disk space, especially on servers or systems with limited storage. With the ability to pinpoint the largest directories and files, users can make informed decisions about which files to clean up, resulting in a more optimized and efficient system.
The Disk Usage Analyzer is a versatile solution that can be easily customized and extended to suit individual needs, and it serves as a solid foundation for anyone looking to build upon disk usage analysis tools in Linux.

OUTPUT

