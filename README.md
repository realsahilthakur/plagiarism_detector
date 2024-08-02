# Plagarism Detector

This Streamlit application can detects plagiarism in the text or file and also capable to measures textual similarities between two files. It allows users to enter text or upload files (docx, pdf, txt). It splits the text into sentences, searches Google for each sentence, and compares the input text with retrieved results using cosine similarity. Users can also compare the similarity between two uploaded files. The results are displayed in a formatted DataFrame.


## Tech Stack

**Client:** Streamlit, HTML/CSS.

**Server:** Python

**Libraries & Algorithms:** 

*Libraries:*
-streamlit
-pandas 
-nltk 
-requests 
-BeautifulSoup 
-sklearn 
-docx2txt
-PyPDF2
-boto3

  
*Algorithms:*
- Tokenization
- Cosine Similarity
- Web Scraping
- Document Retrieval
- Data Visualization


*AWS S3 setup:*
Configuration for uploading and downloading files from an S3 bucket.


*Additional Notes:*
Security: Ensure your AWS credentials and S3 permissions are set correctly to avoid access issues.
Dependencies: Make sure all required libraries are installed and configured properly on your EC2 instance.



## Original Key Features:

*User Input Options:*

Enter text directly into a text area.
Upload a single file in .docx, .pdf, or .txt format.
Upload two files for similarity checks.

*Text Processing:*

The application can read text from different file formats (.txt, .pdf, and .docx).

*Plagiarism Detection:*

For entered text or uploaded files, the application searches Google for each sentence.
It retrieves the first URL from the search results and checks the similarity of the text at that URL with the input text.

*Similarity Check between multiple files:*

When users upload files, the application calculates the similarity between the texts of the files.
It uses cosine similarity to measure how similar the texts are.

## Original Author
- [@KarthikS](https://www.github.com/Karthik-02)


## Changes made by Our team

- Added a feature to only show the "Check for plagiarism" button if the minimum criteria of 40 words is met in the text area.

- Modified the code to only show the "Check for plagiarism or find similarities" button if text is entered or files are uploaded.

- Added logic to ensure only two files can be uploaded for the "Find similarities between files" option.

- Added a warning to ensure exactly two files are uploaded when checking for similarities.

- Added custom CSS to make all text in the Streamlit app cursive.

- Removed line, scatter, bar, pie, box, histogram,3d scatter and violin plots to simplify the output.
  
- integrated with the AWS S3 bucket 


## Run Locally

Clone the project

```bash
  git clone https://github.com/realsahilthakur/plag.git
```

Go to the project directory

```bash
  cd plag
```

Install dependencies

```bash
  pip install -r requirements.txt
```


Start the server

```bash
  streamlit run app.py
```


*NOTE:*

MAKE SURE TO ADD THE "S3 BUCKET NAME" , "AWS ACCESS KEY AND PRIVATE KEY".
