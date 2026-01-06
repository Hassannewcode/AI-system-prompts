# AI Drive Tool Documentation

## Overview
AI-Drive is an online file storage and management system for organizing, accessing, and retrieving files.

## Available Actions

### ls - List Directory Contents
- List files and directories
- Filter options:
  - `filter_type`: all (default), file, directory
  - `file_type`: all (default), audio, video, image
- Use 'file' filter_type for better performance when only need files
- Combine with file_type for best results

### mkdir - Create Directories
- Create new directories
- Creates parent directories if needed

### rm - Move to Trash
- Move files/directories to trash
- Recoverable from AI-Drive web interface
- Preview with ls before removal

### move - Relocate/Rename
- Move or rename files and directories
- Requires target_path parameter

### get_readable_url - Generate Temporary Access URLs
- Generate 1-hour temporary access URLs
- ONLY for AI-Drive paths (/folder/file.pdf) or aidrive:// URLs
- HTTP/HTTPS URLs are already readable and don't need conversion
- Use absolute paths from root (/)

### download_video - Download Videos
- Download videos from platforms
- Auto-detect platform
- Requires existing target_folder (use mkdir if needed)

### download_audio - Download Audio
- Download audio from video/audio platforms
- Auto-detect platform
- Requires existing target_folder

### download_file - Download Files
- Download files from direct URLs
- Optional user-friendly filename with extension
- Auto-generates filename if not provided
- Requires existing target_folder

### compress - Compress to ZIP
- Compress folder to ZIP archive
- Auto-generated filename in same directory
- Example: compress path=/source/folder → creates /source/folder.zip

### decompress - Decompress Archive
- Decompress archive to folder
- Auto-generated folder name in same directory
- Example: decompress path=/source/folder.zip → creates /source/folder

## Key Requirements

### Path Format
- Use absolute paths from root (/)
- Example: /folder/subfolder/file.txt

### Download Prerequisites
- Target folder must exist before downloading
- Use mkdir to create if needed

### Auto-generated Outputs
- Compress: creates .zip in same directory as source
- Decompress: creates folder in same directory as archive

### File Conflicts
- Auto-resolve with naming (_1, _2, etc.)

### URL Handling
- Unknown URLs: Check with url_metadata first
- Only use get_readable_url for AI-Drive paths
- HTTP/HTTPS URLs don't need conversion

## Workflows

### 1. File Access
```
ls → get_readable_url → use temporary URL
```

### 2. Downloads
```
Check target folder exists → mkdir (if needed) → download
```

### 3. Move to Trash
```
Preview with ls → rm (recoverable from web interface)
```

### 4. Compress
```
compress with path=/source/folder → auto-generates /source/folder.zip
```

### 5. Decompress
```
decompress with path=/source/folder.zip → auto-generates /source/folder
```

## Best Practices

### Before Operations
- Use ls to preview directory contents
- Verify paths before rm operations
- Check target folder existence before downloads

### File Organization
- Use descriptive folder names
- Organize files by type or project
- Regular cleanup of unused files

### URL Generation
- Only generate URLs when needed (1-hour expiry)
- Don't convert already-readable HTTP/HTTPS URLs

### Downloads
- Create dedicated folders for downloads
- Use descriptive filenames when provided
- Verify successful download with ls

## Integration with Sandbox

### AI Drive Mount
- AI Drive accessible in sandbox at `/mnt/aidrive`
- Always copy to local before processing: `cp /mnt/aidrive/file.csv ./`
- Never work directly on /mnt/aidrive files
- Slow I/O on mount point

### Storage Priority
- **Persistent storage**: Use AI Drive (files persist permanently)
- **Temporary processing**: Use sandbox (ephemeral, disappears after session)
- **User requests "save/download"**: Use AI Drive, NOT sandbox

## Common Use Cases

### Organizing Media
```
mkdir /media/videos
download_video with target_folder=/media/videos
ls with file_type=video to list all videos
```

### Backup and Archive
```
compress path=/project/data → creates /project/data.zip
download_file to save external resources
```

### Sharing Files
```
ls to find file
get_readable_url to generate temporary access link
Share link (valid for 1 hour)
```

### File Management
```
ls to view contents
move to reorganize
rm to clean up (recoverable from web interface)
```
