# HTB-Keeper Writeup
> Ｏ鈞 & Ｏ樺

## Step 1: Nmap

掃描後發現只有開22和80

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/48300b45-760b-41fc-a751-7b283b03528d)

80上面有Nginx伺服器
連連看

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/bb321619-51f7-46e8-882c-3b41054b5592)

要到"tickets.keeper.htb"
在hosts檔案中加入路徑

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/82a8d827-a327-4308-84c0-213192b82e52)

## Step 2: Request Tracker

進到了一個Request Tracker的網站

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/90976bb3-2386-4616-be97-ef0763e0d7bf)

上網找一下有沒有預設的帳號密碼

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/42a551b0-4b39-42d9-9b86-8f4a5bb93c78)

Username:root
password:password

成功進來了，到處點點看看有甚麼酷東西

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/c981c323-0785-4dd4-a47e-c9d06bf601ec)

在Admin的選單下面發現有User的選項
點進去發現有另一個user

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/ff47bdb7-3542-41a6-9916-964bfd8ab6e5)

發現他是新用戶，密碼是Welcome2023!

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/38929d8f-5acb-43fe-b5a6-93c073bb4d2f)

## Step 3: SSH

利用ssh登入看看他的帳號

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/63e9e3d6-1391-4491-91ed-19b07d000ed8)

找到user.txt ---> 找到第一個flag了

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/7a1e568f-fff3-49f4-9264-67b0ce6da320)

## Step 4: KeePass

解壓縮RT3000.zip這個檔案發現有KeePass的dmp檔和kdbx檔

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/dbd946d8-f391-4d3b-ab20-42c2efc459b8)

google一下有甚麼
[KeePass Exploit](https://www.linkedin.com/pulse/steal-keepass-2x-254-master-password-chance-johnson)

okay來找找看網路上有甚麼寶藏可以用的
[KeePass dump master key](https://github.com/matro7sh/keepass-dump-masterkey)

把兩個檔案都搞到本機上來

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/564d3e22-de6d-4ea4-93a5-4cbbc1771108)

py時間

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/d18ebd89-2f49-45de-80f6-3d303876ac1e)

發現密碼裡有特殊字元
●,dgr●d med fl●de

遇事不覺丟google

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/d823e634-6a14-4147-a052-cab1670150fe)

發現可能是某種食物的名字
Rødgrød med Fløde可能就是密碼

打開KeePass試試看

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/22a1da71-db40-4a2e-a8e8-2ebcb77140d5)

密碼錯了

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/22f05817-02b0-4ef8-af8e-f4ee4fabc168)

都換成小寫試試看

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/5346c8c6-d766-414e-be16-c94e22c8bb44)

成功進去了

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/dab43819-34c6-4fa3-addf-daff63ec4e43)

## Step 5: Putty
把putty金鑰存下來

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/329c87f5-f2b3-48ac-b48a-191087f16dca)

生成pem檔案並改變權限

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/e8492c75-a5eb-4173-afad-9e0e13b39077)

ssh

![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/d995af62-7b74-4249-9b5f-b587aa51a8f7)

## GET FLAG
![image](https://github.com/TwMoonBear-Arsenal/Pub-ClassWork/assets/25276693/58de7fee-f84c-43b0-844a-0dfa1857ecad)



