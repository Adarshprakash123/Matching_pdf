<h5>Invoice Similarity Matching System</h5> </br>
Overview </br>
This project is designed to automatically categorize and match incoming invoices by comparing them to a database of existing invoices. The system identifies the most similar invoice based on content and structural similarity.
</br>
Objective<br>
<h5>The goal is to build a prototype that can:</h5>
<ol>
  <li>Extract and represent text from invoices.</li>
  <li>Extract and analyze features from the invoices.</li>
  <li>Calculate similarity metrics to find the most similar invoice in the database.</li>
</ol>

<h5>Technical Requirements</h5>
<h5>Document Representation</h5>

<ol>
  <li>Text Extraction: We use PyPDF2 to extract text content from PDFs.</li>
  <li>Feature Extraction: Extract relevant features such as keywords, invoice numbers, dates, and amounts from the text.</li>
  <li>Structural Analysis: Use Camelot for table detection and text extraction from tables.</li>
  <li>Similarity Calculation</li>
  <ul>
    <li>Cosine Similarity: Measures the cosine similarity between feature vectors.</li>
    <li>Jaccard Similarity: Measures the overlap between sets of keywords or phrases.</li>
  </ul>
</ol>

Database Integration
<ol>
  <li>An in-memory list is used to store and compare invoices.</li>
</ol>

Setup Instructions
   1. Install Dependencies:</br>
   --> pip install camelot-py[cv] PyPDF2 scikit-learn opencv-python pytesseract </br>
   --> sudo apt-get install -y poppler-utils tesseract-ocr
   2. Prepare Your Environment:
<ul>
  <li>Ensure you have ghostscript and tkinter installed.</li>
  <li>Place your PDF files in the pdf_paths folder.</li>
</ul>
   

<h5>Key Functions</h5>
  1. Add Invoices to Database:

  Place your existing invoices in the pdf_paths folder.
  Run the script to add these invoices to the in-memory database.</br>
  2. Find Most Similar Invoice:

  Place a new invoice (PDF) in the pdf_paths folder.
  Run the script to find the most similar invoice from the existing database.
  
  3. Running the Script:
   python invoice_similarity.py


Code Explanation

<h5>Key Functions</h5>
<ol>
  <li>extract_text_from_pdf(pdf_path): Extracts text content from a PDF file using PyPDF2.</li>
  <li>extract_text_from_images(pdf_path): Extracts text from images within the PDF using Tesseract OCR.</li>
  <li>extract_text_from_tables(pdf_path): Extracts text from tables using Camelot.</li>
  <li>extract_features(text): Extracts relevant features from the text.</li>
  <li>calculate_similarity(text1, text2): Computes cosine similarity between two text inputs.</li>
  <li>add_invoice_to_database(pdf_path): Adds an invoice to the database after extracting text and features.</li>
  <li>find_most_similar_invoice(input_pdf_path): Finds the most similar invoice in the database for a given input invoice.</li>
</ol>








 
