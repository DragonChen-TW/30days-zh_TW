# `st.write`

`st.write` 允許把文字和參數寫入到 Streamlit 應用程式

除了能顯示文字外，還可以使用 `st.write()` 指令顯示下面內容：

- 印出字串，像 `st.markdown()` 一樣
- 顯示 Python `dict`
- `pandas` 的 DataFrame 可以顯示像是 table 一樣
- 圖表從 `matplotlib`、`plotly`、`altair`、`graphviz`、`bokeh`
- 更多東西（看看 [`st.write` on API 文件](https://docs.streamlit.io/library/api-reference/write-magic/st.write)）

## 我們正在建立什麼？

一個簡單的應用程式顯示怎麼使用 `st.write()` 的多種方式：文字、數字、DataFrame 和 圖表

## Demo 應用程式

部署的 Streamlit 應用程式應該類似下面這個連結的應用程式：

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/dataprofessor/st.write/)

## 程式碼

這裡是如何使用 `st.write`：

```python
import numpy as np
import altair as alt
import pandas as pd
import streamlit as st

st.header('st.write')

# Example 1

st.write('Hello, *World!* :sunglasses:')

# Example 2

st.write(1234)

# Example 3

df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)

# Example 4

st.write('Below is a DataFrame:', df, 'Above is a dataframe.')

# Example 5

df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)
```

## 逐行解釋


建立 Streamlit 應用程式時，第一件事情是載入 `streamlit` 套件為 `st`：

```python
import streamlit as st
```

接著建立 header 的文字：

```python
st.header('st.write')
```

**Example 1**
最基礎的用法是顯示**純文字**和使用 **Markdown 語法** 的格式化文字：

```python
st.write('Hello, *World!* :sunglasses:')
```

**Example 2**
上面有提到，也可以永來顯示其他資料格式，例如數字：

```python
st.write(1234)
```

**Example 3**
DataFrames 也可以被顯示出來：

```python
df = pd.DataFrame({
     'first column': [1, 2, 3, 4],
     'second column': [10, 20, 30, 40]
     })
st.write(df)
```

**Example 4**
你可以傳多個參數進去：

```python
st.write('Below is a DataFrame:', df, 'Above is a dataframe.')
```

**Example 5**
最後，你也可以透過傳參數的方式顯示圖表：

```python
df2 = pd.DataFrame(
     np.random.randn(200, 3),
     columns=['a', 'b', 'c'])
c = alt.Chart(df2).mark_circle().encode(
     x='a', y='b', size='c', color='c', tooltip=['a', 'b', 'c'])
st.write(c)
```

## 下一步

現在你已經在本地建立了 Streamlit 應用程式，是時候來部署到 [Streamlit Cloud](https://streamlit.io/cloud)，很快地，後面的挑戰就會提到

因為這是你第一周的挑戰，我們在網頁內提供了完整的程式碼（像是上面 code block）還有解法（demo 應用程式）

在接下來的挑戰中，建議你先試著自己實現 Streamlit 應用程式

如果你卡住了，別擔心～你可以隨時偷看解法

## 後續閱讀

除了 [`st.write`](https://docs.streamlit.io/library/api-reference/write-magic/st.write)，你可以探索其他顯示文字的方式：

- [`st.markdown`](https://docs.streamlit.io/library/api-reference/text/st.markdown)
- [`st.header`](https://docs.streamlit.io/library/api-reference/text/st.header)
- [`st.subheader`](https://docs.streamlit.io/library/api-reference/text/st.subheader)
- [`st.caption`](https://docs.streamlit.io/library/api-reference/text/st.caption)
- [`st.text`](https://docs.streamlit.io/library/api-reference/text/st.text)
- [`st.latex`](https://docs.streamlit.io/library/api-reference/text/st.latex)
- [`st.code`](https://docs.streamlit.io/library/api-reference/text/st.code)
