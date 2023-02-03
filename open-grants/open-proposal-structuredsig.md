# Open Grant Proposal: *StructuredSig*, Structured Multisig for Filecoin

- **Name of Project:** *StructuredSig*
- **Proposal Category:** `app-dev`
- **Proposer:** `fare`
- **Do you agree to open source all work you do on behalf of this RFP and dual-license under MIT and APACHE2 licenses?:** Yes

## Project Description

We propose to port to the Filecoin ecosystem our enterprise-ready multisig solution *StructuredSig.*

*StructuredSig* provides a way for a company to define multisig policies in structured way. A policy might look like the below:

- “One of these two hundred agent must sign.
- Two of these ten reviewers must also sign.
- One of these three VPs must sign for amounts larger than 10,000 dollars.
- The automated policy enforcement and logging system must sign, too.
- Alternatively to all the above, the recovery key must sign.”

Furthermore, unlike its many competitors, *StructuredSig* produces compact fixed-size signatures that can be efficiently checked by a blockchain, and is totally opaque to people outside the company, who can learn nothing about the structure of the signature. By contrast, existing multisig solutions based on counting signatures require the entire structure of the multisig to be revealed to attackers, giving them a plan of attack, in addition to being expensive to use or update on a blockchain.

Finally, unlike its many competitors, *StructuredSig* comes with a policy enforcement and logging system that ensures that every transaction signed leaves an auditable trail for accounting, regulatory, disciplinary or forensic purposes. Existing multisig solutions lack such capability and thereby present a huge legal liability.

*StructuredSig* is currently a product under development. There is a prototype working on the Ethereum blockchain, but we haven’t yet launched a product ready to use by end-users.

## Value

The technical capabilities of *StructuredSig* make it ideally fit for use in corporations of all size, from the single-person operation to the multinational conglomerate:

- The multisig operations of *StructuredSig* are “opaque from the outside, transparent from the inside”.
    - Our “opaque from the outside” property vastly reduces the attack surface by which outside adversaries might hack the system, compared to competing products. It can vastly reduce blockchain fees.
    - Our “transparent from the inside” property vastly reduces risks with respect to accounting accuracy, legal compliance, or insider attacks or mistakes, compared to competing products.
- The multisig validation policy of *StructuredSig* is programmable, which allows the system to fit the varying needs of organizations of any size.
    - Large corporations can notably avoid *key man risk* whereby the betrayal, hacking or death of a single employee could cause funds to be stolen or lost.
    - Even small corporations can benefit from the discipline enforced by our policy and logging system, notably with respect to accounting, compliance and avoiding costly mistakes.
- The operation of *StructuredSig* remains decentralized, wherein each participant is the sole custodian of his cryptographic keys. And yet multisig policies allow for fail-safe redundancy in case any participant leaves, defects, becomes incapacitated, loses their keys, etc.

All in all, *StructuredSig* is a game changer technology that enables organizations of any size to safely handle custody of tokens issued by decentralized networks.

By funding the development of *StructuredSig*, Filecoin could become the first network that benefits from its enterprise readiness, and present itself as the safe conservative solution for corporations looking to adopt a decentralized network.

## Deliverables

For this proposal, we will build a complete structured multisig solution working on top of Filecoin, in several stages, with payment at the beginning and end of each stage that is approved. Filecoin could also play it safe by only committing to one or two phases at first, and only committing to further phases after the first phases are completed with full satisfaction.

The successive stages would have the following deliverables, of increasing functionality:

- The deliverable in a first stage would be a study of how this product would be ported to the Filecoin ecosystem: what APIs it would use or provide, how the existing design of the product and/or Filecoin would have to be amended, etc. This deliverable would identify all the issues that can be thought of in advance with building the product.
- The deliverable in a second stage would be a working prototype, that demonstrates the key functionality of the multisig, even though it isn’t usable by anyone but developers, and even then, mostly as a demonstration of technological feasibility. This deliverable would also identify issues that couldn’t be thought of in advance with building the product.
- The deliverable in a third stage would be a minimum viable product, that brings the functionality of our multisig technology to the regular end-user of Filecoin, albeit only for the simplest of cases in the simplest of ways. This deliverable would bring direct value to the Filecoin ecosystem, and could serve as the basis for future developments.
- The deliverable in a fourth stage would be a full-fledged multisig solution, that makes the Filecoin ecosystem safe for corporations of any size to use. This deliverable would help Filecoin distinguish itself from other blockchain ecosystems that do not have such technology.

Even then, there are a lot of features that Filecoin may or may not want to fund as part of the third and fourth stages of development, and we will negotiate the precise feature set that Filecoin is willing to fund before we reach the point of implementing each feature.

## Development Roadmap

Our development will include the following phases.

### Phase 1: Specification and Evaluation

This is an extended discovery phase. In this phase, we will examine in depth how our *StructuredSig*  **********technology fits in the Filecoin ecosystem: what facilities we can reuse, what functionality we must custom-build for Filecoin vs other blockchains, which interfaces we must hook into (e.g. wallets), what features the interested parties in the Filecoin community deem more important, etc.

Detailed plans will be written to determine exactly which features will be implemented in each of the subsequent phases.

While this phase limits its deliverables to specifications, documentation, and requirements for future phases, it is fundamental to a successful phased roll-out of the system.

Phase 1 Goals:

- Determine how to integrate with Filecoin (e.g. by using the FVM).
- Determine which signature algorithm makes most sense to first support on Filecoin (e.g. ECDSA, Schnorr, BLS).
- Determine if we require any changes to the Filecoin ecosystem before we can fully implement our software.
- Determine which parts of our system we can reuse from the Ethereum prototype, and which we have to rebuild for Filecoin.
- Get some preliminary review of our designs as pertains to the Filecoin ecosystem from a competent cryptographer.
- Define an API that satisfies the interested parties at Filecoin.
- Determine what hosting and storage strategies make most sense for our policy and logging servers when running on the Filecoin ecosystem.
- Determine how to integrate with whatever authentication systems may be used within the Filecoin community and/or the main corporations interested in using it, to manage participant identities.

We estimate this work to take the equivalent of 2 engineers over 6 weeks, or $30,000.00.

### Phase 2: Initial Working Prototype Implementation

In Phase 2, we will establish a prototype that demonstrates feasibility of the product on Filecoin specifically: use of existing signature algorithm support or smart contract facilities to validate multisig-capable signatures; a command-line interface that demonstrates how to send tokens to and from an account managed by such a multisig system, with the signatures indeed involving multiple participants. The code will run against a private test network. No attempt will be made to make this code easy to use, or to integrate it with existing software (wallets, etc.)

Phase 2 Goals:

- Implementation of an account or contract driven by a suitable multisig algorithm.
- Implementation of a command-line interface capable of posting transactions based on signature by multiple participants.

We estimate this work to take the equivalent of 2 engineers over up to 18 weeks, or $90,000.00.

### Phase 3: Minimal Viable Product

In Phase 3, we will transform the previous prototype, suitable only for use by advanced developers, into an actual product, usable by the end-users of the Filecoin ecosystem. We will keep the set of features to a minimum, so as to get a usable product as fast as possible, based on a set of requirements defined in conversation with the Filecoin Foundation during phase 1. While it is yet unclear what exactly those requirements will be, we anticipate that they will look as follows:

Phase 3 Goals:

- Support all ordinary Filecoin transactions beside just sending tokens, if any.
- Write a web interface for end-users to partake in a multisig account on Filecoin.
- Integrate with at least one popular wallet for Filecoin.
- Create a minimal variant of our policy and logging server that can work with Filecoin.
- Implement a domain-specific language (DSL) for configuration of multisig policy and logging.
- Implement any necessary functionality identified during Phase 1 and Phase 2.

While the cost of this phase will be better understood after phase 1 and more so after phase 2, a preliminary estimate is that this phase would take about 20 to 30 weeks for two to three engineers and cost about $100,000.00 to $200,000.00.

### Phase 4: Full Featured Product

Phase 4 will likely involve a series of releases with new functionality implemented at each step. Features will be implemented according to priorities established by the Filecoin Foundation during phase 1 to 3. The precise schedule may change as development progresses, based on which parts we discover are already done or still missing, actually easy or difficult to write, etc. The Filecoin Foundation will be informed of any changes, and consulted any time priorities need to be redefined or confirmed. We expect the goals to look as follows.

Phase 4 Goals:

- Support any kind of Filecoin transaction in our APIs.
- Provide a web interface to all ordinary operations of a multisig.
- Provide a web interface for defining and updating multisig policy and logging configuration.
- Provide an extensibility mechanism allowing arbitrary contracts and their UI to use multisig.
- Provide configuration validation service that ensures that each participant (or a quorum of each category) is indeed capable of partaking in signing before the configuration is changed.
- Integrate with multiple popular wallets for Filecoin.
- Integrate with whatever authentication systems may be used within the Filecoin community and/or the main corporations interested in using it, to manage participant identities.
- Implement any necessary functionality identified during Phases 1 to 3.
- Document and package all the above so it can be easily used by the end-users of Filecoin.
- Iterate on the design and implementation until end-users are happy.

While the cost of this phase will be better understood after phases 1 to 3, a preliminary estimate is that this phase would take about 30 to 50 weeks three engineers and cost about $200,000.00 to $400,000.00.

This stage can be divided into any further number of stages, separately approved and funded by the Filecoin Foundation—and/or by other sponsors.

## Total Budget Requested

We propose that to start with, Filecoin would commit to at least stages 1 and 2 of the project (modulo positive review at the end of stage 1). The combined phases would take an estimated 24 weeks (over 5.5 months) and cost about $120,000.00 to fund the work of two engineers, an architect and support staff.

If Filecoin likes the prototype we show at the end of this period, it could then fund the rest of the development of phase 3 and maybe also phase 4, which could take between 20 and 80 weeks and cost anywhere between $100,000.00 and $600,000.00 depending on the precise set of features requested and the difficulties encountered while working on the Filecoin ecosystem.

## Team

### Contact Info

`alex@mukn.io`

### Team Members

- François-René Rideau, President & Chief Scientist
- Alexander Smart, Chief Executive Officer
- Peter Hubshman, Chief Financial Officer
- Zoe Braiterman, Chief Information Officer
- Gauthier Lamothe, Chief Communication Officer
- Alex Hochberger, Chief Product Officer & Chief Technology Officer
- Marcin Grzybowski, Vice President of Formal Methods
- Donald Fisk, Senior Scientist
- Henri Lesourd, Senior Scientist
- Vibhu Mohindra, Senior Engineer

### Team Member LinkedIn Profiles

- [https://linkedin.com/in/fahree](https://linkedin.com/in/fahree)
- [https://linkedin.com/in/alexandersmart](https://linkedin.com/in/alexandersmart)
- [https://www.linkedin.com/in/peterhubshman/](https://www.linkedin.com/in/peterhubshman/)
- [https://www.linkedin.com/in/zoebraiterman/](https://www.linkedin.com/in/zoebraiterman/)
- [https://linkedin.com/in/gauthier-lamothe](https://linkedin.com/in/gauthier-lamothe)
- [https://www.linkedin.com/in/alexhochberger/](https://www.linkedin.com/in/alexhochberger/)

### Team Website

[https://mukn.io](https://mukn.io)

### Relevant Experience

Relevant previous work by our contributors are listed in the Wiki for our *Glow* language:

[https://github.com/Glow-lang/glow/wiki/Bibliography-Glow](https://github.com/Glow-lang/glow/wiki/Bibliography-Glow)

We are now also part of the Laconic Network, for which we have implemented related multisig technology:

[https://laconic.com](https://laconic.com)

### Team code repositories

Our Glow programming language: [https://github.com/Glow-Lang/glow](https://github.com/Glow-Lang/glow)

Our implementation of Glow on Lurk: [https://github.com/MuKnSys/glow-on-lurk](https://github.com/MuKnSys/glow-on-lurk)

A signing tool we wrote as a multisig demo: [https://github.com/MuKnSys/signing-tool](https://github.com/MuKnSys/signing-tool)

## Additional Information

MuKn is already a partner of Filecoin, as a member of the Lurk project: we have implemented a prototype backend of our smart contract language *Glow* on top of Lurk, and have been working on the formalization of Lurk, for which we have submitted another proposal.

MuKn is also a member of the Laconic Network, another partner of Filecoin.
