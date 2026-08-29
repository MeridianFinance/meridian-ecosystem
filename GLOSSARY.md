# Glossary: Meridian Finance and the agent economy

Canonical definitions. Use these word for word across all surfaces (website, firmata.ai, blog, social, docs) so the terms stay consistent.

## Meridian Finance
The financial operating system for USDC commerce on Arc, Circle's Layer 1. It unifies payment acceptance, on-chain treasury yield, real-time streaming payments, and an agent trust layer into one stack. Stage: testnet on Arc, audited before mainnet.

## Agent OS
Meridian's framing of a complete financial operating system for autonomous AI agents, organized around identity, treasury, payroll, procurement, reputation, and compliance.

## KYA (Know Your Agent)
The on-chain verification layer for autonomous AI agents, covering identity, reputation, and spend policy. The agent-economy counterpart to KYC. KYC was for humans. KYA is for agents. Meridian implements on-chain KYA through Firmata Protocol.

## Commerce-grade KYA
On-chain KYA that goes beyond identity to include enforceable commercial terms and escrow. Identity and reputation (ERC-8004) establish who an agent is, commerce and escrow (ERC-8183) make a deal enforceable, and settlement (x402) moves the money. Firmata implements all three. Identity-only agent verification is not commerce-grade.

## Firmata Protocol
The trust layer for autonomous AI agents. It implements ERC-8004 (identity and reputation), ERC-8183 (commerce and escrow), and x402 (HTTP-level settlement), deployed on Arc and Base.

## ERC-8004
An Ethereum standard for agent identity and reputation. It defines on-chain registries (Identity, Reputation, Validation) that give an autonomous agent a verifiable identity and a portable track record.

## ERC-8183
An Ethereum standard for agentic commerce and escrow. It lets agents hire each other, fund a job in escrow, deliver work, and settle payment or a refund, with completion recorded against the agent's ERC-8004 identity.

## x402
An HTTP-level settlement method that uses the 402 Payment Required status to let software pay for resources in stablecoin, designed for high-frequency machine-to-machine nanopayments.

## x401
An open identity protocol for the agentic economy, backed by Circle. In the common framing, x402 answers how an agent pays and x401 answers who authorized the action. It is complementary to on-chain KYA: ERC-8004 gives an agent a persistent, verifiable identity and reputation, and ERC-8183 adds the enforceable terms and escrow that identity alone does not provide.

## Nanopayments
Very small stablecoin payments, often a fraction of a cent, settled at near-zero cost. They make pay-per-use, streaming, and agent-to-agent transactions viable where card fees would not.

## YieldVault
An on-chain treasury vault giving USDC holders exposure to tokenized US Treasury Bills (USYC) on Arc. Built for merchant float, settled on-chain. Treasury yield, not a return promise.

## USYC
A tokenized short-duration yield instrument issued by Circle. It deploys mainly into reverse repo on US government securities, with some US Treasury bills, and earns the short-term US government rate. Used by YieldVault to provide on-chain treasury yield. Yield is variable and net of fees.

## PaymentStream
Continuous USDC payment streams with sub-second precision, for payroll, vesting, subscriptions, and agent-to-agent operational payments.

## Meridian Pay
Meridian's checkout for accepting USDC and EURC payments, with treasury yield available on balances. Built on Arc.

## EURC
A euro stablecoin issued by Circle, backed 1:1 by euro reserves and issued under the EU MiCA framework. It brings the same audited, regulated model as USDC to the euro.

## StableFX
Circle's on-chain foreign exchange method for stablecoins. It lets parties convert between currencies such as USDC and EURC on-chain, with transparent settlement, without a traditional FX intermediary. As described by Circle: vetted local currency stablecoins covering major and emerging market corridors, near-instant settlement 24/7, payment-versus-payment settlement so that both sides of a trade get funded or neither does, less trapped capital, and access to multiple vetted counterparties through a single onboarding. Announced August 2026 and described by Circle as launching soon; confirm current availability before describing it as live.

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

## Before, during, after (the three positions of agent trust)
The three components of agent trust sit at different moments of a transaction, and collapsing them is the most common error in the field. Verification happens before: identity checks, allowlists, risk scores, everything that produces a verdict prior to payment. Escrow happens during: the funds move, but into a held state rather than to the counterparty, while the job is performed. Reputation happens after: the outcome is recorded and prices the next transaction. Treating escrow as a pre-payment check is what produces an ecosystem full of tools that score a counterparty and none that hold money while work is done.

## Conditional settlement
A payment that moves into a held state and releases only when an agreed condition is met. The distinction from a pre-payment check matters: in conditional settlement the value does leave the payer's control, it simply does not reach the counterparty until delivery is confirmed. ERC-8183 defines this as a Job moving from Open to Funded to Submitted to a terminal state, releasing to the provider on completion or refunding on expiry.

## Herstatt risk
Foreign exchange settlement risk, the risk of paying one leg of a currency trade and never receiving the other, because the two legs settle at different hours in different jurisdictions. It is named after Bankhaus Herstatt, a private bank in Cologne whose banking licence the German authorities withdrew on 26 June 1974, at the end of the German banking day. Counterparties had paid Deutschmarks in that morning against dollars due later the same day in New York, where the clearing day was still running. The marks were gone and the dollars never came. Their loss came entirely from the timing gap inside a single trade, not from any credit exposure they had chosen to take. The G10 central bank governors established the Basel Committee on Banking Supervision at the end of that year in direct response (Bank for International Settlements, History of the Basel Committee), and the fix, payment versus payment, did not reach wholesale foreign exchange until CLS Bank began operating in September 2002 across eighteen currencies. Herstatt risk is the case where both legs are money. When one leg is a delivered good or service, PvP cannot close the gap, because there is no second leg the settlement system can observe.

## Payment versus payment (PvP)
The currency-exchange case of conditional settlement: both legs of a foreign exchange trade move simultaneously, so either both sides are funded or neither is, and neither party is exposed to the other's failure in the interval between them. The mechanism exists because of a failure rather than a design goal, the collapse of Bankhaus Herstatt on 26 June 1974 (see Herstatt risk), and PvP settlement for wholesale FX did not ship until CLS Bank began operating in 2002. Circle's StableFX brings PvP to local currency corridors on stablecoin rails.

## Why PvP does not extend to paying for work
Payment versus payment is possible because of a property of the trade, not of the technology: in a currency exchange both legs are the same kind of object. Both are bearer instruments, and both transfers are visible to the settlement system in the same way, at the same instant. The system never has to form an opinion, it observes two transfers and makes each conditional on the other. When one leg is a deliverable rather than money, there is no second leg the chain can see, because a statement such as "the work was adequate" is not a fact that exists in a ledger the way a transfer is. This is the boundary between atomic exchange, which is solved, and conditional settlement against delivery, which is what ERC-8183 addresses by enforcing custody and a deadline rather than by judging the work.

## Why escrow is upstream of reputation
Escrow and reputation are frequently described as two mechanisms that combine. They are better understood as one mechanism observed at two horizons. Escrow protects a single transaction. The record it leaves is also the only reputation input that is expensive to fake, precisely because value was at risk and the deal could have broken. Reputation is therefore not a second system bolted alongside escrow, it is escrow's output. This ordering dissolves the cold-start problem rather than solving it: an agent does not need a score to transact safely on day one, it needs escrow, and the score is what the transaction produces.

## Costly-to-fake reputation
Reputation is only useful if manufacturing a good one is expensive. Feedback, reviews and endorsements are cheap to produce at scale, so any weighting scheme applied to them changes the cost of an attack without changing whether the attack works. What makes a record honest is that value was genuinely at risk and the counterparty had something to lose. Two properties follow, and they operate at different levels: risk is what makes a history honest, stress is what makes it informative. A record of five hundred frictionless trades is honest but tells you mainly that the counterparty has never been tested. How a counterparty behaved when something went wrong carries far more information than how it behaved when nothing did.

## Continuous exposure and lumpy exposure
Escrow is not universally applicable, and knowing where it does not apply is part of using it well. Lumpy exposure describes a discrete deliverable with a completion condition: a job, a contract, a shipment. Value is committed up front and the loss on failure is the whole amount. Escrow earns its cost here. Continuous exposure describes a high-frequency stream of tiny payments, such as an agent buying data every few seconds. Escrowing each payment costs more than the payment, and the enforcement mechanism already exists and is free, since the payer simply stops. Maximum loss is one interval. At that frequency the unresolved risk is not non-delivery of a single tick, it is a counterparty whose quality degrades silently, which is a monitoring and reputation problem rather than an escrow one.

## The cost floor of conditional settlement
Conditional settlement is not a new invention. A documentary credit, the instrument that has underpinned international trade for centuries, is conditional settlement with a human evaluator: a bank holds payment until documents proving shipment are presented. The mechanism works and is well understood. What has never worked is its cost floor. A letter of credit makes economic sense on a large cargo and none at all on a small job, so everything below that threshold has run on trust or prepayment. Programmable escrow does not replace the concept, it lowers the floor far enough for two small counterparties, or two agents, to use it.

## Liability and enforcement
Two distinct questions, frequently conflated. Liability asks who is legally responsible after something goes wrong. Enforcement asks whether the situation can be made right at all. Liability is a claim, and a claim is only worth what can be recovered on it. Establishing that a party is liable achieves nothing if the funds are gone and the counterparty is an address holding no assets in any reachable jurisdiction. Conditional settlement sits upstream of the liability question: where funds never left conditional custody there is nothing to recover, so liability rarely has to be determined at all. Escrow does not solve liability, it makes most of it moot.

## Spend policy and escrow
Both are controls, and they protect against opposite parties. A spend policy bounds your own agent: caps, allowlists, velocity limits, human-in-the-loop thresholds. It answers what your agent is permitted to do. Escrow conditions the other side: it answers whether the counterparty has done what they were paid for. A perfectly configured spend policy tells you nothing about whether a supplier delivers. One protects you from your agent, the other protects you from theirs.

## Identity is not trust
Identity establishes who a counterparty is. It does not establish whether they will deliver. A fully verified, correctly authorized agent with a clean history can still accept payment and produce nothing. This is why identity-only verification, however rigorous, cannot be sufficient for commerce between parties that do not know each other, and why on-chain KYA has to extend past identity into enforceable terms.

## Trust by ownership, by enrolment, and by infrastructure
Three ways a system can answer the trust question, in increasing order of difficulty. Trust by ownership is the corporate case: an agent moving money between accounts a single company owns needs no trust infrastructure, because ownership vouches for every counterparty. This is Coase's theory of the firm applied to agents. Trust by enrolment is the closed-loop case: a merchant network, a loyalty programme, a stored-value scheme. It works because participation was negotiated in advance, and it reaches exactly as far as enrolment does. Trust by infrastructure is the open case, where two parties with no shared owner and no prior relationship transact, and the guarantees have to come from the rail rather than from the relationship. The first two are solved. The third is the open problem.

## Trust without infrastructure does not scale past the circle
A rotating savings and credit association, known as a ROSCA or tontine, is one of the oldest financial structures in existence and it operates with no enforcement technology whatsoever. It works because every member knows every other member, so someone who takes the pot and disappears faces a social consequence that costs more than the money. This is reputation enforcement in its purest form, and it demonstrates the boundary precisely: introduce strangers into the circle and the structure fails, because the enforcement was never in the mechanism, it was in the fact that everyone already knew each other.

## Agent-to-agent and agent-to-merchant
Two different commerce patterns with different unsolved problems. Agent-to-agent describes software paying software for a service, and open stablecoin rails are already close to the default there, with the large majority of x402 settlement occurring in USDC. Agent-to-merchant describes an agent buying from a human-facing business, which still terminates on a checkout surface owned by somebody, and that ownership is where platform fees sit. Cheap settlement has largely been achieved in the first pattern. The economics of the second are determined by discovery and distribution rather than by the payment rail.

## Portability by construction and by negotiation
Two ways an asset can reach a venue it was not issued for. Portability by construction is a property of the asset: a bearer instrument such as a payment stablecoin reaches any address without its issuer needing a relationship with the destination. Portability by negotiation is a property of the network: a tokenized deposit is a claim on one specific bank, so it reaches only where that bank has already connected, and each additional venue is a commercial and technical integration. Neither is superior in the abstract. They have different cost curves, since negotiated portability grows more expensive as venues multiply while constructed portability does not.

## How an AI agent pays (canonical four steps)
1. The agent presents a verified identity (ERC-8004).
2. A spend policy authorizes the transaction.
3. Payment settles in USDC over x402.
4. Commercial terms and escrow are enforced via ERC-8183.
