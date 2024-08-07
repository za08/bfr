# ren - file renamer script

This Bash script is designed for Arch Linux and other Unix-like operating systems. It renames all files in the current directory by stripping their original extensions and assigning new names consisting of 8 random digits. Additionally, it appends the appropriate file extension based on the file's MIME type.

## Features

- Generates unique filenames using 8 random digits.
- Appends correct file extensions based on the file's MIME type.
- Avoids overwriting existing files by checking for name collisions.

## Requirements

- **Arch Linux** (or any other Unix-like OS).
- **Bash**: The script is compatible with Bash shell.
- **file**: The `file` command-line utility, typically pre-installed in Arch Linux.

## Installation

1. **Clone the Repository**: Use `git` to clone this repository:

   ```bash
   git clone https://github.com/za08/ren.git
   ```

2. **Change to the Directory**:

   ```bash
   cd file-renamer
   ```

3. **Make the Script Executable**:

   ```bash
   chmod +x rename_files.sh
   ```

## Usage

1. **Navigate to the Directory**: Change to the directory containing the files you want to rename.

   ```bash
   cd /path/to/your/files
   ```

2. **Run the Script**:

   ```bash
   /path/to/ren/ren.sh
   ```

   Ensure to provide the correct path to where you cloned the repository if it's not in your current working directory.

## How It Works

1. **Renaming with Random Digits**:
   - The script iterates through all files in the current directory.
   - Each file is renamed to a unique name consisting of 8 random digits. If a file with the new name already exists, the script continues generating new names until a unique one is found.

2. **Appending File Extensions**:
   - After renaming, the script checks the MIME type of each file.
   - It uses the `get_extension` function to map MIME types to their corresponding file extensions (e.g., `.jpg`, `.png`, `.mp4`).
   - If the file lacks the correct extension, it appends the appropriate one.

3. **Handling Unknown MIME Types**:
   - If the script cannot determine a file's MIME type, it will notify the user.

## Supported MIME Types

The script currently recognizes the following MIME types:

- `image/gif` → `.gif`
- `image/jpeg` → `.jpg`
- `video/mp4` → `.mp4`
- `image/png` → `.png`
- `image/webp` → `.webp`
- `application/zip` → `.zip`

You can easily extend the `get_extension` function to add support for more MIME types as needed.

## Important Notes

- **Backup Your Files**: It's recommended to back up your files before running the script, as changes cannot be easily undone.
- **Test in a Safe Environment**: Run the script in a test directory with non-critical files to verify its behavior before using it on important data.

## License

This script is provided as-is. Use it at your own risk. There is no warranty for any data loss or other issues that may arise from its use.

## Contributing

If you would like to contribute to this project, feel free to submit a pull request or open an issue for any bugs or feature requests.

---

### Disclaimer

This script is intended for personal use and may not cover all possible file types. Use responsibly!
