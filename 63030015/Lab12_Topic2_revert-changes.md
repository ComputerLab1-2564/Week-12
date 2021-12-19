# การทดลองสัปดาห์ที่ 12 #
# เจาะลึกการใช้งาน git #


---
### อุ๊ย ผิดแล้ว ทำไงดี ###

บ่อยครั้งที่เราแก้ไขงานแล้วผิดไปเยอะ อยากได้ของเดิมคืนมา จะให้ git ช่วยยังไงดี
git ช่วยได้หลายขั้นตอนเลย
1. ยกเลิกการแก้ไฟล์ก่อนที่จะ staging ด้วยคำสั่ง ```git add``` 
2. ยกเลิกการแก้ไฟล์ก่อนที่จะ commit ด้วยคำสั่ง ```git commit```
3. ยกเลิกการ commit

### ขั้นตอนการทดลอง ###

## 1. ยกเลิกการแก้ไขไฟล์ที่ยังไม่ทำการ ```git add``` ###


1. ทำการ fork  [https://github.com/ComputerLab1-2564/week12-Commit](https://github.com/ComputerLab1-2564/week12-Commit)  มาไว้ใน account ของตนเอง
2. ใช้ git bash ทำการ clone มาไว้ที่เครื่อง (```git clone <Repository URL>```) หรือ clone ด้วย github desktop แล้วเปิด git bash ในภายหลังก็ได้
3. ดูใน git bash ให้แน่ใจว่าอยู่ที่ branch ชื่อ main *(บางระบบจะตั้งชื่อ branch หลักว่า master)*  ถ้าอยู่ที่ branch อื่่นๆ ให้ใช้คำสั่ง ```git checkout <main|master>```
4. เปิดโปรแกรม github desktop ขึ้นมา เราจะใช้มันเป็นตัวแสดงความแตกต่างของไฟล์ 
5. แก้ไขไฟล์ Readme.md ด้วย editor ที่ชอบ **แล้วบันทึกไฟล์**

![](./images/Lab12-fig6.png)

![image](https://user-images.githubusercontent.com/92082259/146556295-c082d83d-ccf9-4a7d-ae69-ce4f39726610.png)

6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)

![image](https://user-images.githubusercontent.com/92082259/146556465-65c30121-63d6-44b7-a596-f7264000c388.png)

7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)

![image](https://user-images.githubusercontent.com/92082259/146556773-878ba4f8-cc35-4c31-b482-6e2929f1bf88.png)

8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)

![image](https://user-images.githubusercontent.com/92082259/146557018-82d798a1-1a71-416d-af6b-7db262c7ad2f.png)

8.1 

![](./images/Lab12-fig10.png)

![image](https://user-images.githubusercontent.com/92082259/146557158-5fa100a5-ea55-454a-9086-25f0a00eb2ba.png)

![](./images/Lab12-fig11.png)

![image](https://user-images.githubusercontent.com/92082259/146557264-dbd8defe-6c4f-4fc7-9dcf-2b2e70958359.png)


สิ่งที่แก้ไข จะถูกไฟล์ที่อยู่ใน local repository เขียนทับไปแล้ว และกลับเป็นเหมือนเดิมก่อนมีการแก่ไขไฟล์นั้น
**ถ้าเป็น source code ที่มีการแก้ไขจนเกิดการผิดพลาดที่หลายตำแหน่ง วิธีนี้จะช่วยกู้คืนงานเราได้**
**ควร commit บ่อยๆ เพราะว่าเวลากู้คืนจะไม่เสียเวลางานมาก**

**ควร commit เฉพาะงานที่ work เพราะว่าจะมีประโยชน์มากกว่าการ commit งานที่เสร็จครึ่งๆ กลางๆ เว้นเสียแต่วันนี้ยังทำไม่เสร็จ ต้อง commit ไว้ก่อน**


---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git add``` และก่อน ```git commit```###

หลังจากที่เราทำการ add ไฟล์ใดๆ เข้าไปยัง staging area แล้ว มันจะพร้อมสำหรับการ commit และ/หรือ push ไปยัง remote repository
แต่ในบางครั้ง มีบางเหตุผลที่ต้องยกเลิกการ add ไฟล์ เราสามารถทำได้ตามขั้นตอนต่อไปนี้
### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig12.png)

![image](https://user-images.githubusercontent.com/92082259/146560622-4c4d7fda-f4e6-4646-ab96-1868eae5db72.png)


ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)

![image](https://user-images.githubusercontent.com/92082259/146558738-be6e4740-6d7f-4720-8438-9697f55b38fc.png)


2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)

![image](https://user-images.githubusercontent.com/92082259/146559053-93607a5e-7c8e-473b-8b1e-7b0903dbcaa4.png)

จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)

![image](https://user-images.githubusercontent.com/92082259/146559363-50b6d6b0-b5d2-4b12-893f-f44a615ba916.png)

5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)

![image](https://user-images.githubusercontent.com/92082259/146559714-905b509b-90fd-465d-9eb8-759ee74a64e1.png)


### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)

![image](https://user-images.githubusercontent.com/92082259/146559819-0039d7c9-a909-4198-adc0-51bf2f1968f5.png)



![](./images/Lab12-fig18.png)

![image](https://user-images.githubusercontent.com/92082259/146559891-e993b67a-e57c-4147-b58a-f68dce97f609.png)

---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)

![image](https://user-images.githubusercontent.com/92082259/146561229-0479c570-3cb7-4937-9684-cf4a4c2c45cd.png)


![](./images/Lab12-fig20.png)

![image](https://user-images.githubusercontent.com/92082259/146561376-438a34e9-5a22-4bd4-a669-9dfe3aa7dbeb.png)


2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)

![image](https://user-images.githubusercontent.com/92082259/146562344-d6b5d93e-380d-48f6-ade9-3af656bd0cad.png)


3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)
![image](https://user-images.githubusercontent.com/92082259/146562846-683177cb-b664-43d4-9b59-5482ea8e2f73.png)

 

### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)

![image](https://user-images.githubusercontent.com/92082259/146562993-8c573eb7-b365-401f-afdf-03d69c0cdd43.png)
5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)

![image](https://user-images.githubusercontent.com/92082259/146563642-b0569f92-cdac-461a-9fcd-64283170f7f2.png)


### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)
![image](https://user-images.githubusercontent.com/92082259/146563805-0f1fc168-3d05-4003-a10e-3f6bfc78c947.png)
![](./images/Lab12-fig26.png)

![image](https://user-images.githubusercontent.com/92082259/146559891-e993b67a-e57c-4147-b58a-f68dce97f609.png)
7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)
![image](https://user-images.githubusercontent.com/92082259/146564143-8f44317c-c680-42ec-9f97-bb4b1a11acc1.png)

