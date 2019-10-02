ALFAcoins API Python implementation.

A Python3.6 wrapper around the [ALFACoins](https://www.alfacoins.com/) [APIs](https://www.alfacoins.com/developers).
 
by [Arash Fatahzade](https://github.com/ArashFatahzade).

[![Build Status](https://travis-ci.org/ALFAcoins/alfacoins-api-python.svg?branch=master)](https://travis-ci.org/ALFAcoins/alfacoins-api-python)
[![Coverage Status](https://coveralls.io/repos/github/ALFAcoins/alfacoins-api-python/badge.svg?branch=master)](https://coveralls.io/github/ALFAcoins/alfacoins-api-python?branch=master)

## Description

**alfacoins_api_python** is a Python3.6 Library for interacting with [ALFAcoins API](https://www.alfacoins.com/developers).

**alfacoins_api_python** provides cryptocurrency payment integration on your website via [ALFAcoins](https://www.alfacoins.com).

**alfacoins_api_python** allows you to integrate payments with the following cryptocurrencies:
* Bitcoin (BTC)
* Ethereum (ETH)
* XRP (XRP)
* Bitcoin Cash (BCH)
* Litecoin (LTC)
* Dash (DASH)

## APIs
* get_fees
* get_rate
* get_rates
* create_order*
* order_status*
* bitsend*
* bitsend_status*
* refund*
* statistics*

*: Private API

## Building
You need to have Python 3.6+ in order to use this package.
Consider using [pyenv](https://github.com/pyenv/pyenv) for virtual Python 3.6 environment.

```bash
pip3.6 install -r requirements_dev.txt
python3.6 setup.py build
```

## Installation

```bash
pip3.6 install alfacoins_api_python
```


## Getting Started

### Gateway

You can get an instance of `ALFACoins` class like this:

#### For public APIs

```python
from alfacoins_api_python import ALFACoins


alfacoins = ALFACoins()
```

#### For private APIs

```python3
from alfacoins_api_python import ALFACoins


alfacoins = ALFACoins(
  name='shop-name',
  password='password',
  secret_key='07fc884cf02af307400a9df4f2d15490'
)
```

### Create order

```python3
result = alfacoins.create_order(
    type='litecointestnet',
    amount=1.2345,
    currency='USD',
    order_id=1,
    options={
        'notificationURL': 'https://example.io/notify',
        'redirectURL': 'https://example.io/redirect',
        'payerName': 'Bob',
        'payerEmail': 'no_reply@alfacoins.com',
        },
    description='This is for test!',
)
```

Additional information and API documentation is here: [ALFAcoins API Reference](https://www.alfacoins.com/developers).
