# Student Futures vs ETF Option Premium Converter

## Overview

This project explores whether ETF options and futures options price probability differently after both markets are converted into a common exposure framework.

Rather than comparing raw premiums or strikes, the workbook converts futures option strikes and premiums into ETF-equivalent units. This allows direct comparison of strike distributions, premium curves, and probability reach across markets with different contract specifications.

The motivating question is:

> For the same approximate probability (delta) and equivalent underlying exposure, does the ETF market or the futures market charge more option premium?

---

## Educational Purpose

This workbook is designed as a derivatives and market microstructure education project.

Topics explored include:

- Exposure normalization
- Futures-to-ETF conversion
- Option premium comparison
- Delta-based probability analysis
- Relative value concepts
- Market structure differences between ETF and futures options

This project is intended for educational and research purposes only.

---

## Inputs

### Market Data

- ETF Spot Price
- Futures Price

Example:

```text
ETF Spot = 742.40
Futures Price = 7436.25
```

### Contract Specifications

```text
ETF Multiplier = 100
Futures Multiplier = 50
```

### Option Chain Data

For each market:

```text
Delta
Strike
Premium
```

Example delta buckets:

```text
1
5
7
10
15
20
25
30
35
40
45
```

These serve as approximate probability buckets for comparison.

---

## Core Logic

### 1. Futures-to-ETF Conversion

Futures prices and strikes are converted into ETF-equivalent units.

Formula:

```text
Futures-to-ETF Ratio
=
ETF Spot / Futures Price
```

Example:

```text
742.40 / 7436.25
=
0.10
```

This creates a common pricing framework.

---

### 2. Strike Conversion

Futures strikes are translated into ETF-equivalent strikes.

Formula:

```text
Converted Futures Strike
=
Futures Strike × Futures-to-ETF Ratio
```

Optional basis adjustments may be applied to align both products to a common reference level.

---

### 3. Exposure Normalization

Contract specifications differ between ETF and futures options.

To compare equivalent exposure:

```text
Exposure Ratio
=
(Futures Price × Futures Multiplier)
/
(ETF Price × ETF Multiplier)
```

This creates a common exposure unit for comparison.

---

### 4. Premium Conversion

Futures premiums are converted into ETF-equivalent premium units.

Formula:

```text
Equivalent Futures Premium
=
Futures Premium
/
Exposure Ratio
```

This allows comparison of premium paid for equivalent underlying exposure.

---

## Outputs

### Converted Strike Curves

Produces ETF-equivalent futures strikes.

Example:

| Delta | ETF Strike | Converted Futures Strike |
|---------|---------|---------|
| 1 | 675 | 680.275 |
| 5 | 705 | 698.275 |
| 10 | 717 | 724.275 |
| 20 | 728 | 734.275 |
| 45 | 741 | 746.775 |

---

### Equalized Premium Curves

Produces ETF-equivalent futures premiums.

```text
ETF Premium
vs
Converted Futures Premium
```

This removes distortions caused by:

- Different contract sizes
- Different underlying price scales
- Different futures multipliers

---

### Probability Reach Analysis

The workbook visualizes:

```text
X-Axis = Delta
Y-Axis = Converted Strike
```

This allows comparison of:

- Strike distribution depth
- Tail risk availability
- Probability reach
- Relative option market structure

---

## Key Questions Explored

- Are ETF options richer than futures options?
- How much premium is charged per unit of exposure?
- Do ETF and futures markets package probability differently?
- Which market offers deeper tail distributions?
- How do contract specifications affect apparent option pricing?

---

## Learning Outcomes

This project demonstrates:

- Derivatives normalization techniques
- Cross-market option comparison
- Exposure-adjusted premium analysis
- Delta-based probability interpretation
- Relative value research workflows

---

## Disclaimer

This workbook is an educational market structure project.

It simplifies many real-world factors including:

- Volatility surfaces
- Vega exposure
- Margin requirements
- Settlement mechanics
- Liquidity constraints
- Financing costs

Results should be interpreted as exploratory research and not as investment advice.
