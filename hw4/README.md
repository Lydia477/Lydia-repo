# LINE Chatbot 評論反應機制  
> 前面多次嘗試想要將情感分析結果在輸出時修改為中文呈現，但並沒有成功。而最後做出來的結果，除了上課所學的情感分析結果以外，我自己也加入了評論分數和評論目標兩個欄目，以下是我加入的程式碼說明。

首先在評論分數部份我加入和修改的程式碼如下:  
const scoreMap = {
  'positive': 5,// 正面評價映射為高分  
  'negative':1,// 負面評價映射為低分  
  'neutral': 3// 中性評價映射為中等分數  
};

const sentiment = results[0].sentiment;  
const score = scoreMap[sentiment];  // 根據情感分析結果獲取對應的評分

text: `情感分析結果：${sentiment}\n評論分數：${score}`

const echo = {  
  type: 'text',  
  text: `情感分析結果：${sentiment}\n評論分數：${score}`  
};

而我在測試了評論分數和情感分析結果都可以同時輸出後，就覺得可以再加上評論目標這個欄目，更容易將評論做分類和檢視。以下是我加入和修改的程式碼:  
const echo={  
    type:'text',  
    text:`情感分析結果：${sentiment}\n評論分數：${score}\n評論目標：${newData.opinionText}`  

最後附上LINE的測試截圖(圖片也放置在此資料夾hw4中)  
![LINE Chatbot截圖1]("hw4/79590.jpg")  
![LINE Chatbot截圖2]("hw4/79591.jpg")  
![LINE Chatbot截圖3]("https://github.com/Lydia477/Lydia-repo/blob/main/hw4/79592.jpg?raw=true") 
