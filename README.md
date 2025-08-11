# Math Assessment Generator

This Python script generates a Microsoft Word document (`Generated_Math_Questions.docx`) containing two math questions aligned with the Quantitative Math curriculum. The questions include a combinatorics problem with a table and a geometry problem with an image of tightly packed spheres. The script runs in Google Colab, using the Google Gemini API to generate questions, `matplotlib` to create the image, and `python-docx` to build the document. The output is automatically downloaded and can be shared via Google Docs and GitHub.

## Prerequisites

- **Google Colab**: The script is designed to run in a Google Colab notebook.
- **Python Libraries**:
  - `python-docx`: For creating Word documents.
  - `matplotlib`: For generating the packed spheres image.
  - `google-generativeai`: For accessing the Gemini API.
- **Gemini API Key**: Obtain from [https://ai.google.dev](https://ai.google.dev) and store in Colab Secrets as `GOOGLE_GEMINI_API_KEY`.
- **Internet Connection**: Required for installing libraries and calling the Gemini API.

## Installation

1. Open a new Google Colab notebook ([https://colab.research.google.com](https://colab.research.google.com)).
2. Install required libraries by running:
   ```bash
   !pip install python-docx matplotlib google-generativeai
   ```
3. Set up the Gemini API key:
   - Go to the Secrets tab (key icon) in Colab.
   - Add a secret named `GOOGLE_GEMINI_API_KEY` with your API key.

## Usage

1. Copy the script (`generate_math_questions.py`) into a Colab notebook cell. The script includes:
   - Library imports and API configuration.
   - Functions to call the Gemini API, generate an image, and create the Word document.
   - Main execution with parameters for a 3x3 grid of spheres with radius 2 cm.
2. Run the cell to execute the script.
3. The script will:
   - Configure the Gemini API.
   - Generate two math questions (or use a fallback response if the API fails).
   - Create an image of packed spheres (`packed_spheres.png`).
   - Produce `Generated_Math_Questions.docx` and download it automatically.

## Expected Output

- **Word Document**: `Generated_Math_Questions.docx` contains:
  - **Title**: "Math Assessment: Combinatorics and Geometry Problems"
  - **Description**: A brief note about the assessment.
  - **Question 1**: A combinatorics problem (e.g., playlist combinations) with a table.
    - Example: "How many playlists can be created from 2 pop, 3 rock, and 3 jazz songs?"
    - Table with headers (e.g., "Genre", "Songs Available").
  - **Question 2**: A geometry problem about a rectangular package with 9 tightly packed spheres (3x3 grid, radius 2 cm).
    - Includes an embedded image (`packed_spheres.png`).
    - Example: "What are the dimensions of a package with 9 spheres, each with radius 2 cm?"
  - **Metadata**: For each question, includes options, correct answer, explanation, instruction, difficulty, order, subject, unit, topic, and marks.
- **Image**: A matplotlib-generated image (`packed_spheres.png`) showing a 3x3 grid of circles (radius 2 units).

## Sharing Instructions

1. **Google Docs**:
   - Upload `Generated_Math_Questions.docx` to Google Drive ([https://drive.google.com](https://drive.google.com)).
   - Right-click, select "Share," and set to "Anyone with the link."
   - Copy the shareable link (e.g., `https://drive.google.com/file/d/...`).
2. **GitHub**:
   - Go to your GitHub repository (create one at [https://github.com/new](https://github.com/new) if needed).
   - Upload `Generated_Math_Questions.docx` via the web interface.
   - Copy the file URL (e.g., `https://github.com/username/repo/blob/main/Generated_Math_Questions.docx`).
3. **Share Links**: Provide the Google Drive and GitHub links in the chat or relevant platform.

## Notes

- **API Key Security**: Store the Gemini API key in Colab Secrets, not in the code.
- **API Fallback**: If the Gemini API call fails, the script uses a fallback response with a 3x4 grid (radius 3 cm), which may not match the requested 3x3 grid (radius 2 cm).
- **LaTeX Rendering**: Equations (e.g., \(4 \times 12\)) may require a LaTeX-compatible viewer in Word.
- **Curriculum**: Questions align with:
  - Quantitative Math > Data Analysis & Probability > Counting & Arrangement Problems
  - Quantitative Math > Geometry and Measurement > Area & Volume
- **Troubleshooting**:
  - Ensure the API key is valid and has sufficient quota.
  - Check that the image description matches the expected format for parsing.
  - If the document doesn’t download, manually save it from Colab’s file system.
