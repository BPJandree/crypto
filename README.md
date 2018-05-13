# Cryptocurrency Market Data

## Historical Cryptocurrency Prices For ALL Tokens!

Retrieves all the open, high, low, close values for all cryptocurrencies. This retrieves data from CoinMarketCap's historical tables.

## Getting Started

These instructions will get you a copy of the crypto R package installed and ready to go.

### Prerequisites

Below are the high level dependencies for the package

```
R (>= 3.4.3), foreach, rvest, xml2
```

### Installing

For now installation is through devtools::install_github("jessevent/crypto") until the cran package is accepted.

#### Installing crypto via Github

```
# for the original code 
library(devtools)
install_github("jessevent/crypto")
# the original code may point to the old json location in whcich coinmarketcap data was stored. If you run into errors you can try my updated package.

# for my adapted code:
library(devtools)
install_github("BPJandree/crypto")
```
### Load Crypto Package

```
library(crypto)
```

### Retrieve All Cryptocurrencies Market History

This is the main function of this package and once ran will go and scrape all the historical tables of all the different cryptocurrencies listed on CoinMarketCap and turn it into a data frame.

```
will_i_get_rich <- getCoins()
```

My code change also allows the following:

```

### GET DATA
# top 100
n = 100
tickers <- listCoins(n)
# check the symbols
symbols <- tickers[,"symbol"]
3 check the coins
curnames <- tickers[,"name"]

# grab the data
df <- getCoins(n)

```

### Output

I've had to go over the code with a fine tooth comb to get it compatible with CRAN so there have been significant enhancements to how some of the field conversions have been undertaken and the data being cleaned. This should eliminate a few issues around number formatting or unexpected handling of scientific notations.

```
    Observations: 649,051
    Variables: 13
    $ slug        <chr> "bitcoin", "bitcoin", "bitcoin", "bitcoin"...
    $ symbol      <chr> "BTC", "BTC", "BTC", "BTC", "BTC", "BTC", ...
    $ name        <chr> "Bitcoin", "Bitcoin", "Bitcoin", "Bitcoin"...
    $ date        <date> 2013-04-28, 2013-04-29, 2013-04-30, 2013-...
    $ ranknow     <dbl> 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, ...
    $ open        <dbl> 135.30, 134.44, 144.00, 139.00, 116.38, 10...
    $ high        <dbl> 135.98, 147.49, 146.93, 139.89, 125.60, 10...
    $ low         <dbl> 132.10, 134.00, 134.05, 107.72, 92.28, 79...
    $ close       <dbl> 134.21, 144.54, 139.00, 116.99, 105.21, 97...
    $ volume      <dbl> 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, ...
    $ market      <dbl> 1500520000, 1491160000, 1597780000, 154282...
    $ close_ratio <dbl> 0.5438, 0.7813, 0.3843, 0.2882, 0.3881, 0...
    $ spread      <dbl> 3.88, 13.49, 12.88, 32.17, 33.32, 29.03, 2...
```
### Authors
Original code from
- **Jesse Vent** - Package Author - [jessevent](https://github.com/jessevent)

### License

This project is licensed under the MIT License - see the 

<license.md> file for details</license.md>

### Acknowledgments

- Thanks to the team at <https://coinmarketcap.com> for the great work they do and to the team at CoinTelegraph where the images were sourced.
- Please star this if you find it useful, and remember the crypto currency market is volatile by nature, please be responsible if trading.
