![](i/cryptokitties-genes01.png)


# Awesome CryptoCollectibles (& CryptoAssets)

A collection about Awesome Crypto Collectibles - Yes, Non Fungible Tokens (NFTs) - Yes, Unique Bits & Bytes on the Blockchain - Buy! Sell! Hodl!


![](i/cryptokitties-modernart-paintings.png)


## Non fungible tokens (NFT)s

_Trade (unique) collectibles on the blockchain_

Non fungible tokens (NFT)s can represent ownership 
over digital or physical assets. Examples:

- Physical property — houses, unique artwork
- Virtual collectibles — unique pictures of kittens, collectible cards
- "Negative value" assets — loans, burdens and other responsibilities

In general, all houses are distinct and no two kittens are alike. Non fungible tokens (NFT)s are 
*distinguishable* and you must track the ownership of each one separately.


### Assets, Assets, Assets - Deeds, Deeds, Deeds - Titles, Titles, Titles

Synonyms for non fungitble tokens in the "universe of distinguishable digital assets" include:

- deed   (descriptive for certain applications, notably, physical property).
- asset
- title
- token
- equity
- ticket


### Unique Identifiers / IDs

Every non fungible token (NFT) is identified by a unique uint265 ID inside the contract e.g.

``` solidity
/// @dev An array containing the Kitty struct for all Kitties in existence. The ID
///  of each cat is actually an index into this array. Note that ID 0 is a negacat,
///  the unKitty, the mythical beast that is the parent of all gen0 cats. A bizarre
///  creature that is both matron and sire... to itself! Has an invalid genetic code.
///  In other words, cat ID 0 is invalid... ;-)

Kitty[] kitties;
```

The number SHALL NOT change for the life of the contract. 
The pair (contract address, uint265 tokenId) will then be a globally unique and fully-qualified identifier for a specific asset on the ethereum blockchain. 

Note: While some contracts may find it convenient to start with ID 0 and simply add one for each new token, callers SHALL NOT assume that ID numbers have any specific pattern,  and MUST treat the ID as a "black box". The choice of uint256 allows a wide variety of applications because UUIDs and SHA3 hashes are directly convertible to uint256.




### Ethereum Request for Comments (ERC) #721

#### Version 1 / V1 

Ethereum Request for Comments (ERC)s

- [ERC #721 Non fungible token standard](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md), Ethereum Improvement Proposals (EIPs) Page Started in Jan 2018


ERC #721 Contract / Service

``` solidity
interface ERC721 /* is ERC165 */ {
    /// @dev This emits when ownership of any NFT changes by any mechanism.
    ///  This event emits when NFTs are created (`from` == 0) and destroyed
    ///  (`to` == 0). Exception: during contract creation, any number of NFTs
    ///  may be created and assigned without emitting Transfer. At the time of
    ///  any transfer, the approved address for that NFT (if any) is reset to none.
    event Transfer(address indexed _from, address indexed _to, uint256 _tokenId);

    /// @dev This emits when the approved address for an NFT is changed or
    ///  reaffirmed. The zero address indicates there is no approved address.
    ///  When a Transfer event emits, this also indicates that the approved
    ///  address for that NFT (if any) is reset to none.
    event Approval(address indexed _owner, address indexed _approved, uint256 _tokenId);

    /// @dev This emits when an operator is enabled or disabled for an owner.
    ///  The operator can manage all NFTs of the owner.
    event ApprovalForAll(address indexed _owner, address indexed _operator, bool _approved);

    /// @notice Count all NFTs assigned to an owner
    /// @dev NFTs assigned to the zero address are considered invalid, and this
    ///  function throws for queries about the zero address.
    /// @param _owner An address for whom to query the balance
    /// @return The number of NFTs owned by `_owner`, possibly zero
    function balanceOf(address _owner) external view returns (uint256);

    /// @notice Find the owner of an NFT
    /// @dev NFTs assigned to zero address are considered invalid, and queries
    ///  about them do throw.
    /// @param _tokenId The identifier for an NFT
    /// @return The address of the owner of the NFT
    function ownerOf(uint256 _tokenId) external view returns (address);

    /// @notice Transfers the ownership of an NFT from one address to another address
    /// @dev Throws unless `msg.sender` is the current owner, an authorized
    ///  operator, or the approved address for this NFT. Throws if `_from` is
    ///  not the current owner. Throws if `_to` is the zero address. Throws if
    ///  `_tokenId` is not a valid NFT. When transfer is complete, this function
    ///  checks if `_to` is a smart contract (code size > 0). If so, it calls
    ///  `onERC721Received` on `_to` and throws if the return value is not
    ///  `bytes4(keccak256("onERC721Received(address,uint256,bytes)"))`.
    /// @param _from The current owner of the NFT
    /// @param _to The new owner
    /// @param _tokenId The NFT to transfer
    /// @param data Additional data with no specified format, sent in call to `_to`
    function safeTransferFrom(address _from, address _to, uint256 _tokenId, bytes data) external payable;

    /// @notice Transfers the ownership of an NFT from one address to another address
    /// @dev This works identically to the other function with an extra data parameter,
    ///  except this function just sets data to ""
    /// @param _from The current owner of the NFT
    /// @param _to The new owner
    /// @param _tokenId The NFT to transfer
    function safeTransferFrom(address _from, address _to, uint256 _tokenId) external payable;

    /// @notice Transfer ownership of an NFT -- THE CALLER IS RESPONSIBLE
    ///  TO CONFIRM THAT `_to` IS CAPABLE OF RECEIVING NFTS OR ELSE
    ///  THEY MAY BE PERMANENTLY LOST
    /// @dev Throws unless `msg.sender` is the current owner, an authorized
    ///  operator, or the approved address for this NFT. Throws if `_from` is
    ///  not the current owner. Throws if `_to` is the zero address. Throws if
    ///  `_tokenId` is not a valid NFT.
    /// @param _from The current owner of the NFT
    /// @param _to The new owner
    /// @param _tokenId The NFT to transfer
    function transferFrom(address _from, address _to, uint256 _tokenId) external payable;

    /// @notice Set or reaffirm the approved address for an NFT
    /// @dev The zero address indicates there is no approved address.
    /// @dev Throws unless `msg.sender` is the current NFT owner, or an authorized
    ///  operator of the current owner.
    /// @param _approved The new approved NFT controller
    /// @param _tokenId The NFT to approve
    function approve(address _approved, uint256 _tokenId) external payable;

    /// @notice Enable or disable approval for a third party ("operator") to manage
    ///  all of `msg.sender`'s assets.
    /// @dev Emits the ApprovalForAll event
    /// @param _operator Address to add to the set of authorized operators.
    /// @param _approved True if the operators is approved, false to revoke approval
    function setApprovalForAll(address _operator, bool _approved) external;

    /// @notice Get the approved address for a single NFT
    /// @dev Throws if `_tokenId` is not a valid NFT
    /// @param _tokenId The NFT to find the approved address for
    /// @return The approved address for this NFT, or the zero address if there is none
    function getApproved(uint256 _tokenId) external view returns (address);

    /// @notice Query if an address is an authorized operator for another address
    /// @param _owner The address that owns the NFTs
    /// @param _operator The address that acts on behalf of the owner
    /// @return True if `_operator` is an approved operator for `_owner`, false otherwise
    function isApprovedForAll(address _owner, address _operator) external view returns (bool);
}

interface ERC165 {
    /// @notice Query if a contract implements an interface
    /// @param interfaceID The interface identifier, as specified in ERC-165
    /// @dev Interface identification is specified in ERC-165. This function
    ///  uses less than 30,000 gas.
    /// @return `true` if the contract implements `interfaceID` and
    ///  `interfaceID` is not 0xffffffff, `false` otherwise
    function supportsInterface(bytes4 interfaceID) external view returns (bool);
}



/// @dev Note: the ERC-165 identifier for this interface is 0xf0b9e5ba
interface ERC721TokenReceiver {
    /// @notice Handle the receipt of an NFT
    /// @dev The ERC721 smart contract calls this function on the recipient
    ///  after a `transfer`. This function MAY throw to revert and reject the
    ///  transfer. This function MUST use 50,000 gas or less. Return of other
    ///  than the magic value MUST result in the transaction being reverted.
    ///  Note: the contract address is always the message sender.
    /// @param _from The sending address
    /// @param _tokenId The NFT identifier which is being transfered
    /// @param data Additional data with no specified format
    /// @return `bytes4(keccak256("onERC721Received(address,uint256,bytes)"))`
    ///  unless throwing
	function onERC721Received(address _from, uint256 _tokenId, bytes data) external returns(bytes4);
}


/// @title ERC-721 Non-Fungible Token Standard, optional metadata extension
/// @dev See https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md
///  Note: the ERC-165 identifier for this interface is 0x5b5e139f
interface ERC721Metadata /* is ERC721 */ {
    /// @notice A descriptive name for a collection of NFTs in this contract
    function name() external pure returns (string _name);

    /// @notice An abbreviated name for NFTs in this contract
    function symbol() external pure returns (string _symbol);

    /// @notice A distinct Uniform Resource Identifier (URI) for a given asset.
    /// @dev Throws if `_tokenId` is not a valid NFT. URIs are defined in RFC
    ///  3986. The URI may point to a JSON file that conforms to the "ERC721
    ///  Metadata JSON Schema".
    function tokenURI(uint256 _tokenId) external view returns (string);
}


/// @title ERC-721 Non-Fungible Token Standard, optional enumeration extension
/// @dev See https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md
///  Note: the ERC-165 identifier for this interface is 0x780e9d63
interface ERC721Enumerable /* is ERC721 */ {
    /// @notice Count NFTs tracked by this contract
    /// @return A count of valid NFTs tracked by this contract, where each one of
    ///  them has an assigned and queryable owner not equal to the zero address
    function totalSupply() external view returns (uint256);

    /// @notice Enumerate valid NFTs
    /// @dev Throws if `_index` >= `totalSupply()`.
    /// @param _index A counter less than `totalSupply()`
    /// @return The token identifier for the `_index`th NFT,
    ///  (sort order not specified)
    function tokenByIndex(uint256 _index) external view returns (uint256);

    /// @notice Enumerate NFTs assigned to an owner
    /// @dev Throws if `_index` >= `balanceOf(_owner)` or if
    ///  `_owner` is the zero address, representing invalid NFTs.
    /// @param _owner An address where we are interested in NFTs owned by them
    /// @param _index A counter less than `balanceOf(_owner)`
    /// @return The token identifier for the `_index`th NFT assigned to `_owner`,
    ///   (sort order not specified)
    function tokenOfOwnerByIndex(address _owner, uint256 _index) external view returns (uint256);
}
```

(Source: [`contracts/ERC721-V0.sol`](contracts/ERC721-V1.sol))




#### Version 0 / V0

Ethereum Request for Comments (ERC)s

- [ERC #721 Non fungible token standard)](https://github.com/ethereum/EIPs/issues/721), Issue Ticket Opened in Sept 2017

ERC #721 Contract / Service

``` solidity
// Required methods
function totalSupply() public view returns (uint256 total);
function balanceOf(address _owner) public view returns (uint256 balance);
function ownerOf(uint256 _tokenId) external view returns (address owner);
function approve(address _to, uint256 _tokenId) external;
function transfer(address _to, uint256 _tokenId) external;
function transferFrom(address _from, address _to, uint256 _tokenId) external;

// Events
event Transfer(address from, address to, uint256 tokenId);
event Approval(address owner, address approved, uint256 tokenId);

// Optional
// function name() public view returns (string name);
// function symbol() public view returns (string symbol);
// function tokensOfOwner(address _owner) external view returns (uint256[] tokenIds);
// function tokenMetadata(uint256 _tokenId, string _preferredTransport) public view returns (string infoUrl);

// ERC-165 Compatibility (https://github.com/ethereum/EIPs/issues/165)
function supportsInterface(bytes4 _interfaceID) external view returns (bool);
```

(Source: [`contracts/ERC721-V0.sol`](contracts/ERC721-V0.sol))




#### Documentation

ERC #721 Info Website (web: [erc721.org](http://erc721.org))


<!--

#### Ethereum Request for Comments (ERC)s

- [ERC #875 Non fungible tokens and simple atomic swaps](https://github.com/ethereum/EIPs/issues/875), Feb 2018

-->




#### Articles

- [The Anatomy of ERC721 - Understanding Non-Fungible Ethereum Tokens](https://medium.com/crypto-currently/the-anatomy-of-erc721-e9db77abfc24)
by Gerald Nash, Howard University '21, Dec 2017



#### Trade ERC #721 Tokens

- **OpenSea** (web: [opensea.io](https://opensea.io)) - Buy, sell, and discover digital items
- **RareBits** (web: [rarebits.io](https://rarebits.io)) - Buy, sell, and discover unique crypto assets




## CryptoKitties (Yes, Cute Little Cartoon Cats) on the Blockchain!

See the [Awesome CryptoKitties (& CryptoCopycats)](https://github.com/openblockchains/awesome-cryptokitties) page »



## CrytoDrakos (Yes, Cute Litte Cartoon Dragons) on the Blockchain! (Upcoming)

Collectible. Breedable. Admirable. Unbeatable.

Learn more @ [cryptodrakos.co](https://cryptodrakos.co), twitter: [CryptoDrakos](https://twitter.com/CryptoDrakos)

![](i/cryptodrakos.png)



## CryptoPuppies (Yes, Cute Little Cartoon Dogs) on the Blockchain! (Upcoming)

Collectable. Breedable. Adorable.

![](i/cryptopuppies_i.png)

Learn more @ [cryptopuppies.org](http://cryptopuppies.org), twitter: [CryptoPuppies_](https://twitter.com/CryptoPuppies_)

---

![](i/cryptopuppies_ii.png)

Learn more @ twitter: [Crypto_Puppies](https://twitter.com/Crypto_Puppies)


## Puppy Planet on the Blockchain! (Upcoming)

Buy, sell, hodl and breed puppies.

![](i/puppyplanet.png)

Learn more @ [puppyplanet.co](http://www.puppyplanet.co),
twitter: [aPuppyPlanet](https://twitter.com/aPuppyPlanet)


## HashPuppies on the Blockchain! (Upcoming)

> We want to have a presale first so we can raise funds to hire more devs and artists
> and pay for scalable infrastructure,
> to have a really great and responsive game.
> We are working out the legal aspects of the presale right now,
> because there is a lot of uncertainty right now around crowdfunding with cryptocurrency.

![](i/hashpuppies.png)

Learn more @ [hashpuppi.es](https://hashpuppi.es),
twitter: [hash_puppies](https://twitter.com/hash_puppies),
reddit: [HashPuppies](https://www.reddit.com/r/HashPuppies)



## CryptoPets on the Blockchain!  (Upcoming)

The first five animals to be sold off...
Please welcome the Dog, Galapagos Turtle, Giant Panda, T-Rex  and Unicorn  
as the founding species on CryptoPets!

> CryptoPets are the newest breed of animals on the block... blockchain that is.
> Unlike cryptocurrencies, which require all tokens to be identical,
> your CryptoPet will be the only one of its kind in the entire world.
> These cute collectibles are cryptographically unique, non-fungible digital assets.
> CryptoPets uses the immutability of blockchain technology to verify and prove that each CryptoPet
> has its own special attributes and is entirely owned by you.  
> Each species will have variations in specific attributes,
> including fur color, eye shape, paw, and feet type, to name a few.


![](i/cryptopets.png)

Learn more @ [cryptopets.co](https://cryptopets.co),
twitter: [CryptoPets](https://twitter.com/CryptoPets),
reddit: [CryptoPets](https://www.reddit.com/r/CryptoPets)



## CryptoMons(ters) on the Blockchain! (Upcoming)

Collect. Combat. Trade. Digital collectible (monster) cards on the blockchain.

> Every CryptoMons(ter) has his own DNA that defines his aspect and stats:
> there are no two identical CryptoMons(ter).

![](i/cryptomons.png)

Learn more @ [cryptomons.com](http://cryptomons.com),
twitter: [cryptomons](https://twitter.com/cryptomons)


## CryptoDrome (CryptoHorses) on the Blockchain! (Upcoming)

Collect. Breed. Compete. Raise your own champions.

> We're CryptoHorses, and we were born to compete. Collect and become a champion of the CryptoDrome.

![](i/cryptodrome.png)

Learn more @ [cryptodrome.co](http://cryptodrome.co),
twitter: [cryptodrome](https://twitter.com/cryptodrome)

Team:

- **Miguel Ángel Fort** (twitter: [@mafp86](https://twitter.com/mafp86))


## CryptoHeroes (Hero Tavern) on the Blockchain! (Upcoming)

Hero Tavern is a decentralized app that based on Ethereum platform. It is also a classic Simulation game. In the Game, player can acquire Heroes via many different ways. For example, Heroes can be purchased directly from the Market. Some of those Heroes are generated by System, and some are put up for sale by other players. After players own at least one Hero, they can begin journals of training and cultivating their Heroes. Every Hero has talent values; these values pretty much determine the combat power of a Hero at certain level. If players do not satisfy heroes’ talent, they can wash talent. In order to have higher Combat Power, Heroes can equip better equipment or cumulate Exp to upgrade Levels. Firstly, Players can assign Heroes to fight and suppress Monsters. Players will gain weaponry of Heroes and Heroes will gain Exp. Also, there is a chance that a Hero can be rescued from Monsters. Secondly, Players can buy Treasure Maps from Auctions, then Heroes is able to go for Treasure Hunts. It is possible to meet a new Hero during the Treasure Hunt beside the chance of finding rare items. Moreover, if Players do not like or need their Heroes, and also do not want to put Heroes on Market to sale, the Factory offers Players another way to deal with their useless Heroes. By adding items, Players can recast their Heroes to generate a new one. Alternatively, Players can just simply dissolve their Heroes into items and bottles of Exp. There are more fun and more surprises for you to explore in the Game. There are more unique Heroes are waiting for you to collect. New Adventures are on the way!

Learn more @ [hero-tavern.org](https://www.hero-tavern.org),
twitter: [crypto_heros](https://twitter.com/crypto_heros)

White Paper V1 ([WHITEPAPER @ Github](https://github.com/Hero-Tavern/HeroTavern/blob/master/WHITEPAPER.md)),
Game Mannual ([MANUAL @ Github](https://github.com/Hero-Tavern/HeroTavern/blob/master/MANUAL.md))


## CryptoFighters on the Blockchain! (Upcoming)

Collectible fighters. Level up and start battling.

Learn more @ [cryptofighters.io](http://cryptofighters.io),
twitter: [CryptoFighters](https://twitter.com/CryptoFighters)


## Fishbank / CryptoFish on the Blockchain! (Upcoming)

Grow your fish to the top of food chain!

> Take your place in a decentralized food chain.
> Grow, fight and trade your predatory fish champion
> on the blockchain!
>
> Hunt other fishes and bite off their weight to take top positions in global leaderboards
> of decentralized deep blue ocean. Trade your winner fish to a better one and grow another champion!

![](i/fishbank.png)

Learn more @ [fishbank.io](https://fishbank.io)

> New Year gift for all the crypto cuties!
> Every owner of Gen 0 asset in any other crypto  pets collectible as of 1th Jan. 2018
> may request a special gift - the Rare fish token in Fishbank.
> That is what can be generally referred to as "hardfork effect" in blockchain ecosystems.

Team:

- Chat Robotic @ [chatrobotic.com](http://www.chatrobotic.com), twitter: [chatrobotic](https://twitter.com/chatrobotic)


White Paper V1  ([PDF Download](https://fishbank.io/whitepaper/FISHBANK-V1.pdf)):

**Game concept**

Player owns fishes (those are in fact ERC-721 crypto tokens) each with its unique name, image and
characteristics defined by type. Core fish parameter is weight that defines its size and influence. Main
target is to grow this parameter to become the biggest fish in the ocean.
Fish is able to gain weight only by attacking other fishes, biting off them in case of win.

The more powerful characteristics and the more weight the fish has the
more chance it to win a fight with another fish it represents.

These fishes can be traded or exchanged between players on central fish market.
Every operation in the game is launched and controlled by a contract script.

**The Fish**

Every crypto fish token has its own set of characteristics:

- Weight - Describes the size of the fish
- Power - Damage on attack
- Agility - Defense on attack
- Speed - Cooldown time before attacks

Weight is dynamic characteristic and can be changed within time while Power, Agility and
Speed are called initial parameters those are given to fish from the very moment of creation
and can't be changed in time.

**Rarity**

There are four kinds of rarity assessment  for fishes determined by sum of all
initial fish characteristics:

- Common
- Rare (10+)
- Legendary (15+)
- Epic (25+)




## CryptoTulips on the Blockchain!  (Upcoming)

Learn by Example from the Real World (Anno 1637) - Buy! Sell! Hold!
Enjoy the Beauty of Admiral of Admirals, Semper Augustus and More.

![](i/cryptotulips.png)

Learn more @ [openblockchains/tulips](https://github.com/openblockchains/tulips)



## More

<!-- add decentraland ??   virtual land (parcels) on the blockchain and more -->



### News

**CryptoGames on the Blockchain! News**

See web: [cryptogamer.net](http://www.cryptogamer.net), twitter: [CryptoGamerNet](https://twitter.com/CryptoGamerNet)



### Awesome Awesomeness

- [Awesome Non Fungible Tokens (NFT)s](https://github.com/buendiadas/awesome-nonfungibletokens) - an awesome curated list of resources regarding implementations of Non Fungible Tokens (ERC721 standard).
- [Awesome Blockchains](https://github.com/openblockchains/awesome-blockchains) - a collection about awesome blockchains - open distributed public databases w/ crypto hashes incl. git ;-). Blockchains are the new tulips. Distributed is the new centralized.




## Meta

**License**

![](https://publicdomainworks.github.io/buttons/zero88x31.png)

The awesome list is dedicated to the public domain. Use it as you please with no restrictions whatsoever.
