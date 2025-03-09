# Delaval v300 AMS automatic webui authentication

## Overview

A python program to authenticate at the webui of the Delaval v300 automatic milking station AMS and establish a websocket connection to interact with the machine.

This project automates authentication and WebSocket communication with multiple AMS machines. It logs in using hashed credentials, establishes WebSocket connections, and can send control messages to specific machines.

## Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/Dokterfrits/Delaval_Web_Authentication_API
   cd websocket-automation
   ```
2. **Create a virtual environment (optional but recommended):**
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

## Configuration

Rename **config_template.json** to **config.json** and update the credentials and urls in the project directory:
   ```json
   {
       "username": "your_username",
       "password": "your_password",
       "urls": [
          "wss://192.168.168.1/ws", // Your AMS on network. Variations on "wss://vms_1.vms.delaval.com/ws" might also work
          "wss://192.168.168.2/ws" // Second machine, add more lines if necessary
       ]
   }
   ```

## Usage

Run the script:

```sh
python main.py
```

## Features

- Secure authentication with hashed credentials
- WebSocket connection to multiple machines
- Sends control messages dynamically to a selected machine
- Logs responses and identifies which machine sent them

## Troubleshooting

- If authentication fails, check the credentials in `config.json`.
- If SSL errors occur, try setting `verify=False` in requests.
- If no messages are received, ensure WebSocket URLs are correct.

## License

MIT License

