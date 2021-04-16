---
description: ShrimpSwap's Contracts
---

# Contracts

Our contracts are publicly accessible in the following repo [github.com/shrimpswap/shrimp-contracts](https://github.com/shrimpswap/shrimp-contracts)

- **SHRIMP:** [TODO](https://bscscan.com/address/TODO)
- **MasterShrimp:** [TODO](https://bscscan.com/address/TODO)
- **Timelock:** [TODO](https://bscscan.com/address/TODO) (delay: 24h)

**How are our contracts safe?**

We have based our implementation in Goose Finance's EGG token and have the following features:

- **24h** timelock added to contract at launch;
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
