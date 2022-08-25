# Chapter 2: Market and Fundamental Data - Sources and tEchniques 
---
### Technical Analysis: 
- Extract Signals from Market Data Using Indicators Computed from Price and Volume Information 
    - Analyze Flow of Buy and Sell Orders 
    - Collect Volume and Price Statistics 

### Market Microstructure: 
- studies how the institutional environment affects the trading process and shapes outcomes: 
    - price sdiscovery, bid-ask spreads + quotes, intraday trading behavior and transaction costs 

### Trades: 
- *Market Order*: immediate execution at price listed upon arrival at trading venue 
- *Limit Order*: 
    - *buy limit order*: executes if market price lower than the limit 
    - *sell limit order*: executes if market price higher than the limit 
- *Stop Order*: 
    - *buy stop order*: activates when market price rises above a specific price 
        - limit loses of short sales 
    - *sell stop order*: activates when market price goes below a specific price 
- *All or None Orders*: prevent partial execution -> filled only if specified number of shares are avaliable
- *Fill or Kill Orders*: prevent partial execution -> cancel if not executed immediately 
- *Immediate or Cancel Orders*: immediately buy or sell the number of shares that are avaliable -> cancel the rest 
- *Not-Held Orders*: allow broker to decide on time and price of ex4ecution 
- *Open/Close Orders*: Execute on or near opening/closing of the market (partial executions allowed) 

### Exchanges: 
- NASDAQ: 
    - [Market Maker](https://www.investopedia.com/terms/m/marketmaker.asp): firm or individual quoting bids and asks + market size (often brokerage houses) 
        - provide liquidity and debth to markets and profit from the bid-ask spread (buy a stock at `x` and sell at `x+y`)
        - *Principal Trades* are market makers trading on their own accounts 
        - receive order from buyer -> sell off shares from their own inventory 
- NYSE: 
    - Specialists: Lone Market Makers for Specific Security 
        - Auction Market: Bids and Asks Competitvely Updated By Buyers and Sellers 
    - dealers acting as principals, brokers acting as agents 
    - Facilitate Price Formation through Auctions
    - Highest Bid and Lowest Ask are Matched or Dealers Buy from Sellers -> then Sell to Buyers 
- [Over-the-Counter Market (OTC)](https://www.investopedia.com/terms/o/over-the-countermarket.asp): 
    - Decentralized Market -> no central exchange/broker
    - less transparent than exchanges = fewer regulations
    - bonds, derivatives, structured products, curencies 
- [Alternative Trading Systems (ATS)](https://www.investor.gov/introduction-investing/investing-basics/glossary/alternative-trading-systems-atss#:~:text=Alternative%20Trading%20Systems%20(ATSs)%20are,become%20a%20national%20securities%20exchange.)

    - - Match orders for buyers and sellers of securities 
    - SEC-regulated electronic trading systems (currently all "dark pools")
    - *Dark Pools*: 
        - allow traders to execute anonymously 
        - Do not broadcast pre-trade data (price, presence, and amount) 
        - Report data to FINRA *after* they occur (not contributing to price discovery until after the trade)
        - Regulation National Market System (Reg NMS) -> 2007 SEC Order Protection Rule (spur competition and cut transaction costs)
    - *[Electronic Communication Network (ECNs)](https://www.investopedia.com/terms/e/ecn.asp)*: 
        - computerized system automatically matching buy and sell orders on major exchanges during market hours (typically limit orders)
        - no third party (privacy)
        - enable after hours trading 
        - typically high fees 
        - registered as 'broker-dealers'

### High-Frequency Data: 
- Two Categories of Market Data: 
    - Consolidated Feed: trade and quote data from each trading venue 
    - Propriety Products: each individual exchange (specific data for that product/exchange)
        - Proprietary Order Flow Data from NASDAQ: stream of orders, trades, and resulting prices on tick-by-tick basis 
- Quote Levels: 
    - Level 1 (L1): Primary Source -> Order Book (real time data, reveals market depth)
        - market depth is a key indicator of liquidity + potential price impact of sizeable market orders 
    - Level 2 (L2): Adds information about bid/ask prices by specific market makers
        - adds size and time of recent transactions (better insight into specific equity's liquidity)
    - Level 3 (L3): Adds ability to enter/change quotes, execute orders, and confirm trades 
        - *only avaliable to market makers and exchange member firms*
        - *access to quotes permits registered brokers to meet best execution requirements* 
- **[Financial Information eXchange (FIX)](https://www.fixtrading.org/what-is-fix/)**: 
    - vendor-neutral electronic communications protocol for real-time exchange of security transaction information 
    - de-facto messaaging standard for *pre-trade, trade, and post-trade* communication (mostly B2B)
    - less phone calls = less information redundancy 
    - High amounts of unstructured data -> challenging to process -> opportunity to exploit 
    - FIX Protocol, Ltd. owns and maintains the FIX system (brought about by Fidelity Investments and Solomon Brothers in 1992)
    - Dominant Market Share (exchanges also offer native protocols) 
- **NASDAQ TotalView-ITCH direct data-feed protocol** 
    - track individual orders for equity instruments from placement to execution or cancellation 
    - Reconstruction of the Order Book via historical records of data flow and tracking of the active limit orders for a specific security 
    - disseminates the [Net Order Imbalance Indicator (NOII)](https://www.investopedia.com/terms/n/net-order-imbalance-indicator-noii.asp) for NASDAQ opening and closing crosses and NASDAQ IPO/Halt Cross 
        - NOII: 
             - shows supply and demand for a stock based on buy-sell orders (10min before close and 5min before open)
            - nhelp identify new trading opportunities and increases market transparency 
        - [Crosses](https://www.investopedia.com/terms/c/cross.asp): (three primary finance definitons)
            - 1.) broker receives a buy and sell order for the same stock at the same price (makes a trade between two separate customers at the same time at the same price)
            - 2.) forex transaction where non-US based currencies traded are exchanged directly for each other without being convered to USD first 
            - 3.) Technical analysis chart pattern





# References 
### Investopedia
- [Investopedia: Market Maker](https://www.investopedia.com/terms/m/marketmaker.asp)
- [Investopedia: Over-the-Counter Market](https://www.investopedia.com/terms/o/over-the-countermarket.asp)
- [Investopedia: Electronic Communication Network](https://www.investopedia.com/terms/e/ecn.asp)
- [Investopedia: Financial Information eXchange](https://www.investopedia.com/terms/f/financial-information-exchange.asp)
- [Investopedia: Net Order Imbalance Indicator (NOII)](https://www.investopedia.com/terms/n/net-order-imbalance-indicator-noii.asp)
- [Investopedia: Cross](https://www.investopedia.com/terms/c/cross.asp)


### Other
- [Fix Trading Community: Financial Information eXchange (FIX®) Protocol](https://www.fixtrading.org/what-is-fix/)
- [Investor.gov: Alternative Trading Systems (ATSs)](https://www.investor.gov/introduction-investing/investing-basics/glossary/alternative-trading-systems-atss#:~:text=Alternative%20Trading%20Systems%20(ATSs)%20are,become%20a%20national%20securities%20exchange.)
- [ITCH Protocol](http://www.nasdaqtrader.com/content/technicalsupport/specifications/dataproducts/NQTVITCHspecification.pdf)

### GITHUBs
> [Python: Simplefix](https://github.com/da4089/simplefix)
> - [How to Download and Parse a Sample File of ITCH Messages](https://github.com/PacktPublishing/Machine-Learning-for-Algorithmic-Trading-Second-Edition/blob/master/02_market_and_fundamental_data/01_NASDAQ_TotalView-ITCH_Order_Book/01_parse_itch_order_flow_messages.ipynb)
> - [Reconstruct Both the Executed Trades and the Order Book for Any Given Ticker](https://github.com/PacktPublishing/Machine-Learning-for-Algorithmic-Trading-Second-Edition/blob/master/02_market_and_fundamental_data/01_NASDAQ_TotalView-ITCH_Order_Book/02_rebuild_nasdaq_order_book.ipynb)