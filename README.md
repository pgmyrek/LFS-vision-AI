# Labour Force Survey Digitization using Generative AI

## Overview
This repository demonstrates how to process Labour Force Survey (LFS) forms using Generative AI, including PDF-to-text conversion, data consolidation, semantic search, and analysis.

## Folder Structure
- **.env**: Stores sensitive API keys (ignored by Git).
- **.gitignore**: Excludes sensitive and temporary files from Git.
- **requirements.txt**: Python dependencies.
- **notebooks**:
  - `Step_1_Extract_content_vision_AI.ipynb`: Extract text from PDFs using AI.
  - `Step_2_LFS_MAIN_SCRIPT.ipynb`: Main script for processing extracted data.
  - `Step_3__Consolidate_Database.ipynb`: Consolidates extracted data into a single database.
  - `Step4_LFS_Weaviate.ipynb`: Builds a semantic search database.
  - `Step5_LFS_Analysis.ipynb`: Analyzes survey data.
- **Images_temp/**: Temporary folder for images generated during processing.
- **To_process/**: Folder for input PDFs.

## Usage
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/LFS-Digitization.git
   cd LFS-Digitization


## Step 1: Extract Content (Vision AI)

This step involves:
1. Converting survey PDFs into individual images.
2. Using Generative AI (GPT-4o) to extract text content from the images.
3. Saving the extracted content into a structured Word document.

### Workflow
1. PDF files are processed from the `To_process/` directory.
2. Each PDF is split into individual JPEG images, stored in the `Images_temp/` directory.
3. Each image is sent to GPT-4o, which:
   - Identifies questions and answer options.
   - Structures the content with questions starting with "Q" and answers starting with "A."
4. The extracted text is appended to a Word document (`Extracted.docx`).

### Inputs
- **PDF files**: Stored in the `To_process/` folder.

### Outputs
- **Word document**: A `.docx` file (`Extracted.docx`) containing the extracted text.
- **Temporary images**: Saved in the `Images_temp/` directory.

### Notes
- Ensure the OpenAI API key is set up in a `.env` file before running this step.
- Update the `doc_path` variable in the code to customize the output file's name if needed.
- This step prepares the data for consolidation and structuring in Step 2.

### Command to Run
Execute the Jupyter notebook `Step_1_Extract_content_vision_AI.ipynb` to process the files and generate outputs.
