# YouTube Video Summarizer

This project provides a Jupyter notebook that can summarize YouTube videos using their transcripts and Groq's AI model. The summarizer extracts the video's transcription and generates a comprehensive summary focusing on main points, key insights, and important conclusions.

## Features

- Extract YouTube video transcripts
- Process transcripts using Groq's Mixtral-8x7b model
- Generate structured summaries with main topics, key points, and conclusions
- Support for both standard YouTube URLs and shortened (youtu.be) links

## Prerequisites

- Python 3.8+
- Groq API key
- Internet connection for accessing YouTube and Groq API

## Installation

1. Clone this repository
2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```
3. Create a `.env` file in the project directory and add your Groq API key:
   ```
   GROQ_API_KEY=your_api_key_here
   ```

## Usage

1. Start Jupyter Notebook:
   ```bash
   jupyter notebook
   ```
2. Open `youtube_summarizer.ipynb`
3. Run all cells in the notebook
4. Replace the example YouTube URL with your desired video URL
5. Run the cell to get your summary

## Example

```python
youtube_url = "https://www.youtube.com/watch?v=your_video_id"
summary = summarize_youtube_video(youtube_url)
print(summary)
```

## Note

- The video must have available transcripts (either auto-generated or manually created)
- The quality of the summary depends on the quality of the transcript and the video content
- Make sure you have sufficient API credits in your Groq account

## License

This project is open-source and available under the MIT License.
