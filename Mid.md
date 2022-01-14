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


