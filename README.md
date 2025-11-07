# <img src="nodes/Imap/node-imap-icon.svg"  height="40"> n8n-nodes-imap-fork-test

This repository started as a fork of the original [n8n-nodes-imap](https://github.com/umanamente/n8n-nodes-imap) project but is now maintained independently by `stttru`. Future changes can diverge from upstream behaviour without preserving backward compatibility.

> **Acknowledgement & Disclaimer**
>
> - Huge thanks to the upstream maintainers of [`umanamente/n8n-nodes-imap`](https://github.com/umanamente/n8n-nodes-imap) for the original implementation.
> - This fork is maintained independently by the `stttru` team to ensure a fully controllable npm distribution (`n8n-nodes-imap-fork-test`).
> - Compatibility with the upstream package is **not guaranteed**; expect breaking changes tailored to the needs of this fork.
> - Updates in this fork are produced with the help of AI assistants and undergo manual review, but you should still audit before using in production.
> - Use at your own risk; verify compatibility and security within your environment before adopting new releases.

This is an n8n community node that adds support for [IMAP](https://en.wikipedia.org/wiki/Internet_Message_Access_Protocol) email servers. In the n8n UI the node appears as **“IMAP Fork”** to avoid clashing with the upstream module.

* [Installation](#installation)  
* [Operations](#operations)  
* [Credentials](#credentials)
* [Troubleshooting & Debug](#troubleshooting--debug)
* [Version history](CHANGELOG.md)
* **For Developers**: [Contributing Guide](CONTRIBUTING.md) | [Developer Quick Start](DEVELOPER.md)

## Installation

Follow the [installation guide](https://docs.n8n.io/integrations/community-nodes/installation/) in the n8n community nodes documentation.

Use `n8n-nodes-imap-fork-test` in N8N settings to install the stable version.

To install beta version, use `n8n-nodes-imap-fork-test@beta`.

NPMJS: [n8n-nodes-imap-fork-test](https://www.npmjs.com/package/n8n-nodes-imap-fork-test)


## Operations

* Mailbox
  * Get list of mailboxes (including status information like number of messages)
  * Get status of a mailbox (number of messages, etc.)
  * Create a mailbox
  * Rename a mailbox
  * ~Delete a mailbox~ (disabled due to danger of accidental data loss and no apparent use case)
* Email
  * Get list of emails in a mailbox
  * Download attachments from an email
  * Permanently delete an email from a mailbox
  * Move an email to another mailbox
  * Copy an email into another mailbox
  * Set/remove flags on an email ("seen", "answered", "flagged", "deleted", "draft")
  * Create email draft in a mailbox
    * Use `n8n-nodes-eml` node to create complex emails. It supports attachments and other features.

## Credentials

Currently, this node supports only basic authentication (username and password).  
OAuth2 authentication is not supported yet.  

> NOTE: You can reuse core [N8N IMAP Trigger node](https://docs.n8n.io/integrations/builtin/credentials/imap/) credentials for this node.

## Troubleshooting & Debug

If you encounter issues with the IMAP node, you can enable debug mode to get detailed logs and diagnostic information:

### Enable Debug Mode

Set the following environment variable before starting n8n:

```bash
N8N_NODES_DEBUG_ENABLED=true
```

When debug mode is enabled:
- The IMAP node will create an additional **"debug"** output containing detailed logs
- Enhanced error messages and diagnostic information will be available
- Connection and operation details will be logged for troubleshooting

### Getting Debug Information

1. **Set environment variables**:
   ```bash
   N8N_LOG_LEVEL=debug
   N8N_NODES_DEBUG_ENABLED=true
   ```

2. **Restart your n8n instance**

3. **Execute your workflow** - the IMAP node will now provide debug output

4. **Check the debug output** - connect the debug output to a Set node or similar to view the diagnostic information

### Reporting Issues

When reporting bugs or issues:
- Always enable debug mode first
- Include the debug output in your issue report
- Remove any sensitive information (passwords, email addresses, etc.) from logs
- Mention whether you are using the upstream package or this fork when reporting issues
- Note that this fork incorporates AI-generated changes; please double-check unexpected behaviour before filing upstream issues
- Use our [issue templates](.github/ISSUE_TEMPLATE/) for structured bug reports

## Credits

- Original project: [`umanamente/n8n-nodes-imap`](https://github.com/umanamente/n8n-nodes-imap)
- Fork maintainers: `stttru`
- AI tooling: GitHub Copilot, GPT-based assistants — all generated changes are reviewed before release, yet please validate in your workflows.
