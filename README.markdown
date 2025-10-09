# NotesGen

NotesGen is a Python program designed to transcribe audio from video or audio files into text, saving the output as a Microsoft Word (.docx) document. It supports both local video/audio files and YouTube videos, making it versatile for generating notes or transcriptions from various sources. The program leverages powerful libraries like `whisper` for transcription, `moviepy` for audio extraction, and `yt-dlp` for downloading YouTube videos.

## Features

- Transcribe audio from local video/audio files or YouTube video URLs.
- Supports any size of audio or video file (limited by system resources).
- Outputs transcriptions as a `.docx` file for easy editing and sharing.
- Automatically handles temporary file cleanup to save disk space.
- Uses OpenAI's Whisper model for accurate audio transcription.

## Prerequisites

Before running NotesGen, ensure you have the following installed:

- Python 3.6 or higher
- `ffmpeg` (required for audio extraction; install via your package manager, e.g., `apt install ffmpeg` on Ubuntu or `brew install ffmpeg` on macOS)
- Git (optional, for installing dependencies from source)

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/Thokhir/NoteGen.git
   cd NoteGen
   ```
2. Install the required Python packages:

   ```bash
   pip install moviepy yt-dlp python-docx
   pip install git+https://github.com/openai/whisper.git
   ```
3. Ensure `ffmpeg` is installed and accessible in your system's PATH:
   - On Windows, download from ffmpeg.org and add to PATH.
   - On Linux: `sudo apt install ffmpeg` (Ubuntu/Debian) or equivalent for your distro.
   - On macOS: `brew install ffmpeg`.

## Usage

1. Run the program:

   ```bash
   python NotesGen.py
   ```
2. Choose an input type:
   - Select `1` for a local video/audio file and provide the file path.
   - Select `2` for a YouTube video and provide the video URL.
3. The program will:
   - Extract audio from the video (if applicable).
   - Transcribe the audio using the Whisper model.
   - Save the transcription as `transcription.docx` in the current directory.
4. Temporary files (e.g., downloaded videos or extracted audio) are automatically deleted after processing.

## Example

```bash
Video Notes Generator
1. Local Video File
2. YouTube Video URL
Select input type (1/2): 2
Enter YouTube video URL: https://www.youtube.com/watch?v=kFWC6M6IHYY
[Downloading and processing...]
Transcription saved to transcription.docx
```

## Notes

- The program uses the `base` Whisper model by default for transcription. You can modify the `model_size` parameter in the `transcribe_audio` function to use other models (e.g., `small`, `medium`, `large`) for potentially better accuracy, though larger models require more memory and processing power.
- Ensure a stable internet connection when transcribing YouTube videos, as the video needs to be downloaded.
- The output `.docx` file can be opened with Microsoft Word, Google Docs, or other compatible software.
- Large files may take longer to process, depending on your system's performance and the length of the audio.

## Dependencies

- `moviepy`: For extracting audio from video files.
- `yt-dlp`: For downloading YouTube videos.
- `whisper`: For audio transcription (OpenAI's Whisper model).
- `python-docx`: For saving transcriptions as `.docx` files.
- `ffmpeg`: For audio extraction (external dependency).

## Troubleshooting

- **"ffmpeg is not installed or not in PATH"**: Install `ffmpeg` and ensure it's in your system's PATH.
- **Download errors for YouTube videos**: Check your internet connection or verify the URL is valid.
- **Memory issues with large files**: Try using a smaller Whisper model (e.g., `tiny`) or ensure your system has sufficient RAM.
- **Module not found errors**: Ensure all dependencies are installed correctly using `pip`.

## License

This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request on GitHub for any bug fixes or feature requests.

## Contact

For questions or support, open an issue on the GitHub repository.