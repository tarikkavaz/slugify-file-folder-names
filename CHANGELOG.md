# Slugify File / Folder Names Changelog

## [v1.1.0] - 2025-01-03

### Added
- 🇩🇪 **German Transliteration Option**: New configurable preference for German umlauts transliteration
  - ä, Ä → ae (instead of a)
  - ö, Ö → oe (instead of o) 
  - ü, Ü → ue (instead of u)
  - ß → ss (unchanged)
- ⚙️ **Extension Preferences**: Added settings panel accessible via `⌘,` in Raycast
- 📚 **Enhanced Documentation**: Updated README with German transliteration examples and usage instructions

### Technical Changes
- Added `useGermanTransliteration` preference to package.json manifest
- Enhanced `slugify()` function with optional German character mapping
- Updated `generateSlugFilename()` to support German transliteration parameter
- Modified main command to read and apply user preferences

## [Initial Version] - 2025-05-30

### Changed
- {PR_MERGE_DATE} Updated extension icon
