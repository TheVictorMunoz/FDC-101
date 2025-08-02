# FDC-101: Flare Data Connector Examples

A comprehensive collection of working examples demonstrating Flare Data Connector (FDC) capabilities. This project showcases how to integrate external data sources with Flare blockchain using various attestation types.

## 🚀 What This Project Demonstrates

- **Web2Json Attestations**: Fetch and verify data from external APIs
- **Weather Insurance**: Real-world insurance contracts using weather data
- **Proof of Reserves**: Cryptographic proof systems for asset verification
- **Cross-Chain FDC**: Multi-chain data connectivity solutions

## ✅ Verified Working Examples

### Star Wars API Integration
- **Contract**: `StarWarsCharacterListV2` deployed at `0xE7f6ff7bD309621ae9e2339C829544E6C58bD8Ba`
- **Network**: Coston2 Testnet
- **Functionality**: Fetches character data from Star Wars API and processes it on-chain
- **Verification**: [View on Block Explorer](https://coston2-explorer.flare.network/address/0xE7f6ff7bD309621ae9e2339C829544E6C58bD8Ba#code)

### Weather Insurance Contracts
- **Min Temperature Insurance**: Insurance against low temperature events
- **Weather ID Verification**: Location-based weather data verification
- **Real-time Data**: Integration with OpenWeather API

## 🛠️ Getting Started

### Prerequisites
- Node.js (v16 or higher)
- Yarn package manager
- Flare testnet tokens (Coston2 faucet)

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/TheVictorMunoz/FDC-101.git
   cd FDC-101
   ```

2. **Install dependencies**:
   ```bash
   yarn install
   ```

3. **Set up environment**:
   ```bash
   cp .env.example .env
   ```

4. **Configure your private key**:
   Edit `.env` file and add your wallet's private key:
   ```
   PRIVATE_KEY=your_private_key_here
   ```

5. **Get testnet tokens**:
   - Visit [Coston2 Faucet](https://coston2-faucet.towolabs.com/)
   - Enter your wallet address
   - Request testnet FLARE tokens

## 🧪 Running Examples

### Web2Json Example (Star Wars API)
```bash
yarn hardhat run scripts/fdcExample/Web2Json.ts --network coston2
```

This will:
- Submit an attestation request to FDC Hub
- Wait for voting round finalization
- Generate cryptographic proof
- Deploy smart contract
- Fetch and display Star Wars character data

### Weather Insurance Examples
```bash
# Create weather insurance policy
yarn hardhat run scripts/weatherInsurance/weatherId/createPolicy.ts --network coston2

# Resolve weather insurance policy
yarn hardhat run scripts/weatherInsurance/weatherId/resolvePolicy.ts --network coston2
```

## 📁 Project Structure

```
├── contracts/
│   ├── crossChainFdc/          # Cross-chain FDC contracts
│   └── fdcExample/            # FDC example contracts
├── scripts/
│   ├── fdcExample/            # Web2Json and FDC examples
│   ├── weatherInsurance/      # Weather insurance contracts
│   ├── proofOfReserves/       # Proof of reserves functionality
│   └── utils/                 # Utility functions
├── utils/                     # Network utilities
└── hardhat.config.ts         # Hardhat configuration
```

## 🔧 Configuration

### Supported Networks
- **Coston2 Testnet** (Chain ID: 114) - Primary testnet
- **Coston Testnet** (Chain ID: 16)
- **Songbird** (Chain ID: 19)
- **Flare Mainnet** (Chain ID: 14)

### Environment Variables
```bash
PRIVATE_KEY=your_wallet_private_key
FLARE_RPC_API_KEY=your_flare_api_key
FLARESCAN_API_KEY=your_flarescan_api_key
OPEN_WEATHER_API_KEY=your_openweather_api_key
```

## 🎯 Key Features

### FDC Attestation Types
- **Web2Json**: HTTP API data fetching and verification
- **Payment Verification**: Payment transaction verification
- **Balance Decreasing**: Balance change verification
- **Address Validity**: Address format verification
- **Block Height**: Block existence verification

### Smart Contract Integration
- **Automatic Deployment**: Contracts deploy automatically
- **Block Explorer Verification**: Source code verification
- **Event Logging**: Comprehensive transaction logging
- **Error Handling**: Robust error handling and recovery

## 📊 Example Output

Running the Web2Json example produces:
```
Star Wars Characters:
[
  [
    'R2-D2',
    '6',
    '3', 
    '34',
    name: 'R2-D2',
    numberOfMovies: '6',
    apiUid: '3',
    bmi: '34'
  ]
]
```

## 🔗 Useful Links

- **Voting Round Explorer**: https://coston2-systems-explorer.flare.rocks/
- **Block Explorer**: https://coston2-explorer.flare.network/
- **FDC Documentation**: https://dev.flare.network/fdc/
- **Flare Developer Hub**: https://dev.flare.network/

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly on testnet
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Troubleshooting

### Common Issues

**"gas required exceeds allowance"**
- Solution: Get testnet tokens from the faucet

**"Tenderly config doesn't exist"**
- This is a warning, not an error. The project works without Tenderly

**"Network connection issues"**
- Check your internet connection
- Verify RPC endpoint availability

### Getting Help
- Check the [Flare Developer Discord](https://discord.gg/flare)
- Review [FDC documentation](https://dev.flare.network/fdc/)
- Open an issue on this repository
