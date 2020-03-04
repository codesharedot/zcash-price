# zcash price

Get zcash price in Python [https://pythonbasics.org](https://pythonbasics.org).
See [https://codesharedot.github.io/zcash-price/](https://codesharedot.github.io/zcash-price/)

```python
import requests
import json
from forex_python.converter import CurrencyRates
import os

c = CurrencyRates()
rate = c.get_rate('USD', 'EUR') 
print(rate)

zcash_api_url = 'https://api.coinmarketcap.com/v1/ticker/zcash/'
response = requests.get(zcash_api_url)
response_json = response.json()
print(response_json)

for coin in response.json():
    price = coin.get('price_usd', 'U$S Price not provided')
    coin_price = float(('{0:.2f}').format(float(price)))
    print('$ ' + str(coin_price))
    
    coin_price_eur = float(('{0:.2f}').format(float(price)*rate))   
    print('€ ' + str(btc_price_eur))
    
    if coin_price_eur > 9000:
           os.system('notify-send trade btc')
           
```
