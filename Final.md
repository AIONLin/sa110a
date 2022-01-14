### 加密，並以檔案測試

 本專案非原創，參考自[這裡](https://medium.com/ccclub/ccclub-python-for-beginners-tutorial-613b2fdf38bf)，並以自身理解再次撰寫






首先將要測試的資料存成txt，並嘗試讀出

![image](https://user-images.githubusercontent.com/62200440/149453851-c365c9a3-203c-4d82-bbc3-49ee8399029f.png)



```

for line in open('C:\\Users\\Lin\\Desktop\\textcase.txt'):
    print(line)
f.close()

```

![image](https://user-images.githubusercontent.com/62200440/149453909-725a8cb8-5a66-495c-83f1-4cf0be6feaca.png)



接著嘗試讀出每個字的ASCII碼

```
theKey=int()
strr=[]
with open('C:\\Users\\Lin\\Desktop\\textcase.txt') as f:    
    for line in f.readline().split():
        if(line.isalpha):
            strr=line
            print(strr)
            for getNum in strr:  # 遍歷所讀檔案內容
                num = ord(getNum)  # 拿到每個字母的ASCII碼
                num2 = num
                print("原本的asicc為: " + f'{num}')

           
        else:
            theKey = line
            #print(theKey)
        
   ```
   
   
   即可得到
   
     
![image](https://user-images.githubusercontent.com/62200440/149453746-cfb4da56-013f-47cc-9000-370e234d169b.png)

      
   
