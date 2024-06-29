# MyToken
---
## Overview

MyToken is a custom ERC20 token built using the OpenZeppelin library. It includes features such as minting, burning, and transferring tokens, with certain functions restricted to the contract owner.

## Features

- **Minting**: Only the contract owner can mint new tokens.
- **Burning**: Any token holder can burn their own tokens.
- **Transferring**: Token holders can transfer tokens to other addresses.

## Prerequisites

- Solidity ^0.8.0
- OpenZeppelin Contracts library


    ```

## Usage

### Deploying the Contract

1. **Compile the contract**:
    Use your preferred Solidity compiler or IDE (e.g., Remix, Truffle).

2. **Deploy the contract**:
    Deploy `MyToken.sol` to your desired Ethereum network.

### Interacting with the Contract

#### Minting Tokens

Only the contract owner can mint new tokens.

```solidity
function mint(address account, uint256 amount) public onlyOwner {
    _mint(account, amount);
}
```

#### Burning Tokens

Any token holder can burn their own tokens.

```solidity
function burn(uint256 amount) public {
    _burn(msg.sender, amount);
}
```

#### Transferring Tokens

Token holders can transfer tokens to other addresses.

```solidity
function transfer(address recipient, uint256 amount) public override returns (bool) {
    _transfer(msg.sender, recipient, amount);
    return true;
}
```

