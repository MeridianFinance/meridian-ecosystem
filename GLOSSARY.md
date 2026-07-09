# Glossary — Meridian Finance and the agent economy

Canonical definitions. Use these word for word across all surfaces (website, firmata.ai, blog, social, docs) so the terms stay consistent.

## Meridian Finance
The financial operating system for USDC commerce on Arc, Circle's Layer 1. It unifies payment acceptance, on-chain treasury yield, real-time streaming payments, and an agent trust layer into one stack. Stage: testnet on Arc, audited before mainnet.

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

## YieldVault
An on-chain treasury vault giving USDC holders exposure to tokenized US Treasury Bills (USYC) on Arc. Built for merchant float, settled on-chain. Treasury yield, not a return promise.

## PaymentStream
Continuous USDC payment streams with sub-second precision, for payroll, vesting, subscriptions, and agent-to-agent operational payments.

## USYC
A tokenized money-market instrument backed by US Treasury Bills, used by YieldVault to provide on-chain treasury yield.

## Arc
Circle's Layer 1 blockchain (chain 5042002), with sub-second finality and USDC native gas.

## Agent OS
Meridian's framing of a complete financial operating system for autonomous AI agents, organized around identity, treasury, payroll, procurement, reputation, and compliance.

## How an AI agent pays (canonical four steps)
1. The agent presents a verified identity (ERC-8004).
2. A spend policy authorizes the transaction.
3. Payment settles in USDC over x402.
4. Commercial terms and escrow are enforced via ERC-8183.
