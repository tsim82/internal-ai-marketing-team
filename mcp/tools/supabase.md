# Supabase

## Purpose

PostgreSQL database and backend platform. Used for storing content analysis data, call transcripts, and other structured data.

## Agents That May Use It

- n8n Automation Agent
- Analytics Agent
- Video Agent

## Common Use Cases

- Storing content analysis results
- Logging call transcripts
- Querying performance data

## Required Credentials

- Supabase project URL
- Service role key or anon key depending on use case

Do not add real credentials here.

## Expected MCP Server Name

supabase-mcp

Placeholder.

## Required Environment Variables

SUPABASE_URL=placeholder
SUPABASE_ANON_KEY=placeholder
SUPABASE_SERVICE_ROLE_KEY=placeholder

Placeholder values only.

## Setup Notes

Placeholder. See mcp/configs/README.md for setup instructions when ready to connect.

## Risks And Permissions

Service role keys have full database access. Use anon key when possible and restrict with RLS policies.

## Status

Not connected yet.
