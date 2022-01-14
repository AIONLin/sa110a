## Caesar cipher 實作

此程式碼非原創，參考過後進行思考與嘗試，思路與部分程式碼參考自 https://iter01.com/570152.html`11

初步處理 : 先拿到所輸入字串的ASCII碼，與使用者輸入位移量　　

接著ASCII碼加上位移量　


```
strr = input("Enter your input: ")  # 先輸入字串
theKey = int(input("Enter a Number: ")) # 輸入數字 當位移量
#ord(strr) ord只收字元 並將她轉成ASCII碼

for getNum in strr:  # 遍歷剛剛輸入的字串
        num = ord(getNum)  # 拿到每個字母的ASCII碼
        num2 = num
        num2 += theKey  # 針對位移量進行移動
        
        #mystring = str(num2)
        print("原本的asicc為: " + f'{num}')
        print("經過位移的數字為: ",f'{num2}')

print("接收到的input是 : ", strr )
print("")
```

結果：　

　
![image](https://user-images.githubusercontent.com/62200440/149460048-8715ef2e-49b9-4248-859b-2fe3d9dc28a5.png)


將位移後結果轉換

```
print("經過位移的數字為: " , f'{num2}' , " 轉換後為" + chr(num2))
```
會出現其他非英文字母的符號

![image](https://user-images.githubusercontent.com/62200440/149460216-1590a624-5a34-4811-9f8a-01613b5c1fda.png)


對照[ASCII轉換的圖](https://commons.wikimedia.org/wiki/File:ASCII-Table-wide.svg)可知，加上位移量轉換後會超出英文字母範圍

![image](https://user-images.githubusercontent.com/62200440/149460431-e67cf273-32ad-4f4e-b180-84cab3ce568c.png)



所以接著要對超出英文字母範圍的碼進行進行加減
```
    if getNum.isupper():     # 先判斷大小寫
        if num2 > ord('Z'):    # 如果加上位移量後比Z的ASCII還大 就-
            num2 -=26         
        elif num2 < ord('A'):    # 如果加上位移量後比A的ASCII還小 就+
            num2 +=26
    elif getNum.islower():
        if num2 > ord('z'):           # 如果加上位移量後比z的ASCII還大 就-
            num2 -=26
        elif num2 < ord('a'):         # 如果加上位移量後比a的ASCII還小 就+
            num2 +=26
    
    after += chr(num2)
```    
結果:


![image](https://user-images.githubusercontent.com/62200440/149460885-9d9fd8ca-5a5f-4093-b6f4-1dcbf055bd86.png)


雖然解決超出英文ASCII碼的問題，但仍然可見有奇怪的字混入　　

這是因為空白鍵也被進行運算了　　　

所以下一個步驟是將非英文的字元抓出來　　

```  
 if getNum.isalpha():
 　　才進行位移運算　　
 else:　
      after += getNum　否則將他放回去
```  

結果：


![image](https://user-images.githubusercontent.com/62200440/149461286-9c285dc3-b78e-45d0-bf4e-c7217db0ebb5.png)


字串已經可以正確的加密了


### 解密

在已知位移量的情況下可以直接推回去
```  
theKey = -theKey       (將剛剛的位移量推回去)
```  

![image](https://user-images.githubusercontent.com/62200440/149461568-8e864f91-3ecb-47c6-a159-340d36addcc4.png)

簡易的Caesar cipher實作已經完成

``` 
其他解密的方法還有窮舉法、頻率分析或者樣式單詞分析等等
``` 

[參考資料](https://zh.wikipedia.org/wiki/%E5%87%B1%E6%92%92%E5%AF%86%E7%A2%BC)
