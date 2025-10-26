# Troubleshooting Guide - Helius AirShip

## Common Issues & Solutions

### RPC Connection Issues
**Problem**: RPC endpoint not responding or CORS errors
**Solutions**:
- Verify RPC supports ZK Compression and DAS API
- Check API key validity
- Use Helius RPC for guaranteed compatibility
- Ensure CORS is configured for web usage

### Database Initialization Errors
**Problem**: Database fails to initialize
**Solutions**:
- Clear browser storage/cache
- Check SQLite compatibility
- Verify sqlocal installation
- Restart application

### Wallet Connection Problems
**Problem**: Wallet fails to connect
**Solutions**:
- Install supported wallet extension
- Check wallet is unlocked
- Verify network selection (mainnet/devnet)
- Clear wallet cache

### Airdrop Creation Failures
**Problem**: Airdrop creation process fails
**Solutions**:
- Verify sufficient SOL for fees
- Check token balance
- Validate recipient addresses
- Reduce batch size

### Memory Issues
**Problem**: Application crashes with large airdrops
**Solutions**:
- Increase Node.js memory limit
- Process in smaller batches
- Use CLI for large airdrops (>200k recipients)
- Clear browser cache

### Transaction Failures
**Problem**: Transactions fail to confirm
**Solutions**:
- Check network congestion
- Increase transaction fees
- Retry failed transactions
- Verify RPC stability

## Development Issues

### Build Failures
**Problem**: Build process fails
**Solutions**:
- Run `pnpm install` to update dependencies
- Clear node_modules and reinstall
- Check Node.js version (>= v20.17.0)
- Verify pnpm version (>= v9.15.2)

### TypeScript Errors
**Problem**: Type checking fails
**Solutions**:
- Run `pnpm typecheck`
- Update @types packages
- Check tsconfig.json configuration
- Verify import paths

### Linting Issues
**Problem**: ESLint errors
**Solutions**:
- Run `pnpm lint` to identify issues
- Use `pnpm format` for auto-formatting
- Check eslint.config.js
- Update ESLint rules if needed

## Performance Issues

### Slow Airdrop Processing
**Problem**: Airdrops process slowly
**Solutions**:
- Optimize batch sizes
- Use faster RPC endpoint
- Enable ZK Compression
- Reduce concurrent transactions

### High Memory Usage
**Problem**: Application uses excessive memory
**Solutions**:
- Process recipients in chunks
- Clear unused data
- Use web workers efficiently
- Monitor memory usage

## Network Issues

### Rate Limiting
**Problem**: RPC rate limits exceeded
**Solutions**:
- Implement exponential backoff
- Reduce request frequency
- Use premium RPC tier
- Distribute load across endpoints

### Network Timeouts
**Problem**: Requests timeout
**Solutions**:
- Increase timeout values
- Retry failed requests
- Check network stability
- Use reliable RPC provider

## CLI Specific Issues

### Installation Problems
**Problem**: CLI installation fails
**Solutions**:
- Use correct Node.js version
- Install globally with `-g` flag
- Check npm/pnpm permissions
- Build from source if needed

### Wallet File Issues
**Problem**: Wallet file not recognized
**Solutions**:
- Verify file path is correct
- Check file permissions
- Ensure valid Solana keypair format
- Test wallet with Solana CLI

## Debugging Tips

### Enable Verbose Logging
- Set verbose flags in configuration
- Check browser console for errors
- Monitor network requests
- Use Solana explorer for transaction tracking

### Testing Strategies
- Start with small test airdrops
- Use devnet for testing
- Verify recipient addresses
- Test resume functionality

### Monitoring Tools
- Browser DevTools
- Solana Explorer
- RPC endpoint monitoring
- Database inspection tools