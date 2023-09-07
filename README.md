# USDSHARES-API-ALGORITHM
API Smart Contract Reactionary Algorithm for USDSHARES (USDS) Non-Volatile Stablecoin/Stabletoken
pragma solidity ^0.8.0;

contract USDSReactionaryAlgorithm {
    uint256 public USDSPrice; // Variable to store the price of USDS
    uint256 public USDSHARESPrice; // Variable to store the price of USDSHARES
    uint256 public CRYTOSHARESPrice; // Variable to store the price of CRYTOSHARES
    uint256 public BITCOINPrice; // Variable to store the price of BITCOIN
    uint256 public ETHEREUMPrice; // Variable to store the price of ETHEREUM
    uint256 public BNBPrice; // Variable to store the price of BNB
    uint256 public MATICPrice; // Variable to store the price of MATIC
    uint256 public TRONPrice; // Variable to store the price of TRON

    constructor() {
        USDSPrice = 1; // Initial price of USDS
        USDSHARESPrice = 1; // Initial price of USDSHARES
        CRYTOSHARESPrice = 1; // Initial price of CRYTOSHARES
        BITCOINPrice = 1; // Initial price of BITCOIN
        ETHEREUMPrice = 1; // Initial price of ETHEREUM
        BNBPrice = 1; // Initial price of BNB
        MATICPrice = 1; // Initial price of MATIC
        TRONPrice = 1; // Initial price of TRON
    }

    function reactToSupplyDemand(uint256 supplyChange, uint256 demandChange) external {
        if (supplyChange >= 10 || demandChange >= 10) {
            USDSHARESPrice = USDSHARESPrice * 105 / 100; // Increase USDSHARES price by 5%
        }
    }

    function reactToMarketPriceChange(
        uint256 crytoSharesPriceChange,
        uint256 bitcoinPriceChange,
        uint256 ethereumPriceChange,
        uint256 bnbPriceChange,
        uint256 maticPriceChange,
        uint256 tronPriceChange
    ) external {
        if (
            crytoSharesPriceChange < 0 ||
            bitcoinPriceChange < 0 ||
            ethereumPriceChange < 0 ||
            bnbPriceChange < 0 ||
            maticPriceChange < 0 ||
            tronPriceChange < 0
        ) {
            USDSHARESPrice = USDSHARESPrice + 100000; // Increase USDSHARES price by $100000
        }
    }
}
