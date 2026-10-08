# Coinbase-Api-Automation-with-Python

Project Overview

This project features a production-ready Python script engineered to automatically consume real-time market metrics from the CoinMarketCap API.
The script transitions smoothly between testing environments and live production endpoints. It includes defensive programming mechanisms to catch network disruptions, ensuring that downstream applications receive highly reliable data pipelines.

🛠️ Technical Stack

• Language: Python 3.x
• HTTP Client: requests (Utilizing Session persistence)
• Data Formatting: json (REST API payload parsing)
• Architecture Pattern: Defensive Exception Management

🚀 Key Architectural Features

1. Persistent Connection Architecture (requests.Session)

• What it does: Instead of spinning up raw, isolated HTTP connections for every request, the pipeline instantiates a persistent Session().
• Why recruiters care: This reuse optimization keeps TCP connections open via keep-alive flags, significantly reducing latency overhead and optimizing resource usage when scaling scripts into cron jobs or cloud functions.

2. Sandbox to Production Deployment Lifecycle

• Testing Layer: Initial schema structures were validated using the CoinMarketCap Sandbox endpoint (sandbox-api.coinmarketcap.com) to prevent burning through premium API request credits during early-stage debugging.
• Production Layer: Once the payload structure was confirmed, the target destination was cleanly pointed to the live endpoint (pro-api.coinmarketcap.com) to extract real-time data for market leaders like Bitcoin (BTC) and Ethereum (ETH).


