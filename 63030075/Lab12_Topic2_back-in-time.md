# การทดลองสัปดาห์ที่ 12 #
# เจาะลึกการใช้งาน git #


---
### ย้อนเวลาไปดูเนื้อหาใน commit ต่างๆ  และตั้งชื่อ (tag) ให้กับ commit ###

การทำงานต่างๆ บน git repository จะถูกบันทึกไว้ใน log เราสามารถเรียกดูด้วยคำสั่ง ```git log```

## ขั้นตอนการทดลอง ##
1. ทำการ clone repository จ่ากที่นี่ [week12-Commit](https://github.com/ComputerLab1-2564/week12-Commit)

2. ดูประวัติการ commit ทั้งหมดใน repository (ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```)
   **คำสั่ง** ให้จับภาพหน้าจอมาวางในใบงาน
![image](https://user-images.githubusercontent.com/92082233/142033244-29c68ef8-7f87-4451-abd0-d4270ae6bc71.png)

3. ย้อนไปดูไฟล์ตามประวัติการแก้ไข
    
   * คำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short``` จะบอกข้อมูลที่สำคัญคือ hash value ของ commit เราสามารถกระโดดย้อนเวลาไปยัง commit นั้นได้โดยใช้คำสั่ง ```git checkout <hash>``` โดย <hash> ก็คือตัวเลขผสมตัวอักษรที่ปรากฏอยู่คอลัมน์แรกสุดของแต่ละ commit
   * ทดลอง checkout commit แรกสุด และ commit ที่ชื่อ edit typo เพื่อดูความแตกต่างในเนื้อหาของไฟล์     *
   * capture หน้าจอของไฟล์ readme.md เปรียบเทียบกันใน 2 commit นั้น
   * สังเกตุที่หน้าจอ git bash ในวงเล็บท้ายชื่อ path จะแสดงหมายเลข commit
   * ในขณะ checkout ไปยัง commit อ่านและทำความเข้าใจข้อความแจ้งเตือนที่ปรากฏที่หน้าจอ อธิบายตามความเข้าใจ 
![image](https://user-images.githubusercontent.com/92082233/142033629-0f1d6900-a2e6-4702-bf41-c8f545be9aa2.png)
 ![image](https://user-images.githubusercontent.com/92082233/142033496-8d950070-acef-4bfc-b287-318b4f2e0c7f.png)
4. เราสามารถตั้งชื่อ (tag) ให้กับ commit นี้โดยใช้คำสั่ง ```git tag <tag name>```
   * สังเกตุชื่อ repository ในหน้าต่าง git bash ตอนท้ายจะมี (<hash number>) 
   * ให้พิมพ์คำสั่ง ```git tag V1``` 
   * สังเกตุชื่อ repository ในหน้าต่าง git bash ตอนท้ายจะมี ((V1))) แสดงว่าระบบได้ทำการสร้างชื่อใหม่ให้กับ commit นี้แล้ว โดนเรากำหนดให้เป็น V1 ซึ่งหมายถึง version 1
![image](https://user-images.githubusercontent.com/92082233/142034221-f198bb7d-ae5e-4763-8aec-f6738e552860.png)

5. ให้ branch กลับไปยัง main branch โดยคำสั่ง ```git checkout main```
![image](https://user-images.githubusercontent.com/92082233/142034581-6cf19c56-5fd0-48c8-9dba-9201dcc637d7.png)

6. ทดลอง branch กลับไปยัง commit นั้น โดยใช้ ```git checkout V1```
    * เปรียบเทียบผลที่ได้กับการใช้คำสั่ง git branch <hash>

![image](https://user-images.githubusercontent.com/92082233/142034548-cfd86c3a-19a3-4b13-b3e9-b08969fc7202.png)

7. ถึงแม้จะใช้ tag name แต่การ branch มาที่ commit จะทำให้เกิดการตัดจากหัว (HEAD) ของ link การกระทำใดๆ ที่ commit นี้อาจจะก่อให้เกิดปัญหาได้ ดังนั้นเพื่อความปลอดภัย ให้ branch กลับไปที่ main โดยคำสั่ง ```git checkout main```
![image](https://user-images.githubusercontent.com/92082233/142034634-d382f859-472b-4798-b470-264f65e6eca8.png)

8. เราสามารถเรียกดูรายการ tag ได้โดยใช้คำสั่ง ```git tag```
![image](https://user-images.githubusercontent.com/92082233/142034697-c99a5b63-8d8a-49ac-aa40-76476aac489b.png)

9. เราสามารถเรียกดูรายการ commit ในแต่ละ tag ได้โดยใช้คำสั่ง 

 ```git log <tag name|branch name> --pretty=format:'%h %ad | %s%d [%an]' --date=short```
![image](https://user-images.githubusercontent.com/92082233/142034805-877c1c20-972f-4866-ba81-a9016b00f23a.png)
