# IR2022_A1_47

## Assignment Info
Course: Information Retrieval [CSE508]  
Semester: Winter 2022  
Group: 47  
Assignment 1  

## Repository Description
Q1.ipynb: Complete code with comments for Question 1  
Q2.ipynb: Complete code with comments for Question 2

## .gitignore Description
All the data files are stored in the Dataset folder which is present in the root folder. Link to dataset: [Dataset](https://drive.google.com/file/d/199eN4r2HDhil-N-hKm1xFPGbF0ZZHprd/view?usp=sharing)  
The file name for pickle files of unigram iverted index and positional index are unigram_iverted_index_pickle_file and positional_index_picke file respectively. Link to pickle files: [unigram_iverted_index_pickle_file](https://drive.google.com/file/d/1N4Mj8Xe0tPu5ZsD2AInMC4uPOhibokHN/view?usp=sharing),  [positional_index_picke](https://drive.google.com/file/d/19yvp5vsJrUHLuyuG65XbQUJ1hZBlZwIp/view?usp=sharing)  

- Question 1
  - Methodology
    - Relevant libraries are imported
    - List of path of all the files in the dataset is determined and a file_dictionary is constructed
    - preprocessing is done on each document using which unigram iverted index is created
    - unigram iverted index is saved as a pickle file to avoid computing again and again
    - N queries are input, each query is sanitized by the same preprocessing steps. Each query is evaluated two query tokens at a time in left-to-right manner with boolean logic applied by the operation sequence
    - Number of operations is updated with each step
    - Final number of documents, number of operations and document list is displayed
  - Preprocessing Steps (in order of execution)
    - lowercase
    - tokenization
    - stopword removal from tokens
    - punctuation removal from tokens
    - blank space token removal
  - Assumptions
    - The number of tokens present in the sanitized input query on the same preprocessing steps must be 1 more than the number of operators present in the sanitized input operation sequence (NOTE: and, or, and not, or not are the 4 operators considered as a singular entity post sanitization)
    - If above condition is not followed then the query is treated as INVALID.

- Question 2
  - Methodology
    - Relevant libraries are imported
    - List of path of all the files in the dataset is determined and a file_dictionary is constructed
    - preprocessing is done on each document using which positional index is created
    - positional index is saved as a pickle file to avoid computing again and again
    - N phrase queries are input, each query is sanitized by the same preprocessing steps
    - common document IDs among all the phrase query tokens is determined
    - Each document ID from above step is analyzed to check the presence of phrase query
    - Final number of documents and document list is displayed
  - Preprocessing Steps
    - lowercase
    - tokenization
    - stopword removal from tokens
    - punctuation removal from tokens
    - blank space token removal
  - Assumptions
    - Document: "Good stop_word_1 stop_word_2 morning",  Phrase Query: "Good stop_word_3 morning"
    - The above document is treated as valid for the phrase query. Such cases are not considered as False Positives but rather an indented consequence of the instructions of the assignment (as per instructions 2a and the note at the end: "Perform preprocessing on the input query as well")
    - An alternate method (which has its own set of unintended False Positives) of assigning term position before preprocessing is NOT considered in this implementation
