# Coinmarketcap price source for Beancount

If you use the beancount cli accounting tool (http://furius.ca/beancount/), this price source will let you fetch cryptocurrency prices from coinmarketcap.com. This tool originally worked by scraping the website, but now queries a JSON API (the same API the website itself uses to populate the historical prices table).

This is **only** intended for personal use and not for scraping at scale. Coinmarketcap will likely block you if you query too frequently and, for this reason, the code is set by default to query no more than 1 time per 15 seconds. I encourage you to be a good internet citizen and not go any quicker than that or use this tool for anything but limited personal use.

## Setup

1. Add the `price_sources` folder of this project into some location defined in your $PYTHONPATH
2. Go to the commodity definition of your cryptocurrency and add a "price" attribute to refer to this price source. For example, for bitcoin you would add _EUR:price_sources.coinmarketcap/bitcoin_
3. You should now be able to use the bean-price tool to fetch prices!

On step 2, please note that the last part that says "bitcoin" is based on the URL used to get the historical prices, not the ticker symbol (in that example, the URL is https://coinmarketcap.com/currencies/bitcoin/historical-data/).

Credit to this post for the idea: https://medium.com/@danielcimring/downloading-historical-data-from-coinmarketcap-41a2b0111baf

This fork is a modification of the upstream using EUR as currency instead of USD.
