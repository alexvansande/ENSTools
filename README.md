# ENSTools
A set of simple solidity contracts to extend ENS functionality to other smart contracts.

# Supports ENS

This is a quick and small library for allowing any contract to use ENS names like they would use a standard address. Things it can be used for:

* Create a token whose owner is defined by an ENS name, not an address – when minting new tokens, this library will check if the msg.sender is the correct owner!
* A DAO can have it's members be set by their ENS names, instead of addresses
* Set up money in escrow to be given to the owner of a given example.com website, until a given date – even if the owner never heard of ENS!

To use it, just use a store the NameHash as a string and then call updateAddress(NameHash) to save the latest ethereum address it points to Once that has been saved, use ensAddresses(NameHash) to obtain a valid eth address. Optionally, you can check lastUpdatedENSAt(NameHash) to check the last time it was updated. If it was never updated then both functions should return 0: IMPORTANT: check if address is not address(0) before sending ether.


# Push To ENS


A little contract that adds push & pull money transfer to ENS ensAddresses. Will work with any ENS, existing or future, including DNS names! Ether, tokens and NFTs remain locked by contract until ENS is set up properly. Once ENS points to a non-zero address, anyone can pull it there.

* Want to donate USDC to wikipedia.org but they don't have an eth address yet?
* Want to send an NFT to xkcd.org but you're not sure how to trust the address?
* Want to make an Ether bounty so the Ethiopian government is be aware of ENS?

Now you can do all that! But wait, there's more! You can also use it to push to a normal address. Just because.

ATTENTION: use at your own risk! I've barely tested it. And by barely I mean I tried a couple different things on rinkeby. Haven't even deployed to mainnet yet!. NFTs don't use _safeTransfer because I was too lazy to build my own onerc721Received. Be careful out there.
