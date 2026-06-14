# Flow Blockchain

Flow is a developer-friendly Layer 1 proof-of-stake blockchain built for consumer applications, NFTs, games, AI agents, and DeFi at scale. The Flow REST API (Access API) enables developers to query accounts, blocks, collections, events, and transactions, execute Cadence scripts, and submit signed transactions to the network.

## API

- **Base URL (Mainnet):** `https://rest-mainnet.onflow.org/v1`
- **Base URL (Testnet):** `https://rest-testnet.onflow.org/v1`
- **Documentation:** https://developers.flow.com/http-api
- **OpenAPI Spec:** https://raw.githubusercontent.com/onflow/flow/master/openapi/access.yaml

## Endpoints

- `GET /blocks` — Query blocks by height range or list of heights
- `GET /blocks/{id}` — Get blocks by ID
- `GET /blocks/{id}/payload` — Get block payload by block ID
- `GET /transactions/{id}` — Get a transaction by ID
- `GET /transaction_results/{transaction_id}` — Get transaction result
- `POST /transactions` — Submit a signed transaction
- `GET /collections/{id}` — Get a collection by ID
- `GET /execution_results` — Get execution results by block ID
- `GET /execution_results/{id}` — Get execution result by ID
- `GET /accounts/{address}` — Get account data by address
- `GET /accounts/{address}/keys` — Get account keys
- `GET /accounts/{address}/balance` — Get account balance
- `POST /scripts` — Execute a read-only Cadence script
- `GET /events` — Query on-chain events by type
- `GET /subscribe_events` — WebSocket stream for event subscriptions
- `GET /network/parameters` — Get network parameters
- `GET /node_version_info` — Get node version information

## Authentication

No authentication is required for the public community access nodes.

## Rate Limits

Public access nodes enforce per-IP rate limits:

| Endpoint | Limit (RPS) |
|----------|-------------|
| POST /transactions (SendTransaction) | 50 |
| POST /scripts (ExecuteScript) | 5 |
| GET /events | 30 |
| Other GET requests | 100 |

Exceeding limits returns a `ResourceExhausted` error.

## Pricing

API access via public community nodes is free. Transaction fees are paid in FLOW tokens based on compute units consumed. See [finops/finops.yml](finops/finops.yml) for details.

## Resources

- [Developer Portal](https://developers.flow.com/)
- [GitHub Organization](https://github.com/onflow)
- [Flow CLI](https://developers.flow.com/tools/flow-cli)
- [Discord Community](https://discord.gg/flow)
- [Flow Explorer (Flowscan)](https://flowscan.org/)
