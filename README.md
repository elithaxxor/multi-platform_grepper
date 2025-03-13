```markdown
# System Information Utility (C)

This C program retrieves and displays various system information on Windows, macOS, and Linux.  It uses shell commands to gather the data and presents it in a formatted way on the console.

## Features

*   **Cross-Platform:** Works on Windows, macOS, and Linux, automatically detecting the operating system and using appropriate commands.
*   **Comprehensive Information:** Retrieves a wide range of system details, including:
    *   Operating System Type (Windows, macOS, Linux)
    *   OS Version/Build/Distribution
    *   Hostname
    *   Username
    *   Hardware Model
    *   Serial Number (macOS)
    *   Hardware UUID (macOS)
    *   CPU Architecture
    *   Kernel Version
    *   System Uptime
    *   Load Average
    *   CPU Core Count
    *   Total Memory
    *   Swap Usage
    *   Available Disk Space
    *   CPU Temperature (where available)
    *   Battery Percentage (where available)
    *   Network IP Address (primary interface)
    *   Gateway IP Address
*   **Formatted Output:**  Presents the information in a clear, readable format with ANSI color codes (optional; will fall back to plain text if the terminal doesn't support them).
*   **Memory Management:** Carefully manages memory allocated for command output, freeing it after use to prevent leaks.
*   **Error Handling:**  Includes basic error handling for command execution failures.
* **Clear Screen**: Clears the screen to remove clutter for best viewing.
* **Pause**: Pauses the system information output.
*   **Modular Design:** Uses separate functions for different tasks (executing commands, clearing the screen, getting system information), making the code more organized and maintainable.

## Compilation

To compile the code, you'll need a C compiler (like GCC).  Use the following command in your terminal:

```bash
gcc systeminfo.c -o systeminfo
```

*   **`systeminfo.c`:**  Replace this with the actual name of your C source file.
*   **`-o systeminfo`:**  This specifies the name of the output executable file (`systeminfo` in this case).  You can choose any name you like.

**Example (macOS/Linux):**

```bash
gcc systeminfo.c -o systeminfo
```

**Example (Windows - using MinGW/GCC):**

```bash
gcc systeminfo.c -o systeminfo.exe
```

## Usage

After compiling, run the executable from your terminal:

**macOS/Linux:**

```bash
./systeminfo
```

**Windows:**

```bash
systeminfo.exe
```

The program will then display the system information on your console.

## Code Structure

*   **`systeminfo.c`:** The main source file.
*   **`execute_command(const char* cmd)`:** Executes a shell command and returns its output as a dynamically allocated string.  Handles errors and memory management.
*   **`clear_screen()`:** Clears the console screen (works on Windows, macOS, and Linux).
*   **`pause_me()`:** Pauses execution until the user presses Enter.
*   **`system_information()`:**  Retrieves and displays the system information, handling OS-specific commands.
* **Preprocessor Directives**: `#ifdef _WIN32`, `#elif defined(__APPLE__)`, `#else` these directivies determine what code gets compiled base on the OS.

## Important Notes

*   **Shell Commands:** The program relies on the availability of specific shell commands (like `sw_vers`, `scutil`, `sysctl`, `uname`, etc. on macOS, and `cat /etc/issue`, `hostname`, `whoami`, etc. on Linux).  These commands are generally standard, but their output format might vary slightly between different versions or distributions.
*   **Error Handling:** The error handling is basic.  It checks if `popen` fails, but it doesn't handle all possible errors that might occur when executing shell commands.  More robust error handling could be added.
*   **Security:** Be cautious when running this program, especially if you modify it to execute arbitrary commands.  Avoid running it with elevated privileges (e.g., as root/administrator) unless absolutely necessary.
*   **Portability:** The `#ifdef _WIN32` / `#elif defined(__APPLE__)` / `#else` blocks ensure that the correct commands are used for each operating system.  The `clear_screen` and other functions use similar techniques for portability.

## Potential Improvements

*   **More Robust Error Handling:**  Handle a wider range of errors that might occur during command execution (e.g., command not found, permission denied).
*   **Configuration File:** Allow users to customize the commands used to retrieve information (e.g., to support different Linux distributions with different command-line tools).
*   **GUI:** Create a graphical user interface (GUI) for a more user-friendly experience.
*   **Cross Platform Temperature**: Implement a more robust, cross-platform method for getting the CPU temperature.
* **Network information** Expand network details gathered.
*   **Library Usage:**  Instead of relying solely on shell commands, explore using system libraries (like `sysinfo` on Linux) for more direct access to system information (this would improve performance and potentially portability).

This README provides a comprehensive overview of the C system information utility, covering its features, compilation, usage, code structure, important notes, and potential improvements. It's suitable for use in a GitHub repository.



# UPDATE
# ALPHA STAGE
## SPEEDY ALPHA GREPPER
```
.	Displays a clear warning about potential ramifications of file deletions.
	2.	Collects and displays basic system information (OS, RAM, storage, hostname, network name, local IP, CPU, gateway).
	3.	Pauses for two seconds so the user can read the info.
	4.	Searches the current directory for “bugs” (any lines containing “BUG,” “FIXME,” or “TODO”).
	5.	Provides a menu if no arguments are given, including an option to delete files (with a log of deleted items).
	6.	Uses colorful and legible ANSI escape codes for clarity.
	7.	Logs all key actions (including deletions) to a time-stamped log file.
```
# ALPHA STAGE
## SPEEDY ALPHA GREPPER II 
```
# System Cleanup Utility

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS-lightgrey.svg)

A comprehensive utility for safely cleaning temporary files and caches on both Linux and macOS systems. This tool helps reclaim disk space by removing unnecessary files while preserving system integrity.

## 🌟 Features

* **Cross-Platform Support**: Works on both Linux and macOS
* **Interactive Menu**: User-friendly interface with multiple cleaning options
* **System Information**: Displays detailed system information
* **Safety Measures**: Confirmation prompts and sensitive file protection
* **Detailed Logging**: Comprehensive logs of all actions
* **Disk Space Analysis**: Before and after cleanup reports
* **Time Machine Management**: Optional Time Machine snapshot cleanup for macOS
* **Wi-Fi Diagnostics**: View nearby Wi-Fi networks and signal strength

A comprehensive utility for safely cleaning temporary files and caches on both Linux and macOS systems. This tool helps reclaim disk space by removing unnecessary files while preserving system integrity.

## 🌟 Features

- **Cross-Platform Support**: Works on both Linux and macOS
- **Interactive Menu**: User-friendly interface with multiple cleaning options
- **System Information**: Displays detailed system information
- **Safety Measures**: Confirmation prompts and sensitive file protection
- **Detailed Logging**: Comprehensive logs of all actions
- **Disk Space Analysis**: Before and after cleanup reports
- **Time Machine Management**: Optional Time Machine snapshot cleanup for macOS
- **Wi-Fi Diagnostics**: View nearby Wi-Fi networks and signal strength
- **macOS System Data Cleanup**: Advanced tools to reclaim space from system data storage

## 📋 Requirements

- Bash shell (version 4.0+)
- Administrative privileges for some operations
- Linux or macOS operating system

## 🚀 Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/system-cleanup-utility.git

# Navigate to the directory
cd system-cleanup-utility

# Make the script executable
chmod +x cleanup.sh
```

## 💻 Usage

Simply run the script and follow the interactive menu:

```bash
./cleanup.sh
```

### Available Options

1. **System Information**: Display detailed system information
2. **Analyze Disk Usage**: Show disk usage of temporary directories
3. **Clean User Cache**: Remove user cache files
4. **Clean Temporary Files**: Remove temporary system files
5. **Clean Trash/Recycle Bin**: Empty trash/recycle bin
6. **Clean Logs**: Remove log files to free up space
7. **Wi-Fi Diagnostics**: Scan and display nearby Wi-Fi networks (requires wireless interface)
8. **Clean Time Machine Snapshots**: Remove local Time Machine snapshots (macOS only)
9. **Clean macOS System Data**: Clean up system data storage including iOS backups, XCode caches, and more (macOS only)
10. **Exit**: Exit the program

## ⚠️ Warning

This tool deletes files from your system. While it has been designed with safety in mind:

- **Always backup important data before running cleanup operations**
- Review the logs after each operation
- Use caution when cleaning system directories

## 📊 Logs

All operations are logged to:
- `~/cleanup_logs/deletions.log`: Record of deleted files
- `~/cleanup_logs/operations.log`: Record of all operations performed
- `~/cleanup_logs/errors.log`: Record of any errors encountered
- `./cleanup_[timestamp].log`: A summary log in the current working directory for easy reference

## 🔍 How It Works

The System Cleanup Utility works by:

1. Detecting your operating system (Linux or macOS)
2. Identifying safe-to-clean directories specific to your OS
3. Analyzing disk usage before cleanup
4. Safely removing unnecessary files with appropriate permissions
5. Protecting sensitive system files from deletion
6. Providing detailed logs of all actions
