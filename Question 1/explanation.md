# CLI SGA 1 - Question 1: Linux Command Line Tasks

---

## Task 1: User Identity Verification

### Question
Display your currently logged-in username and all groups your user account belongs to. Your name or login ID must appear in the output.

### Screenshot
`screenshots/task_1.png`

### Commands Used
```bash
whoami
groups
id
```

### Output
| Command | Output |
|---------|--------|
| `whoami` | Displays the username (e.g., `coder`) |
| `groups` | Shows group memberships (e.g., `coder sudo`) |
| `id` | Shows UID, GID, and all groups (e.g., `uid=1000(coder) gid=1000(coder) groups=1000(coder),27(sudo)`) |

### Explanation
- **`whoami`**: Displays the username of the currently logged-in user, confirming the active user account.
- **`groups`**: Shows all the Linux groups that the current user belongs to, indicating their access permissions.
- **`id`**: Displays the user's UID, GID, and all group memberships in a single output, providing a complete identity overview.

---

## Task 2: Workspace Validation

### Question
Display the current working directory and list all files and directories in that location using long format listing.

### Screenshot
`screenshots/task_2.png`

### Commands Used
```bash
pwd
ls -la
```

### Output
| Command | Output |
|---------|--------|
| `pwd` | Displays current directory path (e.g., `/home/coder`) |
| `ls -la` | Lists all files with permissions, owner, size, and timestamps |

### Explanation
- **`pwd`**: The `pwd` command displays the current working directory.
- **`ls -la`**: The `ls -la` command lists all files and directories (including hidden ones) in a detailed format, providing the long format listing including permissions, owner, group, size, and modification date.

---

## Task 3: Environment Confirmation File

### Question
Create a file named `user_info.txt` and write the line: `"Linux user environment verified"`

### Screenshot
`screenshots/task_3.png`

### Commands Used
```bash
echo "Linux user environment verified" > user_info.txt
cat user_info.txt
```

### Output
```
cat user_info.txt → "Linux user environment verified"
```

### Explanation
- **`echo "Linux user environment verified" > user_info.txt`**: This command creates a file named `user_info.txt` and writes the confirmation message into it. The `>` operator redirects the output to the file.
- **`cat user_info.txt`**: The `cat` command displays the file contents to verify that the data was written correctly.

---

## Task 4: File Integrity Check

### Question
Display the number of characters present in `user_info.txt`.

### Screenshot
`screenshots/task_4.png`

### Command Used
```bash
wc -m user_info.txt
```

### Output
```
32 user_info.txt
```

### Explanation
- **`wc -m user_info.txt`**: The `wc -m` command counts the total number of characters present in the file. The `-m` option specifically counts characters (as opposed to `-c` for bytes or `-w` for words).

---

## Task 5: Learning the Tools

### Question
Access the manual page of the `mkdir` command. Identify one useful option and briefly explain what it does.

### Screenshots
- `screenshots/task_5_1.png` - Coursera labs (no manual entry error)
- `screenshots/task_5_2.png` - Personal Linux installation (successful output)

### Command Used
```bash
man mkdir
```

### Output
Displays the manual page for `mkdir` with all available options and descriptions.

### Explanation
- **`man mkdir`**: To access the manual page for the `mkdir` command, I used `man mkdir`. I used my personal Linux installation as the terminal in Coursera labs showed "No manual entry for mkdir" (shown in first screenshot). The successful result is shown in the second screenshot.

#### Useful Option Identified: `-p`

> **Option Explanation:**  
> The `-p` option allows creation of parent directories if they do not already exist. It prevents errors when creating nested directory structures.  
> **Example:** `mkdir -p /home/user/dir1/dir2/dir3` will create all directories in the path even if `dir1` and `dir2` don't exist.

---

## Task 6: Home Directory Inspection

### Question
List the contents of your home directory sorted alphabetically.

### Screenshot
`screenshots/task_6.png`

### Commands Used
```bash
ls ~
ls ~ | sort
```

### Output
Displays home directory contents in alphabetical order.

### Explanation
- **`ls ~`**: The `ls ~` command lists the contents of the home directory. The `~` symbol is a shortcut representing the current user's home directory.
- **`ls ~ | sort`**: Piping the output to `sort` arranges the entries alphabetically for better readability. The pipe (`|`) passes the output of `ls` to the `sort` command.

---

## Task 7: Log Investigation

### Question
Search for the word "admin" inside a file named `log.txt` and display only the matching lines.

### Screenshot
`screenshots/task_7.png`

### Commands Used
```bash
grep "admin" log.txt
grep -n "admin" log.txt
```

### Output
Displays all lines containing the word "admin" from `log.txt`.

### Explanation
- **`grep "admin" log.txt`**: To search for the word "admin" and display only the matching lines, I used the `grep` command, which is designed for pattern matching within files. I first created the `log.txt` file and added some lines containing the word "admin", since the file was not pre-existing in the system provided.
- **`grep -n "admin" log.txt`**: The `grep -n` command searches for "admin" in `log.txt` and displays both the matching lines and their line numbers. This allows you to quickly locate where "admin" appears in the file, which is helpful for debugging or verification.

---

## Task 8: System Information Check

### Question
Display the Linux kernel version currently running.

### Screenshot
`screenshots/task_8.png`

### Command Used
```bash
uname -r
```

### Output
```
6.5.0-1024-aws
```

### Explanation
- **`uname -r`**: To display the current running kernel version, I used `uname -r`. The `-r` option specifically shows the kernel release version. Other useful options include `-a` (all information) and `-s` (kernel name).

---

## Task 9: Network Connectivity Test

### Question
Verify network connectivity by sending ICMP packets to www.google.com.

### Screenshot
`screenshots/task_9.png`

### Command Used
```bash
ping www.google.com
```

### Output
Shows ICMP packet transmission results with response times and statistics.

### Explanation
- **`ping www.google.com`**: I used the `ping` command to verify connectivity. It sends ICMP Echo Request packets to the destination (www.google.com) and waits for a reply.

**The output shows:**
- Packet transmission success/failure
- Round-trip time (RTT) in milliseconds
- Packet loss percentage

---

## Task 10: System Health Awareness

### Question
Display the command used to check system uptime and briefly explain its output (uptime duration, number of users, load average).

### Screenshot
`screenshots/task_10.png`

### Command Used
```bash
uptime
```

### Output
```
16:59:26 up 20 days, 9:01, 0 users, load average: 7.63, 5.65, 5.21
```

### Explanation
- **`uptime`**: I used the `uptime` command to get system health information.

#### Output Components

| Component | Description | Output |
|-----------|-------------|---------|
| **Current Time** | The current system time | `16:59:26` |
| **Uptime Duration** | How long the system has been running since last boot | `up 20 days, 9:01` |
| **Number of Users** | Count of currently logged-in users | `0 users` |
| **Load Average** | System load over 1, 5, and 15 minutes | `7.63, 5.65, 5.21` |

#### Load Average Breakdown
| Value | Meaning |
|-------|---------|
| `7.63` | Average load over last **1 minute** |
| `5.65` | Average load over last **5 minutes** |
| `5.21` | Average load over last **15 minutes** |

---