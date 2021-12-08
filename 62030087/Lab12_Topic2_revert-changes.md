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
![image](https://user-images.githubusercontent.com/71489984/145278314-25812203-95b2-443c-b784-215bba9572f6.png)

6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)
![image](https://user-images.githubusercontent.com/71489984/145278340-3a0b025c-fbd2-41d4-9ce5-330104076acb.png)

7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)
![image](https://user-images.githubusercontent.com/71489984/145278400-6e65c4ca-a7f2-4bba-b9a9-c58ab64d09c1.png)

8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)
![image](https://user-images.githubusercontent.com/71489984/145278434-afac66a1-3348-496e-8327-e05428f03984.png)

8.1 

![](./images/Lab12-fig10.png)
![image](https://user-images.githubusercontent.com/71489984/145278460-db05facc-62c9-456f-832a-7a46d55a182b.png)


![](./images/Lab12-fig11.png)
![image](https://user-images.githubusercontent.com/71489984/145278491-bba1d23f-1b5b-48b6-a5fa-4c4602d157d2.png)


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
![image](https://user-images.githubusercontent.com/71489984/145278559-b3fd6454-b4d5-4bfe-bbbb-3903c9d9d9c2.png)


ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)
![image](https://user-images.githubusercontent.com/71489984/145278583-74b80aff-6fb6-447d-a4be-93a0117bd8fb.png)


2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)
![image](https://user-images.githubusercontent.com/71489984/145278673-1960f26c-21e0-4c46-b4bc-628318d9b0ce.png)

จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)
![image](https://user-images.githubusercontent.com/71489984/145278725-94379567-b3aa-4144-a2cf-da605b3084b9.png)

5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)
![image](https://user-images.githubusercontent.com/71489984/145278772-0d3df0d5-f9dc-4db2-8cb7-8270ee4999fd.png)


### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)
![image](https://user-images.githubusercontent.com/71489984/145278799-93cfd908-737b-4057-886c-c1e97fb8afa4.png)



![](./images/Lab12-fig18.png)
![image](https://user-images.githubusercontent.com/71489984/145278818-8fc7d9eb-587f-411c-8c3c-7c131e544552.png)

---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)
![image](https://user-images.githubusercontent.com/71489984/145278974-da475f55-4449-4e36-94d8-8785da818e8a.png)

![](./images/Lab12-fig20.png)
![image](https://user-images.githubusercontent.com/71489984/145279007-478c2d52-6d70-4c54-bca3-61e8c52b7878.png)


2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)
![image](https://user-images.githubusercontent.com/71489984/145279070-13d8227a-ca5a-4fae-9bc7-693a6c099b0f.png)


3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)
 ![image](https://user-images.githubusercontent.com/71489984/145279124-1e3f0672-b315-4b09-95ba-fc565a08a9ad.png)


### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)
![image](https://user-images.githubusercontent.com/71489984/145279211-cc19850c-3dc2-42c9-ba98-73ca99e0392f.png)

5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)
![image](https://user-images.githubusercontent.com/71489984/145279244-18ab8992-4c04-41c9-bf02-e879a0ab9672.png)


### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)
![image](https://user-images.githubusercontent.com/71489984/145279266-604aef2c-770a-43f6-8707-ba0bbe327124.png)

![](./images/Lab12-fig26.png)
![image](https://user-images.githubusercontent.com/71489984/145279287-64042f6f-0f4a-468f-890f-78ab9ab2d1f7.png)

7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)
![image](https://user-images.githubusercontent.com/71489984/145279353-042d92c6-ca36-4de8-9fe3-9ca6d32f844e.png)

