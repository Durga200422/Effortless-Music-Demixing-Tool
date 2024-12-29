# Hi, I'm Narapureddy Durga Prasad Reddy! 👋

This project is a Music Stem Splitter developed using open-source model. The model was selected after rigorous comparison with multiple existing models due to its superior functionalities. The project is implemented as a Streamlit application.
# Effortless Music Demixing Tool

Effortless Music Demixing Tool is a powerful yet user-friendly application that leverages the open-source Demucs model for music source separation. Designed for musicians, producers, and hobbyists, this tool allows you to separate audio tracks into distinct stems, such as drums, bass, vocals, and others. The application ensures streamlined performance and compatibility across various audio formats.
## Features

- 4-Stem Configuration: Separates audio into drums, bass, other, and vocals.

- Format Conversion: Automatically converts audio files to WAV format for processing.

- Batch Uploads: Supports multiple files for simultaneous processing.

- Downloadable Outputs: Easily download separated stems.

- Streamlit Interface: Interactive and intuitive UI for ease of use.

## Tech Stack

**Python:** Core programming language

**Streamlit:** Web-based interface

**Demucs:** Model for stem separation

**Torchaudio:** Audio handling and processing

**Pydub:** Audio format conversion fallback


## Installation

### 1. Prerequisites

- Python 3.8 or later

- Dependencies listed in requirements.txt


**2. Required Libraries** 

     torch

     torchaudio

     pydub

     streamlit
    
     demucs

**3. System Dependencies**

### FFmpeg: 
Required for audio format conversion and processing.

- Download FFmpeg from the [official FFmpeg website.](https://ffmpeg.org/)
- Follow the installation instructions for your operating system.

### libsndfile: 
Required for audio file I/O operations.
- Download libsndfile from the [official libsndfile GitHub repository.](https://github.com/libsndfile/libsndfile)
- Follow the installation guide provided in the repository.

## Usage/Examples

    1. Launch the app and upload your audio files (MP3, WAV, FLAC).

    2. Wait for the AI to process the uploaded files.

    3. Download the separated stems as WAV files.


## Run Locally

Clone the project

```bash
  git clone https://github.com/Durga200422/Effortless-Music-Demixing-Tool
```
Set up a virtual environment (optional but recommended):

```bash
  python -m venv myvenv
  source myvenv/Scripts/activate  # On Windows
  source myvenv/bin/activate      # On Linux/MacOS
```
Go to the project directory

```bash
  cd Effortless-Music-Demixing-Tool
```

Install dependencies

```bash
  pip install -r requirements.txt
```

Start the Streamlit server

```bash
  streamlit run BeatBreakdown.py
```


## Demo

Here is how the application looks and works:

**Screen Looks Like:**
![Screenshot 2024-12-29 173613](https://github.com/user-attachments/assets/504f0436-2ec8-4971-a740-9694eb11f5dc)

**Uploading multiple audio files simultaneously:**
![Screenshot 2024-12-29 173812](https://github.com/user-attachments/assets/8ddca363-4142-4e5b-8547-017e827da971)

**Processing Indicator -> The app displays a spinner while the AI processes the uploaded files.
Playback and Download:**
![Screenshot 2024-12-29 173820](https://github.com/user-attachments/assets/beca9455-960f-46e5-8849-9a6674254d28)

**Listen to the separated stems directly in the app.
Download each stem in WAV format.**
![Screenshot 2024-12-29 174016](https://github.com/user-attachments/assets/9894770c-0884-42a1-8845-a532567df7ce)

## Authors

- Narapureddy Durga Prasad Reddy, pursuing Bachelor's in Manav Rachna University


## Acknowledgements

- **Demucs Developers:** For creating the open-source model.

- **Streamlit Community:** For their fantastic framework.


## Lessons Learned

Initially, I attempted to use the open-source Spleeter model for stem separation. While it is a robust tool, I encountered significant challenges due to its heavy dependencies and high computational requirements. My system struggled to handle these dependencies efficiently, leading to performance bottlenecks and frequent interruptions during processing. This experience highlighted the importance of selecting tools that align with system capabilities for smoother workflows.

As a result, I transitioned to the Demucs open-source model, which proved to be more compatible with my setup. While Demucs offered excellent performance for 4-stem separation, I also realized its limitation in handling 2-stem configurations effectively. My decision to avoid a workaround (summing drums, bass, and other stems into one) reinforced my focus on maintaining output quality over quick fixes. This journey underscored the need to balance computational efficiency and output accuracy in AI-powered applications.
## Roadmap

- Add support for 2-stem configuration.

- Improve processing time for large audio files.

- Extend format compatibility beyond current supported formats.


## Optimizations

**Fallback Mechanism for Audio Conversion:**
When Torchaudio occasionally fails to convert audio files to WAV format due to codec-related complexities, I integrated a fallback mechanism using Pydub. This ensures seamless processing of various input formats without manual intervention, enhancing user experience and reliability.

**Standardization of Audio Input:**
I standardized all input audio files to uncompressed PCM WAV format. This eliminates potential compatibility issues with different codecs and allows the Demucs model to process data more efficiently. The uncompressed format ensures that the audio retains its quality and prevents data loss during conversion.

**Device-Aware Model Loading:**
The application dynamically detects available hardware (GPU or CPU) and optimizes model execution accordingly. By leveraging GPU acceleration when available, processing times are significantly reduced.

**Improved User Experience:**
Added clear status messages and progress indicators to keep users informed during the processing phase. The interface also handles multiple file uploads efficiently, catering to diverse user needs.

**Streamlined Error Handling:**
Implemented robust error-handling mechanisms to identify and notify users of issues like incompatible file formats, missing dependencies, or unexpected input errors. This ensures that users receive actionable feedback instead of vague error messages.


## Limitations

#### 2-Stem Configuration:

-   Demucs does not natively support 2-stem separation.
-   A potential workaround is summing Drums, Bass, and Other into one stem and separating Vocals, but this approach compromises accuracy and was not implemented.
#### Dependency Challenges with Spleeter:

-   Earlier, we explored Spleeter, another open-source model.
-   However, due to system capability issues, such as hardware limitations and dependency complexities, we could not achieve the desired performance.
#### File Format Conversion:

-   While torchaudio is the default library for conversion, it occasionally fails.

-   To address this, we integrated pydub as a fallback for reliable WAV conversion.

    #### Why WAV?

    WAV standardizes the input to uncompressed PCM audio, simplifying the processing for   models like Demucs and avoiding codec-specific complexities.
## Feedback

If you have any feedback, please reach out to me at narapureddydurgaprasad818@gmail.com or [@Linkedin](https://www.linkedin.com/in/narapureddy-d-2a5402252?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)
 


## Support

For support, email narapureddydurgaprasad818@gmail.com or contact [@Linkedin](https://www.linkedin.com/in/narapureddy-d-2a5402252?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app)
  .


## Troubleshooting Common Issues


| Issue | Possible Cause    | Solution                |
| :-------- | :------- | :------------------------- |
| Model fails to load| Missing or incompatible torch installation | Ensure torch and torchaudio are installed correctly.|
|Conversion to WAV fails|torchaudio failure	|Ensure pydub is installed as a fallback.|
|GPU not utilized|	Incorrect CUDA setup|	Verify CUDA installation and availability with torch.cuda.is_available().|
|Streamlit app won't start|	Port conflict or dependency issues|	Check port usage and ensure all libraries are installed.|


