# Video and Audio Analysis with Google Gemini API

This repository provides a solution for analyzing videos and extracting both visual and audio data using the Google Gemini API. The script facilitates video processing and automatic caption generation based on scene descriptions and audio transcription.

## Requirements

- **Google Colab**: The code is intended to run in a Google Colab environment.
- **Google Gemini API**: Used for video and audio analysis.
- **Python Libraries**: `google-genai`, `time`, `IPython`

## Setup Instructions

1. **Install Required Packages**:
   - Install the `google-genai` Python package using the following command:

     ```bash
     !pip install --upgrade --quiet google-genai
     ```

2. **API Key Setup**:
   - Ensure you have a valid Google Gemini API key.
   - The key should be available in the Colab environment, retrieved through `userdata.get('GOOGLE_API_KEY')`.

3. **Google Colab Integration**:
   - The code integrates with Google Colab for file uploads and processing.

## Video Upload and Processing

1. **Upload Video**:
   - Upload a video file (e.g., `video.mp4`) to the Colab environment.
   - The script uploads the video to Google Gemini, where it will be processed.

2. **Video Processing**:
   - The video file undergoes processing until its state changes from "PROCESSING" to either "COMPLETED" or "FAILED".
   - The process may take some time depending on the video size.

## Caption and Audio Transcription

1. **Video Caption Generation**:
   - The system generates captions for each scene in the video.
   - Captions include scene descriptions and any spoken text in quotation marks.
   - The captions are matched with corresponding timecodes in the video.

2. **Audio Transcription**:
   - The script extracts and transcribes the audio from the video.
   - The transcription includes a detailed analysis of what is being spoken.

3. **Custom Prompt for Analysis**:
   - The prompts used for the video and audio analysis are customizable.
   - Example prompt for scene captions and speech transcription:

     ```text
     For each scene in this video, generate captions that describe the scene along with any spoken text placed in quotation marks.
     Place each caption into an object with the timecode of the caption in the video.
     Can you also tell me what I am saying in the video in the first 2 seconds?
     ```

4. **Output**:
   - The response from the API will contain the generated captions and the spoken text from the video.

## Output Display

- The output is displayed using Markdown in the notebook.
- Each scene's description and the transcribed speech will be shown with their respective timecodes.

## Troubleshooting

- If the video processing fails, check the video file format and size.
- Ensure that the API key is valid and properly set in the environment.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.