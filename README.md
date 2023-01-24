# DAREC DATABASE 

## This is a guidance help you access and retrieve data from our database

## NOTE : DO NOT SHARE DAREC URL AND KEYS TO SOMEONE ELSE 

| **TABLE NAME** |  `Cryptocurrency_Daily`  | `CryptoRanking_500`|
| ------------- | ---------- | ------- |
|  **Description**   |  `Top 500 Crytocurrency daily data` |   `Top 500 Crytocurrency rankings`  |

  

## Sample code for retrieving data from database

Python file - restapi_version_view_databse.py - will be used to do this work.

- Symbol_ID Data 
```python
if __name__ == "__main__":
	# ranking data
	symbol_id, ranking_data = supabase_ranking_data_collected()
	print(symbol_id)
```
&nbsp; &nbsp; &nbsp; Example Results : 
```bash
['BTC_1', 'ETH_1027', 'USDT_825', 'BNB_1839', 'USDC_3408', 'XRP_52']
```

- Ranking_Data
```python 
if __name__ == "__main__":
	# ranking data
	symbol_id, ranking_data = supabase_ranking_data_collected()
	print(ranking_data)
```
&nbsp; &nbsp; &nbsp; Example Results : 
```bash
[{'rank': 1, 'symbol_id': 'BTC_1', 'name': 'Bitcoin'}, {'rank': 2, 'symbol_id': 'ETH_1027', 'name': 'Ethereum'}, {'rank': 3, 'symbol_id': 'USDT_825', 'name': 'Tether'}]
```

- Crypto_Daily Data
```python
if __name__ == "__main__":
	# crypto daily data 
	# you can change the second parameter with other crypto symbol_id
	test = supabase_crypto_data_collected("Cryptocurrency_Daily", "BTC_1")
	df_test = create_df(test)
	print(df_test)
```
&nbsp; &nbsp; &nbsp; Example Results : 
```bash
    symbol_id                     time_close          open  ...         close          volume     marketcap
0       BTC_1  2020-04-30T00:59:59.999+00:00   8797.670050  ...   8821.793647            None  1.619041e+11
1       BTC_1  2020-05-01T00:59:59.999+00:00   8672.781914  ...   8743.645078            None  1.604846e+11
2       BTC_1  2020-05-02T00:59:59.999+00:00   8869.057619  ...   8885.831536            None  1.631108e+11
3       BTC_1  2020-05-03T00:59:59.999+00:00   8983.614149  ...   9143.715140            None  1.678608e+11
4       BTC_1  2020-05-04T00:59:59.999+00:00   8895.744874  ...   8839.892644            None  1.623013e+11
..        ...                            ...           ...  ...           ...             ...           ...
992     BTC_1  2023-01-19T00:59:59.999+00:00  20686.745906  ...  20701.978176  30141936001.15  3.988488e+11
993     BTC_1  2023-01-20T00:59:59.999+00:00  21085.372338  ...  21059.031868  20979292006.69  4.057470e+11
994     BTC_1  2023-01-21T00:59:59.999+00:00  22677.427382  ...  22598.413589  29985651874.81  4.354249e+11
995     BTC_1  2023-01-22T00:59:59.999+00:00  22777.986661  ...  22880.744845  32632969494.79  4.408845e+11
996     BTC_1  2023-01-23T00:59:59.999+00:00  22721.088672  ...  22752.046429  24583793970.93  4.384262e+11

[997 rows x 8 columns]
Execution time: 0.6166572570800781 seconds
```

## Others

The maximum rows of crypto_daily data you can get no more than 1000 due to the limit from our database.  









