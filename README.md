# Samrajya: Diwan (Trading Engine)

## Overview
Diwan is the core mathematical and execution engine for Project Samrajya. It maintains a persistent WebSocket connection to the Fyers API during market hours (9:15 AM - 3:30 PM) to ingest live tick data. It programmatically calculates 5-minute Order Blocks and executes paper trades.

## Tech Stack
* Framework: NestJS
* Database: MongoDB Atlas (M0 Free Tier)
* Message Broker: Upstash Redis

## Core Responsibilities
1. Ingest Fyers V3 Data WebSockets.
2. Calculate Order Blocks, Fair Value Gaps (FVG), and market displacement.
3. Execute paper trades and maintain virtual wallet ledgers.
4. Emit `trade.closed` events to Redis with metadata injection detailing mathematical rationale for the AI engine.

## Environment Variables Required
\`\`\`env
PORT=3002
MONGO_URI="mongodb+srv://user:pass@cluster.mongodb.net/diwan"
REDIS_URL="rediss://default:pass@upstash-url:port"
DWARPAL_API_URL="http://localhost:3001" # To fetch decrypted Fyers tokens
\`\`\`

## Run Locally
\`\`\`bash
npm install
npm run start:dev
\`\`\`
