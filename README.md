# PDF Chat Application

## Overview

The PDF Chat Application is a Streamlit-based web application that allows users to upload multiple PDF files and ask questions about their content. It utilizes Google's Generative AI model to provide detailed answers based on the information contained in the uploaded PDFs. This tool is ideal for quickly extracting information from large documents without having to read through them manually.

## Features

- Upload and process multiple PDF files
- Extract text content from PDFs
- Use AI to answer questions based on the PDF content
- Display chat history for easy reference
- User-friendly interface with clear instructions

## Prerequisites

Before you begin, ensure you have met the following requirements:

- Python 3.7 or higher
- A Google API key for Generative AI

## Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/pdf-chat-application.git
   cd pdf-chat-application
   ```

2. Create a virtual environment (optional but recommended):
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install the required packages:
   ```
   pip install streamlit python-dotenv PyPDF2 langchain langchain_google_genai faiss-cpu google-generativeai
   ```

4. Create a `.env` file in the project root and add your Google API key:
   ```
   GOOGLE_API_KEY=your_api_key_here
   ```

## Usage

1. Run the Streamlit app:
   ```
   streamlit run app.py
   ```

2. Open your web browser and navigate to the URL provided by Streamlit (usually `http://localhost:8501`).

3. Use the sidebar to upload your PDF files and click on "Process PDFs".

4. Once the PDFs are processed, you can start asking questions in the main chat interface.

5. Click "Get Answer" to receive AI-generated responses based on the content of your PDFs.

6. View the chat history displayed below the input area.

## How it Works

1. PDF Processing:
   - The application reads the uploaded PDF files and extracts their text content.
   - The extracted text is then split into smaller chunks for efficient processing.

2. Embedding and Indexing:
   - The text chunks are converted into embeddings using Google's Generative AI model.
   - These embeddings are stored in a FAISS index for quick similarity search.

3. Question Answering:
   - When a user asks a question, the application searches for the most relevant text chunks.
   - These chunks are then passed to the AI model along with the question to generate a response.

## Customization

You can customize the application by modifying the following:

- Adjust the `chunk_size` and `chunk_overlap` in the `get_text_chunks` function to optimize for your specific use case.
- Modify the prompt template in `get_conversational_chain` to change how the AI generates responses.
- Update the UI components in the `main` function to alter the application's layout and design.

## Troubleshooting

If you encounter any issues:

1. Ensure your Google API key is correctly set in the `.env` file.
2. Check that you have a stable internet connection for API calls.
3. Verify that the uploaded PDFs are not corrupted and are readable.

For persistent problems, please open an issue on the GitHub repository.

## Contributing

Contributions to the PDF Chat Application are welcome. Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature-branch-name`.
3. Make your changes and commit them: `git commit -m 'Add some feature'`.
4. Push to the branch: `git push origin feature-branch-name`.
5. Create a pull request.

## Acknowledgments

- Google for providing the Generative AI API
- Streamlit for the excellent web app framework
- The creators of PyPDF2, langchain, and FAISS for their powerful libraries

## Contact

If you have any questions or feedback, please open an issue on the GitHub repository.

Happy chatting with your PDFs!
