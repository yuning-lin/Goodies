## Goodies
Record useful tools
紀錄有用的小工具的 repository  
對學習有幫助或可立即使用看效果、不用親自寫程式省卻許多麻煩的工具  

* [Way to Access Papers](https://sci-hub.se/)
* [Free Labeling Tool](https://trainset.geocene.com/)

## Free Labeling Tool
### 時間序列資料
[WEB 版](https://trainset.geocene.com/)快速標籤時序資料異常與否  
注意事項：
* 上傳檔案為：csv
* 所需欄位為：
  * series/filename：為不同序列的命名
  * timestamp：須為 ISO8601 format
  * value：可接受實數
  * label：可為空值或自行預設 
* 切記欄位順序必須遵照範例：`filename, timestamp, value, label`
* 時間格式轉換可[參考](https://stackoverflow.com/questions/2150739/iso-time-iso-8601-in-python/40484010#40484010)
```python
def iso_8601_format(dt):
    """YYYY-MM-DDThh:mm:ssTZD (1997-07-16T19:20:30-03:00)"""

    if dt is None:
        return ""

    fmt_datetime = dt.strftime('%Y-%m-%dT%H:%M:%S')
    tz = dt.utcoffset()
    if tz is None:
        fmt_timezone = "+00:00"#".000Z"
    else:
        fmt_timezone = str.format('{0:+06.2f}', float(tz.total_seconds() / 3600))

    return fmt_datetime + fmt_timezone
```
  
如何建立標籤：
1. 右下選取欲標籤的序列
2. 右下選取欲標籤的類別
3. 在縮圖拖曳欲標籤範圍
4. 在主圖滑鼠框選欲標籤的點
5. 右上 EXPORT 輸出檔案
  
![](https://github.com/yuning-lin/Goodies/blob/main/TutorPics/TRAINSET.PNG)
  
[API 版](https://labelstud.io/guide/)快速標籤多種資料異常與否

## Color Map 選色工具
* [Adobe Color](https://color.adobe.com/zh/create/color-wheel)
  * 左上＞色輪：提供補色、三元群等色號
  * 上方＞探索、趨勢：有很多好看的顏色套組
* [coolors](https://coolors.co/)
  * Start the generator! > 右上三條線 ＞ Explore：有很多好看的顏色套組
  * 點選色號上複製鍵，即可複製色碼
  * 點選色號上 view shadow 可以選擇漸層色號
