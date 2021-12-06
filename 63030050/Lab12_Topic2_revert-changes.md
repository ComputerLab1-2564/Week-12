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

6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)
![image](https://user-images.githubusercontent.com/92082350/144760803-6c8f9de2-df43-433c-b287-34bba204a933.png)


7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)
![image](https://user-images.githubusercontent.com/92082350/144761176-4efff349-6772-48ae-8e6b-2e6976de4c82.png)


8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)
![image](https://user-images.githubusercontent.com/92082350/144761201-8a3488e7-7d15-4ec0-8815-7f1875ee78de.png)

8.1 

![](./images/Lab12-fig10.png)
![image](https://user-images.githubusercontent.com/92082350/144761362-6a56fecf-1045-4a57-82c0-c0770e419c9b.png)


![](./images/Lab12-fig11.png)
![image](https://user-images.githubusercontent.com/92082350/144761442-81d9eab7-7e05-4096-aa14-b1aa07ac634c.png)



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
![image](https://user-images.githubusercontent.com/92082350/144761537-30788adb-45aa-4bc4-a62c-f2f2f72dd285.png)


ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)
![image](https://user-images.githubusercontent.com/92082350/144761557-5919b43d-2497-4c88-a984-232290211a4d.png)


2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)
![image](https://user-images.githubusercontent.com/92082350/144761645-1ba151b3-7deb-44ea-b6c9-b042bcfac16c.png)

จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)
![image](https://user-images.githubusercontent.com/92082350/144761776-65a13380-5445-48af-b65f-a550136b96ce.png)


5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)
![image](https://user-images.githubusercontent.com/92082350/144761799-699e3ee7-5933-4556-a057-9615ec7506a7.png)


### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)
![image](https://user-images.githubusercontent.com/92082350/144761809-bf47f4c0-6efe-4a4c-9aa5-64c282004ed1.png)



![](./images/Lab12-fig18.png)
![image](https://user-images.githubusercontent.com/92082350/144761821-f6dca968-1ddd-4005-86d9-61f0d5b7c4a2.png)

---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)

![](./images/Lab12-fig20.png)
![image](https://user-images.githubusercontent.com/92082350/144761995-29c0aff7-5652-4215-9f70-663f1a88121e.png)
![image](https://user-images.githubusercontent.com/92082350/144762009-0615fe83-0c65-4c36-9019-da875ecd0ad2.png)


2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)
![image](https://user-images.githubusercontent.com/92082350/144762027-159368ab-f199-47c1-96ba-7c85a5090efb.png)


3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)
 ![image](https://user-images.githubusercontent.com/92082350/144762115-35a93a96-278d-47a2-9261-7628a2a145cc.png)


### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)

5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)
![image](https://user-images.githubusercontent.com/92082350/144762184-b2ed310c-76b3-4822-a108-c1825afddf29.png)


### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)

![](./images/Lab12-fig26.png)

7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)
![image](https://user-images.githubusercontent.com/92082350/144762205-4c726192-5021-4023-9ab8-5b82780259eb.png)

