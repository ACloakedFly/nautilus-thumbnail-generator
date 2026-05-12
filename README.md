# Gnome Files / Nautilus Thumbnail Generator

The Nautilus Thumbnail Generator is a Python-based service that automatically creates thumbnails for images in specified directories. It integrates with the Nautilus file manager, ensuring that thumbnails are generated and updated as files are added or modified.
This approach serves as a temporary solution for situations where thumbnails fail to load while accessing the recent menu or using the file picker.

## Features

- Generates thumbnails for images efficiently in the background.
- ~~Watches for new or updated files in real-time to keep thumbnails current.~~
- Can be run from anywhere with no arguments to run in current working directory, or with directory specified as argument.
- Supports adding option in context menu using [Actions for Nautilus](https://github.com/bassmanitram/actions-for-nautilus)
    - Check out [config.json](./config.json) for a working example!
- TODO use other thumbnailers depending on the format

## Prerequisites

- Tested on Fedora 39
- systemd
- Python 3
- ~~`watchdog` Python package~~
- `filetype` Python package
- `gdk-pixbuf-thumbnailer`

## Installation

To install the Nautilus Thumbnail Generator, follow these steps:

1. Clone the repository:

```bash
git clone https://github.com/yourusername/nautilus-thumbnail-generator.git
```

2. Navigate to the project directory:

```bash
cd nautilus-thumbnail-generator
```

3. Make the install script executable and run it:

```bash
chmod +x install.sh
./install.sh
```

This script will install the necessary files and set up a user service to run the thumbnail generator automatically.

## Usage

Once installed, the Nautilus Thumbnail Generator can be run from anywhere in a terminal, or use [Actions for Nautilus](https://github.com/bassmanitram/actions-for-nautilus) with [config.json](./config.json) for a context menu option to generate for any directory. Thumbnails will be generated in the appropriate cache directory and used by Nautilus or other file managers that follow the FreeDesktop.org thumbnail specification.

**First run can take a long time to generate all thumbnails, depends on the scope as well**

## Uninstall

To uninstall the Nautilus Thumbnail Generator, follow these steps:

1. Navigate to the project directory (if not already there):

```bash
cd nautilus-thumbnail-generator
```

2. Make the uninstall script executable and run it:

```bash
chmod +x uninstall.sh
./uninstall.sh
```

This script will stop the service, remove installed files, and clean up the system service entries.
