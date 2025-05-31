SSH Brute Force Testing Project — Execution Guide
User ID: karan-1310
GitHub: https://github.com/karan-1310

Overview
This project demonstrates how to perform an SSH brute force attack simulation on a local machine using a Python script (ssh_bruteforce.py) and a password wordlist (wordlist.txt). The goal is to understand how brute force attacks work and how to verify password security.

Prerequisites
A Windows laptop or PC with Windows 10 or later.

Python 3 installed. (Recommended: Anaconda or official Python installer)

Administrator access to run some commands.

Basic knowledge of PowerShell or Command Prompt.

Text editor (Notepad or any simple editor).


Step-by-Step Execution
Step 1: Setup SSH Server on Windows
Enable OpenSSH Server on your Windows PC:

Open PowerShell as Administrator.

Run this command to check if SSH Server is installed:
Get-Service -Name sshd
If status is not "Running", install and start SSH Server:
Add-WindowsCapability -Online -Name OpenSSH.Server~~~~0.0.1.0
Start-Service sshd
Set-Service -Name sshd -StartupType 'Automatic'
Confirm SSH server is running and listening on port 22:
netstat -an | findstr ":22"

You should see lines showing port 22 in LISTENING state.

Step 2: Create Test User and Set Password
Create a new test user for brute force testing:
net user bruteforce_test newpassword
net user bruteforce_test newpassword
Replace newpassword with any initial password.

Change password to your known password (for example):
net user bruteforce_test Test@12345


Step 3: Prepare Your Wordlist
Create a text file named wordlist.txt on your Desktop.

Add multiple possible passwords line by line, for example:
123456
admin123
letmein
Test@12345
password123

Make sure your actual password (like Test@12345) is included somewhere in this list.

Step 4: Place the Python Script and Wordlist
Download or copy the ssh_bruteforce.py file to your Desktop folder.

Ensure wordlist.txt is also saved on the Desktop.

Your directory should look like:
C:\Users\karan-1310\Desktop\
    ├── ssh_bruteforce.py
    └── wordlist.txt
Step 5: Run the Brute Force Script
Open PowerShell (normal user is fine).

Change directory to Desktop:
cd $env:USERPROFILE\Desktop
Run the brute force script with:
python ssh_bruteforce.py -t localhost -p 22 -w wordlist.txt -u bruteforce_test

Here:

-t localhost means target is your own machine.

-p 22 is the SSH port.

-w wordlist.txt is the file with passwords.

-u bruteforce_test is the username.

The script will try each password from the list until it finds the correct one or exhausts the list.


Step 6: Interpreting the Output
The script prints each password attempt.

When it finds the correct password, you will see a message like:
[22] [ssh] host:localhost  login:bruteforce_test  password:Test@12345
This means the password Test@12345 was successful for user bruteforce_test.


Troubleshooting & Tips
If you get errors about missing files, make sure you are running the script from the folder where the script and wordlist exist.

If you see encoding errors when redirecting output (> output.txt), avoid redirecting or change console code page with:
chcp 65001


If the script uses colors and causes issues, disable or comment out banner coloring in the Python script.

Always include your real password in the wordlist.txt to test if the brute force works.

Summary for Beginners
Set up SSH server on your Windows.

Create a user and set a password.

Prepare a list of passwords including your known password.

Run the Python brute force script pointing to your user and wordlist.

Observe output to see which password worked.

This simple project helps you learn how brute force attacks work and understand the importance of using strong passwords.

If you want, you can also visit my GitHub: https://github.com/karan-1310 for the full code and files.
