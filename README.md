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

ERC #721 Contract / Service

``` solidity
// ERC20 compatible functions
function name() constant returns (string name);
function symbol() constant returns (string symbol);
function totalSupply() constant returns (uint256 totalSupply);
function balanceOf(address _owner) constant returns (uint balance);

// Functions that define ownership
function ownerOf(uint256 _tokenId) constant returns (address owner);
function approve(address _to, uint256 _tokenId);
function takeOwnership(uint256 _tokenId);
function transfer(address _to, uint256 _tokenId);
function tokenOfOwnerByIndex(address _owner, uint256 _index) constant returns (uint tokenId);

// Token metadata
function tokenMetadata(uint256 _tokenId) constant returns (string infoUrl);

// Events
event Transfer(address indexed _from, address indexed _to, uint256 _tokenId);
event Approval(address indexed _owner, address indexed _approved, uint256 _tokenId);
```

#### Documentation

ERC #721 Info Website (web: [erc721.org](http://erc721.org))


#### Ethereum Request for Comments (ERC)s

- [ERC #721 Non fungible token standard](https://github.com/ethereum/EIPs/issues/721), Sept 2017
- [ERC #875 Non fungible tokens and simple atomic swaps](https://github.com/ethereum/EIPs/issues/875), Feb 2018


#### Articles

- [The Anatomy of ERC721 - Understanding Non-Fungible Ethereum Tokens](https://medium.com/crypto-currently/the-anatomy-of-erc721-e9db77abfc24)
by Gerald Nash, Howard University '21, Dec 2017


#### Trade ERC #721 Tokens

- **OpenSea** (web: [opensea.io](https://opensea.io)) - Buy, sell, and discover digital items
- **RareBits** (web: [rarebits.io](https://rarebits.io)) - Buy, sell, and discover unique crypto assets



## CryptoKitties (Yes, Cute Little Cartoon Cats) on the Blockchain!

See the [Awesome CryptoKitties (& CryptoCopycats)](https://github.com/openblockchains/awesome-cryptokitties) page »



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
