# Policy Server direct cellular connection 

* Proposal: [SDL-NNNN](nnnn-policy_server_direct_cellular_connection.md)
* Author: [Lexander Kutsan](https://github.com/LuxoftAKutsan)
* Status: **Awaiting review**
* Impacted Platforms: [Core]

## Introduction

This proposal is about communication with PolicyServer directly via vehicle celluar data, reducing of communicaitons amount and simplify policies flow. 

## Motivation

Policy update is complicated process, it requires many RPC communications and send a lot of data throw mobile chanel.
Nearest generation of headunits will have dirrect cellular connection, and communicaiton with policy server
can be done dirrectly wihtout using SDLProxy ad Mobile cellular data. 
Remove layer of abstraction in Policy table updates.
It will reduce amount of data sent via mobile transport, simplify Update Policy flow.
Also there would be no need to add additional encryption for policy table,
because there will be no intermediate actors between SDL and PolicyServer. 
The HTTPS connection would be enough.


## Proposed solution

Create dirrect connection to Policy Server from SDL. So PolicyManager will perfrom HTTPS request for fetching Policy table updates dirrectly.



## Potential downsides

Describe any potential downsides or known objections to the course of action presented in this proposal, then provide counter-arguments to these objections. You should anticipate possible objections that may come up in review and provide an initial response here. Explain why the positives of the proposal outweigh the downsides, or why the downside under discussion is not a large enough issue to prevent the proposal from being accepted.

## Impact on existing code

Describe the impact that this change will have on existing code. Will some SDL integrations stop compiling due to this change? Will applications still compile but produce different behavior than they used to? Is it possible to migrate existing SDL code to use a new feature or API automatically?

## Alternatives considered

Describe alternative approaches to addressing the same problem, and why you chose this approach instead.
