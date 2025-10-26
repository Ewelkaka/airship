# Helius AirShip - Memory Bank

## Project Overview
Helius AirShip is an open-source tool for simplified, affordable token airdrops on Solana. It supports ZK Compression to reduce costs and offers both web and CLI interfaces.

## Architecture
- **Monorepo Structure**: Uses pnpm workspaces with Turbo for build orchestration
- **Frontend**: React + TypeScript + Vite web application
- **Core Library**: Shared TypeScript library for airdrop functionality
- **CLI Tool**: Command-line interface for advanced users
- **Database**: SQLite with Drizzle ORM for local data persistence

## Key Technologies
- **Blockchain**: Solana, ZK Compression, SPL Tokens
- **Frontend**: React 18, TypeScript, Vite, Tailwind CSS, Radix UI
- **Backend**: Node.js, Drizzle ORM, SQLite (sqlocal)
- **Build Tools**: Turbo, pnpm, Changesets
- **Wallet Integration**: Solana Wallet Adapter

## Project Structure
```
airship/
├── apps/web/                 # React web application
│   ├── src/components/       # React components
│   ├── src/workers/          # Web workers for background tasks
│   └── public/              # Static assets
├── packages/
│   ├── core/                # Core airdrop functionality
│   ├── cli/                 # Command-line interface
│   ├── eslint-config/       # Shared ESLint configuration
│   └── typescript-config/   # Shared TypeScript configuration
```

## Core Features
- **Airdrop Types**: Saga Chapter 2 holders, NFT/cNFT holders, SPL token holders, CSV imports
- **ZK Compression**: Cost reduction for large airdrops
- **Web Interface**: Up to 200,000 recipients
- **CLI Interface**: Unlimited scale for advanced users
- **Resume Functionality**: Continue interrupted airdrops
- **Cost Calculator**: Estimate airdrop costs

## Key Components
- **CreateAirdrop**: Main airdrop creation interface
- **ResumeAirdrop**: Resume interrupted airdrops
- **AirdropSelection**: Choose between create/resume
- **DecompressPage**: ZK compression utilities
- **CostCalculator**: Airdrop cost estimation

## Development Setup
- **Node.js**: >= v20.17.0
- **Package Manager**: pnpm >= v9.15.2
- **Build**: `pnpm build`
- **Dev**: `pnpm dev`
- **Preview**: `pnpm preview`

## Dependencies
- **Solana**: @solana/web3.js, @solana/spl-token, @solana/wallet-adapter-*
- **ZK Compression**: @lightprotocol/compressed-token, @lightprotocol/stateless.js
- **UI**: @radix-ui/*, lucide-react, tailwindcss
- **Data**: drizzle-orm, sqlocal, papaparse
- **Utils**: bs58, comlink, zod

## Configuration Files
- **dev-services.json**: Development service configuration
- **turbo.json**: Turbo build configuration
- **pnpm-workspace.yaml**: Workspace configuration
- **vercel.json**: Deployment configuration

## Requirements
- RPC endpoint supporting ZK Compression and DAS API (Helius recommended)
- Solana filesystem wallet for CLI usage
- Modern browser for web interface

## Deployment
- **Web**: Hosted at airship.helius.dev
- **CLI**: Available via npm as `helius-airship`
- **Local**: Can be run locally via `pnpm preview`

## License
Apache-2.0