# Audio Transcription Tool with Whisper

This project leverages OpenAI's powerful Whisper model to automatically transcribe an entire folder of audio files (like those from WhatsApp), organizing the results into a structured table (`.csv`) ready for analysis.

Need to know what was said in dozens of voice messages but don't have time to listen to them all? This tool solves that problem, converting hours of audio into searchable text in a matter of minutes.

*[Leia em Português](README.md)*

### Key Features

* **🤖 High-Accuracy Transcription:** Utilizes the state-of-the-art Whisper family of models, with the flexibility to choose the version that best fits your needs.
* **📊 Structured Output:** Organizes all transcriptions into a single `.csv` table, containing the filename, duration, and the transcribed text, ideal for future analysis.
* **🗑️ Smart Duplicate Removal:** Checks for and offers to remove duplicate files based on their content (using MD5 hash), saving time and resources.
* **⚙️ Interactive Setup:** Allows the user to define important parameters during execution, such as model selection and the inclusion of a context "prompt."

Designed by: neidaniel6@gmail.com

### How to Use

1.  **Initial Run:** Open the notebook in Google Colab and run the first few cells to create the working folder (`audios_para_transcrever`) in your Google Drive.
2.  **Add Audios:** Move all your audio files into this newly created folder.
3.  **Finish Execution:** Return to the notebook and run the remaining cells in order, following the interactive prompts.

---

## Notebook Structure

### Cell 1: Installing Dependencies
Prepares the environment by installing the `openai-whisper`, `pydub`, and `ffmpeg` libraries. It is essential to wait for this cell to complete before proceeding.

### Cell 2: Connecting to Google Drive
Creates a secure connection to your Google Drive, allowing the script to access your files. Follow the authorization prompts that appear.

### Cell 3: Defining and Creating the Workspace
Automatically defines and creates the default working folder (`audios_para_transcrever`) in your Google Drive. You don't need to edit the code; simply move your audio files to this folder after it runs.

### Cell 3.5: Listing Files and Checking for Duplicates
Scans the working folder, lists the found audio files, and checks for content-based duplicates. If any are found, it will ask if you want to perform a cleanup.

### Cell 4: Choosing and Loading the AI Model
Presents an interactive menu to choose the Whisper model version (balancing speed and accuracy). **Warning:** larger models may fail with very long audio files.

### Cell 5: Running the Transcription
This is the main cell where the transcription occurs. It will ask if you want to use an "initial prompt" to improve accuracy for specific names or jargon.

### Cell 6: Creating, Formatting, and Saving the Transcription Table
Takes all the results, organizes them into a table, formats the duration column, and saves the final `transcricoes.csv` file in your working folder, compatible with Excel and Google Sheets.