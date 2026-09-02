# OpenMandate MCP Server

> [!IMPORTANT]
> OpenMandate is in private development. We are not currently accepting new mandates or new integrations.
> The documentation below is retained as a historical compatibility reference; operations that start new work are unavailable.

This repository retains the hosted MCP endpoint and its integration history for
existing OpenMandate accounts. Historical reads and explicit withdrawal actions
remain available; tools that start or advance new work return
`SERVICE_PRIVATE_DEVELOPMENT`.

> **Endpoint**: `https://mcp.openmandate.ai/mcp`

The frozen 0.6.0 protocol surface exposes 15 tools across mandate history,
matching and contact management.

---

## Setup

### Claude Desktop / Cursor

Add to your MCP config:

```json
{
  "mcpServers": {
    "openmandate": {
      "type": "url",
      "url": "https://mcp.openmandate.ai/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_API_KEY"
      }
    }
  }
}
```

### Claude Code (CLI)

```bash
claude mcp add --transport http openmandate https://mcp.openmandate.ai/mcp \
  --header "Authorization: Bearer YOUR_API_KEY"
```

### Existing API keys

Existing users may continue using retained read and withdrawal actions. New accounts and API keys are not available.

---

## Tools

| Tool | Description |
|------|-------------|
| `openmandate_create_mandate` | Create a mandate with what you need and what you offer |
| `openmandate_submit_answers` | Answer follow-up questions to sharpen your mandate |
| `openmandate_get_mandate` | Get details of a specific mandate |
| `openmandate_list_mandates` | List your mandates (defaults to open) |
| `openmandate_close_mandate` | Close a mandate |
| `openmandate_list_matches` | List matches for a mandate |
| `openmandate_get_match` | Get match details with compatibility grade |
| `openmandate_respond_to_match` | Accept or decline a match |
| `openmandate_submit_outcome` | Report how a confirmed match went |
| `openmandate_list_contacts` | List your verified contacts |
| `openmandate_add_contact` | Add a contact (email, verified via OTP) |
| `openmandate_verify_contact` | Verify a contact with OTP code |
| `openmandate_update_contact` | Update contact details |
| `openmandate_delete_contact` | Remove a contact |
| `openmandate_resend_otp` | Resend verification code |

---

## How it works

1. You tell your AI what you're looking for and what you bring
2. The system asks follow-up questions to build a strong mandate
3. OpenMandate keeps working on your behalf across all active mandates
4. When there's a strong fit, both sides get notified
5. Both accept before contact info is shared
6. Report how it went — mandate closes or reactivates for new matches

---

## Other ways to use OpenMandate

- **Website**: [openmandate.ai](https://openmandate.ai)
- **Python SDK**: `pip install openmandate` ([PyPI](https://pypi.org/project/openmandate/))
- **JavaScript SDK**: `npm install openmandate` ([npm](https://www.npmjs.com/package/openmandate))
- **Claude Code Skill**: `npx skills add openmandate/skills`

---

## Links

- Website: [openmandate.ai](https://openmandate.ai)
- MCP Registry: [modelcontextprotocol.io](https://modelcontextprotocol.io)
- GitHub: [github.com/openmandate](https://github.com/openmandate)
