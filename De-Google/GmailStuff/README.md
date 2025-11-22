-----

# Gmail Takeout Service Parser

A simple Python script that analyzes your Google Takeout MBOX file to generate a list of every service, newsletter, or company that has ever emailed you.

**Great for:**

  * Finding forgotten subscriptions.
  * Auditing who has your email address.
  * Seeing which of your email aliases/forwarders are being used.

## Requirements

  * Python 3.x
  * No external libraries required (uses standard `mailbox`, `csv`, etc.).

## Setup

1.  **Get your Data:** Go to Google Takeout, deselect all, select **Mail**, and download your data.
2.  **Extract:** Unzip the download. You will find a file (usually inside a `Mail` folder) named something like `All mail Including Spam and Trash.mbox`.
3.  **Place Files:** Move that `.mbox` file into the same folder as this script.

## Usage

1.  Open the script and ensure `MBOX_FILENAME` matches your file name:
    ```python
    MBOX_FILENAME = 'All mail Including Spam and Trash.mbox'
    ```
2.  Run the script:
    ```bash
    python parser.py
    ```
3.  Wait for the process to finish (large inboxes may take a few minutes).

## Output

The script generates `my_services_list.csv` with the following columns:

  * **Service Domain:** The sender's website (e.g., `netflix.com`).
  * **Most Common Sender Name:** (e.g., "Netflix").
  * **Email Count:** How many times they have emailed you.
  * **Sent To (My Accounts):** Which of your email addresses/aliases received the mail.

## Configuration

You can edit the `IGNORE_DOMAINS` set at the top of the script to exclude common providers or personal contacts (e.g., `gmail.com`).

-----
