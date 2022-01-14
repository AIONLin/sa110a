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

