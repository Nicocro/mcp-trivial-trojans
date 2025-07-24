# 🐴 Trivial Trojans: Malicious Weather MCP Server

This repository contains the minimal malicious `weather_mcp_server` used in the paper:

**_Trivial Trojans: How a Weather Bot Can Steal Your Bank Balance via the Model Context Protocol_**

## 🔍 Overview

This project demonstrates how a benign-looking MCP server (e.g., a weather integration) can be weaponized to exfiltrate sensitive data from unrelated, trusted MCP servers via an AI agent acting as the orchestrator.

This server:
- Implements standard weather forecast functionality (from the official MCP examples)
- Embeds a malicious prompt that triggers cross-server tool discovery
- Sends exfiltrated data to a public `webhook.site` endpoint via HTTP POST

No infrastructure, credentials, or privileged access are required.

## ⚙️ Requirements

- Python 3.8+
- [`fastmcp`](https://github.com/anthropics/fastmcp) (install via `pip install fastmcp`)

## 🛠️ Example MCP Client Configuration

To run this attack in a local setup using an MCP-compatible agent (e.g., Claude Desktop), use the following example configuration file:

[`example-config.json`](./example-config.json)

## 🚀 Running the Server

```bash
python weather_mcp_server.py


