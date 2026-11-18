# Fuentes Teams

Remote MCP connector for Microsoft Teams at The Fuentes Firm: read chats and channels, get attached files, and send messages as the signed-in person with a confirmation step.

- Each user signs in with their own Microsoft 365 account and sees only the chats, teams, channels and files they can already open in Teams. Access is limited to members of the Entra group "SharePoint MCP Users".
- Read tools: `find_teams` (matches an attorney's first name, "[first name]'s Team", or [first name]steam@fuentesfirm.com), `find_chats`, `list_chat_messages`, `list_channel_messages`, `get_teams_attachment_download`, `get_message_downloads`.
- Send tools: `create_chat` (people and/or teams/groups; reuses an existing 1:1, otherwise creates a group chat), `send_chat_message`, `post_channel_message` (new post or thread reply).
- Every send is two steps: the first call returns a preview (who receives it, or which chat/channel, and the exact text) plus a confirmation code valid for about 15 minutes; only a second call with that code sends. In a chat, the bot shows the preview and waits for an explicit yes. In an unattended routine, it may confirm only when the routine's saved instructions name that action (recipients or chat/channel, and the message or a clear template); otherwise it stops and reports.
- Names that are ambiguous or not found are reported back, never guessed. Nothing can be edited, deleted or reacted to.
- Files go directly from OneDrive/SharePoint to the bot's computer through Microsoft's short-lived download links; the server never handles file content. Attached files only; pasted images are not supported. To file a Teams attachment in SharePoint, download it here, then upload it with Fuentes SharePoint.
- Usage instructions are delivered by the server when a bot connects.

## Admin setup
After adding this plugin to the team marketplace, set `TEAMS_MCP_CLIENT_SECRET` under Plugins > Configure. Do not commit the secret to this repository.
