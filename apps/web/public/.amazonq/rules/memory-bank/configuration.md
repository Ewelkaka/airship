# Configuration Guide - Helius AirShip

## Environment Configuration

### Required Environment Variables
- **RPC_URL**: Solana RPC endpoint with ZK Compression + DAS API support
- **WALLET_PATH**: Path to Solana filesystem wallet (CLI only)

### Development Services
```json
{
  "services": [{
    "name": "app",
    "command": "pnpm",
    "args": ["start"],
    "path": "./",
    "type": "frontend",
    "port": 3000
  }],
  "settings": {
    "startDelay": 1000,
    "logOutput": true,
    "autoRestart": false
  }
}
```

## Build Configuration

### Turbo Configuration
- Orchestrates monorepo builds
- Caches build outputs
- Manages dependencies between packages

### Package Configuration
- **Web App**: Vite + React + TypeScript
- **Core Library**: tsup for bundling
- **CLI Tool**: Node.js executable

## Database Configuration
- **Engine**: SQLite via sqlocal
- **ORM**: Drizzle ORM
- **Storage**: Browser IndexedDB (web) / Local file (CLI)

## Wallet Configuration
- **Web**: Solana Wallet Adapter with multiple wallet support
- **CLI**: Filesystem wallet (JSON keypair)
- **Networks**: Mainnet, Devnet, Testnet support

## RPC Configuration
- **Recommended**: Helius RPC
- **Requirements**: ZK Compression + DAS API support
- **Fallback**: Any compatible Solana RPC

## ZK Compression Settings
- **Provider**: Light Protocol
- **Cost Reduction**: Up to 90% for large airdrops
- **Compatibility**: SPL tokens and compressed tokens