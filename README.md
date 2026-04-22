# Jupyter Notebook Viewer for Obsidian

Renders `.ipynb` (Jupyter notebook) files natively inside Obsidian — markdown cells as prose, code cells with syntax highlighting and execution-count badges, and outputs (text, tables, errors) inline.

## Features

- **Markdown cells** rendered using Obsidian's own renderer — wikilinks, bold, italics, and all standard formatting work
- **Code cells** with Python syntax highlighting and `[N]` execution-count badges
- **Stream output** (`stdout`/`stderr`) displayed as monospace text
- **Rich output** — pandas and polars DataFrame HTML tables rendered with scrollable, theme-aware styling
- **Error tracebacks** with ANSI escape codes stripped for clean display
- **Theme-aware** — all colors use Obsidian CSS variables; works in light mode, dark mode, and any community theme
- **No build step** — plugin is plain JavaScript, no Node.js or npm required

## Installation

### From the Community Plugin Directory

Search for **"Jupyter Notebook Viewer"** in **Settings → Community plugins → Browse**.

### Manual installation

1. Download `main.js`, `manifest.json`, and `styles.css` from the [latest release](../../releases/latest).
2. Create a folder `<your-vault>/.obsidian/plugins/jupyter-viewer/`.
3. Place the three downloaded files into that folder.
4. Open Obsidian, go to **Settings → Community plugins**, disable Restricted Mode if prompted, then enable **Jupyter Notebook Viewer**.

## Usage

Click any `.ipynb` file in the Obsidian file explorer. It opens in the notebook viewer automatically.

To switch back to raw JSON (e.g., for copying cell contents), right-click the file and choose **Open with → Default editor**.

## Supported output types

| Output type | Rendered as |
|---|---|
| `stream` (stdout) | Monospace preformatted text |
| `stream` (stderr) | Monospace text in error color |
| `execute_result` / `display_data` with `text/html` | Scrollable HTML table |
| `execute_result` / `display_data` with `text/plain` | Monospace preformatted text |
| `error` | Exception header + cleaned traceback |
| `image/png` | Inline image (base64) |

## Compatibility

- Obsidian 1.0.0+
- Desktop only (uses Obsidian's desktop file APIs)
- Jupyter notebook format v4 (nbformat 4)

## License

MIT — see [LICENSE](LICENSE).
