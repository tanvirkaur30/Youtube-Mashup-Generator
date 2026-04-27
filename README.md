# YouTube Mashup Generator

Python-based web application that generates a YouTube audio mashup and sends it via email using Flask.

---

## Project Overview

This project is developed to create a **YouTube Mashup Generator** using Python. The main objective is to automatically generate a mashup by taking audio clips from multiple YouTube videos of a given singer and combining them into a single output file.

The assignment consists of two parts:

### Program 1: Command-Line Mashup Generator

This program takes input from the user through the command line:

- Singer Name
- Number of Videos
- Duration of each video clip

The system searches YouTube videos related to the singer, downloads the audio, trims the required duration from each video, and combines all clips into one final mashup audio file.

The final output is saved as:

`combined_audio.mp3`

---

### Program 2: Web Service for Mashup

A Flask-based web application is created where the user enters:

- Singer Name
- Number of Videos
- Duration of each video
- Email ID

After submission:

- The mashup is generated automatically
- The output file is prepared
- The result is sent to the user through email

This fulfills the requirement of developing a proper web service.

---

## Technologies Used

The following tools and libraries were used in this project:

- Python
- Flask
- yt-dlp
- pydub
- FFmpeg
- smtplib
- Gmail App Password
- Google Colab
- GitHub
- PythonAnywhere (for deployment)

---

## Methodology

The YouTube Mashup Generator project is developed to automatically create a mashup of songs from YouTube videos based on user input.

The methodology followed in this project is explained step-by-step below.

---

### Step 1: User Input Collection

The user provides the following inputs:

- Singer Name
- Number of Videos
- Duration of each video clip
- Email ID (for Program 2)

**Example:**

- Singer Name = Sharry Mann
- Number of Videos = 3
- Duration = 30 seconds

These inputs are used for mashup generation.

---

### Step 2: Searching YouTube Videos

The program searches YouTube videos related to the given singer name using the `yt-dlp` library.

Only the top required number of videos are selected.

**Example:**  
If the user enters `Number of videos = 3`, then only 3 relevant videos are selected.

This helps in controlling the size of the final mashup.

---

### Step 3: Downloading Audio

Audio is extracted from the selected YouTube videos.

Only audio is downloaded, not the full video.

This reduces storage usage and improves processing speed.

**Library used:** `yt-dlp`

Temporary audio files are stored for further processing.

---

### Step 4: Audio Trimming

The downloaded audio files are processed using:

- FFmpeg
- Pydub

Each song is trimmed according to the duration entered by the user.

**Example:**  
If duration = 30 seconds, then only the first 30 seconds of each song is used.

This ensures uniform mashup creation.

---

### Step 5: Mashup Creation

All trimmed audio clips are combined into one final audio file.

This creates the mashup output.

The final file is saved as:

`combined_audio.mp3`

This file contains the final mashup of all selected songs.

---

### Step 6: Web Application Development

A Flask-based web application is created for Program 2.

The webpage allows the user to enter:

- Singer Name
- Number of Videos
- Duration
- Email ID

**Frontend:** HTML (`index.html`)  
**Backend:** Flask (`app.py`)

This converts the project into a proper web service. The form accepts user input and sends it to the backend for processing.

---

### Step 7: Email Sending Functionality

After mashup generation, the output file is sent to the user’s email address.

This is implemented using:

- `smtplib`
- Gmail App Password

A Gmail App Password is used instead of the normal Gmail password because Google blocks direct login using standard passwords.

This fulfills the assignment requirement:  
> “User should get the result file through email.”

---

### Step 8: Deployment

The web application is deployed using **PythonAnywhere**.

**Live Web App Link:**  
`https://tanvir30.pythonanywhere.com`

This makes the project publicly accessible as a real web service.  
Anyone can use the web form through this public link.

This completes the actual deployment requirement of Program 2.

---

## Problems Faced and Solutions

During the development of the project, several practical issues were faced.

These problems and their solutions are explained below.

---

### Problem 1: FFmpeg Not Found Error

**Error:**  
`Couldn't find ffmpeg or avconv`

**Reason:**  
The `pydub` library requires FFmpeg for audio processing. Without FFmpeg, trimming and combining audio files is not possible.

**Solution:**  
- FFmpeg was downloaded manually  
- FFmpeg path was added to system environment variables  
- Installation was verified using:

```bash
ffmpeg -version

After this, audio processing worked successfully.

### Problem 2: ModuleNotFoundError for google.colab

**Error:**  
`No module named 'google'`

**Reason:**  
The code worked inside Google Colab but failed in local CMD because `google.colab` is available **only** inside Colab.

**Solution:**  
- Colab-specific code was removed while running locally.  
- Separate execution methods were used for:
  - Google Colab
  - Local Command Prompt

✅ This solved the issue successfully.

---

### Problem 3: SMTP Authentication Error

**Error:**  
`Username and Password not accepted`

**Reason:**  
Google blocks login using the normal Gmail password for external applications for security reasons.

**Solution:**  
The following steps were performed:
1. Enabled **2-Step Verification** in Gmail
2. Generated **Gmail App Password**
3. Used App Password inside Flask code instead of normal password

✅ This fixed the email sending functionality successfully.

---

## Problem 4: GitHub Upload Issue

**Problem:**  
Files were not uploading properly to GitHub, which created submission issues.

**Solution:**  
The following files were uploaded separately:
- `.py`
- `.ipynb`
- `.mp3`
- `program2.zip`

Additionally, all files were also submitted through **email as a backup** to avoid submission risk.

✅ This ensured safe and complete submission.

---

## Problem 5: Incorrect ZIP Structure

**Problem:**  
The ZIP file structure was incorrect because unnecessary nested folders were created inside the ZIP file.

**Wrong Structure:**
program2.zip
└── program2/
    └── files

**Correct Structure:**
program2.zip
│
├── app.py
├── utils.py
├── requirements.txt
└── templates/


**Solution:**  
The ZIP file was recreated properly without unnecessary extra folders.

✅ This solved both deployment and submission issues.

---

## Problem 6: Render Deployment Issue

**Problem:**  
Render required debit/credit card verification for deployment. This created difficulty because card verification was needed even for free hosting.

**Solution:**  
Deployment was shifted to **PythonAnywhere** because:
- Free hosting is available
- No card verification required
- Flask deployment is easier
- Better suited for academic submission

✅ This successfully solved the deployment issue and provided a working public link.

---

## Output

The project successfully generates the following outputs:

- Final mashup audio file (`combined_audio.mp3`)
- Working web application using Flask
- Email delivery of output file
- Public deployment link
- Webpage screenshots for proof of execution

This confirms the successful completion of both:
- **Program 1** (Command-Line Mashup Generator)
- **Program 2** (Web Service for Mashup)

---

## Conclusion

The **YouTube Mashup Generator** project was successfully implemented using **Python** and **Flask**. This project demonstrates the practical use of:

- YouTube audio extraction
- Audio processing using Python
- Web development using Flask
- Email automation using SMTP
- Public deployment of a real web service
- Real-world debugging and problem solving

Both **Program 1** and **Program 2** were completed successfully according to the assignment requirements. The project helped in understanding important real-world concepts such as:

- Dependency handling
- Deployment concepts
- Practical debugging
- Project structure management
- Web service development
- Real-world implementation of Python-based applications

This project was not only useful for assignment completion but also provided valuable hands-on experience in building and deploying a complete working application.
