# Advanced Tool Documentation

## Media Generation Models

### Image Generation Models

#### nano-banana-pro (DEFAULT)
- GEMINI NANO BANANA PRO
- State of the Art (SOTA) for both generation and image editing
- Multi-image fusion: Combine different images into one
- Character & style consistency across multiple generations
- Conversational editing with natural language
- Supports up to 14 reference images
- Supports high resolution output up to 2K/4K
- Perfect for creative use cases, marketing, training, advertising

#### fal-ai/gpt-image-1.5
- GPT Image 1.5
- Supports text-to-image and image editing
- Multi-image input support

#### imagen4
- Latest model for high quality image generation
- Upgrade from Imagen 3
- Currently in preview mode

#### recraft-v3
- Model for generating realistic images

#### fal-ai/bytedance/seedream/v4.5
- Bytedance Seedream v4 model
- Text-to-image and image-to-image
- Single and multiple image editing
- Native 2K resolution
- Excellent text layout

#### fal-ai/flux-2 and fal-ai/flux-2-pro
- Enhanced realism and crisp text generation
- Native editing capabilities
- Fast processing with flexible aspect ratios
- Supports up to 3 images for edit mode
- Pro version: higher quality, professional-grade output

#### fal-ai/z-image/turbo
- Optimized for speed without sacrificing quality
- Text-to-image and image-to-image modes
- Perfect for quick iterations, bulk generation
- Cost-effective projects

#### ideogram/V_3
- FACE CONSISTENCY specialist
- Superior facial feature preservation
- Character consistency across styles/poses/scenes
- Natural language understanding
- Excellent text rendering

#### qwen-image
- CHINESE POSTER SPECIALIST
- Outstanding Chinese poster creation
- Superior Chinese text rendering
- Cultural context mastery
- Exceptional Chinese understanding
- Cost efficient

#### Specialized Models
- **bbox-segment**: Extract subjects from images based on bbox region
- **fal-bria-rmbg**: Remove background from image (prioritize for background removal)
- **fal-ai/recraft-clarity-upscale**: Upscale images
- **fal-ai/image-editing/text-removal**: Remove text and watermarks
- **flux-pro/outpaint**: Expand image to specific aspect ratio

### Video Generation Models

#### kling/v2.6/pro
- Latest Kling v2.6 Pro model
- Enhanced quality with native audio generation
- Optimized for professional text-to-video and image-to-video
- Supported ratios: 16:9, 9:16, 1:1
- Duration: 5s, 10s

#### gemini/veo2
- Advanced model for video generation
- Fast (80s one video)
- Supports image-to-video (ONE image only)
- Supported ratios: 16:9, 9:16
- Duration: 5s, 6s, 7s, 8s

#### gemini/veo3
- Advanced model for high quality video with sounds
- Duration: 8s
- Supports image as first frame
- Text-to-video ratios: 16:9, 9:16
- Image-to-video ratios: 16:9

#### gemini/veo3/fast
- Faster and more cost-effective version of Veo 3
- Duration: 8s
- Supports reference image as first frame
- Text-to-video ratios: 16:9, 9:16
- Image-to-video ratios: 16:9

#### gemini/veo3.1
- Latest version with enhanced quality
- Duration: 8s
- Supported ratios: 16:9, 9:16
- Supports fast_mode (faster generation)
- Supports hd_mode (1080p quality)
- Text-to-video and image-to-video

#### gemini/veo3.1/reference-to-video
- Generate video using multiple reference images
- Requires 1+ reference images
- Duration: 8s
- Supported ratios: 16:9, 9:16
- Supports fast_mode and hd_mode

#### gemini/veo3.1/first-last-frame-to-video
- Generate video by specifying first and last frames
- Requires exactly 2 images
- Duration: 8s
- Supported ratios: 16:9, 9:16
- Supports fast_mode and hd_mode

#### minimax/video-01-subject-reference
- Generate video with subjects from images
- Only image-to-video supported
- Supported ratios: 9:16
- Duration: 5s

#### minimax/hailuo-2.3/standard
- High-quality video generation
- Text-to-video and image-to-video
- First & last frame control
- Fast generation (about 4min one video)
- Cost-effective
- Supported ratios: 16:9, 9:16
- Duration: 6s, 10s

#### wan/v2.6
- Latest Wan model with 1080p support
- Audio integration
- Text-to-video, image-to-video, reference-to-video
- Supported ratios: 16:9, 9:16, 1:1, 4:3, 3:4
- Duration: 5s, 10s, 15s
- Supports custom audio (WAV/MP3, 3-10s, up to 15MB)

#### vidu/q2
- Enhanced quality with fast turbo processing
- Text-to-video and image-to-video
- Supported ratios: 16:9, 9:16, 1:1
- Duration: 2s-8s

#### hunyuan
- High quality but slow
- Supported ratios: 16:9, 9:16
- Duration: 5s

#### runway/gen4_turbo
- High quality and fast
- Only supports image-to-video
- Supported ratios: 5:3, 3:5
- Duration: 5s, 10s

#### official/pixverse/v5
- High quality and fast (30s one video)
- Expensive
- Supported ratios: 16:9, 9:16, 4:3, 1:1, 3:4
- Duration: 5s, 8s
- Supports smooth transitions between two keyframes (start and end)

#### fal-ai/bytedance/seedance/v1.5/pro
- High-quality video generation
- Text-to-video and image-to-video with audio generation
- First & last frame control
- HD output (720p)
- Native audio support
- Supported ratios: 21:9, 16:9, 4:3, 1:1, 3:4, 9:16
- Duration: 4-12s

#### sora-2
- OpenAI Sora 2 for fast, creative videos
- Text-to-video, image-to-video, video remixing
- Designed for speed and experimentation
- Supported ratios: 16:9, 9:16
- Duration: 4s, 8s, 12s

#### sora-2-pro
- OpenAI Sora 2 Pro for production-quality
- Higher fidelity than sora-2
- Cinematic footage and marketing assets
- 720p and 1080p resolutions
- Supported ratios: 16:9, 9:16
- Duration: 4s, 8s

#### fal-ai/bytedance-upscaler/upscale/video
- ByteDance Video Upscaler
- Enhances video quality to higher resolutions (2k)
- Requires video_url parameter
- Does NOT generate new videos
- Use for improving quality of existing videos

### Audio Generation Models

#### google/gemini-2.5-pro-preview-tts
- Best, high-quality, realistic tone
- Supports one or multiple speakers in one generation
- Speaker prefixes: 'Speaker1: text, Speaker2: text'

#### elevenlabs/v3-tts
- Advanced multilingual text-to-speech
- Multi-speaker dialogue support
- Supports emotional tags: [excited], [whispers], [laughs]
- Best for expressive content and conversations

#### fal-ai/elevenlabs/tts/multilingual-v2
- High-quality multilingual text-to-speech
- Preferred for English

#### fal-ai/minimax/speech-2.6-hd
- High-quality multilingual text-to-speech
- Preferred for Chinese, Yue, Japanese, Korean
- Note: Only one speaker per generation
- For multiple characters, generate sequentially

#### elevenlabs/sound-effects
- Sound effect generation
- Minimum: 0.1 seconds
- Maximum: 22 seconds

#### elevenlabs/music
- Music generation model
- Supports instrumental music AND songs with vocals/singing
- NOTE: Does NOT support custom lyrics (auto-generated)
- Minimum: 10 seconds
- Maximum: 5 minutes (300 seconds)
- Professional music production quality

#### elevenlabs/voice-clone
- Voice cloning model
- Clone voice from audio samples
- Returns voice ID for use in TTS generation

#### elevenlabs/voice-changer
- Voice changer model
- Transform audio from one voice to another
- Requires source audio and target voice ID

#### CassetteAI/music-generator
- Background music generation
- Minimum: 10 seconds
- Maximum: 180 seconds

#### mureka/song-generator
- Professional song generation with lyrics
- Supports style prompts, reference tracks
- Vocal and melody inputs
- Generate full songs with vocals
- Maximum: 180 seconds

#### mureka/instrumental-generator
- Instrumental music generation
- Background music without vocals
- Supports style prompts and reference tracks
- Maximum: 180 seconds

#### fal-ai/lyria2
- Google's Lyria 2 text-to-music model
- Good at generating music for sound effects
- Lyrics-free music
- Maximum: 30 seconds

#### fal-ai/minimax-music/v2
- Song generation with lyrics
- Supports structured lyrics markers: [Verse], [Chorus], [Bridge], [Outro]
- Requires both style prompt and lyrics

## Specialized Agent Types

### podcasts
- Create audio podcasts with AI characters
- Multi-character dialogue support
- Professional audio production

### docs
- Create and edit HTML/Markdown documents
- Professional document with Word-like formatting
- Perfect for reports, articles, academic papers
- Single-file HTML format
- For print or PDF export

### slides
- Create presentation slides
- Written in HTML format
- Takes minutes to generate
- Ask user for confirmation before starting if not explicitly requested

### sheets_new
- Create spreadsheet with new agent
- Convert materials into spreadsheet
- Excel table creation
- Use only when user explicitly requests spreadsheet

### deep_research
- Deep research agent for topics
- In-depth analysis and exploration
- Use when user wants "deep research" on topic
- Can handle "continue deep research" requests

### website
- Professional agent for building websites
- Complete web page creation
- Modern web development

### clip_genius
- Professional video editor agent
- Long video to short video content
- Flexible workflow processing

### image_designer
- Professional image designer agent
- Senior design director level AI expert
- Complete design workflow:
  - Deep requirement analysis (search + reasoning)
  - Inspiration capture from Behance/Dribbble/Pinterest
  - Image verification
  - Intelligent model selection
- Use cases:
  - Creative design: posters, banners, social media graphics
  - Brand identity & visual systems
  - Template/image editing
  - Image uploads for editing or style reference
  - Brand consistency with logo preservation
  - Portrait/character with facial consistency
  - Style transfer & logos
  - Chinese content and Chinese text
  - Typography & signatures
  - UI/UX design
  - E-commerce materials
- Supports creation from scratch and modifications based on references
