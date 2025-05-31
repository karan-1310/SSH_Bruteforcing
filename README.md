Introduction
SSH BruteForce is a Python script developed to perform brute force attacks on SSH servers by attempting various passwords for a specified username. It assists in testing the security of SSH configurations.

Author
Name: Karan Shukla
GitHub: https://github.com/karan-1310

Features

Password guessing for a specified username on an SSH server.

Utilizes asyncio for asynchronous execution to improve performance.

Color-coded output for visually clear and informative display.

Customizable through command-line arguments.

Usage

Clone the Repository:
git clone https://github.com/yourusername/SSH-BruteForce.git

Navigate to the Directory:
cd SSH-BruteForce

Install Dependencies:
pip install asyncssh colorama termcolor

Run the Script:
python ssh_bruteforce.py -t <TARGET_HOST> -p <PORT> -w <WORDLIST_PATH> -u <USERNAME>

Prerequisites

Python 3.x installed.

Python libraries: asyncssh, colorama, termcolor.

Command-line Arguments

-t, --target: Host to attack (e.g., 10.10.10.10).

-p, --port: SSH port to attack (Default is 22).

-w, --wordlist: Path to the wordlist file.

-u, --username: Username to perform brute force.

Example Usage

bash
Copy
Edit
python ssh_bruteforce.py -t 10.10.10.10 -p 22 -w wordlist.txt -u admin
Output

Color-coded result for each attempt (success or failure).

Displays host, login, and password if authentication succeeds.

Wordlist

Required for the tool to function.

Should be a text file containing possible passwords to test.

Concurrency Limit

Uses asyncio concurrency to manage simultaneous login attempts.

Concurrency can be adjusted via the concurrency_limit variable in the script depending on system resources and server load tolerance.

Exception Handling

Gracefully handles errors and exceptions during execution.

Provides informative output about progress and login attempts.

Logs failed attempts and announces when the correct password is found.
