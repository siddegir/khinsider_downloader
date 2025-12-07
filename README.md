# khinsider_downloader

## Overview
`khinsider_downloader` is a Python-based asynchronous scraper for downloading game soundtrack albums from [KHInsider](https://downloads.khinsider.com/).  
The site doesn’t provide an efficient way to batch-download tracks, so this tool automates the process for command-line users. It was built as a hobby project to streamline downloads while keeping things lightweight and transparent.

## Features
- **Async scraping** with `aiohttp` and `asyncio` for faster page requests.
- **Three-stage workflow**:
  1. Parse album page for track entries.
  2. Resolve each track’s direct `.mp3` link.
  3. Prompt user to confirm downloads interactively.
- **Graceful exit** with `q` option during downloads.
- **Lightweight dependencies** managed via `requirements.txt`.

## Installation
Clone the repository and install dependencies:

```bash
git clone https://github.com/siddegir/khinsider_downloader.git
cd khinsider_downloader
pip install -r requirements.txt
```

## Usage
Run the script with an album URL:

```bash
python main.py "https://downloads.khinsider.com/game-soundtracks/album/example-album"
```

You’ll be prompted for each track:

```
[INFO] Download trackname.mp3 [y/n/q]?
```

- `y` → download the file  
- `n` → skip the file  
- `q` → quit gracefully  

## Requirements
- Python 3.11+ (uses `asyncio.TaskGroup`)
- Libraries:
  - `aiohttp`
  - `beautifulsoup4`
  - `lxml`

## Limitations
- Interactive prompts mean downloads aren’t fully automated (by design).
- KHInsider site structure may change, which could break scraping logic.
- No retry logic beyond manual confirmation.

## License
This project is licensed under the MIT License.  
See the [LICENSE](LICENSE) file for details.

## Contributing
Contributions are welcome!  
Open issues or submit pull requests for bug fixes, new features, or documentation improvements. Even small tweaks are appreciated.

## Credits
Created entirely by me as a hobby project.
