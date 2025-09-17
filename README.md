# Smoke-Testing iP/tP JAR files

## General steps:

1. Set up the required JRE/JDK and include them in your PATH
1. Create a folder 'jars' in the same directory as the `<os>.py` script
1. Place all the jars to be tested in that folder
1. Run the script and wait until it generates a csv file

Note: `linux.py` can be used to test in MacOs as well.

## Testing JAR Files in WSL

This guide gives a brief explaination on how to set up WSL and test the JAR files using the provided script.

### Prerequisites

Ensure you have the following components installed before proceeding:

- WSL installed in your machine
- Python3 installed in your WSL distribution
- Java 17 or above installed in your WSL distribution

#### Install WSL

Refer to the official [Microsoft guide](https://learn.microsoft.com/en-us/windows/wsl/install)

### Install and Verify Python in WSL

```bash
sudo apt update
sudo apt install python3 -y
python3 --version # should show something similar: Python 3.12.3
```

#### Install and verify Java 17 in WSL

```bash
sudo apt install openjdk-17-jdk -y
java -version
# Should show something similar to below
# openjdk 17.0.16 2025-07-15
# OpenJDK Runtime Environment (build 17.0.16+8-Ubuntu-0ubuntu124.04.1)
# OpenJDK 64-Bit Server VM (build 17.0.16+8-Ubuntu-0ubuntu124.04.1, mixed mode, sharing)
```

### Diretory Structure

Set up your project directory as follows:

```text
$root/
 ├─ linux.py       # Python script provided
 └─ jars/          # Directory containing .jar files to test
     ├─ file1.jar
     ├─ file2.jar
     └─ ...
```

### Running the Script in WSL

⚠️Note: WSL may behave slightly different due to your system settings and installed packages.

#### Option 1: From Windows File Explorer

1. Open the root directory (the folder containing `linux.py` and `jars/`) in File Explorer.
2. In the address bar, type `cmd` and press Enter to open a Command Prompt.
3. Enter WSL by typing `bash` and press Enter.
4. Run the script:

```bash
python3 linux.py
```

The script will test each JAR file and generate a `linux.csv` report.

#### Option 2: From Windows Desktop

1. Press WIndows key, search for "WSL", and open it.
2. Navigate to the directory

```bash
cd /mnt/c/Users/<directory_path>
```

3. Run the script:

```bash
python3 linux.py
```