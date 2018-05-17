Auction Contracts
=================

## About
This repo contains Solidity smart contracts for conducting auctions on the initial version of the AUX Platform. While the contracts are combined into monoliths (see `contracts/`), the original directory structure may also be helpful in understanding the relationship(s) among contracts:

### Current Structure
```
contracts/
├── AscendingPriceCryptoKittyAuction.sol
├── AscendingPriceERC20Auction.sol
├── AscendingPriceERC721Auction.sol
├── BuyItNowCryptoKittyAuction.sol
├── BuyItNowERC20Auction.sol
├── BuyItNowERC721Auction.sol
├── DescendingPriceCryptoKittyAuction.sol
├── DescendingPriceERC20Auction.sol
└── DescendingPriceERC721Auction.sol
```

### Original Structure
```
contracts/
├── AuctionComponents
│   ├── AscendingPriceAuction.sol
│   ├── AuctionBase.sol
│   ├── BuyItNowAuction.sol
│   ├── CryptoKittyAuction.sol
│   ├── DescendingPriceAuction.sol
│   ├── ERC20Auction.sol
│   ├── ERC721Auction.sol
│   ├── FeeCollector.sol
│   └── Whitelistable.sol
├── Auctions
│   ├── AscendingPriceCryptoKittyAuction.sol
│   ├── AscendingPriceERC20Auction.sol
│   ├── AscendingPriceERC721Auction.sol
│   ├── BuyItNowCryptoKittyAuction.sol
│   ├── BuyItNowERC20Auction.sol
│   ├── BuyItNowERC721Auction.sol
│   ├── DescendingPriceCryptoKittyAuction.sol
│   ├── DescendingPriceERC20Auction.sol
│   └── DescendingPriceERC721Auction.sol
└── CryptoKittyInterface
    └── CKERC721.sol
```

## Auction Components
These are the contracts that comprise complete auctions. They either describe an auction format (such as an ascending price auction, where bidders incrementally increase the bidded amount until someone wins the auction) or a supported asset type (such as an ERC721, or non-fungible, token). The below table summarizes supported auction formats and asset types (_i.e._ token interfaces) as of this writing.

### Auction Formats
| Original Filename            | Type/Description                                                                                    |
| ---------------------------- | --------------------------------------------------------------------------------------------------- |
| `AscendingPriceAuction.sol ` | Ascending price auction. Bidders incrementally increase the bidded amount until the auction ends.   |
| `BuyItNowAuction.sol`        | "Buy It Now" auction. Bidders can choose to purchase the item at the advertised price.              |
| `DescendingPriceAuction.sol` | Descending price auction. The price ticks down continually until a bidder bids, ending the auction. |

### Asset Types
| Original Filename        | Type/Description                                                              |
| ------------------------ | ----------------------------------------------------------------------------- |
| `CryptoKittyAuction.sol` | [CryptoKitty](https://www.cryptokitties.co/).                                 |
| `ERC20Auction.sol`       | [ERC20 token](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-20.md).   |
| `ERC721Auction.sol`      | [ERC721 token](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-721.md). |

## Auctions
These are combinations of an auction format and an asset type, as outlined above.

## CryptoKitty Interface
Since the CryptoKitty non-fungible asset implementation does not quite follow Open Zeppelin's [current ERC721 implementation](https://github.com/OpenZeppelin/openzeppelin-solidity/tree/master/contracts/token/ERC721), we include this as a separate interface.

## Compilation
We use [Truffle](http://truffleframework.com/) to compile and migrate contracts. We currently use Truffle version 4.1.7 and Solidity version 0.4.23 (except where otherwise noted for compatibility purposes).
