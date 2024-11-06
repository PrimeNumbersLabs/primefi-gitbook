# Maximum APR by asset

### Maximum APR by asset

<figure><img src="../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

On the Markets Page, users have the ability to assess the Maximum pLP Locking APR. Additionally, there is an asset breakdown modal that provides a detailed view of the APR for each specific asset.

<figure><img src="../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

#### Maximum Lock APR:

This is determined as the highest APR achievable when pLP is locked for a one-year period.

**Formula:**

`1-month lock APR * 1-year lock multiplier (25x)`

#### 1-Month Locking APR:

This represents the current APR for locking your pLP tokens for a one-month period.

**Formula:**

`(Total 1 Month Lockers’ Share of Annualized Protocol Fees) / (Total 1 Month Lockers’ Share of pLP Pool Size)`

#### 1 Month Locker Share of Protocol Fees:

**Formula:**

`(1 Month Locker Share of Protocol Power) / (Total Protocol Locking Power)`

#### Total Protocol Locking Power:

This is the sum of all lockers’ shares, each adjusted by its respective multiplier.

```
= (1 Month Lockers' Share of pLP Pool Size * 1 Month Locker Multiplier (1x)) 
+ (3 Month Lockers’ Share of pLP Pool Size * 3 Month Locker Multiplier (4x))
+ (6 Month Lockers’ Share of pLP Pool Size * 6 Month Lockers’ Multiplier (10x))
+ (12 Month Lockers' Share of pLP Pool Size * 12 Month Locker Multiplier)
```
