# Flight Booking Chatbot

This repository contains the code for a flight booking chatbot using Rasa. The chatbot can handle user requests to search for flights between specified locations and dates.

## Table of Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Setup](#setup)
4. [Training the Model](#training-the-model)
5. [Running the Bot](#running-the-bot)
6. [Interactive Learning](#interactive-learning)
7. [File Descriptions](#file-descriptions)
8. [License](#license)

## Introduction
The flight booking chatbot uses the Rasa framework to understand user inputs and perform actions such as searching for flights and displaying flight information. The bot can handle user queries for origin, destination, and travel dates.

## Requirements
- Python 3.6+
- Rasa 1.x
- BeautifulSoup4
- urllib

## Setup
1. Clone the repository:
    ```bash
    git clone https://github.com/yourusername/flight-booking-chatbot.git
    cd flight-booking-chatbot
    ```

2. Create a virtual environment and activate it:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

## Training the Model
### Natural Language Understanding (NLU)
1. Train the NLU model:
    ```bash
    python nlu_model.py
    ```

### Dialogue Management
1. Train the dialogue model:
    ```bash
    python dialogue_management_model.py
    ```

## Running the Bot
1. Start the Rasa action server:
    ```bash
    rasa run actions
    ```

2. Run the bot:
    ```bash
    python actions.py
    ```

## Interactive Learning
You can improve the bot's performance using interactive learning:
```bash
python -m rasa_core.train --online -d config/domain.yml -s data/stories.md -o models/dialogue -u models/nlu/default/chatter --epochs 250 --endpoints endpoints.yml
