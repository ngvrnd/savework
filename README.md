# savework

## Overview

The `savework` command-line tool provides a simple way to manage and restore backups of your current working directory. It's useful when you want to try out changes without the risk of permanently altering your files.

This tool creates a backup of your entire working directory, allowing you to revert back to the saved state or even create a duplicate of it in a new location.

## Features

* **push**: Saves the current state of your working directory.
* **pop**: Restores the most recently saved state of your working directory and removes it from the list of saved states.
* **restore**: Restores a saved state without removing it from the list of saved states. 
* **list**: Displays all saved states.
* **backup_dir**: Prints the path to the backup directory.

**Note**: push and restore take an optional argument **merge**; without it they wipe out any new files and cleanly restore the save; with it they leave newly created files alone. **merge** is perhaps not the best name for this option and may be renamed in future releases.


## Installation

Copy the `savework` script to a directory included in your PATH environment variable.

## Usage

```bash
savework push                       # Save the current state of the subtree rooted in the current working directory.
savework pop                        # Restore the most recently saved state cleanly -- deleting any newly created files, and delete the backup
savework pop merge                  # Restore the most recently saved state on top of the current work, preserving any created files, and delete the backup
savework restore                    # Restore the most recently saved state cleanly -- deleting any newly created files, without deleting the backup
savework restore merge              # Restore the most recently saved state on top of the current work, preserving any newly created files, without deleting the backup
savework list                       # List all saved states
savework backup_dir                 # Display the path to the backup directory
```

## Testing

A basic test script `simpletest` is included in the repository. This script exercises each of the commands and can be used as a basic test of the functionality in the script.

## Disclaimer

This tool is provided as-is with no warranty. Always ensure that your files are properly backed up before using this tool.
