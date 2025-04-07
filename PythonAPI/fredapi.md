## Resource
* [fredapi Docs](https://pypi.org/project/fredapi/)
* [FRED Official Site: Search Engine](https://fred.stlouisfed.org/)
    * 可以用關鍵字搜索資料
    * 點進相關資料頁面可以看見資料全名稱（API 資料名稱代碼）
        * EX：https://fred.stlouisfed.org/series/UMCSENT，點進網址可以看到
        * 資料全名稱：University of Michigan: Consumer Sentiment
        * API 資料名稱代碼：UMCSENT
        * 以及上傳時間、資料頻率等資訊
* [FRED Official Site: Search by Tags](https://fred.stlouisfed.org/tags/series)

## Usage
* 需先申請 API KEY：https://fred.stlouisfed.org/docs/api/api_key.html
* `pip install fredapi`

## Example
### 尋找消費者相關的資料
```python
from fredapi import Fred
fred = Fred(api_key=API_KEY)

search_results = fred.search('consumer')
print(search_results[['id', 'title', 'frequency']])
```

### 獲取密西根大學消費者信心指數資料
```python
from fredapi import Fred
fred = Fred(api_key=API_KEY)

df = fred.get_series("UMCSENT")
print(df)
```
