---
description: ShrimpSwap's Contracts
---

# Contracts

Our contracts are publicly accessible in the following repo [github.com/shrimpswap/shrimp-contracts](https://github.com/shrimpswap/shrimp-contracts)

- **SHRIMP:** [0x62ee12e4fe74a815302750913c3c796bca23e40e](https://bscscan.com/address/0x62ee12e4fe74a815302750913c3c796bca23e40e)
- **MasterShrimp:** [0xABEE2aaF12E92384274D61d0dbd31bD7Fc35f38c](https://bscscan.com/address/0xABEE2aaF12E92384274D61d0dbd31bD7Fc35f38c)
- **Timelock:** [0xa6835d6b0e3760e32458d3a8c0e59c96c921fbb9](https://bscscan.com/address/0xa6835d6b0e3760e32458d3a8c0e59c96c921fbb9) (delay: 12h)

## V2
- **WHALE:** [0x93662179C3590D4dA42858ABE917C10542a40831](https://bscscan.com/address/0x93662179C3590D4dA42858ABE917C10542a40831)
- **MasterWhale:** [0x709Fb31315ce6DE514C7991CCAAeF8B63ABBb77e](https://bscscan.com/address/0x709Fb31315ce6DE514C7991CCAAeF8B63ABBb77e)

**How are our contracts safe?**

We have based our implementation in Goose Finance's EGG token and have the following features:

- **12h** timelock added to contract at launch;
- No migrator code, it was totally removed;
- Contract audit in the pipeline.

**Removed migratator code**

Removed from PancakeSwap's [MasterChef.sol](https://github.com/pancakeswap/pancake-farm/blob/master/contracts/MasterChef.sol)

```javascript
// Set the migrator contract. Can only be called by the owner.
function setMigrator(IMigratorChef _migrator) public onlyOwner {
    migrator = _migrator;
}

// Migrate lp token to another lp contract. Can be called by anyone. We trust that migrator contract is good.
function migrate(uint256 _pid) public {
    require(address(migrator) != address(0), "migrate: no migrator");
    PoolInfo storage pool = poolInfo[_pid];
    IBEP20 lpToken = pool.lpToken;
    uint256 bal = lpToken.balanceOf(address(this));
    lpToken.safeApprove(address(migrator), bal);
    IBEP20 newLpToken = migrator.migrate(lpToken);
    require(bal == newLpToken.balanceOf(address(this)), "migrate: bad");
    pool.lpToken = newLpToken;
}
```

**Diff EGG's MasterChef vs SHRIMP's MasterShrimp**

Please refer to the following diffchecker: [diffchecker.com/TODO](https://www.diffchecker.com/TODO)
