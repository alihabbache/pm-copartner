# Security Policy

## Scope

PM CoPartner is a static documentation and prompt repository — it contains no server-side code, no authentication, no user data storage, and no network services.

The attack surface is limited to:
- **HTML pages** served as static files (GitHub Pages)
- **Markdown prompt files** consumed by end users in third-party AI assistants

## Supported Versions

All content in the `main` branch is considered current. There are no versioned releases to patch separately.

## Reporting a Vulnerability

If you discover a security issue (e.g. a link that could mislead users, a prompt pattern that could enable prompt injection against an AI assistant, or a supply-chain concern in a referenced MCP server), please report it responsibly:

1. **Do not open a public GitHub issue** for security vulnerabilities.
2. **Email** the maintainer directly: open a [GitHub private security advisory](https://github.com/alihabbache/pm-copartner/security/advisories/new) instead.
3. Describe the issue clearly: what the vulnerability is, where it appears, and what impact it could have.

You can expect an acknowledgement within **5 business days** and a resolution or public disclosure timeline within **30 days**.

## Known Non-Issues

- The `copyPrompt()` JavaScript function in the HTML pages reads from a static DOM element — it does not accept external input and is not vulnerable to XSS.
- All external links open with `rel="noopener noreferrer"` to prevent tab-napping.
- No API keys, tokens, or credentials are stored in this repository.
