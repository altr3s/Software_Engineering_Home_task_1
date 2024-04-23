# Bash Script

This repository contains a simple bash script created as a homework assignment for Software Engineering at HSE (Higher School of Economics).

![last update](https://img.shields.io/github/last-commit/altr3s/Software_Engineering_Homework_1)

## Overview

The bash script (`task1.sh`) provided in this repository is designed to copy files from an input directory to an output directory. The script is platform-independent and can be used on macOS, Linux, and Windows (with WSL).

## Prerequisites

- For macOS and Linux:
  - Bash should be available by default.
- For Windows:
  - WSL (Windows Subsystem for Linux) should be installed.

## Installation on Windows (WSL)

To run the script on Windows, you will need to install and set up Windows Subsystem for Linux (WSL). Here are the steps to install WSL on Windows:

1. **Open PowerShell as Administrator** and run:
    ```powershell
    wsl --install
    ```
   This command will install the Ubuntu distribution by default. If you want a different Linux distribution, you can list available distributions using:
    ```powershell
    wsl --list --online
    ```
   and then install a specific one with:
    ```powershell
    wsl --install -d <DistributionName>
    ```

2. **Restart your computer** when prompted.

Once WSL is installed, continue with the script setup as described below.

## General Setup

Follow these general setup steps for macOS, Linux, and Windows (WSL):

1. **Install `dos2unix`** (needed to convert Windows-style line endings if you're editing scripts in Windows):
    ```bash
    sudo apt-get update
    sudo apt-get install dos2unix
    ```

2. **Make the script executable**:
    ```bash
    chmod +x task1.sh
    ```

## Usage

To use the script, navigate to the directory containing `task1.sh` and execute it by specifying the input and output directories:
```bash
./task1.sh <inputDirectory> <outputDirectory>
