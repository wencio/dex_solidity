### Decentralized Exchange (DEX) Contract

This Solidity contract implements a simple decentralized exchange (DEX) on the Ethereum blockchain. The DEX allows users to trade ERC20 tokens with each other using limit and market orders.

#### Contract Details

- **Solidity Version**: 0.6.3

#### Features

1. **Token Management**:
   - Allows the addition of ERC20 tokens to the exchange.
   - Supports deposit and withdrawal of tokens.

2. **Order Management**:
   - Facilitates the creation of limit orders to buy or sell tokens at a specified price.
   - Enables the creation of market orders to buy or sell tokens at the best available price.

#### Contract Structure

- **Enums**:
  - `Side`: Enumerates the types of orders (BUY or SELL).

- **Structs**:
  - `Token`: Represents an ERC20 token with a ticker symbol and contract address.
  - `Order`: Represents an order placed by a trader, including details such as order ID, trader address, side (BUY or SELL), ticker, amount, filled amount, price, and date.

- **Mappings**:
  - `tokens`: Maps ticker symbols to Token structs.
  - `traderBalances`: Maps trader addresses to token balances.
  - `orderBook`: Maps tickers and order sides to arrays of Order structs.

- **Variables**:
  - `admin`: Address of the contract administrator.
  - `nextOrderId`: Counter for generating unique order IDs.
  - `nextTradeId`: Counter for generating unique trade IDs.
  - `tokenList`: Array containing the list of supported token tickers.
  - `DAI`: Constant representing the ticker symbol for DAI token.

- **Events**:
  - `NewTrade`: Triggered when a trade occurs between two traders.

#### Usage

1. **Adding Tokens**: Use the `addToken` function to add ERC20 tokens to the exchange by providing the token's ticker symbol and contract address.

2. **Depositing and Withdrawing Tokens**: Users can deposit and withdraw tokens using the `deposit` and `withdraw` functions, respectively.

3. **Creating Orders**:
   - Use `createLimitOrder` to place limit orders to buy or sell tokens at a specified price.
   - Use `createMarketOrder` to place market orders to buy or sell tokens at the best available price.

4. **Trade Execution**: Orders are matched and trades are executed automatically when market orders are placed.

#### Usage Restrictions

- The contract restricts trading of DAI tokens to prevent trading DAI directly.

#### Additional Notes

- This contract is designed to be deployed on the Ethereum blockchain.
- It utilizes OpenZeppelin's ERC20 interface for interacting with ERC20 tokens.
- User authentication and authorization are not implemented in this contract.

#### Contract Source

The Solidity contract source code is available in the provided file.

#### Disclaimer

This contract is provided for educational and demonstration purposes only. Use caution when interacting with smart contracts on the blockchain, as they are immutable and irreversible once deployed.
