# What is kernel
kernel是linux作業系統中的核心程式，他可以管理、控制如Mem、HD、cpu、Network等硬體。  
收到來自位於使用者空間(user space)的程式或指令，來控制、管理硬體。  
但要能使用kernel空間必須要有root的權限。  
kernel空間的模組(module)是動態的，只有呼叫到才會掛載，
而硬體是靜態的寫死在裡面。  
![](https://i.imgur.com/1t0ZXZb.png)  
---
查看這個linux有多少核心module
```
$ lsmod
```