# CRMown

Connect your CRMown account to Grok Bot or Cursor. Look up contacts, companies and deals, read meeting summaries and pipeline totals, and — with your approval — add notes, create tasks, draft emails or texts, and move deals.

You sign in with your CRMown login. **No API key to paste.** The bot acts as you: same role and record visibility as the CRMown app. It cannot delete records or send messages.

**Connector URL:** https://mcp.crmown.io/mcp

This repository is the Cursor Marketplace plugin package. It points at CRMown’s hosted MCP server. Authentication is OAuth 2.1 (dynamic client registration). The package contains no API keys, tokens, or other secrets.

## Connect in Grok Bot

1. In Grok Bot, open **Connect apps** and add **CRMown** (once it is listed). Until then, add a custom / remote MCP server with the connector URL above.
2. A CRMown page opens. Sign in if asked, check the account and workspace, and choose what the app may do: always **see your contacts, companies, deals, tasks, meetings and knowledge base**; optionally tick **Create and update…** if you want the bot to make changes.
3. Click Allow. Back in Grok Bot, try: “Who am I in CRMown?”, “Find contacts at Acme”, or “Which deals close this month?”
4. To disconnect, remove the plugin in Grok Bot, or go to CRMown → **Settings → Integrations → Connected apps & AI assistants** and click Disconnect. Owners and admins can see every app connected in the workspace.

## Connect in Cursor

Install this plugin from the Cursor Marketplace (once listed), or add a remote MCP server with URL `https://mcp.crmown.io/mcp`. Complete the CRMown sign-in and consent prompt the first time.

## What it can do

- **Read (32 tools):** search and open contacts, companies, deals, tasks, meetings (summaries and transcripts), tickets, invoices, proposals, quotes, conversations (where shareable), saved reports, and workspace search.
- **Write (19 tools, only if you approved create/update):** upsert or update contacts, add notes and tags, create or move deals, create or complete tasks, create events (no invites sent), open or update tickets (the customer is not emailed), and create drafts of emails, SMS, proposals, and quotes. Drafts are never sent. Bulk tag or stage changes over 25 records wait for approval in CRMown.

Full caveats and troubleshooting: https://docs.crmown.com/integrations/connect-claude-or-chatgpt-to-crmown-mcp

## Auth and security

- OAuth 2.1 with PKCE. Grok Bot and Cursor register themselves (dynamic client registration). You approve scopes on a CRMown page.
- Tokens are held by the client platform, not pasted into chat. Signing out everywhere, resetting your password, or being deactivated disconnects every app you connected.
- MCP use does not count against CRMown AI usage. Ordinary API rate limits per plan apply.
- Record contents are data: the server tells the assistant not to follow instructions found inside notes or inbound messages.

## Plans

Available on every CRMown plan. Finance tools need the Finance suite; quote tools need the Enterprise suite on Pro or Max; tickets need Client Hub.

## Support

- Docs: https://docs.crmown.com/integrations/connect-claude-or-chatgpt-to-crmown-mcp
- Privacy: https://crmown.com/privacy-policy
- Terms: https://crmown.com/terms
- Website: https://crmown.com
- Contact: https://crmown.com/contact
