# Vocab Farming
#Previously known as Book Metadata Study Guides

## Purpose
This tool aims to help those learning English at a mid to advanced level enlarge their vocabulary. It processes text, mainly from books, and returns study guides customized for each chapter. These study guides feature new words the learner might not know, as well as definitions for other potentially unfamiliar words.

## How to Use
The tool is run from the driver file called <addr>ProcessBook.py</addr>

Before running the tool, the user must create the following file structure. Follow these steps. We will use Tom Sawyer as our example book and definitions as our language code.

In the same directory as <addr>ProcessBook.py</addr>, create a directory called Tom_Sawyer

In the directory Tom_Sawyer, create a directory called chapters

Place each chapter to be processed in the directory chapters. Each chapter must be in JSON format, with 3 entries: chapter_number, chapter_title, and body. The file names do not matter, but must have .txt extension. Example:

{
    "chapter_number": 2,
    "chapter_title": "3. How Dorothy Saved the Scarecrow",
    "body": "\nWhen Dorothy was left alone she began to feel hungry...."
}

Once everything is set up, run the program with the following command:

<addr>python3 ProcessBook.py \<directory\> \<language_code\></addr>

Currently, the only supported language codes are definitions, ru (Russian), and es (Spanish).
PDF creation only supports Russian and Spanish.

## Google Translate API
In order to use language codes other than 'definitions', you must set up a project with the Google Translate API. They currently offer a free tier of 500,000 characters per month.

How to: https://cloud.google.com/translate/docs/basic/setup-basic

After you set up the API, you will have to set the GOOGLE_APPLICATION_CREDENTIALS environment variable every time you start a new terminal session:

export GOOGLE_APPLICATION_CREDENTIALS=\<path_to_api_key\>

## Preprocessing Chapters
The Utils directory contains 2 scripts to help prepare texts for this project. They are called Full_Text_To_Raw_Chapters_Template.py and Raw_Chapters_To_Formatted_Template.py. However, these files are simply templates, and will likely need to be modified slightly to work with any specific book.
