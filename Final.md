### 加密，並以檔案測試

 本專案非原創，參考自[這裡](https://medium.com/ccclub/ccclub-python-for-beginners-tutorial-613b2fdf38bf)，並以自身理解再次撰寫






首先將要測試的資料存成txt，並嘗試讀出

![image](https://user-images.githubusercontent.com/62200440/149455527-9d9b5806-c849-4271-ace4-6ecbe880f95e.png)



```

for line in open('C:\\Users\\Lin\\Desktop\\textcase.txt'):
    print("檔案裡的資料 : ",line)
f.close()

```

![image](https://user-images.githubusercontent.com/62200440/149455491-888c6c54-d698-4349-a428-c5f72559d041.png)



接著嘗試讀出每個字的ASCII碼

```
theKey=3
strr=[]
with open('C:\\Users\\Lin\\Desktop\\textcase.txt') as f:
    
    for line in f.readline().split():
        
        if(line.isalpha):
            strr=line
            print(strr)
            for getNum in strr:  # 遍歷檔案的內容
                num = ord(getNum)  # 拿到每個字母的ASCII碼，
                print(getNum,"原本的asicc為: " + f'{num}')              
        else:
            theKey = line
f.close()       
        
   ```
   
   ![image](https://user-images.githubusercontent.com/62200440/149455721-e1672ff7-f61c-45d7-8f69-aea26d84d65a.png)

   
   
   
   
   進行位移
   
   ```
theKey=3
strr=[]
with open('C:\\Users\\Lin\\Desktop\\textcase.txt') as f:
    
    for line in f.readline().split():
        
        if(line.isalpha):
            strr=line
            print(strr)
            for getNum in strr:  # 遍歷檔案的內容
                num = ord(getNum)  # 拿到每個字母的ASCII碼，
                num2 = num
                num2 += theKey  # 針對位移量進行移動
                print("原本的asicc為: " + f'{num}')   
                print("經過位移的數字為: ",f'{num2}', " 轉換後為" + chr(num2))
                #mystring = str(num2)
           
        else:
            theKey = line
            #print(theKey)
    f.close()      
   ```
   
   
   
   即可得到
   
     
![image](https://user-images.githubusercontent.com/62200440/149455346-bcecd7a2-3e46-42c2-92bf-26479d850fad.png)


      
   
