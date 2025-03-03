# YouTube to Blog Converter & Blog Analyzer

## Project Overview

I've developed this soo farrrr
1. Converts YouTube videos into high-quality, SEO-optimized blog posts
2. Analyzes blog content for quality, readability, and SEO metrics
3. Supports multiple input formats (YouTube URLs, HTML, Markdown, text files)

## Key Features

### Video to Blog Conversion
- Downloads YouTube videos with yt-dlp (more stable than PyTube)
- Extracts audio for efficient processing
- Transcribes audio with OpenAI's Whisper API
- Translates transcripts into well-formatted blog posts with GPT-4o
- Uses parallel processing to transcribe long videos quickly
- Utilizes caching to prevent reprocessing same videos

### Blog Analysis
- In-depth scoring system for blog quality
- Readability scores (Flesch Reading Ease, Grade Level)
- SEO analysis (keyword density, header organization)
- Content quality evaluation (grammar, AI detection, engagement)
- Structure evaluation (headings, paragraphs, formatting)

### Technical Enhancements
- Intelligent chunking for coping with large audio files
- Parallel processing for faster transcription
- Caching system to avoid redundant processing
- Robust error handling throughout the pipeline
- Support for multiple file formats (MD, HTML, TXT)

## How to Use

### Converting a YouTube Video to a Blog Post

```
python phase.py --url https://www.youtube.com/watch?v=your_video_id

```



### Options
- `--url`: YouTube video URL to convert
- `--file`: Path to blog file to analyze (.md, .html, .txt)
- `--output`: Output directory (default: "output")
- `--temp`: Temporary directory (default: "temp")
- `--cache`: Cache directory (default: "cache")
- `--no-cache`: Disable caching
- `--analyze-only`: Analyze the blog only, don't convert

## Implementation Details

### Video Processing Pipeline
1. Extract video ID from YouTube URL
2. Download audio with yt-dlp
3. Split audio into chunks if necessary
4. Transcribe audio with OpenAI's Whisper API
5. Convert transcript to blog post with GPT-4o
6. Write blog post as Markdown file

### Blog Analysis Pipeline
1. Read content from file or URL
2. Sanitize and normalize text
3. Compute basic metrics (word count, read time)
4. Compute readability using textstat
5. Check SEO indicators (keywords, headers)
6. Check content quality (grammar, AI detection)
7. Compute final weighted score
8. Print detailed analysis report

## Future Improvements
- Support additional video platforms other than YouTube
- Add local transcription option for improved processing speed
- Improve SEO optimization with better techniques
- Include image extraction and insertion in blog posts
- Utilize custom blog styling and template options

## Dependencies
- yt-dlp: To ensure accurate YouTube video download
- OpenAI API: To process transcription and blog creation
- textstat: To determine readability level
- scikit-learn: To perform TF-IDF keyword analysis
- BeautifulSoup: To parse HTML
- NLTK: To process natural language tasks

## Notes
- An OpenAI API key is required for transcription and blog creation
- Processing time varies with video duration and quality setting
- Blog quality score relies on several weighted variables

