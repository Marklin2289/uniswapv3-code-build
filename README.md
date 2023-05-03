# Uniswap V3 smart contract learning and rebuild

- using solidity and foundry testing

# tips:

- Foundry package install rari-capital/solmate (no @)
  or npm i @rari-capital/solmate

# Core Contracts:

- Permissionless access
- Permissionless operation
- The ability to exchange tokens

  - architectural standpoint: Contract Factory

    - Any user should be able to interact with any pool
    - Any user should be able to perform liquidity management operations on pools
    - Pools should operate indefinitely without requiring centralized inputs
    - Any user should be able to trustlessly create new pools

  - Contract factory : deploy copies of its code payload as new smart contracts. In the case of Uniswap V3, the factory’s job is to deploy shiny new Uniswap V3 pools.

  - Using a factory pattern ensures that:

    - The source code is the same for all pools
    - Each pool behaves exactly the same as any other
    - Each pool can be interacted with in exactly the same way
    - One and only one pool exists for each allowable combination

      ![plot](./asset/image-37.png)

# Core Contracts: The Pool Deployer

This contract gives a very simple and easy way to deploy new pools with a single high-level function call.
![plot](./asset/image-38.png)
