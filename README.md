# Backup Keyboard Shortcuts on macOS

This repository provides a Bash script to backup and restore user-defined keyboard shortcuts on macOS.

It streamlines the management of custom keyboard shortcuts by saving them to a file and restoring them as needed. This feature ensures that custom keyboard shortcuts are preserved across macOS updates and during system migrations.

## Features

- Backup all user-defined keyboard shortcuts to a JSON or XML file.
- Restore keyboard shortcuts from the backup file.
- Supports interactive mode for ease of use.
- Includes an option (`-y`) to skip confirmation prompts during restoration.
- Handles domain-specific shortcuts effectively.

## Requirements

- macOS
- [jq](https://jqlang.github.io/jq/) (required only for restoring shortcuts). Install it using [Homebrew](https://brew.sh):
    ```bash
    brew install jq
    ```

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/ElfSundae/backup-keyboard-shortcuts.git
    cd backup-keyboard-shortcuts
    ```
    Or download the script directly:
    ```bash
    curl -O https://github.com/ElfSundae/backup-keyboard-shortcuts/raw/master/backup-keyboard-shortcuts
    ```

2. Make the script executable:
    ```bash
    chmod +x backup-keyboard-shortcuts
    ```

3. **Optionally**, move the script to a directory in your `$PATH` for global use:
    ```bash
    mv backup-keyboard-shortcuts /usr/local/bin/
    ```

## Usage

```bash
backup-keyboard-shortcuts [OPTION] [FILE]
```

### Options

- `backup`: Backup keyboard shortcuts to a file.
- `restore [-y]`: Restore keyboard shortcuts from a file. Use `-y` to skip confirmation.
- `help, -h, --help`: Display the help message.

### Arguments

- `FILE`: Optional. Path to the backup file. If not provided, defaults to: `$HOME/.backup-keyboard-shortcuts/keyboard-shortcuts.json`.

If no arguments are provided, the script runs in interactive mode, prompting for user input to select an action.

## Examples

### Backup Shortcuts

To back up your keyboard shortcuts to the default file:

```bash
backup-keyboard-shortcuts backup
```

To back up to a specific file:

```bash
backup-keyboard-shortcuts backup ~/my-shortcuts.json
```

### Restore Shortcuts

To restore keyboard shortcuts from the default file:

```bash
backup-keyboard-shortcuts restore
```

To restore from a specific file:

```bash
backup-keyboard-shortcuts restore ~/my-shortcuts.json
```

To restore without confirmation:

```bash
backup-keyboard-shortcuts restore -y ~/my-shortcuts.json
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
