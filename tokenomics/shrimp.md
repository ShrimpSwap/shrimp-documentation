---
description: A perpetual deflationary token
---

# SHRIMP

![SHRIMP Logo](../.gitbook/assets/shrimp.svg)

**Token:** SHRIMP

- **SHRIMP:** [0x62ee12e4fe74a815302750913c3c796bca23e40e](https://bscscan.com/address/0x62ee12e4fe74a815302750913c3c796bca23e40e)
- **MasterShrimp:** [TODO](https://bscscan.com/address/TODO)
- **Timelock:** [TODO](https://bscscan.com/address/TODO) (delay: 12h)

**Chain:** Binance Smart Chain \(BEP-20\)

**Tokenomics**

- **MAX Supply** - There will be a max of 21M SHRIMP tokens.
- **IDO distribution** - 2.1M SHRIMP allocated for the IDO. 1.05M sold to IDO participants, 1.05M added as liquidity. Non sold tokens will be burned.
- **Distribution** - 18,9M SHRIMP to farmers during 60 days
- **Reward per block** - 21.875 SHRIMP at blockStart, decreases every block during 60 days ([read more](deflationary-token.md))
- **Farming Fees**

ShrimpSwap collects a decreasing deposit fee, starting at just 3% and decreasing each block to reach 0% at the end of the 60 day period. Here is how the fee will be used:
| Fee | Purpose |
------|-----------
| 1%  | Stays on the deployer wallet (0x1076CFA6ADd884F3fd3B3003FfC5941f97c8978B) to be used for: <br> - Audit <br> - Marketing activities such as paid AMAs, paid marketing influencers, etc. <br> - Moderator compensation; <br> - Launchpools; <br> - Listing on Exchanges;|
| 0.5% | Buyback SHRIMP and burn 🔥 (0x7b5715BDaf8b9C4407d974657bFa1eb0f03f255e) |
| 1.5% | Product Research and Development 💻 (0x430c2c5314d2e1C7289211C1Ed5afC1ad107dE9e) <br> - Designers, developers, servers, domains, among other operational costs.|

**Time lock**

We will be adding a timelock contract as the owner of the MasterShrimp. The timelock will be activated with a **12h delay**, this should give you enough time to validate any of our transactions.

## Unsold Tokens

Due to the nature of our deflationary reward, the more you harvest the more rewards you will receive. Slow farmers in other hand will receive less rewards.
For this reason, some SHRIMP might never be distributed to the farmers. If any SHRIMP remains in the farming contract after the farming is over we will burn all it!
