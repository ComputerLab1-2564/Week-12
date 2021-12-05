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
![image](https://user-images.githubusercontent.com/92082685/144747633-c6d4e952-bfda-4fd5-a8aa-733b206f80bd.png)

6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)
![image](https://user-images.githubusercontent.com/92082685/144747505-d364ea83-5c43-427f-97d1-680e1500d30a.png)

7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)
![image](https://user-images.githubusercontent.com/92082685/144747527-4b6100cc-3607-4044-9af2-82f69f223907.png)

8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)
![image](https://user-images.githubusercontent.com/92082685/144747554-0a9339fd-dc62-4e5f-b41a-9ea5fe918665.png)

8.1 

![](./images/Lab12-fig10.png)
![image](https://user-images.githubusercontent.com/92082685/144747568-09c076b7-0ce2-49d8-bc7b-e00269ba4ee2.png)


![](./images/Lab12-fig11.png)
![image](https://user-images.githubusercontent.com/92082685/144747641-92fc8854-ff84-42dd-9fd5-e7b70f7082c0.png)


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
![image](https://user-images.githubusercontent.com/92082685/144747731-42d3fb04-8562-43c2-a464-5e443dd80f34.png)


ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)
![image](https://user-images.githubusercontent.com/92082685/144747739-becaab99-6362-4f81-bac7-2e59b6ba35ca.png)


2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)
![image](https://user-images.githubusercontent.com/92082685/144747766-7e5fa2eb-37dd-44b7-b9b8-1c783fd65e1d.png)

จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)
![image](https://user-images.githubusercontent.com/92082685/144747809-ad1a4d95-9a33-4c68-a648-03a87003417a.png)

5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)
![image](https://user-images.githubusercontent.com/92082685/144747828-094ec5f3-e19c-4d98-bed5-0fa11e12d539.png)


### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)
![image](https://user-images.githubusercontent.com/92082685/144747842-edef339d-baa8-409b-bac6-991deb7c577e.png)



![](./images/Lab12-fig18.png)
![image](https://user-images.githubusercontent.com/92082685/144747859-1ba9260c-9dcb-4286-9ded-10ad1233619c.png)

---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)
![image](https://user-images.githubusercontent.com/92082685/144747878-6a10ad67-9ebd-4f1e-a572-8a1a4c9991af.png)

![](./images/Lab12-fig20.png)
![image](https://user-images.githubusercontent.com/92082685/144747888-f1d00bf5-f670-4aa5-8c18-6a4cf18bb737.png)


2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)
![image](https://user-images.githubusercontent.com/92082685/144747898-0596d232-60b9-4ae8-b3ad-a54de88a8d2f.png)


3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)
 ![image](https://user-images.githubusercontent.com/92082685/144747928-96050405-04c4-410b-a48b-e3a1e9fe40ec.png)


### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)
![image](https://user-images.githubusercontent.com/92082685/144747953-cd92f550-11c6-4916-95ab-40197dde2f2f.png)

5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)
![image](https://user-images.githubusercontent.com/92082685/144747961-5f06c8a0-a2a3-457c-b76a-99522a89357e.png)


### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)
![image](https://user-images.githubusercontent.com/92082685/144747973-3cab8130-3d66-4a7a-8e7d-5fcabd293051.png)

![](./images/Lab12-fig26.png)
![image](https://user-images.githubusercontent.com/92082685/144747983-c819e00e-2b87-46af-8518-84debba6412e.png)

7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)
![image](https://user-images.githubusercontent.com/92082685/144747999-a51fb305-7b6c-4c1f-9f06-cabf06477b2c.png)

