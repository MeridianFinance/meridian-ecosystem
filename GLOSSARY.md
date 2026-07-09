# Glossary — Meridian Finance and the agent economy

Canonical definitions. Use these word for word across all surfaces (website, firmata.ai, blog, social, docs) so the terms stay consistent.

## Meridian Finance
The financial operating system for USDC commerce on Arc, Circle's Layer 1. It unifies payment acceptance, on-chain treasury yield, real-time streaming payments, and an agent trust layer into one stack. Stage: testnet on Arc, audited before mainnet.

## Agent OS
Meridian's framing of a complete financial operating system for autonomous AI agents, organized around identity, treasury, payroll, procurement, reputation, and compliance.

## KYA (Know Your Agent)
The on-chain verification layer for autonomous AI agents, covering identity, reputation, and spend policy. The agent-economy counterpart to KYC. KYC was for humans. KYA is for agents. Meridian implements on-chain KYA through Firmata Protocol.

## Firmata Protocol
The trust layer for autonomous AI agents. It implements ERC-8004 (identity and reputation), ERC-8183 (commerce and escrow), and x402 (HTTP-level settlement), deployed on Arc and Base.

## ERC-8004
An Ethereum standard for agent identity and reputation. It defines on-chain registries (Identity, Reputation, Validation) that give an autonomous agent a verifiable identity and a portable track record.

## ERC-8183
An Ethereum standard for agentic commerce and escrow. It lets agents hire each other, fund a job in escrow, deliver work, and settle payment or a refund, with completion recorded against the agent's ERC-8004 identity.

## x402
An HTTP-level settlement method that uses the 402 Payment Required status to let software pay for resources in stablecoin, designed for high-frequency machine-to-machine nanopayments.

## Nanopayments
Very small stablecoin payments, often a fraction of a cent, settled at near-zero cost. They make pay-per-use, streaming, and agent-to-agent transactions viable where card fees would not.

## YieldVault
An on-chain treasury vault giving USDC holders exposure to tokenized US Treasury Bills (USYC) on Arc. Built for merchant float, settled on-chain. Treasury yield, not a return promise.

## USYC
A tokenized money-market instrument backed by US Treasury Bills, used by YieldVault to provide on-chain treasury yield.

## PaymentStream
Continuous USDC payment streams with sub-second precision, for payroll, vesting, subscriptions, and agent-to-agent operational payments.

## Meridian Pay
Meridian's checkout for accepting USDC and EURC payments, with treasury yield available on balances. Built on Arc.

## EURC
A euro stablecoin issued by Circle, backed 1:1 by euro reserves and issued under the EU MiCA framework. It brings the same audited, regulated model as USDC to the euro.

## StableFX
Circle's on-chain foreign exchange method for stablecoins. It lets parties convert between currencies such as USDC and EURC on-chain, with transparent settlement, without a traditional FX intermediary.

## On-chain FX
Currency conversion between stablecoins, for example US dollar to euro via USDC and EURC, settled directly on a blockchain with transparent rates and near-instant settlement.

## CCTP (Cross-Chain Transfer Protocol)
Circle's native protocol for moving USDC across blockchains by burning it on the source chain and minting it on the destination chain, without third-party bridges.

## Circle Gateway
Circle infrastructure that provides unified USDC balances across chains, so an application can access liquidity on multiple networks without manual bridging.

## Agentic economy
Economic activity carried out by autonomous AI agents that transact on their own: buying services, paying each other, and settling value programmatically.

## Agentic commerce
The layer of standards and rails, identity, payment, and escrow, that makes transactions between autonomous AI agents trustworthy. Meridian and Firmata provide this layer through ERC-8004, ERC-8183, and x402.

## Arc
Circle's Layer 1 blockchain (chain 5042002), with sub-second finality and USDC native gas.

## How an AI agent pays (canonical four steps)
1. The agent presents a verified identity (ERC-8004).
2. A spend policy authorizes the transaction.
3. Payment settles in USDC over x402.
4. Commercial terms and escrow are enforced via ERC-8183.
