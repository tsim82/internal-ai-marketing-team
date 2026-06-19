# Slack

## Purpose

Team communication platform. Used for sending notifications, alerts, and internal updates from automated workflows.

## Agents That May Use It

- n8n Automation Agent (primary)
- Marketing Director (supporting)
- Analytics Agent (supporting)

## Common Use Cases

- Sending workflow notifications
- Alerting team to lead activity
- Posting weekly report summaries
- Escalating QA flags

## Required Credentials

- Slack bot token
- Channel IDs for each channel the bot posts to

Do not add real credentials here.

## Expected MCP Server Name

slack-mcp

Placeholder.

## Required Environment Variables

SLACK_BOT_TOKEN=placeholder
SLACK_CHANNEL_ID=placeholder

Placeholder values only.

## Setup Notes

Placeholder. See mcp/configs/README.md for setup instructions when ready to connect.

## Risks And Permissions

Slack messages go to real channels. Use a test channel for development and automation testing.

## Status

Not connected yet.
