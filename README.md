# Automated Video Review Generator

## Overview

This project automates the process of reviewing educational videos, specifically focusing on generating structured reviews for Generative AI content. It leverages the Whisper library to transcribe the video, ffmpeg-python to extract audio, and a large language model (LLM) through Ollama (with llama3.2) to create a detailed review in Markdown format.

## Project Description

The application automates the video review process through the following steps:

1.  **Audio Extraction:** Extracts the audio track from the input video file using ffmpeg-python.
2.  **Transcription:** Transcribes the extracted audio into text using the Whisper ASR (Automatic Speech Recognition) model.
3.  **Summarization and Analysis:** Feeds the transcribed text into an LLM (llama3.2) with a carefully designed prompt. The LLM generates a structured Markdown review covering:
    * Video Summary
    * Topics Covered
    * Content Quality Evaluation
    * Beginner-Friendliness Assessment
    * Suggestions for Improvement
    * Final Verdict
4.  **Output:** Saves the generated Markdown review to a file.

This automation significantly speeds up the process of evaluating video content, providing valuable insights into content quality, suitability for beginners, and areas for improvement.

## Key Features

* **Automated Video Review:** Generates comprehensive reviews of educational videos.
* **Audio Extraction:** Utilizes ffmpeg-python for efficient audio extraction from various video formats.
* **Speech-to-Text Conversion:** Employs the Whisper model for accurate transcription of video audio.
* **Structured Markdown Output:** Produces reviews in a well-organized Markdown format, enhancing readability.
* **LLM-Powered Analysis:** Leverages the capabilities of the llama3.2 language model for content summarization and evaluation.
* **Customizable Prompt:** The prompt provided to the LLM can be adapted to suit different review requirements or video types.
* **Clear Processing Pipeline:** The notebook provides a clear and modular workflow for video processing, transcription, and review generation.

## Technologies Used

* **Whisper:** An open-source Automatic Speech Recognition (ASR) system by OpenAI, used for transcribing audio.
* **ffmpeg-python:** A Python wrapper for the ffmpeg command-line tool, used for audio extraction.
* **Ollama:** A tool for running language models locally, used here to serve the llama3.2 model.
* **llama3.2:** The specific language model used for generating the video reviews.
* **Python:** The primary programming language used for the project.
* **os:** Python's built-in operating system module for file path manipulation and cleanup.

## Installation and Setup

1.  **Install Dependencies:** Ensure you have Python 3.6 or later installed. It is highly recommended to create a virtual environment to manage dependencies. Then, install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

    *(Note: You'll need to create a `requirements.txt` file by running `pip freeze > requirements.txt` in your project directory.)*

2.  **Ensure ffmpeg is installed:** ffmpeg needs to be installed on your system and accessible from the command line.
    * On Windows, you can download it from the official website and add its `bin` directory to your PATH.
    * On macOS, you can use Homebrew (`brew install ffmpeg`).
    * On Linux, use your distribution's package manager (e.g., `sudo apt-get install ffmpeg`).

3.  **Set up Ollama and llama3.2:**
    * Install Ollama from the official website ([https://ollama.ai/](https://ollama.ai/)).
    * Make sure you have the `llama3.2` model available in Ollama.  If not, pull it:

        ```bash
        ollama pull llama3:latest
        ```

4.  **Prepare your video:** Place the video file you want to summarize in the specified directory or modify the `video_path` variable in the script to point to your video file.

## Usage

1.  **Place the video file:** Put the video you want to process in the `C:/Vedios_to_summarize/` directory, or change the `video_path` variable in the script to the correct location.
2.  **Run the notebook:** Execute the `file.ipynb` notebook in a Jupyter environment.
3.  **Review the output:** The script will:
    * Print messages to the console indicating the video being processed.
    * Save the generated Markdown review in a file named after the video (e.g., `1.1. Introduction to Generative AI.md`).
4.  **Open the Markdown file:** Open the generated `.md` file to view the structured review.

## Important Notes

* **Video Path:** The notebook currently has a hardcoded video path (`C:/Vedios_to_summarize/`).  You'll likely want to make this more flexible (e.g., using command-line arguments or user input).
* **Model Choice:** The notebook is configured to use `llama3.2`.  Ensure this model is compatible with your Ollama setup. You can modify the `llm = Ollama(model="llama3.2")` line to use a different model if desired.
* **Error Handling:** The current script has minimal error handling.  Consider adding more robust error handling for production use.
* **Performance:** Transcription and LLM processing can be time-consuming, especially for long videos.

## Potential Enhancements

* **Command-Line Interface (CLI):** Convert the notebook into a CLI tool for easier use.
* **Video Format Support:** Expand support for different video formats.
* **Batch Processing:** Add functionality to process multiple videos at once.
* **Customizable Output:** Allow users to customize the structure or content of the generated review.
* **Progress Tracking:** Implement progress bars or other feedback mechanisms for long videos.
* **Error Handling:** Add more comprehensive error handling.
* **Parameterization:** Allow users to specify the video path, output directory, and other settings via command-line arguments.

## Author

Sai Kumar
