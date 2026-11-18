# Fuentes Teams

Read-only remote MCP connector for files attached to Microsoft Teams chat and channel messages at The Fuentes Firm.

- Each user signs in with their own Microsoft 365 account and sees only the chats, teams, channels and files they can already open in Teams. Access is limited to members of the Entra group "SharePoint MCP Users".
- Tools: `find_teams` (matches an attorney's first name, "[first name]'s Team", or [first name]steam@fuentesfirm.com), `find_chats`, `list_chat_messages`, `list_channel_messages`, `get_teams_attachment_download`, `get_message_downloads`.
- Files go directly from OneDrive/SharePoint to the bot's computer through Microsoft's short-lived pre-authenticated download links. No token is handed to the bot and the server never handles file content.
- Attached files only; images pasted into a message are not supported. Read-only: nothing is posted or changed. To file a Teams attachment in SharePoint, download it here, then upload it with Fuentes SharePoint.
- Usage instructions are delivered by the server when a bot connects.

## Admin setup
After adding this plugin to the team marketplace, set `TEAMS_MCP_CLIENT_SECRET` under Plugins > Configure. Do not commit the secret to this repository.
