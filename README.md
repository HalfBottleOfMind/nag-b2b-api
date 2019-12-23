# nag-b2b-api

Library for processing data from https://b2b-api.nag.ru/api/

Installing: pip install nag_b2b_api_halfbottleofmind

Using example:
```
from nag_b2b_api import Database
# import Database class

db = Database(database="PATH-TO-YOUR-SQLITE-DATABASE" api_key="YOUR-API-KEY")
# default path to database is :memory:
# when database created there will be seven empty tables
# you can use database in file for saving tables content

db.refreshDatabase()
# this function downloading data and import it in tables

products = db.getProducts()
# returns all products

brands = db.getBrands()
# returns all brands

products = db.getProductsByBrand(brands[0].guid)
# returns all products of first brands

prices = db.execute('SELECT * FROM prices').fetchall()
# you can write your own database queries and send it in "execute" function
```
