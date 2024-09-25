# 商品匹配

## 目錄

- [環境設置](#環境設置)
- [參數設置](#參數設置)

### 環境設置

執行以下指令以安裝必要模組

```bash
pip install -r requirements.txt
```

### 參數設置

打開 `scraper.ipynb` ，找到 **Parameter Setting** 部分。在這裡，您可以定義或修改以下參數：

1. **query_path**: 搜尋詞的路徑。
2. **results_search**: 保存搜尋到的100筆資料。
3. **results_sorted**: 保存經BM25比對後的結果。
4. **short_time_sleep**: 等待時間(短)。
5. **medium_time_sleep**: 等待時間(中)。
6. **long_time_sleep**: 等待時間(長)。

### 說明及已知問題

先將兩個網站資料存至csv，由csv讀出資料使用BM25比對，再將比對結果轉換為word格式，可點擊商品名稱開啟目標網頁
以MOMO的名稱建立model，再套入PChome名稱進行比對，找出最適合的，因此一個MOMO商品可能對應到多個PChome商品
商品排序由分數高至低
如果MOMO的商品筆數過少，則大多錯誤
其中一個網站缺乏搜尋結果，則跳過比對
MOMO有些商品大於100項，但沒有下一頁按鈕，只抓到前30項，未解決