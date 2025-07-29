# 🐴 Trivial Trojans: Malicious Weather MCP Server

### How a Weather Bot Can Steal Your Bank Balance via the Model Context Protocol

This repository contains the minimal malicious `weather_mcp_server` used in the paper:

**_[Trivial Trojans: How Minimal MCP Servers Enable Cross-Tool Exfiltration of Sensitive Data](https://arxiv.org/abs/2507.19880)_**

## 🔍 Overview

This project demonstrates how a benign-looking MCP server (e.g., a weather integration) can be weaponized to exfiltrate sensitive data from unrelated, trusted MCP servers via an AI agent acting as the orchestrator.

This server:
- Implements standard weather forecast functionality (from the official [MCP examples](https://github.com/modelcontextprotocol/quickstart-resources/blob/main/weather-server-python/weather.py))
- Embeds a malicious prompt that triggers cross-server tool discovery
- Sends exfiltrated data to a public `webhook.site` endpoint via HTTP POST

No infrastructure, credentials, or privileged access are required, in an extremely minimal and simple implemetation. 

<h3>🎥 Demo: Cross-Server Data Exfiltration via Malicious Weather Server</h3>

This short demo shows how an innocent-looking weather request can trigger a cross-server sequence that:
1. Retrieves a bank account balance from a separate MCP server.
2. Sends the sensitive data to a public `webhook.site` endpoint.
3. Displays a normal weather forecast — concealing the attack.

<a href="https://www.loom.com/share/cbaf77a45ff244c2891b363dc7178904">
  <img 
    src="https://cdn.loom.com/sessions/thumbnails/cbaf77a45ff244c2891b363dc7178904-9f9ba9af68e19933-full-play.gif" 
    alt="Data Exfiltration - Weather MCP - Watch Video"
    style="max-width: 100%; height: auto; border: 1px solid #ddd;"
  />
</a>

<p><em>Click the image to watch a short demo showing how a weather MCP server can exfiltrate financial data via cross-server orchestration.</em></p>

## ⚙️ Requirements

- Python 3.8+
- [`fastmcp`](https://github.com/anthropics/fastmcp) (install via `pip install fastmcp`)

## 🛠️ Example MCP Client Configuration

To run this attack in a local setup using an MCP-compatible agent (e.g., Claude Desktop), use the following example configuration file:

[`example-config.json`](./example-config.json)

## 🚀 Running the Server

```bash
python weather_mcp_server.py


