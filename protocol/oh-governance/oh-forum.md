---
description: Protocol Proposer
---

# Oh! Forum

The `OhForum` contract acts as the Proposer in the Proposer-Executor model. The Forum keeps a record of all user proposals and votes. User votes are tallied by finding the amount of Oh! Finance Tokens delegated to the user at the proposal's starting block.

## Parameters

* `quorumVotes` - **4,000,000 OH** - Minimum votes required for a proposal to be considered valid
* `proposalThreshold` - **1,000,000** **OH** - Minimum amount of tokens required to make a proposal
* `votingDelay` - **1** - Time period in blocks that must pass before a proposal can be voted on
* `votingPeriod` - **17280 \(~3 days\)** - _\*\*_Time period in blocks that a proposal can be voted on
* `maxOperations` - **10** - Maximum amount of functions that be included in each proposal

## Proposals

Proposals are a set of on-chain functions that modify the Oh! Finance protocol. These proposals could contain instructions to add contracts for a new Yield Index to the protocol, change protocol parameters, or upgrade a proxy contract.

## Voting Phases

Once a proposal has been made, it enters into a review phase where voting is not yet allowed, the `votingDelay`. As soon as the review phase ends, delegated users can cast votes during the voting phase, the `votingPeriod`. If quorum has been met and the proposal has a majority passing votes, then the proposal can be queued up for execution on the Oh! Governor.

