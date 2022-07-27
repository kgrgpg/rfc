---
slug: 38
title: 38/WAKU2-RLN-CONTRACT
name: Rate Limiting Nullifier Contract
status: raw
category: RLN
tags: 17/WAKU-RLN-RELAY
editor: Keshav Gupta <keshav@status.im>
contributors:
---

## Tags

Currently identified tags comprise

* `17/WAKU-RLN-RELAY` protocol is an extension of `11/WAKU-RELAY` which additionally provides spam protection using Rate Limiting Nullifiers (RLN).


# Abstract
The following standard allows for the implementation of a standard API for Rate Limiting Nullifier Contract that manages membership of the participants in a group.


# Background / Rationale / Motivation

This contract serves as the basis for the implementation of RLN membership. New members can be registered by depositing a stake of valuable funds. They can also be slashed if they misbehave like spamming in a peer to peer pseudo-anonymous messaging network.

# Theory / Semantics

A standard track RFC in `stable` status MUST feature this section.
A standard track RFC in `raw` or `draft` status SHOULD feature this section.
This section SHOULD explain in detail how the proposed protocol works.
It may touch on the wire format where necessary for the explanation.
This section MAY also specify endpoint behaviour when receiving specific messages, e.g. the behaviour of certain caches etc.

# Wire Format Specification / Syntax

Methods

register

`function register(uint256 pubkey) external payable`



registerBatch

`function registerBatch(uint256[] calldata pubkeys) external payable`


withdraw

`function withdraw(
		uint256 secret,
		uint256 _pubkeyIndex,
		address payable receiver
	) external`

withdrawBatch

`function withdrawBatch(
		uint256[] calldata secrets,
		uint256[] calldata pubkeyIndexes,
		address payable[] calldata receivers
	) external`


Events

MemberRegistered

`event MemberRegistered(uint256 indexed pubkey, uint256 indexed index)`


MemberWithdrawn

`event MemberWithdrawn(uint256 indexed pubkey, uint256 indexed index)`


# Implementation Suggestions (optional)


# (Further Optional Sections)


# Security/Privacy Considerations

A standard track RFC in `stable` status MUST feature this section.
A standard track RFC in `raw` or `draft` status SHOULD feature this section.
Informational RFCs (in any state) may feature this section.
If there are none, this section MUST explicitly state that fact.
This section MAY contain additional relevant information, e.g. an explanation as to why there are no security consideration for the respective document.

# Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

# References

References MAY be subdivided into normative and informative.

## normative
A list of references that MUST be read to fully understand and/or implement this protocol.
See [RFC3967 Section 1.1](https://datatracker.ietf.org/doc/html/rfc3967#section-1.1).

## informative
A list of additional references.

