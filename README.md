WebsiteRedirectMatch-Translated is a Python script that translates website links from one language to another and finds the best match for the translated link among a list of target links. This script was created with the inspiration and help of ChatGPT 4.

Requirements
Python 3.6 or later
Google Cloud Translation API
FuzzyWuzzy library
Installation
Install the required Python libraries:
bash
Copy code
pip install google-cloud-translate fuzzywuzzy python-Levenshtein
Set up the Google Cloud Translation API following these instructions.
Usage
Prepare two CSV input files:
source_links.csv: Contains the source links to be translated. Each line should have the following format:
csv
Copy code
link,language_code
target_links.csv: Contains the target links to compare the translated links to. Each line should have the following format:
csv

link,language_code
Run the script:
bash

python WebsiteRedirectMatch-Translated.py
The script will output a CSV file named output.csv with the following format:
csv
Copy code
source_link,source_language,target_link,target_language,best_match_link,similarity
Explanation of Sleep Functions
Sleep functions are used to introduce a delay between requests to external services, such as the Google Cloud Translation API, to avoid hitting rate limits or to handle temporary issues. The translate_link function has a retries parameter and a delay parameter. If an error occurs during translation, the function will wait for the specified delay in seconds before retrying the request. The function will retry the request up to the specified retries times.
