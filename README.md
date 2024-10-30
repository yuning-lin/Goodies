## Goodies
Record useful tools or websites  
紀錄不錯的學習程式平台  
以及寫程式以外，對學習有幫助的影音內容，或可立即使用看效果的軟體或工具  

## 綱要
### programming
* [W3Schools：各種知名程式入門](https://www.w3schools.com/)
* [菜鳥教程：各種知名程式入門](https://www.runoob.com/)
* [RefactoringGuru：各種知名程式進階設計模式](https://refactoringguru.cn/design-patterns/python)
* [CodeBeautify：html、css 等視覺化線上轉換](https://codebeautify.org/)
* [regexr：正則表達式線上轉換](https://regexr.com/)
* [Google Cloud Skills Boost：Google 雲端程式、非程式技巧](https://www.cloudskillsboost.google/paths)

### non-programming
* [YouTube：天文物理數學歷史等知識型老師李永樂](https://www.youtube.com/c/%E6%9D%8E%E6%B0%B8%E4%B9%90%E8%80%81%E5%B8%88)
* [Tool：Way to Access Papers](https://sci-hub.se/)
* [Tool：Free Labeling](https://github.com/yuning-lin/Goodies#free-labeling-tool%E6%99%82%E9%96%93%E5%BA%8F%E5%88%97%E8%B3%87%E6%96%99)
* [Tool：選色工具－Adobe Color](https://github.com/yuning-lin/Goodies#color-map-%E9%81%B8%E8%89%B2%E5%B7%A5%E5%85%B7)
* [Tool：選色工具－Coolors](https://github.com/yuning-lin/Goodies#color-map-%E9%81%B8%E8%89%B2%E5%B7%A5%E5%85%B7)
* [Tool：介面設計工具 Figma](https://www.figma.com/)
* [Tool：線上白板 Miro](https://miro.com/)
* [Tool：截圖工具 Snipaste](https://www.snipaste.com/download.html#)
* [Blog：Data 📊 關於資料科學 … 我想說的是(上、中、下)](https://medium.com/%E7%A8%8B%E5%BC%8F%E7%8C%BF%E5%90%83%E9%A6%99%E8%95%89/data-science/home)

### GPT
* [Fast & Free & GPTs Bots Store](https://flowgpt.com/)
* [Chatgpt 指令大全－中文介面](https://www.explainthis.io/zh-hant/chatgpt)
* [Chatgpt 指令大全－英文介面](https://contentatscale.ai/ai-prompt-library/)
* [ChatGPT Prompt : 各職業詠唱大全](https://domyweb.org/chatgpt/#act-as-a-keyword-researcher)
* [AI Prompt Optimizer](https://promptperfect.jina.ai/)

## 實作
### Free Labeling Tool－時間序列資料
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

### Color Map 選色工具
* [Adobe Color](https://color.adobe.com/zh/create/color-wheel)
  * 左上＞色輪：提供補色、三元群等色號
  * 上方＞探索、趨勢：有很多好看的顏色套組
* [Coolors](https://coolors.co/)
  * Start the generator! > 右上三條線 ＞ Explore：有很多好看的顏色套組
  * 點選色號上複製鍵，即可複製色碼
  * 點選色號上 view shadow 可以選擇漸層色號
