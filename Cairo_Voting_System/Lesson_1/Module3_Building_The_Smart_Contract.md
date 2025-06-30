# Building The Smart Contract

You have made it this far so let's keep going. Now we need to build this voting application. We already have an idea of what we want. These are:

- Submit proposal for users to vote for me
- Request for stake tokens to use and vote
- Vote for people

Sounds a bit easy right?.

Now let's cook!.

![Cooking](../assets/lets_start.gif)

## Interface Section.

Now we have listed all those functions we need yes?. Now brainstorm with me. There are certain conditions we should take into account while creating these functions.

1. Submit proposal for users to vote for me
- We need users to create proposals and be able to know who created the proposal yes?

2. Request for stake tokens to use and vote
- We need tokens avaliable to be able to give out yes?

3. Vote for people
- We need to be able to put the tokens to vote for people yes?.

So taking all these into account, we can be able to picture how the smart contract should work right. 


Now for backend developers, I believe you may take this an average REST API and DB to listen, but no.
Yes, the ecosystem does keep track but it is not like a universal DB that keeps record of everything and being able to find and pinpoint what we need.

Now imagine a library

![library](../assets/big_library.avif)

Imagine each time a block (a transaction) is created, it placed at random in anywhere in this library, Would it not be cumbersome to go through every floor just to find what you are looking for?.

Also blockchain saves a transaction, not the details (i.e the user details, the receiver details, what they just placed into the blockchain). They save more of the addresses and the transaction details into just a block. An these blocks cannot be accessed through smart contracts, only through explorers.

Make sense?

So back to code, Copy this to start with the interface in your `lib.cairo`: 

```
#[starknet::interface]
pub trait IVotingStarknetV4<TContractState> {
    fn create_a_proposal(ref self: TContractState, name: felt252);
    fn stake_tokens(ref self: TContractState);
    fn vote_on_proposals(ref self: TContractState, name: felt252);
    fn get_staked_tokens_from_current_addr(self: @TContractState) -> u32;
    fn get_total_proposals_by_name(self: @TContractState, name: felt252) -> u32;
    fn get_tokens(self: @TContractState) -> u32;
    fn get_proposals_made_by_addr_through_name(self: @TContractState, name: felt252) -> u32;
    fn get_total_votes(self: @TContractState) -> u32;
}
```

These are the main functions which defines the structure of the smart contract. Let us dive down a bit shall we?

1. `create_a_proposal`: This 
2. second
3. third

