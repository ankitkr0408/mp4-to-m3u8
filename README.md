# MP4 to M3U8 Converter

## Prerequisites (First First)

Before using this tool, you must have the following installed on your system:

1.  **FFmpeg**: This tool relies heavily on FFmpeg for the actual video conversion.
    *   **Windows**: Download from [ffmpeg.org](https://ffmpeg.org/download.html), extract it, and add the `bin` folder to your System PATH environment variable.
    *   **Mac/Linux**: Install via package manager (e.g., `brew install ffmpeg` or `sudo apt install ffmpeg`).
2.  **Python 3.x**: If you intend to use the Python script version (`run.py`), make sure Python is installed.

## Usage

This tool converts an `.mp4` video file into an HLS `.m3u8` playlist and corresponding segment files (`.ts`). It automatically creates a new directory with the same name as your input file to store the output.

### Using Python
1.  Open your terminal or command prompt.
2.  Navigate to the directory containing `run.py`.
3.  Run the command:
    ```bash
    python run.py input_video.mp4
    ```

### Using Batch Script (Windows)
1.  Open your terminal or command prompt.
2.  Navigate to the directory containing `run.bat`.
3.  Run the command:
    ```cmd
    run.bat input_video.mp4
    ```

**Output**: 
The tool will generate a folder named `input_video` (based on your filename) containing:
- `input_video.m3u8`: The playlist file.
- Multiple `.ts` segment files.

## Need of M3U8 (HLS)

You might be wondering, "Why convert MP4 to M3U8?"

*   **Streaming Efficiency**: M3U8 is the file format for **HLS (HTTP Live Streaming)**. Unlike a single large MP4 file that needs to be downloaded (or buffered heavily) to play, HLS breaks the video into small chunks (`.ts` segments).
*   **Faster Playback**: The player only downloads the chunks it needs right now, leading to faster startup times and less buffering.
*   **Adaptive Bitrate**: While this specific script generates one quality level, HLS supports adaptive streaming, allowing players to switch video quality based on the user's internet speed.
*   **Industry Standard**: HLS is the standard protocol for video streaming on the web today, compatible with standard HTML5 video players like Video.js, Hls.js, etc.

## Support

If you found this tool helpful, please consider **giving this repository a Star ⭐**!

It helps others find the project and encourages further development.

---
*Feel free to open issues or pull requests if you find bugs or want to add features!*
