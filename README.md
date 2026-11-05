# futoroku for Claude

Record income, expenses and account transfers in your approved [Futoroku](https://futoroku.app/about) Spaces, review saved receipts, and summarize transactions, balances and budgets from Claude.

Futoroku records the information you enter. It does not connect to your bank or make payments. A Futoroku account is required, and access follows your connection permissions and current Space role. MCP writes, receipt reading and storage have separate allowances.

## Install

```bash
claude plugin marketplace add epfmydx/futoroku-plugin-claude
```

```bash
claude plugin install futoroku@futoroku
```

Then run `/mcp` in Claude Code, select the `futoroku` server and sign in. The connection requests the `finance:read` and `finance:write` scopes.

## Skills

| Skill | Use it to |
| --- | --- |
| `/futoroku:choose-space` | Choose the Space, ledger and account for a task, or check permissions and usage |
| `/futoroku:record-money` | Record income, expenses, received reimbursements or account transfers |
| `/futoroku:review-receipt` | Review an attached receipt and propose a separately confirmed correction |
| `/futoroku:correct-record` | Correct or delete explicitly identified records |
| `/futoroku:reconcile` | Summarize or reconcile transactions, balances, budgets and member contributions |

Claude can also pick these up from a plain request, for example:

- "Summarize last month's spending in my chosen Space, keeping currencies separate."
- "Help me record an expense in the right Space, ledger and account."
- "Review a saved receipt and show any uncertain details before changing the record."

## What this plugin runs and sends

This plugin contains skills and one remote MCP server reference. It has no hooks, scripts, local servers or package installs.

Its only network destination is the Futoroku MCP server at `https://futoroku.app/mcp`, which Futoroku operates. You sign in with OAuth, and access is limited to your approved Spaces and current Space role.

- **Reads:** Spaces, ledgers, accounts, categories, members, transactions, balances, budgets, reports and receipts.
- **Writes:** the records you ask Claude to create, correct or delete, the receipts you ask it to upload, and the receipt readings you ask it to start. Permanent deletion requires your explicit confirmation.
- **Not included:** bank connections, payments or other real money movement. A transfer in Futoroku is a bookkeeping record only.
- **Outside the connection's scope:** Journal and note bodies, account security, membership administration, billing actions, and complete Space backup or restore.

The details you give Claude for these tasks are sent to Futoroku. See the [privacy policy](https://futoroku.app/privacy).

## Develop

Load the plugin from a local checkout:

```bash
claude --plugin-dir .
```

Validate it before release:

```bash
claude plugin validate --strict .
```

Each skill carries its own identical copy of `references/mcp-safety.md`, so change all five together.

## Links

- [Help](https://futoroku.app/help)
- [Privacy policy](https://futoroku.app/privacy)
- [Terms of service](https://futoroku.app/terms)
