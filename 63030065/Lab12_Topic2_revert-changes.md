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
![image](https://user-images.githubusercontent.com/92078869/145558949-4ac14d44-c8ca-48de-805b-947cb9a3de42.png)


6. ใน github desktop จะแสดงเนื้อหาส่วนที่ถูกแก้ไข

![](./images/Lab12-fig7.png)
![image](https://user-images.githubusercontent.com/92078869/145559057-e5d44627-2177-463b-a337-c198219ea6b3.png)


7. ใน git bash ให้ทำการตรวจสอบสถานะ โดยคำสั่ง ```git status```

![](./images/Lab12-fig8.png)
![image](https://user-images.githubusercontent.com/92078869/145559314-58e6bbbc-2527-4018-aff1-a8c87c30284c.png)


8. ถ้าต้องการยกเลิกการเปลี่ยนแปลงที่ทำกับ Readme.md ให้ใช้คำสั่ง ```git checkout Readme.md``` **ระวังเรื่องการใช้ตัวพิมพ์เล็ก/พิมพ์ใหญ่ในชื่อไฟล์ด้วย**

![](./images/Lab12-fig9.png)
![image](https://user-images.githubusercontent.com/92078869/145559407-a30da865-2de3-4da1-9ab4-26474c3cf7dd.png)


8.1 

![](./images/Lab12-fig10.png)
![image](https://user-images.githubusercontent.com/92078869/145559510-2e8711fa-264f-4892-b91b-76a6388f8878.png)



![](./images/Lab12-fig11.png)
![image](https://user-images.githubusercontent.com/92078869/145559600-98bf6c76-4fec-4cc5-8087-2d7228c8e4e2.png)



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
![image](https://user-images.githubusercontent.com/92078869/145559767-e45a4496-2abf-4259-936b-346927aa9261.png)



ตรวจสอบโดย github desktop

![](./images/Lab12-fig13.png)
![image](https://user-images.githubusercontent.com/92078869/145559844-80510342-f79f-4073-b75f-3797fb2bd7e2.png)



2. เพิ่มไฟล์ Readme.md ไปยัง staging area ด้วยคำสั่ง ```git add Readme.md````

3. เช็คสถานะ git ด้วยคำสั่ง ```git status```

![](./images/Lab12-fig14.png)
![image](https://user-images.githubusercontent.com/92078869/145559937-e0bfc14b-ce0a-4daf-9057-64236b665080.png)


จะเห็นว่าคำสั่ง ```git status``` จะมีคำแนะนำบางอย่าง ซึ่งเราสามารถนำมาใช้เพื่อยกเลิกการกระทำขั้นก่อนหน้านี้ได้
### ขั้นแก้ไขปัญหา ###

4. ล้างค่าใน staging area โดยคำสั่ง ```git restore --staged Readme.md"```

![](./images/Lab12-fig15.png)
![image](https://user-images.githubusercontent.com/92078869/145560212-e018e227-6827-4558-961b-28247d5082ec.png)


5. ยกเลิกการเพิ่มไฟล์เข้าไปใน staging areae ตามขั้นตอนการทดลองในหัวข้อก่อนหน้านี้ หรือทำตามคำแนะนำใน git bash 
(ในขั้นนี้จะลองทำตามที่ git bashบอก คือ ) ```git restore Readme.md```

![](./images/Lab12-fig16.png)
![image](https://user-images.githubusercontent.com/92078869/145560271-91f80a58-7982-46ce-ac01-7bb7e2eca0dc.png)



### ขั้นตรวจสอบผลลัพธ์ ###

6. ตรวจสอบไฟล์ใน editor และ github desktop

![](./images/Lab12-fig17.png)
![image](https://user-images.githubusercontent.com/92078869/145560338-01738dac-28e5-40f9-9624-f7e528a02c2c.png)




![](./images/Lab12-fig18.png)
![image](https://user-images.githubusercontent.com/92078869/145560372-d833dc08-8a94-42dc-98e8-56d5b68a9648.png)


---
## 2. ยกเลิกการแก้ไขไฟล์หลังทำการ ```git commit```###

เมื่อเราทำการ commit ไปแล้ว ก็สามารถยกเลิกการ commit ได้เช่นกัน

### ขั้นเตรียมการ ###
1. แก้ไขไฟล์ Readme.md

![](./images/Lab12-fig19.png)
![image](https://user-images.githubusercontent.com/92078869/145560527-3a3ea904-9956-47a5-8fc1-4f9db53d6fa5.png)


![](./images/Lab12-fig20.png)
![image](https://user-images.githubusercontent.com/92078869/145560555-f7ab2217-b8a3-4652-9d7b-35cb2dd8f3e5.png)



2. เพิ่ม Readme.md เข้าไปยัง staging area โดยคำสั่ง ```git add Readme.md```
   
![](./images/Lab12-fig21.png)
![image](https://user-images.githubusercontent.com/92078869/145560708-14042eab-a5df-489b-a4ed-bd38bcf0fcf5.png)



3. commit ไฟล์ Readme.md โดยคำสั่ง ```git commit -m "commit Readme.md"```

![](./images/Lab12-fig22.png)
![image](https://user-images.githubusercontent.com/92078869/145560810-6dde023b-f9bc-4e24-b8ff-af5f2934a1ae.png)

 

### ขั้นแก้ไขปัญหา ###

4. ยกเลิกการ commit โดยพิมพ์คำสั่ง ```git revert HEAD```
จะปรากฏ text editor ขึ้นมา 
   * ใครเชื่อมไว้กับ text editor ของ OS ก็แก้ไขข้อความบน text editor นั้นได้เลย แต่ถ้าไม่ได้เชื่อมไว้ ต้องแก้บน text editor บน git bash
   * ทำตามคำอธิบายในภาพด้านล่างนี้

![](./images/Lab12-fig23.png)
![image](https://user-images.githubusercontent.com/92078869/145561270-0ab346b3-67b1-4b64-8c9a-f05d4865fd26.png)


5. เมื่อกลับมาจาก text editor จะปรากฏข้อความต่อไปนี้


![](./images/Lab12-fig24.png)
![image](https://user-images.githubusercontent.com/92078869/145561439-23715759-4ace-41e7-9246-9b377f6fa47e.png)



### ขั้นตรวจสอบผลลัพธ์ ###
6. ตรวจสอบไฟล์ต้นฉบับด้วย text editor และ github desktop

![](./images/Lab12-fig25.png)
![image](https://user-images.githubusercontent.com/92078869/145561559-f9b6d0bf-b374-4c13-be73-328bfbc840f7.png)


![](./images/Lab12-fig26.png)
![image](https://user-images.githubusercontent.com/92078869/145561737-98d8916d-a089-46a4-bbcd-303a92272a0d.png)


7. ตรวจสอบ history log ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```


![](./images/Lab12-fig27.png)
![image](https://user-images.githubusercontent.com/92078869/145561876-e9dd9247-9652-4b56-8bf1-4c89e428c719.png)


