# `st.button`

`st.button` 可以顯示一個按鈕部件。

## 我們正在建立什麼？

一個簡單的應用程式，能按照不同條件印出不同的訊息，根據按鈕有無被按下

程式的流程：

1. 預設狀況下，程式印出 `Goodbye`
2. 點擊按鈕後，程式顯示第二則訊息 `Why hello there`

## Demo 應用程式

部署的 Streamlit 應用程式應該類似下面這個連結的應用程式：

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/dataprofessor/st.button/)

## 程式碼

這裡是實現上述應用程式的程式碼：

```python
import streamlit as st

st.header('st.button')

if st.button('Say hello'):
     st.write('Why hello there')
else:
     st.write('Goodbye')
```

## 逐行解釋

建立 Streamlit 應用程式時，第一件事情是載入 `streamlit` 套件為 `st`：

```python
import streamlit as st
```

接著建立 header 的文字：

```python
st.header('st.button')
```

然後，我們使用條件判斷式 `if` 和 `else` 來印出第二則訊息

```python
if st.button('Say hello'):
     st.write('Why hello there')
else:
     st.write('Goodbye')
```

從上面程式碼中我們可以看到，`st.button()` 指令可以接收 `label` 輸入參數，為 `Say hello`，也就是按鈕上面顯示的文字

`st.write` 指令則是用來印出文字訊息 `Why hello there` 或 `Goodbye`，根據按鈕是否被點擊，透過以下方式實現：

```python
st.write('Why hello there')
```

和

```python
st.write('Goodbye')
```

需要注意的是，上述 `st.write` 要背被放在 `if` 和 `else` 中，用來執行上面訊息顯示的過程

## 下一步

現在你已經在本地建立了 Streamlit 應用程式，是時候部署到 [Streamlit Community Cloud](https://streamlit.io/cloud)，後面的挑戰很快就會解釋這是什麼

因為這是你第一周的挑戰，我們在網頁內提供了完整的程式碼（像是上面 code block）還有解法（demo 應用程式）

在接下來的挑戰中，建議你先試著自己實現 Streamlit 應用程式

如果你卡住了，別擔心～你可以隨時偷看解法

## 參考資料

閱讀 Streamlit API 文件中的 [`st.button`](https://docs.streamlit.io/library/api-reference/widgets/st.button)
