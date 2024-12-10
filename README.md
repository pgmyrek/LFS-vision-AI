# **Labour Force Survey Digitization Using Generative AI**

## **Overview**
This repository comes with ILO Research Brief "A new chapter for the ILO’s textual assets: Applying Generative AI to Labour Force Survey questionnaires" by Pawel Gmyrek and Poleth Vega Ruales, DOI: https://doi.org/10.54394/SORG5455

It provides a comprehensive pipeline for digitizing Labour Force Survey (LFS) forms using Generative AI. The workflow includes extracting text from PDFs, consolidating structured data, and performing semantic searches and analysis using vector databases and OpenAI's GPT-4. While LFS are used as an example, the script can be applied to other types of text extraction, especially to other survey forms.

## **Folder Structure**
- **`Database/`**: Contains consolidated `.xlsx` files and semantic search results.
- **`Images_temp/`**: Temporary folder for storing images generated during PDF processing.
- **`To_process/`**: Directory for input PDF files awaiting processing.
- **`.env`**: File to securely store sensitive API keys (excluded from Git).
- **`.gitignore`**: Specifies files and folders to exclude from version control.
- **`README.md`**: Project documentation (this file).
- **`requirements.txt`**: Python dependencies required for the project.
- **Jupyter Notebooks**:
  - **`Step_1_Extract_content_vision_AI.ipynb`**: Extracts and structures text from PDFs using AI.
  - **`Step_2_Extract_Q-A_markers.ipynb`**: Extracts and saves Q&A markers from structured text.
  - **`Step_3_LFS_Consolidate_Database.ipynb`**: Consolidates structured files into a unified database.
  - **`Step_4_LFS_Weaviate.ipynb`**: Builds and queries a semantic search database using vector embeddings.

## **Setup Instructions**

### **Clone the Repository**
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/yourusername/LFS-Digitization.git
   cd LFS-Digitization

### **Install Main Dependencies**
2. Install the required Python dependencies using:
   pip install -r requirements.txt

### **Configure API Keys**
3. Create `.env` file in the root directory and provide the following content:
   OPENAI_API_KEY=your_openai_api_key
   WEAVIATE_URL=your_weaviate_cluster_url
   WEAVIATE_USERNAME=your_weaviate_username
   WEAVIATE_PASSWORD=your_weaviate_password

