# Amazon_API
From JAN code, obtain ASIN code, price, review, category and ranking on Amazon market by using Amazon API.
<img src="https://github.com/shutokawabata0723/Amazon_API/blob/master/amazon_api.png" width="800px">



# Important portion
Can get information of Amazon from only JAN code.

This is a big merit for users selling merchandise on Amazon.

# Input
/output/output.csv

Check before running

# Output
/output/output2.csv


# Usage and Flow
0. Import modules here
```python
from amazon.api import AmazonAPI
from amazon.api import LookupException, AsinNotFound
```

1. Edit here<br>
```python
ACCESS_KEY = "ここにアクセスキーを入力"
SECRET_ACCESS_KEY = "ここにシークレットアクセスキーを入力"
ASSOCIATE_TAG = "ここにアソシエイトタグを入力"
```
2. Here, get informations by using API (The most important code)
```python
def amazon_api(JAN,name,price,url,counter):
	try:
		product = amazon.lookup(ItemId=JAN, IdType="EAN", SearchIndex="All")
		if isinstance(product, list):
			print 'NO amazon'
		else:
			asin = product.asin
			title= product.title
			amazon_price= product.price_and_currency[0]
			group = product.product_group
			rank  = product.sales_rank
```


# Caution
You need to create "ASSOCIATE TAG", "ACCESS KEY", "SECRET ACCESS KEY" for using Amazon API in advance.<br>
As default, you can get information of 2000 items per hour.<br>



# Licence
CopyRight (c) 2018 Shuto Kawabata

Released under the MIT licence

https://opensource.org/licenses/MIT

# Author
Shuto Kawabata
