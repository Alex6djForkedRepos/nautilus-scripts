# Enhanced File Manager Actions for Linux

This project offers a collection of file manager actions, also known as _Nautilus Scripts_, designed to enhance the functionality of file managers. With intuitive right-click options for files and directories, it simplifies tasks, boosts productivity, and provides a more efficient workflow.

![screenshot](.assets/screenshot.svg)

## Installation

You can install in two ways:

### Option 1 - Online installation (recommended)

You can use either **curl** or **wget**. Choose **one** of the following commands and run it in your terminal:

#### Using `curl`

```bash
bash -c "$(curl -fsSL https://raw.githubusercontent.com/cfgnunes/nautilus-scripts/HEAD/install.sh)"
```

#### Using `wget`

```bash
bash -c "$(wget -qO- https://raw.githubusercontent.com/cfgnunes/nautilus-scripts/HEAD/install.sh)"
```

### Option 2 - Local installation

After cloning this repository, run the following command:

```bash
bash install.sh
```

## Advantages

While numerous scripts are available for file managers on the web, many suffer from poor functionality, lack of error checking, and dependency management. Some scripts only work with files that don't have special characters in their names, among other limitations. To address these shortcomings, I have developed my own set of scripts, which offer the following advantages:

- **Parallel task execution**: Processes multiple files simultaneously. Very fast!
- **Progress dialog**: Displays a progress dialog and allows interruption of tasks at any time.
- **Status notifications**: Notifies users of dependency errors and MIME types.
- **Dependency management**: Prompts users to install any missing dependencies.
- **Keyboard accelerators**: Provides keyboard shortcuts for some scripts.
- **Easy access to recent scripts**: Includes a menu, _Accessed recently_, to quickly access recently used scripts, saving time and streamlining workflows.
- **Non-destructive output**: Never overwrites the input file; the output is distinct.
- **Direct usage**: Allows direct usage without requiring input parameters.
- **Log file**: Produces an `Errors.log` file when a task finishes with an error.
- **File manager compatibility**: Designed for major file managers like GNOME Files (Nautilus), Dolphin, Caja, Nemo, and Thunar.
- **Distro compatibility**: Works on major GNU/Linux distributions, such as Ubuntu, Debian, Fedora, and Arch Linux.
- **Remote file support:** Works with files stored on remote servers.
- **Easy adaptation**: Scripts can be easily copied and adapted for other purposes.
- **Bash implementation**: All scripts are implemented in Bash. So, the scripts work well in the shell (without a graphical interface) and file managers.
- **Shell script validation**: All scripts have been checked using [ShellCheck](https://github.com/koalaman/shellcheck).

**Design philosophy:** Fewer clicks, dependencies, and verbose notifications, with a simple and intuitive directory structure.

## Keyboard accelerators

| Key                 | Action                            |
| ------------------- | --------------------------------- |
| `F3`                | Code Editor                       |
| `F4`                | Terminal                          |
| `F7`                | Disk Usage Analyzer               |
| `<Control>E`        | Extract here                      |
| `<Control><Alt>G`   | Compress to .tar.gz (each)        |
| `<Control><Alt>S`   | Compress to .tar.zst (each)       |
| `<Control><Alt>X`   | Compress to .tar.xz (each)        |
| `<Control><Alt>Z`   | Compress to .zip (each)           |
| `<Control><Alt>I`   | Show files information            |
| `<Control><Alt>H`   | Find hidden items                 |
| `<Control><Alt>J`   | Find junk files                   |
| `<Control><Alt>U`   | Find duplicate files              |
| `<Control><Alt>P`   | List permissions and owners       |
| `<Control><Alt>B`   | List largest files                |
| `<Control><Alt>R`   | List recently modified files      |
| `<Control><Alt>C`   | Copy filename to clipboard        |
| `<Control><Alt>V`   | Paste clipboard as a file         |
| `<Control><Shift>V` | Paste as symbolic link            |
| `<Control><Shift>C` | Compare items                     |
| `<Control><Shift>O` | Open item location                |
| `<Control><Shift>H` | Compute all file hashes           |
| `<Control><Shift>E` | Find empty directories            |
| `<Control><Shift>G` | Git: Clone URLs (clipboard, file) |
| `<Control><Shift>R` | Git: Reset and pull               |
| `<Control><Shift>X` | URL: Download (clipboard, file)   |

## Compatibility

File managers compatibility:

| File manager           | Environment | Menu integration | Application shortcuts | Keyboard accelerators | Menu "Accessed recently" |
| ---------------------- | ----------- | ---------------- | --------------------- | --------------------- | ------------------------ |
| GNOME Files (Nautilus) | GNOME       | 🟢                | 🟢                     | 🟢                     | 🟢                        |
| Caja                   | MATE        | 🟢                | 🟢                     | 🟢                     | 🟢                        |
| Nemo                   | Cinnamon    | 🟢                | 🟢                     | 🟢                     | 🟢                        |
| Thunar                 | Xfce        | 🟢                | 🟢                     | 🟢                     | 🔴                        |
| Dolphin                | KDE Plasma  | 🟢                | 🟢                     | 🔴                     | 🔴                        |
| PCManFM-Qt             | LXQt        | 🟢                | 🟢                     | 🔴                     | 🔴                        |

Most scripts have been tested on the following GNU/Linux distributions:

- Ubuntu/Debian
  - Ubuntu 14.04, 16.04, 18.04, 20.04, 22.04, 24.04
  - Debian 12, 13 (GNOME and KDE)
  - Kubuntu 22.04, 24.04
  - Lubuntu 22.04, 24.04
  - Xubuntu 23.10, 24.04
  - KDE neon 2024, 2025
  - Mint 21, 22 (Cinnamon, MATE and Xfce)
  - Zorin OS Core 17.1, 17.2
- Fedora
  - Workstation 39, 40, 41, 42
- Arch Linux
  - CachyOS
  - EndeavourOS
  - Manjaro 23, 24, 25 (GNOME)
- openSUSE
  - Tumbleweed 2024, 2025 (GNOME)
- Others
  - NixOS
  - Termux

## Handling large input lists

This project includes a functionality specifically designed to manage scenarios where input lists are too large for processing (e.g., 100,000 input files). Excessively large input lists can lead to errors like:

`Could not start application: Failed to execute child process "/bin/sh" (Argument list too long)`

In some cases, the scripts may fail to run. To avoid such issues, follow these steps:

1. Create a single directory with a name that includes the word `batch`;
2. Place all the files you want to process into this directory;
3. Execute the desired script using this directory as the input.

When batch mode is detected, the script recognizes the directory as a special case and process each file inside it individually, instead of treating the entire directory as a single input.
This approach prevents errors caused by excessively long argument lists and ensures reliable execution.

## Acknowledgments

This project was also inspired by other extraordinary projects and their authors.
Many thanks to all of them for their excellent and creative script collections:

- [Nautilus Scripts (by yeKcim)](https://github.com/yeKcim/my_nautilus_scripts)
- [NaughtyLust (by Dipankar Pal)](https://github.com/deep5050/NaughtyLust)
- [Vault (by Maravento)](https://github.com/maravento/vault)
- [Nautilus Scripts (by Bernhard Tittelbach)](https://github.com/btittelbach/nautilus-scripts)

## Contributing

If you spot a bug or want to improve the code or even improve the content, you can do the following:

- [Open an issue](https://github.com/cfgnunes/nautilus-scripts/issues/new)
  describing the bug or feature idea;
- Fork the project, make changes, and submit a pull request.
