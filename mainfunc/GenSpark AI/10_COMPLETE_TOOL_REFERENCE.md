# Complete Tool Reference

## Search and Discovery Tools

### web_search
**Purpose**: General web search
**Parameters**:
- q (required): Search query (max 20 words, no line breaks)
**Returns**: Titles, URLs, snippets, thumbnails
**Use when**: Fallback for general information after specialized tools

### scholar_search
**Purpose**: Search scholarly articles and academic papers
**Parameters**:
- query (required): Academic search query
**Use when**: Need peer-reviewed research, academic papers, scientific articles

### maps_search
**Purpose**: Geographical information and location services
**Parameters**:
- query_type (required): search, place, distances, directions
- engine (required): maps, maps_directions
- query: Search query for places (required if engine=maps)
- start_addr: Starting address (required if engine=maps_directions)
- end_addr: Ending address (required if engine=maps_directions)
- travel_mode: 0-9 for different transport modes
- avoid: highways, tolls, ferries
- prefer: bus, subway, train, tram_light_rail
**Use when**: Location info, business info, distances, directions

### image_search
**Purpose**: Find existing images on the internet
**Parameters**:
- query (required): Image search terms
**Use when**: Need real photos, diagrams, illustrations (not generating new)

### video_search
**Purpose**: Search for existing videos (YouTube)
**Parameters**:
- query (required): Video search terms
**Use when**: Need tutorials, reviews, demonstrations, visual explanations

## Content Retrieval Tools

### crawler
**Purpose**: Fetch complete raw content from URLs
**Parameters**:
- url (required): HTTP/HTTPS URL to crawl
**Returns**: Complete markdown content
**Supports**: Webpages, PDFs, CSV, Word, PowerPoint (NOT Excel)
**Use when**: Need full text for articles, blogs, documentation

### summarize_large_document
**Purpose**: Answer specific questions about very long documents
**Parameters**:
- url (required): Document URL
- question (required): Specific question about content
**Supports**: PDFs, webpages, Word, PowerPoint (NOT Excel)
**Use when**: Document is explicitly very long (100+ pages) and need specific info

### url_metadata
**Purpose**: Check URL metadata without downloading
**Parameters**:
- url (required): Single URL or array of URLs (max 5)
**Returns**: Content-type, content-length, filename, extension, CORS (for images)
**Use when**: Need to check file type/size before processing

### webpage_capture_screen
**Purpose**: Capture screenshot of webpage
**Parameters**:
- url (required): Webpage URL
- viewport (optional): width/height settings
**Use when**: Crawler fails or need visual representation

### resource_discovery
**Purpose**: Detect and catalog downloadable media from webpages
**Parameters**:
- url (required): Webpage URL
- resource_types (optional): Array of types to detect (images, videos, documents, audios, archives, all)
**Returns**: Up to 30 resources with metadata
**Limitations**: 30s timeout, high computational cost
**Use when**: Need to catalog available media before downloading

## Content Understanding Tools

### understand_images
**Purpose**: Analyze and understand image content
**Parameters**:
- image_urls (required): Array of image URLs or AI Drive paths
- instruction (required): Detailed analysis instructions
- model (optional): gpt-4o (default), gemini-flash
**Use when**: Need to extract information, analyze content, read text from images

### understand_video
**Purpose**: Extract transcript from video
**Parameters**:
- video_id (required): YouTube video ID
- provide_download_link (required): Boolean for transcript download
**Use when**: Need video transcript (YouTube only)

### batch_understand_videos
**Purpose**: Process multiple videos efficiently
**Parameters**:
- jobs (required): Array of {video_id, questions_to_answer}
**Use when**: Need transcripts/answers for multiple videos (YouTube only)

### audio_transcribe
**Purpose**: Transcribe audio to text with timestamps
**Parameters**:
- audio_urls (required): Array of audio file URLs or AI Drive paths
- prompt (optional): Context to improve transcription quality
**Supports**: mp3, mp4, mpeg, mpga, m4a, wav, webm
**Use when**: Need accurate audio transcription with timestamps

### analyze_media_content
**Purpose**: Deep analysis of images, audio, video
**Parameters**:
- media_urls (required): Array of media URLs or AI Drive paths
- requirements (optional): Detailed analysis instructions (in English)
- analyze_type (optional): '' (default) or 'video_style_replication'
- video_metadata (optional): {start_offset, end_offset, fps}
**Use when**: Need comprehensive media analysis beyond basic understanding

## Content Generation Tools

### image_generation
**Purpose**: Generate or edit images
**Parameters**:
- query (required): Detailed description in English
- image_urls (required): Array of reference images (empty [] for text-only)
- model (required): Model selection (default: nano-banana-pro)
- aspect_ratio (required): 1:1, 4:3, 16:9, 9:16, 3:4, 2:3, 3:2, auto
- task_summary (required): Brief summary of task
- image_size (optional): auto, 2k, 4k
- bbox (optional): For bbox segmentation [x1, y1, x2, y2]
**Requires**: User confirmation (costs credits and time)
**Use when**: Need to generate new images or edit existing ones

### video_generation
**Purpose**: Generate 5-10 second video clips
**Parameters**:
- query (required): Detailed video description
- model (required): Model selection (various options)
- image_urls (required): Array of reference images (empty [] for text-only)
- aspect_ratio (required): Varies by model
- duration (required): Video length in seconds
- task_summary (required): Brief summary of task
- file_name (optional): Output filename
- video_urls (optional): For reference-to-video (Wan v2.6)
- audio_url (optional): Custom audio (Wan v2.6, OmniHuman)
- fast_mode (optional): Boolean for Veo 3.1 models
- hd_mode (optional): Boolean for Veo 3.1 models (1080p)
**Requires**: User confirmation (costs credits and time)
**Use when**: Need video clips, animations, visual content

### audio_generation
**Purpose**: Generate TTS, sound effects, music, songs
**Parameters**:
- model (required): Model selection based on needs
- task_summary (required): Brief summary of task
- file_name (required): Output filename
- query (optional): Text or description
- requirements (optional): Detailed TTS requirements
- duration (optional): For sound effects/music (seconds)
- image_urls (optional): Reference images (default [])
- previous_audio_params (optional): For voice consistency
- custom_voice_id (optional): For voice cloning/changing
- voice_files (optional): For voice cloning
- source_audio_file (optional): For voice changing
- lyrics (optional): For song generation
- script_url (optional): For Gemini TTS
**Requires**: User confirmation (costs credits and time)
**Use when**: Need TTS, sound effects, background music, songs

### infographic_answer
**Purpose**: Answer questions visually with infographic
**Parameters**:
- title (required): Main title
- key_points (required): Array of 3-7 key points
- style (required): modern, minimalist, corporate, colorful, tech, creative, professional
- aspect_ratio (required): 1:1, 4:3, 16:9, 9:16, 3:4
- color_scheme (optional): Color preferences
- include_icons (optional): Boolean
- additional_context (optional): Design instructions
- image_urls (optional): Reference images
**Requires**: User confirmation (costs credits and time)
**Use when**: Best to communicate through visual representation

## File and Media Tools

### file_format_converter
**Purpose**: Convert file formats
**Parameters**:
- from_format (required): Source format
- to_format (required): Target format
- file_url (required): URL of file to convert
**Requires**: User confirmation (costs credits and time)
**Use when**: Need to convert between file formats

### merge_audio
**Purpose**: Merge multiple audio clips
**Parameters**:
- audio_clips (required): Array of clips with {ai_drive_path, start_time, end_time, insert_position, merge_type, volume, fade_type, fade_duration}
- original_audio_path (optional): Base audio file (optional for concat-only mode)
**Returns**: Public URL of merged audio
**Merge types**: insert, parallel, concat
**Use when**: Need to combine audio clips with precise control

### extract_audio_from_video
**Purpose**: Extract audio track from video
**Parameters**:
- video_urls (required): Array of video URLs or AI Drive paths
- output_aidrive_path (required): AI Drive destination path
- audio_bitrate (optional): Default 128k
- audio_sample_rate (optional): Default 16000
**Output format**: MP3
**Use when**: Need audio track from video files

## Shopping Tools

### product_search
**Purpose**: Search Amazon products
**Parameters**:
- type (required): product_search or product_detail
- query (optional): Search query (required for product_search)
- ASIN (optional): Product ASIN (required for product_detail)
- location_domain (optional): com (default)
**Returns**: ASIN, Prime eligibility, Amazon's Choice, prices, ratings
**Use when**: Need Amazon-specific data or ASIN info

### google_product_search
**Purpose**: Cross-retailer product search
**Parameters**:
- query (required): Product search query
- num (optional): Number of results (default 100, max 100)
- page (optional): Page number (default 0)
**Returns**: Aggregated results from multiple sellers
**Use when**: Need price comparison across retailers

## Finance Tools

### stock_price
**Purpose**: Get current stock price
**Parameters**:
- symbol (required): Stock ticker symbol (e.g., AAPL, MSFT)
**Use when**: User explicitly asks about stock price

### financial_report
**Purpose**: Search official financial reports
**Parameters**:
- symbol (required): Stock ticker symbol
- fiscal_year (required): 4-digit year
- period (required): Q1, Q2, Q3, Q4, or FY
- focus_question (required): Specific question to answer
- company_name (optional): Full company name
- need_earning_call_content (optional): Boolean for call transcript
**Use when**: Need earnings reports, 10-K, 10-Q, financial statements

## Communication Tools

### phone_call
**Purpose**: Create AI-powered phone call card
**Parameters**:
- recipient (required): Name of person or business
- contact_info (required): Phone number or Google Maps place_id
- is_place_id (required): Boolean (true for business, false for personal)
- purpose (required): Clear reason for call
**Phone number format**: +1-555-123-4567 (with country code)
**Data lineage**: MUST have verifiable source, NEVER fabricate
**Limitations**: Not available in China, Iran, few other regions
**Use when**: User wants to contact someone to get info or make arrangements

### query_call_logs
**Purpose**: Query call history
**Parameters**:
- time_range_hours (optional): Hours to look back
- limit (optional): Max results (default 3)
- include_transcript (optional): Boolean (default false)
**Returns**: Call logs in reverse chronological order
**Use when**: Need to review previous call history

## AI Drive Tools

### aidrive_tool
**Purpose**: Manage files in AI Drive cloud storage
**Actions**:
- ls: List directory contents
- mkdir: Create directories
- rm: Move to trash (recoverable)
- move: Relocate/rename files
- get_readable_url: Generate 1-hour temp URL
- download_video: Download videos from platforms
- download_audio: Download audio from platforms
- download_file: Download files from URLs
- compress: Compress folder to ZIP
- decompress: Decompress archive to folder
**Parameters**: Vary by action
**Use when**: Need persistent file storage and management

## Sandbox Tools

### Bash
**Purpose**: Execute bash commands in sandbox
**Parameters**:
- command (required): Bash command to execute
- description (optional): What command does (5-10 words)
- timeout (optional): Max time in ms (default 120000, max 600000)
**Environment**: Ephemeral Linux container
**Use when**: Custom computation, code execution, data processing

### Read
**Purpose**: Read files from sandbox
**Parameters**:
- file_path (required): Absolute path to file
- offset (optional): Starting line number
- limit (optional): Number of lines to read
**Default**: Up to 2000 lines
**Supports**: Text files, images (displays visually)
**Use when**: Need to view sandbox file contents

### Write
**Purpose**: Create or overwrite files in sandbox
**Parameters**:
- file_path (required): Absolute path (must start with /)
- content (required): File content
**Use when**: Creating new files (especially code files for Bash execution)

### MultiEdit
**Purpose**: Perform multiple edits to a file
**Parameters**:
- file_path (required): Absolute path
- edits (required): Array of {old_string, new_string, replace_all}
**Atomic**: All edits succeed or none applied
**Use when**: Need to make multiple precise edits to existing file

### DownloadFileWrapper
**Purpose**: Download file wrapper URLs to sandbox
**Parameters**:
- file_wrapper_url (required): File wrapper URL
- destination_directory (optional): Where to save (default ./)
- filename (optional): Custom filename
**Supported URLs**: https://www.genspark.ai/api/files/s/...
**Use when**: User explicitly requests sandbox download

## Agent Creation Tools

### create_agent
**Purpose**: Create specialized agent for complex tasks
**Parameters**:
- task_type (required): podcasts, docs, slides, sheets_new, deep_research, website, clip_genius, image_designer
- task_name (required): Name for task/project
- query (required): Query describing task
- instructions (required): Detailed instructions (system prompt)
- session_id (optional): For agent reuse
- agent_config_id (optional): For dynamic agents
**Use when**: Complex workflows better handled by specialized agent
**Note**: Direct users to task URL for modifications

## Utility Tools

### think
**Purpose**: Internal reasoning and planning
**Parameters**:
- thought (required): Thought to record
**Use when**: Need complex reasoning or cache memory

### get_current_utc_time
**Purpose**: Get precise current UTC time
**Parameters**: None
**Returns**: Current UTC time with second precision
**Use when**: User explicitly asks for precise time (hours/minutes/seconds)
**Note**: For date-only questions, use current date 2026-01-06 directly
