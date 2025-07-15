# Slugify File / Folder Names - Raycast Extension

A Raycast extension that converts selected files and folders in Finder to URL-friendly slug format with comprehensive international character support.

## Features

- 🌍 **International Characters**: Handles accented and special characters from multiple languages
- 🇩🇪 **German Transliteration**: Optional German umlauts transliteration (ä→ae, ö→oe, ü→ue, ß→ss)
- 📁 **Batch Processing**: Rename multiple files and folders at once
- 🔄 **Extension Preservation**: Keeps file extensions intact
- ⚡ **Conflict Resolution**: Automatically handles filename conflicts
- 📋 **Rename Log**: Copies a summary of renamed items to clipboard
- ⚙️ **Configurable Settings**: Customize transliteration behavior via extension preferences

## German Transliteration Option

The extension includes an optional German transliteration mode that provides more accurate German spelling conventions:

| Character | Standard | German Mode |
|-----------|----------|-------------|
| **ä, Ä** | a | ae |
| **ö, Ö** | o | oe |
| **ü, Ü** | u | ue |
| **ß** | ss | ss |

### Enabling German Transliteration

1. Open Raycast and search for "Slugify Selected Files & Folders"
2. Press `⌘,` (Command + Comma) to open Extension Preferences
3. Toggle "Use German transliteration for umlauts" checkbox
4. The setting will be remembered for future uses

### Examples

| Original Name | Standard Mode | German Mode |
|---------------|---------------|-------------|
| `Müller.txt` | `muller.txt` | `mueller.txt` |
| `Döner Kebab` | `doner-kebab` | `doener-kebab` |
| `Größe` | `grosse` | `groesse` |
| `Straße` | `strasse` | `strasse` |

## Character Mappings

### Standard International Characters
- **á à â ä æ ã å ā** → a
- **é è ê ë ē ė ę** → e
- **í ì î ï ī į ı İ** → i
- **ó ò ô ö œ õ ø ō** → o
- **ú ù û ü ū** → u
- **ç** → c
- **ğ** → g
- **ş** → s
- **ñ** → n
- **ß** → ss
- **ý** → y
- **ž** → z

### Special Character Rules
- Spaces and separators (`/`, `\`, `_`) → `-`
- Punctuation (`,`, `.`, `!`, `?`, `:`, `;`) → removed
- Symbols (`@`, `#`, `$`, `%`, `^`, `&`, `*`, `+`, `=`, `~`) → removed
- Quotes (`"`, `'`, `` ` ``) → removed
- Parentheses and brackets → removed
- Multiple hyphens → single hyphen
- Leading/trailing hyphens → removed

## Usage

1. **Configure Preferences** (Optional): 
   - Open Raycast, search for "Slugify Selected Files & Folders"
   - Press `⌘,` to open Extension Preferences
   - Toggle "German Transliteration" if needed
2. **Select Files/Folders**: In Finder, select one or more files or folders you want to rename
3. **Run Command**: Open Raycast and type "Slugify Selected Files & Folders" or use the configured shortcut
4. **View Results**: The extension will:
   - Show progress toast during processing
   - Display success/failure summary
   - Copy rename log to clipboard (format: `original-name → new-name`)

## Examples

| Original Name | Standard Mode | German Mode (if enabled) |
|---------------|---------------|-------------------------|
| `Çılgın %50 İndirim! (Şimdi Başla)` | `cilgin-50-indirim-simdi-basla` | `cilgin-50-indirim-simdi-basla` |
| `café résumé.pdf` | `cafe-resume.pdf` | `cafe-resume.pdf` |
| `Müller & Söhne.txt` | `muller-sohne.txt` | `mueller-soehne.txt` |
| `Größe (ähnlich).docx` | `grosse-ahnlich.docx` | `groesse-aehnlich.docx` |
| `My File (copy).txt` | `my-file-copy.txt` | `my-file-copy.txt` |
| `naïve piñata.docx` | `naive-pinata.docx` | `naive-pinata.docx` |
| `Hello World!` | `hello-world` | `hello-world` |

## Error Handling

- **No Selection**: Shows error if no files/folders are selected in Finder
- **Permission Issues**: Displays specific error messages for access problems
- **Naming Conflicts**: Automatically appends numbers (`-1`, `-2`, etc.) to avoid overwrites
- **Already Slugified**: Skips files that are already in slug format

## Development

### Building
```bash
npm run build
```

### Development Mode
```bash
npm run dev
```

### Testing
The extension includes comprehensive test cases for the slugify function covering:
- International character mappings
- Special character handling
- Edge cases and file extensions

## Technical Details

- **Framework**: Raycast API
- **Language**: TypeScript
- **File Operations**: Node.js `fs.promises`
- **Mode**: No-view command for quick execution

## Changelog

## [Initial Version] - {PR_MERGE_DATE}
- Initial release
- International character support
- Batch file processing
- Extension preservation
- Conflict resolution
- Clipboard integration