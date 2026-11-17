# Fuentes SharePoint

Remote MCP connector for The Fuentes Firm's SharePoint (Dataverse and PI Defense Team sites).

- Each user signs in with their own Microsoft 365 account. Access is limited to members of the Entra group "SharePoint MCP Users".
- File bytes go directly between the bot and SharePoint; the server never handles file content.
- Usage instructions are delivered by the server when a bot connects.

## Admin setup
After adding this plugin to the team marketplace, set `SP_MCP_CLIENT_SECRET` under Plugins > Configure. Do not commit the secret to this repository.
