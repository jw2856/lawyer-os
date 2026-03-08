# Payments & Money Transmission

## Key Concepts

### Money Transmission
- The act of receiving money for transmission or transmitting money — regulated activity
- Distinction between money transmission and payment processing is critical and jurisdiction-specific
- Regulatory classification of each party matters for agreement structure

### Settlement Mechanisms
- **BTC/Lightning**: Near-instant settlement (< 3 minutes)
- **Stablecoins (USDC, USDT)**: Blockchain-based settlement, varies by chain
- **SEPA/SWIFT**: Traditional EUR bank rails
- **ACH/RTP**: US domestic rails (ACH = batch, RTP = real-time)
- Settlement finality varies by mechanism and has contractual implications

### Fund Segregation
- Regulatory requirement for money transmitters to hold customer funds separate from corporate funds
- Failure to segregate is typically a material breach and regulatory violation

### Fee Models
- **Per-transaction**: Aligns incentives with volume. Standard for payment partnerships.
- **Monthly subscription + minimums**: Creates fixed cost exposure regardless of volume.
- **Platform fee offset**: Fixed fee reduced by transaction-based fees.
- **Tiered pricing**: Volume-based discounts.

## Common Contract Issues in Payments
- **Settlement timing and risk**: Who bears the risk during the settlement window?
- **FX exposure**: When does the rate lock? Who bears currency fluctuation risk?
- **Refund denomination**: In original currency, settlement currency, or at what rate?
- **Network fee fluctuations**: Who absorbs fee spikes (especially for crypto networks)?
- **Compliance responsibility allocation**: Who performs KYC? Who monitors transactions? Who files SARs?
- **Liquidity requirements**: Pre-funding, collateral, loss reserves
- **Insurance**: Payment-related insurance requirements

## Regulatory Landscape

### United States
- **Federal**: FinCEN MSB registration, BSA/AML compliance
- **State**: Money transmitter licenses required state-by-state (varies significantly)
- **Federal banking agencies**: OCC, FDIC guidance on crypto-related activities

### European Economic Area
- **MiCA**: Markets in Crypto-Assets Regulation
- **PSD2**: Payment Services Directive
- **Country-specific**: Each EU member state may have additional requirements

### Other Key Jurisdictions
- **Mexico**: IFPE (Institución de Fondos de Pago Electrónico)
- **Singapore**: MAS licensing (Major/Standard Payment Institution)
- **Canada**: FINTRAC MSB licensing
- **Africa**: Country-by-country regulation varies widely
- **UK**: FCA regulation, separate from EU post-Brexit

[To be expanded with specific jurisdiction details as needed]
