# Genesis collector review | 20 November 2026

Keep the first collector purchase in euros. Issue the artwork, license and numbered certificate through the customer library. A purchase test, internal order or simulated receipt does not meet the prerequisite for considering an on-chain right. [Genesis work item](https://github.com/Arcanea-Labs/arcanea-ai-app/issues/759)

The owner placed collection contracts, the marketplace and Solana rewards on hold. After a real fiat book sale, a print or adaptation license can enter review on Story with a human signer and recorded gas, custody or legal costs. The rail is `on-chain-right`, and the right must be a `license` or `royalty-split`. The referenced Agentic Income enforcement branch is described as unmerged. Keep all financial actions subject to explicit separate authorization. [Product decision](https://github.com/Arcanea-Labs/arcanea-onchain/issues/3) · [Story architecture](https://docs.story.foundation/developers/smart-contracts-guide/overview)

The existing `ArcaneaNFT` demonstrates technically why product language needs review. Its administrator can adjust supply, change metadata and set royalties. A bounded initial constructor value does not establish permanently fixed scarcity. Base supports ordinary ERC-721 and both OpenSea and Rarible support Base, but marketplace compatibility confers neither approval nor a listing. MiCA classification turns on the actual underlying rights and fungibility. Dutch counsel and the rights owner must review the actual proposed grant. [Contract source](../contracts/evm/src/ArcaneaNFT.sol) · [OpenSea](https://learn.opensea.io/learn/blockchain/blockchains-compatible-with-opensea) · [Rarible](https://docs.rarible.org/docs/supported-chains) · [MiCA recitals 10–11](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32023R1114)

The Foundry regression exercises the existing contract locally after an administrator pauses it. It calls the authorized paid batch-mint entry point with the required value in the local test VM. The call reverts and leaves serial count, buyer balance and contract proceeds unchanged. This tests the implementation of the pause. The release hold remains an operating decision independent of contract state. No changes to contracts, deploy scripts or customer purchase flows are required.

Run from `contracts/evm` with the repository's pinned submodules and compiler:

```sh
forge test --match-test test_PauseRejectsBatchWithoutAllocatingSerialsOrCollectingPayment -vv
```
