# metacrafters
### Overview
The MyToken contract is a simple implementation of a basic ERC-20 token with functionalities to mint and burn tokens.
### Features
**Token Details**: Public variables store the token name, symbol, and total supply. <br/> 
**Address Balances**: A mapping of addresses to balances. <br/> 
**Mint Function**: Increases the total supply and the balance of a specified address. <br/> 
**Burn Function**: Decreases the total supply and the balance of a specified address, with a balance check. <br/> 

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public name = "mani";
    string public symbol = "MN";
    uint256 public totalSupply = 0;

    // Mapping of address to balance
    mapping(address => uint256) public balances;

    // Mint function
    function mint(address _to, uint256 _amount) public {
        balances[_to] += _amount;
        totalSupply += _amount;
    }

    // Burn function
    function burn(address _from, uint256 _amount) public {
        require(balances[_from] >= _amount, "Insufficient balance to burn");
        balances[_from] -= _amount;
        totalSupply -= _amount;
    }
}

```
