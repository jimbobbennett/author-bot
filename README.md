# AuthorBot

A OpenAI GPT-4 powered tool to help author books! This is designed to be a sample app to show how to build and execute prompts against the chat completions API.

## Setup

To use this notebook, open this repo in VS Code. You will need the Python extension installed, and this will be recommended when you first open this repo.

Create and activate a virtual environment, then install the packages from the `requirements.txt` file. You can then open the `author-bot.ipynb` notebook, and set the kernel to your virtual environment.

To configure OpenAI, you will need either an OpenAI API key, or an instance of the Azure OpenAI service.

To configure for OpenAI:

* Rename `.env.openai.example` to `.env`

* Set the value of the `KEY` key in the `.env` file to your key.

* Run the notebook

To configure for Azure OpenAI service:

* Rename `.env.azureopenaiservice.example` to `.env`

* Set the value of the `KEY` key in the `.env` file to your Azure OpenAI service key.

* Set the value of the `ENDPOINT` key in the `.env` file to your Azure OpenAI service endpoint.

* Uncomment the lines that set the Azure values:

    ```python
    # openai.api_base = os.environ['ENDPOINT']
    # openai.api_type = 'azure'
    # openai.api_version = '2023-05-15'
    ```

    Update the `api_version` if necessary

## Running the authorbot

* Configure the story type by setting the `genre` and `audience` fields

    ```python
    genre = 'science fiction'
    # genre = 'fantasy'
    # genre = 'horror'
    # genre = 'romance'
    # genre = 'mystery'
    # genre = 'thriller'
    # genre = 'western'
    # genre = 'drama'
    # genre = 'comedy'
    # genre = 'action'
    # genre = 'adventure'
    # genre = 'historical fiction'
    # genre = 'literary fiction'
    
    audience = 'adults'
    # audience = 'teenagers'
    # audience = 'children'
    ```

* Run the notebook till the book suggestions are created

* Update the index of the selected book idea:

    ```python
    # Select your book idea by setting this index
    SELECTED_BOOK_IDEA = 0
    ```

* Run the rest of the notebook. Your book will appear in the `books` folder.

* Read and enjoy your new short story!

## Notes

Sometimes the response from ChatGPT can be unpredictable, so you may need to run some cells again. For example, when running the cells the request the output as JSON, sometimes the output includes prose, such as opening with "Here you go". Running the cell again can fix this, or try changing the prompt before you run again.

Running this notebook can be expensive, especially if you use GPT-4. As an estimate, a complete book run can be as much as $2.
