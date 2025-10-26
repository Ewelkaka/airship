# Development Guide - Helius AirShip

## Quick Start Commands
```bash
# Install dependencies
pnpm install

# Build all packages
pnpm build

# Start development server
pnpm dev

# Run web app locally
cd apps/web && pnpm preview

# Lint code
pnpm lint

# Format code
pnpm format
```

## Development Workflow
1. **Setup**: Clone repo, run `pnpm install`
2. **Build**: Run `pnpm build` to build all packages
3. **Development**: Use `pnpm dev` for hot reload
4. **Testing**: Web app supports up to 200k recipients
5. **CLI Testing**: Use `helius-airship` command after build

## Key Development Files
- **apps/web/src/App.tsx**: Main application entry point
- **apps/web/src/components/**: React components
- **packages/core/**: Core airdrop functionality
- **packages/cli/**: CLI implementation
- **dev-services.json**: Service configuration

## Environment Setup
- **Node.js**: >= v20.17.0 required
- **pnpm**: >= v9.15.2 required
- **RPC**: Helius RPC with ZK Compression + DAS API support
- **Wallet**: Solana filesystem wallet for CLI

## Database Schema
- Uses SQLite with Drizzle ORM
- Local database file managed by sqlocal
- Schema configured in core package

## Web Workers
- **create.ts**: Airdrop creation worker
- **poll.ts**: Status polling worker  
- **send.ts**: Transaction sending worker

## Build Configuration
- **Turbo**: Orchestrates monorepo builds
- **Vite**: Web app bundling
- **tsup**: Package building
- **Changesets**: Version management

## Common Issues
- **RPC Requirements**: Must support ZK Compression and DAS API
- **Memory**: Large airdrops may require increased Node.js memory
- **Wallet**: CLI requires filesystem wallet with SOL for fees
- **CORS**: Web version may have RPC CORS limitations

## Testing Checklist
- [ ] Web app loads correctly
- [ ] Database initialization works
- [ ] Wallet connection functional
- [ ] Airdrop creation flow
- [ ] Resume functionality
- [ ] Cost calculator accuracy
- [ ] CLI commands work
- [ ] ZK compression features