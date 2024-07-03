# Telegram Bot for Vessel ETA Information

## Table of Contents
- [Project Overview](#project-overview)
- [Technologies Used](#technologies-used)
- [Project Workflow](#project-workflow)
- [Results and Insights](#results-and-insights)
- [Future Work](#future-work)
- [Contact](#contact)

## Project Overview
The aim of this project is to test how using retrieval-augmented generation (RAG) with an open-source large language model (LLM) can provide responses to users via a Telegram chatbot. This project also compares the performance of this approach with the classical decision tree logic approach for generating responses based on information in the dataset.

## Technologies Used
- **Programming Language**: Python
- **Libraries**:
  - `pyTelegramBotAPI` (for Telegram API interaction)
  - `pandas` (for data manipulation)
  - `requests` (for downloading the CSV file)
  - `transformers` (for text generation)
  - `torch` (for model training)

## Project Workflow
The project is organized in the following steps:

1. **Initialization**:
   - Initialize the Telegram bot using the `telebot` library.
   - Load the pre-trained text generation model `meta-llama/Meta-Llama-3-8B-Instruct` using the `transformers` library.

2. **Data Loading**:
   - Download the latest Tauranga Container Terminal Cargo Schedule from [Port of Tauranga](https://www.port-tauranga.co.nz/operations/tauranga-container-terminal/cargo-availability/).
   - Merge the `Vessel` and `Outbound Voyage #` columns into a single column called `Vessel_Voyage`.
   - Create a specific dataset to feed the RAG model.

3. **Command Handling**:
   - Define a handler for the `/start` command to send a welcome message.
   - Define a handler for the `/eta` command to extract the vessel and voyage information, retrieve the ETA, and generate a response.

4. **Response Generation**:
   - Generate and send the appropriate response based on the provided vessel and voyage information.

5. **Error Handling**:
   - Implement error handling to capture and respond to any errors that occur during execution.

## Results and Insights
- The bot successfully retrieves and responds with the ETA and Cut-off time for the specified vessel and voyage.
- In scenarios with limited resources, the classical logic approach performs much faster than the LLM. However, the LLM allows for more flexible requests, even if the user types the vessel name with errors or uses the wrong voyage number.

## Future Work
- Implement a caching mechanism to reduce the load time for frequently accessed data.
- Explore acceleration frameworks to increase response time.
- Explore the integration of other data sources to provide more comprehensive information.

## Contact
If you have any questions or feedback, feel free to reach out:

- [**LinkedIn**](https://www.linkedin.com/in/vlad-plyusnin-b65b501b2/)
- [**GitHub**](https://github.com/VladPlusIn/)

Thank you for reviewing my project on the Telegram bot for vessel ETA information!

## Additional Files
- **TestBot.ipynb**: Jupyter notebook containing additional testing and analysis for the Telegram bot.
