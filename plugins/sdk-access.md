# SDK Access

Programmatic API access via SDK API keys with scoped permissions.

**Status:** Available | **Minimum tier:** Team

## Features

- Up to 10 active API keys per organization
- Scoped permissions — restrict what each key can do
- Optional key expiration for added security
- Usage tracking — see when each key was last used

## Getting Started

1. Enable the SDK Access plugin in the Swarmix dashboard
2. Create an API key in **Settings > API Keys**
3. Use the key to authenticate requests from external code (Python SDK, LangChain, CrewAI, or direct HTTP)

This plugin is a prerequisite for the LangChain Adapter and CrewAI Adapter plugins.
