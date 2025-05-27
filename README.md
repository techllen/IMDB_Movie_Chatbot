# IMDB_Movie_Chatbot
This repository contains the code for an AI-powered IMDb Movie Chatbot in a Google Colab Notebook. Leveraging Natural Language Processing (NLP), Large Language Models (LLMs) and AI Agent, the chatbot provides users with an interactive and conversational way to explore movie data.  It can answer questions about movies, provide recommendations, and offer details sourced from the IMDb dataset.  The application includes data preprocessing, exploratory data analysis, a GPT-based chatbot implementation, and a Gradio-based user interface.  An agentic architecture is included to provide movie trends.

## Architectural Diagram

<img src="https://github.com/techllen/Savannah-canopy/blob/main/screenshots/Self%20Healing%20Application%20Pipeline%20Architecture-Page-2.jpg" alt="Pipeline Architecture">

## Overview

This project implements an AI-powered chatbot that interacts with users to provide information and recommendations about movies. By utilizing Natural Language Processing (NLP) and Large Language Models (LLMs), the chatbot offers a conversational interface to explore the IMDb dataset.

## Features

* **Interactive Movie Search:** Users can search for movies based on various criteria (genre, actors, plot, etc.) using natural language.
* **Movie Details Retrieval:** The chatbot provides details about movies, including ratings, reviews, and other relevant information.
* **Personalized Recommendations:** (Future Enhancement) The chatbot can be extended to provide personalized movie recommendations based on user preferences.
* **User-Friendly Interface:** A Gradio interface is included for easy interaction with the chatbot.
* **Trending Movies:** An optional agentic architecture is included to provide movie trends from the internet.

## Technologies Used

* Python
* LangChain
* LangGraph
* LangSmith (for evaluation)
* FAISS
* Gradio
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* OpenAI API
* BeautifulSoup
* Requests
* Operator
* Requests API
* JSON

## Setup and Installation

1.  **Clone the repository:**

    ```bash
    git clone https://github.com/techllen/IMDB_Movie_Chatbot.git
    cd IMDB_Movie_Chatbot
    ```

2.  **Install the required Python packages:**

    ```bash
    pip install langchainhub langchain-openai langchain langchain-community faiss-cpu gradio langsmith openai requests beautifulsoup4 langgraph
    ```

    Or install using libraries cell on colab notebook

3.  **Obtain API Keys:**

    * You will need an OpenAI API key.  You'll be prompted to enter this when running the code.
    * (Optional) To use the trending movies feature, you'll also need a Google Custom Search JSON API key and a Google Custom Search ID.
    * To upload test dataset to langsmith you will also need to signup in langsmith and obtain a akey.

4.  **Download the Dataset:**

    * Ensure you have the `IMDb_Dataset.csv` file.  You may need to adjust the path or download the dataset and place it there.

5.  **Run the Chatbot:**

    * The primary chatbot interface can be run from colab notebook provided.  Look for the Gradio interface section to launch the web UI.
    * If you want to run the agentic version, look for the agentic architecture section and run that code.

## Data Preprocessing

The dataset was preprocessed to:

* Handle missing values (none in this case).
* Remove unnecessary columns (`Poster-src`).
* Convert object columns to categorical types for efficiency.
* Remove duplicate rows.
* Clean movie titles by removing special characters.
* Construct text data by combining relevant movie details into a single string for each movie.
* Vectorize the text data using OpenAI embeddings and FAISS for efficient retrieval.

## Model Implementation

* The chatbot uses the GPT model (via the OpenAI API) to generate responses.
* LangChain is used to create chains for document retrieval and question answering.
* FAISS is used for efficient similarity search to find relevant movie information.

## Chatbot Interface

* Gradio is used to create an interactive web-based user interface for the chatbot.

## Evaluation

* LangSmith is used for evaluating the chatbot's performance, including metrics like correctness.
* The evaluation process includes defining test cases and using an LLM to judge the quality of the chatbot's responses.

## Agentic Architecture

* An agentic architecture is included, with below tools
  - Tool to search the internet for trending movies
  - Tool to search the local IMDB dataset.
    
* LangGraph is used to define the workflow of the agent.
* Single-node LangGraph with stateful flow is used where gent function agent_node is wrapped in a graph node, turning it into a step in a flow, where state is passed and returned.
* This is a LangGraph agent with a single node wrapping a LangChain Zero-Shot ReAct agent (AgentType.ZERO_SHOT_REACT_DESCRIPTION).
* It is designed for simplicity and modularity, and can be extended into a more complex agent graph.

## Future Work

* Enhance personalized recommendation capabilities.
* Improve the accuracy and robustness of the chatbot's responses.
* Expand the dataset to include more movie information.
* Implement more sophisticated evaluation metrics.

## Credits

* Allen Matare Mwita (Author)

## License

This project is licensed under the MIT License.
