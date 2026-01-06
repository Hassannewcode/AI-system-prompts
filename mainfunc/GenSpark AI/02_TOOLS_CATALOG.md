# Tool Capabilities Catalog

## Information Retrieval Tools

### web_search
- General web search with query
- Returns titles, URLs, snippets, thumbnails
- Fallback when specialized tools insufficient
- Max 20 words query, no line breaks

### scholar_search
- Search scholarly articles and academic papers
- For research and academic content

### maps_search
- Geographical information and locations
- Local business information
- Distance calculations and directions
- Modes: maps (places), maps_directions (routes)

### crawler
- Fetches COMPLETE raw content from URLs as markdown
- Best for moderate-length content (articles, blogs, news, docs)
- Preserves complete structure (headings, lists, code blocks)
- Supports webpages, PDFs, CSV, Office docs (Word, PowerPoint)
- Cannot read Excel

### summarize_large_document
- Answers SPECIFIC questions about VERY LONG documents
- Use when document explicitly described as very long (hundreds of pages)
- Intelligent retrieval for relevant content only
- Best for: annual reports, legal contracts, academic papers, e-books
- Supports PDFs, web pages, Word, PowerPoint
- Cannot process Excel

### url_metadata
- Check URL metadata without downloading
- Returns content-type, content-length, filename, extension
- For images, checks CORS support

### financial_report
- Search official financial reports and earnings
- 10-K, 10-Q, annual/quarterly reports
- Public company financial statements

### stock_price
- Retrieve current stock price information
- Only use when user explicitly asks about stock price

## Content Understanding Tools

### understand_images
- Read and understand images from URLs or AI Drive paths
- Supports web URLs and AI Drive (starting with '/' or 'aidrive://')
- Models: gpt-4o (default), gemini-flash
- Requires detailed instruction for analysis

### understand_video
- Extract transcript from videos
- Currently supports YouTube videos only
- Can provide download link for transcript

### batch_understand_videos
- Process multiple videos efficiently
- Fetch transcripts and answer specific questions
- YouTube only

### audio_transcribe
- Precisely transcribes audio to text
- Word-level and segment-level timestamps
- Supports: mp3, mp4, mpeg, mpga, m4a, wav, webm
- Can handle large files by auto-splitting
- Optional prompt for improved quality

### analyze_media_content
- Analyze images, audio, video
- Deep analysis based on requirements
- Supports parallel processing of multiple formats
- Supports web URLs and AI Drive paths
- Special mode: video_style_replication

## Content Generation Tools

### image_generation
- Generate images from text descriptions or reference images
- Default model: nano-banana-pro
- Supports text-to-image and image editing
- Multiple aspect ratios: 1:1, 4:3, 16:9, 9:16, 3:4, 2:3, 3:2
- Available models:
  - nano-banana-pro (default, SOTA for generation and editing)
  - fal-ai/gpt-image-1.5 (multi-image input support)
  - imagen4 (high quality, preview mode)
  - recraft-v3 (realistic images)
  - fal-ai/flux-2, fal-ai/flux-2-pro (enhanced realism)
  - ideogram/V_3 (face consistency specialist)
  - qwen-image (Chinese poster specialist)
  - bbox-segment (subject extraction)
  - fal-bria-rmbg (background removal)
  - fal-ai/recraft-clarity-upscale (upscaling)
  - fal-ai/image-editing/text-removal (remove text/watermarks)
  - flux-pro/outpaint (expand images)
- Requires user confirmation (costs credits and time)

### video_generation
- Generate 5-10 second video clips
- Text-to-video or image-to-video
- Multiple models available:
  - kling/v2.6/pro (latest, enhanced quality, audio)
  - gemini/veo2, veo3, veo3/fast (advanced, high quality)
  - gemini/veo3.1 (latest with fast/HD modes)
  - minimax models (subject reference, hailuo-2.3)
  - wan/v2.6 (1080p, audio integration)
  - vidu/q2 (enhanced quality, fast)
  - hunyuan (high quality, slow)
  - runway/gen4_turbo (high quality, fast)
  - official/pixverse/v5 (high quality, fast)
  - sora-2, sora-2-pro (OpenAI models)
  - fal-ai/bytedance/seedance/v1.5/pro (HD with audio)
  - fal-ai/bytedance-upscaler/upscale/video (enhance quality)
- Various aspect ratios and durations
- Requires user confirmation (costs credits and time)

### audio_generation
- Text-to-speech with customizable voices
- Sound effects generation (up to 22 seconds)
- Music generation (up to 180 seconds)
- Song generation with lyrics
- Voice cloning and voice changing
- Available models:
  - google/gemini-2.5-pro-preview-tts (best quality, multi-speaker)
  - elevenlabs/v3-tts (advanced multilingual, emotional)
  - fal-ai/elevenlabs/tts/multilingual-v2 (high quality)
  - fal-ai/minimax/speech-2.6-hd (Chinese/Japanese/Korean preferred)
  - elevenlabs/sound-effects (0.1-22 seconds)
  - elevenlabs/music (10-300 seconds, auto-generated lyrics)
  - elevenlabs/voice-clone (clone voices)
  - elevenlabs/voice-changer (transform voices)
  - CassetteAI/music-generator (10-180 seconds)
  - mureka/song-generator (with lyrics, up to 180s)
  - mureka/instrumental-generator (no vocals, up to 180s)
  - fal-ai/lyria2 (Google's text-to-music, up to 30s)
  - fal-ai/minimax-music/v2 (song with lyrics)
- Requires user confirmation (costs credits and time)

### infographic_answer
- Answer questions visually with infographics
- Best for: comparisons, statistics, timelines, processes
- Styles: modern, minimalist, corporate, colorful, tech, creative, professional
- Aspect ratios: 1:1, 4:3, 16:9, 9:16, 3:4
- Requires user confirmation (costs credits and time)

## File and Media Tools

### file_format_converter
- Convert file formats
- Requires user confirmation (costs credits and time)

### merge_audio
- Merge multiple audio clips into original audio
- Supports clipping, positioning, fade effects
- Three modes: insert, parallel, concat
- Auto-uploads to blob storage, returns public URL

### extract_audio_from_video
- Extract audio from video files
- Saves to AI Drive in MP3 format
- Supports URLs and AI Drive paths

### resource_discovery
- Detect and catalog downloadable media from webpages
- Finds images, videos, documents, audio, archives
- Uses headless browser technology
- Max 30 resources, 30s timeout
- High computational cost

## Shopping and Product Tools

### product_search
- Search products on Amazon
- Returns ASIN, Prime eligibility, Amazon's Choice badges
- Modes: product_search (by query), product_detail (by ASIN)

### google_product_search
- Cross-retailer product search via Google Shopping
- Aggregates results from multiple sellers
- Best for price comparison

## Communication Tools

### phone_call
- Create AI-powered phone call card
- Two modes:
  - Personal contacts (is_place_id=false): requires phone number
  - Business contacts (is_place_id=true): uses Google Maps place_id
- Phone numbers MUST have verifiable data lineage
- Cannot fabricate or generate phone numbers
- Supports most countries globally (except China, Iran)

### query_call_logs
- Query call history logs
- Filter by time range and limit
- Can include full conversation transcripts
- Returns in reverse chronological order

## Agent Creation Tools

### create_agent
- Create and execute tasks using specialized agents
- Task types:
  - podcasts: Audio podcasts with AI characters
  - docs: HTML/Markdown documents with Word-like formatting
  - slides: Presentation slides (takes minutes)
  - sheets_new: Spreadsheets and Excel tables
  - deep_research: Deep research on topics
  - website: Professional website building
  - clip_genius: Video editing (long to short)
  - image_designer: Professional image design workflows
- For modifications, direct users to task URL (/agents?id=xxxx)

## Search Tools

### image_search
- Search for existing images on the internet
- Find real photos, diagrams, illustrations

### video_search
- Search for existing videos
- Currently supports YouTube platform
- Good for tutorials, reviews, demonstrations

## Webpage Tools

### webpage_capture_screen
- Capture screenshot of webpage
- Alternative when crawling fails
- Configurable viewport dimensions
