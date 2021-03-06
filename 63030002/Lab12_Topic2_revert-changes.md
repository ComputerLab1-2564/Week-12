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

![image](https://user-images.githubusercontent.com/92086229/146633666-e6a772ee-a254-4285-bd38-0bc4ba5ee21d.png)

6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)

![image](https://user-images.githubusercontent.com/92086229/146633698-e768b254-3685-46d0-91fd-a8fe9c2e39d6.png)

7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)

![image](https://user-images.githubusercontent.com/92086229/146633727-151ff1ed-5bba-49b8-a05f-a581a8bf5134.png)

8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)

![image](https://user-images.githubusercontent.com/92086229/146633742-6e5e468a-0f2e-404d-aee7-3d658a6982a2.png)

8.1 

![](./images/Lab12-fig10.png)

![image](https://user-images.githubusercontent.com/92086229/146633759-d2a14eae-7fa4-4671-b595-10d624d88eff.png)


![](./images/Lab12-fig11.png)

![image](https://user-images.githubusercontent.com/92086229/146633770-1eadb9b0-84bf-4410-8e42-ee1ca472cf53.png)


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

![image](https://user-images.githubusercontent.com/92086229/146633806-6c8afa8c-66f6-471c-8455-f3c24d6fc2ed.png)

ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)

![image](https://user-images.githubusercontent.com/92086229/146633819-242afe8c-d938-458b-bf27-e6db6dbadedf.png)


2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)

![image](https://user-images.githubusercontent.com/92086229/146633860-4345bb31-4320-4a29-ac8f-6cc268bff834.png)

จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)

![image](https://user-images.githubusercontent.com/92086229/146633904-38aee0ea-6694-4616-afdf-57abf5f0159e.png)

5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)

![image](https://user-images.githubusercontent.com/92086229/146634013-230f7da7-cb99-4caf-9925-ec9e7021a7d0.png)


### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)

![image](https://user-images.githubusercontent.com/92086229/146634072-d4a3d1e8-4259-4e35-a936-7c54569b247d.png)



![](./images/Lab12-fig18.png)

![image](https://user-images.githubusercontent.com/92086229/146634075-ca9297af-f565-4fbf-a882-ff215865c8b8.png)

---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)

![image](https://user-images.githubusercontent.com/92086229/146634119-b14825db-5b2a-4f0a-a3ea-7ffc011c9cda.png)

![](./images/Lab12-fig20.png)

![image](https://user-images.githubusercontent.com/92086229/146634123-ef0bcef9-e483-422f-83f6-bbd2e42c947b.png)


2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)

![image](https://user-images.githubusercontent.com/92086229/146634173-d85ec39a-6b57-4f38-9393-fb53f5397f9b.png)


3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)

![image](https://user-images.githubusercontent.com/92086229/146634263-8b7f9db7-7652-48c9-a5d8-bdf1363bc692.png)
 

### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)

![image](https://user-images.githubusercontent.com/92086229/146634294-89bebb3c-2b19-46fd-9fba-adcc75123062.png)

5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)

![image](https://user-images.githubusercontent.com/92086229/146634318-c328e57f-8be5-4478-8307-77746ac194dd.png)


### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)

![image](https://user-images.githubusercontent.com/92086229/146634358-053c9c9a-ccbf-4e5d-925d-d0a163f0e518.png)

![](./images/Lab12-fig26.png)

![image](https://user-images.githubusercontent.com/92086229/146634363-e37ca880-b743-46d4-8220-03690161de1f.png)

7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)

![image](https://user-images.githubusercontent.com/92086229/146634399-4624a038-becc-46ba-b6c5-7d30f63239f4.png)

