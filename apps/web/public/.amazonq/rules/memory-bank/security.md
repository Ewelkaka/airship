# Security Guidelines - Helius AirShip

## Wallet Security
- **Private Keys**: Never expose private keys in code or logs
- **Filesystem Wallets**: Secure file permissions (600)
- **Web Wallets**: Use reputable wallet extensions only
- **Backup**: Always backup wallet files securely

## RPC Security
- **API Keys**: Store securely, never commit to version control
- **Rate Limiting**: Implement proper rate limiting
- **HTTPS**: Always use HTTPS endpoints
- **Validation**: Validate all RPC responses

## Transaction Security
- **Verification**: Always verify transaction signatures
- **Amounts**: Double-check token amounts before sending
- **Recipients**: Validate recipient addresses
- **Fees**: Monitor and cap transaction fees

## Data Security
- **Local Storage**: Database contains sensitive airdrop data
- **Encryption**: Consider encrypting sensitive data at rest
- **Access Control**: Limit database access appropriately
- **Cleanup**: Clear sensitive data when no longer needed

## Network Security
- **CORS**: Configure CORS properly for web deployment
- **CSP**: Implement Content Security Policy
- **Input Validation**: Sanitize all user inputs
- **Error Handling**: Don't expose sensitive info in errors

## Best Practices
- **Principle of Least Privilege**: Minimal required permissions
- **Regular Updates**: Keep dependencies updated
- **Audit Logs**: Log important operations
- **Testing**: Test security measures regularly