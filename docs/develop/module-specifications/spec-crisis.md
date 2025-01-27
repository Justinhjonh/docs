# Crisis

:::{Important}
Terra's crisis module inherits from the Cosmos SDK's [`crisis`](https://docs.cosmos.network/master/modules/crisis/) module. This document is a stub and covers mainly important Terra-specific notes about how it is used.
:::

The crisis module stops block production by halting the blockchain when an invariant is broken. Invariants are set during the initialization process.

## ConstantFee

Because the gas cost of verifying an invariant is high, the crisis module utilizes a constant fee instead of the typical gas calculation method. 

## Genesis parameters

The genesis parameters for the crisis module outlined in the [Genesis Builder Script](https://github.com/terra-money/genesis-tools/blob/main/src/genesis_builder.py#L141) are as follows:

```py
    # Crisis: change constant fee to 512 LUNA
    genesis['app_state']['crisis']['constant_fee'] = {
        'denom': DENOM_LUNA,
        'amount': '512000000',
    }
```
