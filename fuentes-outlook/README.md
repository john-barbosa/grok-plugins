# Fuentes Outlook

Read-only remote MCP connector for The Fuentes Firm's Outlook mail. It fills the one gap in the built-in Outlook connector for shared bots: getting attachment files.

- Each user signs in with their own Microsoft 365 account and reaches only their own mailbox (Graph Mail.Read). Access is limited to members of the Entra group "SharePoint MCP Users".
- Tools: `find_messages`, `get_message` (full body as text), `list_attachments`, `get_attachment_download`, `get_message_downloads`.
- Attachment bytes go directly from Microsoft to the bot's computer: the server returns the Graph download address and a short-lived, read-only token, and the bot runs `curl`. The server never handles file content or refresh tokens.
- Read-only: no send, reply, move, flag or delete. Shared bots keep the built-in Outlook connector for those. To file an attachment in SharePoint, download it here, then upload it with Fuentes SharePoint.
- Usage instructions are delivered by the server when a bot connects.

## Admin setup
After adding this plugin to the team marketplace, set `MAIL_MCP_CLIENT_SECRET` under Plugins > Configure. Do not commit the secret to this repository.
