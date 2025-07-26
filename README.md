# Solana Arbitrage Bot

A sophisticated Solana on-chain arbitrage bot designed to identify and execute profitable trading opportunities across multiple decentralized exchanges. This bot intelligently calculates optimal trade sizes between various DEX pools on Solana and executes trades when profitable arbitrage opportunities are detected, utilizing on-chain programs for seamless trade execution.

**🚀 Advanced Features: gRPC integration, Shredstream support, ZeroSlot compatibility, and offline signing capabilities for maximum performance and reliability.**

## Example Transaction

https://solscan.io/tx/5ubSXSDdCJxYcgLBtAuuRb1CZur6k8cq1TSEg3t4xTFx8a1HHHR6yNpEa5B2gbxZiACHxkYcsDHKj6MrTGoBLBVx

## On-Chain Program

https://solscan.io/account/MEViEnscUm6tsQRoGd9h6nLQaQspKj7DB2M5FwM3Xvz

## Key Features

- **Configuration Management**: Load settings from config files for easy deployment
- **Automatic Token Account Creation**: Seamlessly create Associated Token Accounts (ATA) when needed
- **Multi-RPC Transaction Broadcasting**: Send transactions through multiple RPC endpoints for enhanced reliability
- **Kamino Flashloan Integration**: Leverage flashloan capabilities for capital-efficient arbitrage
- **Comprehensive Pool Support**: Parse and interact with all major pool types (Raydium, DLMM, Whirlpool, and more)

## Supported Decentralized Exchanges

- **Pump AMM** - High-performance automated market maker
- **Raydium V4** - Advanced concentrated liquidity pools
- **Raydium CPMM** - Constant product market maker
- **Raydium CLMM** - Concentrated liquidity market maker
- **Meteora DLMM** - Dynamic liquidity market maker
- **Meteora Dynamic AMM** - Adaptive automated market maker
- **Meteora DAMM V2** - Enhanced dynamic AMM
- **Orca Whirlpool** - Concentrated liquidity pools
- **SolFi** - Solana-focused DeFi platform
- **Vertigo** - Innovative DEX protocol

## Quick Start

### Prerequisites

- **Rust & Cargo**: Latest stable version installed
- **Solana Wallet**: Configured wallet with sufficient SOL balance

### Installation & Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/wakeupwakeupwakeup/solana-arb-bot-patched
   cd Solana-Arbitrage-Bot
   ```

2. **Configure the Bot**

   ```bash
   cp config.toml.example config.toml
   # Edit config.toml with your settings
   ```

3. **Run Using Universal Launcher (Recommended)**

   ```bash
   chmod +x run.sh
   ./run.sh
   ```

   The `run.sh` script automatically detects your system architecture and runs the appropriate binary:

---

## 📦 Supported Platforms

The build script automatically detects your platform and creates optimized binaries for multiple architectures:

### 🐧 Linux Distributions

| Binary                                   | Target                     | Description                                                                                           |
| ---------------------------------------- | -------------------------- | ----------------------------------------------------------------------------------------------------- |
| `sol-arb-bot-patched_x86_64-linux-musl`  | x86_64-unknown-linux-musl  | **Universal Linux** - Compatible with most distributions (Ubuntu, Debian, CentOS, Fedora, Arch, etc.) |
| `sol-arb-bot-patched_aarch64-linux-musl` | aarch64-unknown-linux-musl | **ARM 64-bit** - For ARM-based systems (Raspberry Pi 4, ARM servers)                                  |
| `sol-arb-bot-patched_x86_64-linux-glibc` | x86_64-unknown-linux-gnu   | **Modern Linux** - For systems with glibc (Ubuntu 20+, Debian 11+, etc.)                              |

## Configuration Guide

### Bot Settings

- `compute_unit_limit`: Maximum compute units per transaction
- `process_delay`: Processing interval in milliseconds

### Trading Configuration

- `mint_config_list`: Token mint configurations
  - `mint`: Token mint address
  - `raydium_pool_list`: Raydium pool addresses
  - `meteora_damm_pool_list`: Meteora Dynamic AMM pools
  - `meteora_dlmm_pool_list`: Meteora DLMM pools
  - `meteora_damm_v2_pool_list`: Meteora DAMM V2 pools
  - `raydium_cp_pool_list`: Raydium CP pools
  - `pump_pool_list`: Pump AMM pools
  - `whirlpool_pool_list`: Orca Whirlpool addresses
  - `raydium_clmm_pool_list`: Raydium CLMM pools
  - `solfi_pool_list`: SolFi pool addresses
  - `vertigo_pool_list`: Vertigo pool addresses
  - `lookup_table_accounts`: Address lookup tables
  - `process_delay`: Processing delay in milliseconds

### Network Configuration

- `url`: Primary RPC endpoint URL

### Transaction Broadcasting

- `enabled`: Enable multi-RPC transaction broadcasting
- `sending_rpc_urls`: List of RPC endpoints for transaction sending
- `compute_unit_price`: Fixed compute unit pricing
- `max_retries`: Maximum retry attempts
- `enable_simple_send`: Enable simplified sending mode

### Wallet Configuration

- `private_key`: Wallet private key (file path or environment variable)

### Flashloan Settings

- `enabled`: Enable Kamino flashloan functionality

## Advanced Usage

### Using the Universal Launcher

The `run.sh` script provides a seamless cross-platform experience:

```bash
# Basic usage with config file
./run.sh --config config.toml
```

### Troubleshooting

If the launcher fails to find a suitable binary:

1. Ensure the `binaries/` directory contains the correct executables
2. Verify file permissions: `chmod +x binaries/*`
3. Check system architecture: `uname -m`

## Security Considerations

- Never commit private keys to version control
- Use environment variables for sensitive configuration
- Regularly update dependencies and monitor for security patches
- Test thoroughly on devnet before mainnet deployment
