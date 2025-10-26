# API Reference - Helius AirShip

## Core Library Functions

### Database Operations
```typescript
// Initialize database and airdrop system
await init({ db })

// Check if airdrop exists
const exists = await exist({ db })

// Configure database schema
await configureDatabase(db)
```

### Airdrop Types
- **Saga Chapter 2**: Target Saga phone holders
- **NFT/cNFT Holders**: Target NFT collection holders
- **SPL Token Holders**: Target specific token holders
- **CSV Import**: Custom recipient list

### Key Components API

#### CreateAirdrop
```typescript
interface CreateAirdropProps {
  db: DrizzleDB
  onBackToHome: () => void
}
```

#### ResumeAirdrop
```typescript
interface ResumeAirdropProps {
  db: DrizzleDB
  onBackToHome: () => void
}
```

#### AirdropSelection
```typescript
interface AirdropSelectionProps {
  existingAirdrop: boolean | null
  onCreateAirdrop: () => void
  onResumeAirdrop: () => void
}
```

## Solana Integration

### Wallet Adapter
- Uses @solana/wallet-adapter-react
- Supports multiple wallet types
- Handles connection state

### Token Operations
- SPL Token transfers
- ZK Compressed token operations
- Batch transaction processing

### RPC Requirements
- ZK Compression support
- DAS API support
- Helius RPC recommended

## Database Schema

### Tables
- Airdrop configurations
- Recipient lists
- Transaction status
- Progress tracking

### Operations
- CRUD operations via Drizzle ORM
- SQLite local storage
- Batch operations support

## Web Workers API

### Create Worker
- Handles airdrop creation
- Background processing
- Progress updates

### Poll Worker
- Status monitoring
- Transaction confirmation
- Error handling

### Send Worker
- Transaction broadcasting
- Retry logic
- Batch processing

## CLI Commands

### Basic Usage
```bash
helius-airship --keypair /path/to/wallet.json --url "RPC_URL"
```

### Options
- `--keypair`: Wallet file path
- `--url`: RPC endpoint URL
- `--help`: Show help information

## Error Handling
- Network errors
- RPC failures
- Wallet connection issues
- Insufficient funds
- Invalid recipients

## Rate Limiting
- RPC rate limits
- Transaction throughput
- Batch size optimization
- Retry strategies