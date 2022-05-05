

## DS Test

```solidity
    function assertApproxEq(
        int256 a,
        int256 b,
        uint256 maxDelta
    ) internal virtual {
        int256 delta = a > b ? a - b : b - a;

        if (delta > int256(maxDelta)) {
            emit log("Error: a ~= b not satisfied [uint]");
            emit log_named_int("  Expected", b);
            emit log_named_int("    Actual", a);
            emit log_named_uint(" Max Delta", maxDelta);
            emit log_named_int("     Delta", delta);
            fail();
        }
    }
```