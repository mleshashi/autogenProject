# Email Agent for Automatic Responses

This Python script is designed to automatically fetch the latest email from a specified sender, generate a response based on the content, and send a reply. It utilizes IMAP to interact with Gmail for fetching emails and SMTP for sending replies. The script also leverages a hypothetical `autogen` library to generate email responses.

## Key Features

- **Fetch Latest Email**: Connects securely to Gmail's IMAP server to fetch the most recent email from a specific sender.
- **Email Parsing**: Decodes and extracts the subject and body of the email. It includes functionality to strip quoted replies or forwarded message chains using regex patterns.
- **Response Generation**: Utilizes a configured instance of `AssistantAgent` from the `autogen` library to automatically generate responses based on the email's content.
- **Sending Replies**: Crafts a reply email with the generated response and sends it back to the original sender using Gmail's SMTP server.

## Configuration

1. **IMAP and SMTP**: Uses Gmail's IMAP and SMTP servers for email operations. Requires user credentials (email and app-specific password).
2. **Email Filtering**: Searches for emails based on the sender's address.
3. **Response Generation**: Configures `AssistantAgent` with specific models and API keys for generating responses.
4. **Environment Variables**: Sensitive information such as user credentials and API keys are stored in `config.py` for security.

## Dependencies

- Python's `imaplib` and `smtplib` for email operations.
- `email` and `MIMEText`, `MIMEMultipart` for parsing and crafting emails.
- Hypothetical `autogen` library for response generation.
- Regular expressions (`re`) for processing email content.

## Usage

1. Update `config.py` with your Gmail credentials and the sender's email address you wish to interact with.
2. Run the script. It will automatically fetch the latest email from the specified sender, generate a response, and send it.

## Security Notes

- The script uses an app-specific password for Gmail, which is a secure way to access your account without exposing your actual password.
- Ensure `config.py` is properly secured and not included in public repositories.
