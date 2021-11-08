# ENSTools
A set of simple solidity contracts to extend ENS functionality to other smart contracts.

# Supports ENS

This is a quick and small library for allowing any contract to use ENS names like they would use a standard address. Things it can be used for:

* Create a token whose owner is defined by an ENS name, not an address – when minting new tokens, this library will check if the msg.sender is the correct owner!
* A DAO can have it's members be set by their ENS names, instead of addresses
* Set up money in escrow to be given to the owner of a given example.com website, until a given date – even if the owner never heard of ENS!

To use it, just use a store the NameHash as a string and then call updateAddress(NameHash) to save the latest ethereum address it points to Once that has been saved, use ensAddresses(NameHash) to obtain a valid eth address. Optionally, you can check lastUpdatedENSAt(NameHash) to check the last time it was updated. If it was never updated then both functions should return 0: IMPORTANT: check if address is not address(0) before sending ether.
