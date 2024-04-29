# Bash Script

This repository contains a simple bash script created as a homework assignment for Software Engineering at HSE (Higher School of Economics).

![last update](https://img.shields.io/github/last-commit/altr3s/Software_Engineering_Homework_1)

## Overview

The bash script (`task1.sh`) provided in this repository is designed to copy files from an input directory to an output directory. The script is platform-independent and can be used on macOS, Linux, and Windows (with WSL).

## Task Description

**Objective:** Write a bash script that accepts two parameters: an input directory and an output directory. The script must traverse the input directory and copy all files from it (and all its nested directories) to the output directory, but just as flat files within the output directory.

**Example:**

- Input directory = `/home/input_dir`
- Output directory = `/home/output_dir`

Initially, `/home/output_dir` is empty.

Structure of `/home/input_dir`:
```css
input_dir/
  -- a.txt
  -- dir2/
    -- b.txt
  -- dir3/
    -- c.txt
```

After running your script, the structure of `/home/output_dir` should be:

```css
output_dir/
  -- a.txt
  -- b.txt
  -- c.txt
```

## Prerequisites

- **macOS and Linux**:
  - Bash should be available by default.
- **Windows**:
  - WSL (Windows Subsystem for Linux) should be installed.

## Installation on Windows (WSL)

To run the script on Windows, you will need to install and set up Windows Subsystem for Linux (WSL). Here are the steps to install WSL on Windows:

1. **Open PowerShell as Administrator** and run:
    ```powershell
    wsl --install
    ```
   This command will install the Ubuntu distribution by default. To install a different Linux distribution, you can list available distributions with:
    ```powershell
    wsl --list --online
    ```
   and then install a specific one with:
    ```powershell
    wsl --install -d <DistributionName>
    ```

2. **Restart your computer** when prompted.

## General Setup

Follow these general setup steps for macOS, Linux, and Windows (WSL):

1. **Install `dos2unix`** (to convert Windows-style line endings if you're editing scripts in Windows):
    ```bash
    sudo apt-get update
    sudo apt-get install dos2unix
    dos2unix task1.sh
    ```

2. **Make the script executable**:
    ```bash
    chmod +x task1.sh
    ```

## Usage

To use the script, navigate to the directory containing `task1.sh` and execute it by specifying the input and output directories:
    ```bash
    ./task1.sh <inputDirectory> <outputDirectory>
    ```


**Note:** Files with the same name may exist in different subdirectories of the input directory. During copying to the output directory, these situations should be resolved to prevent file loss and maintain file contents.

## Requirements and Evaluation Criteria

- **1 point** for the script starting and accepting two parameters.
- **1 point** for listing files directly in the input directory.
- **1 point** for listing directories in the input directory.
- **3 points** for listing all files nested within the input directory.
- **1 point** for copying all files nested within the input directory to the output directory.
- **3 points** for resolving the issue of files with identical names.

## Implementation Details

The script (`task1.sh`) is designed to handle the specified tasks efficiently:

- **Directory and File Handling:** It uses the `find` command to identify and process files in the input directory, including nested ones.
- **Duplicate Filename Resolution:** To address files with the same names, the script appends a counter to the filenames in the output directory. This method ensures that no file is overwritten, preserving all data.
- **Script Robustness:** The script includes checks for the existence of directories and adjusts file paths dynamically based on the presence of file extensions.

The solution provided adheres to the requirements by implementing robust file handling and unique naming strategies to handle duplicate file names effectively.
