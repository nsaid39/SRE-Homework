# Alpine安裝教學
## 下載Alpine iso映像檔

[Alpine官方下載點](https://alpinelinux.org/downloads/)

選擇[3.13.4]版，[STANDARD]標準的[x86_64]  
![](https://i.imgur.com/g9uykHU.jpg)


---
## **VMware設定**
選擇第三個，先處理好硬體設備再安裝OS  
![](https://i.imgur.com/ely5WoB.png)

選擇"Other Linux 5.x kernel 64-bit"  
"5.x kernel"是kernel版本，跟Alpine釋出的版本3.14.3不同  
![VMware Select OS](https://i.imgur.com/Z74Kjgm.jpg)

1.取好的名字讓你上天堂，一眼就能辨別這台VM是做什麼的  
1. A->alpine  
2. R->router  
3. 50->網段  
4. 1->第一台router  

2.路徑放在簡單、好記的位置，不要在亂七八糟的"下載"目錄下
![](https://i.imgur.com/7rn9dSx.png)

1.硬碟大小越大越好。  
通常是與客戶談好需求後，自己再多留一些空間，以便未來公司做擴展時，能有空間再新增。  
2.我們將該虛擬硬碟的檔案不做分割。  
這是做給以往FAT32的檔案系統，因為該系統單一檔案不能超過4GB；而現在則都是NTFS，單一檔案能到16TB，所以就沒有分割的需求了。  
單一檔案也比較好做集中設定、管理。  
![](https://i.imgur.com/ThO5vZi.png)

這裡可以定制硬體設備  
![](https://i.imgur.com/YF5UI5D.jpg)

1.memory  
記憶體越大越好，以前的記憶體很昂貴，但現在技術進步，便宜很多。現在主要的技術難度在於網路頻寬。  
一個Client連進Server所需的資源大概是1Kbytes，所以我們給定2GBytes是很足夠的。  
2.Processors  
處理器核心也是越多越好，主要看你server內執行的程式數有多少來設定。  
3.用不到的硬體設備要刪除  
特別是USB Controller，一旦中毒或資料外洩，損失會非常可觀。  
![](https://i.imgur.com/SZvk4Zg.jpg)


---
## **Alpine安裝**

開機後，預設的登入帳號為 root ，而且沒有密碼。  
![root](https://i.imgur.com/TVgwdT0.jpg)

使用預設指令來安裝Alpine  
```
# setup-alpine
```

*安裝過程中，只要一有輸入錯誤或想反悔就必須^C重來！  
![](https://i.imgur.com/6BWItv0.jpg)

1.輸入鍵盤配置：tw  
2.選擇語系：tw  
![](https://i.imgur.com/Z4b2g9n.jpg)

設定主機名稱（只接受小寫a-z、數字0-9、-號）  
![](https://i.imgur.com/k6VRlLD.jpg)

按"Enter"使用預設的eth0網卡  
"Enter"用DHCP自動配發ip位址  
是否做任何手動網路配置：n  
![](https://i.imgur.com/HNDvLW2.jpg)

設定root密碼：root  
![](https://i.imgur.com/7wVrYYv.png)

選擇時區：Asia  
Taipei  
![timezone](https://i.imgur.com/DoEuysh.jpg)

選擇proxy代理伺服器  
*因為資安問題，公司內網無法透通外網，所以需要透過proxy才能上網  

這裡我們不需要用到proxy代理伺服器，所以"Enter"[none]  
![](https://i.imgur.com/JOMmQfL.jpg)

選擇網路時間伺服器，預設"Enter"[chrony]  
![](https://i.imgur.com/7tvrtv3.jpg)

選擇使用更新的網站  
我們使用交通大學的網站，49  
![](https://i.imgur.com/CLcc7yZ.jpg)

openssh，選擇SSH連線的工具，以進行遠端管理  
![](https://i.imgur.com/YEOnp7H.png)

sda，選擇唯一的sda硬碟  
![](https://i.imgur.com/xOeg7x5.jpg)

sys，將此硬碟做系統用  
![](https://i.imgur.com/CpHdAr9.jpg)

y，格式化這個硬碟  
![](https://i.imgur.com/klvSOeL.jpg)

最後reboot，並拿掉光碟  
![](https://i.imgur.com/qtNfMLC.jpg)
