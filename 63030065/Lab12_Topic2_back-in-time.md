# การทดลองสัปดาห์ที่ 12 #
# เจาะลึกการใช้งาน git #


---
### ย้อนเวลาไปดูเนื้อหาใน commit ต่างๆ  และตั้งชื่อ (tag) ให้กับ commit ###

การทำงานต่างๆ บน git repository จะถูกบันทึกไว้ใน log เราสามารถเรียกดูด้วยคำสั่ง ```git log```

## ขั้นตอนการทดลอง ##
1. ทำการ clone repository จ่ากที่นี่ [week12-Commit](https://github.com/ComputerLab1-2564/week12-Commit)

2. ดูประวัติการ commit ทั้งหมดใน repository (ด้วยคำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```)
   **คำสั่ง** ให้จับภาพหน้าจอมาวางในใบงาน
   ![image](https://user-images.githubusercontent.com/92078869/145556011-a2244b3d-7921-4ab4-af3e-78a4d9d0b4a3.png)


3. ย้อนไปดูไฟล์ตามประวัติการแก้ไข
    
   * คำสั่ง ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short``` จะบอกข้อมูลที่สำคัญคือ hash value ของ commit เราสามารถกระโดดย้อนเวลาไปยัง commit นั้นได้โดยใช้คำสั่ง ```git checkout <hash>``` โดย <hash> ก็คือตัวเลขผสมตัวอักษรที่ปรากฏอยู่คอลัมน์แรกสุดของแต่ละ commit
   * ทดลอง checkout commit แรกสุด และ commit ที่ชื่อ edit typo เพื่อดูความแตกต่างในเนื้อหาของไฟล์     *
   * capture หน้าจอของไฟล์ readme.md เปรียบเทียบกันใน 2 commit นั้น
  ![image](https://user-images.githubusercontent.com/92078869/145556685-8148595f-ff38-46f2-9156-651024d5a85d.png)

   * สังเกตุที่หน้าจอ git bash ในวงเล็บท้ายชื่อ path จะแสดงหมายเลข commit
   * ในขณะ checkout ไปยัง commit อ่านและทำความเข้าใจข้อความแจ้งเตือนที่ปรากฏที่หน้าจอ อธิบายตามความเข้าใจ 

4. เราสามารถตั้งชื่อ (tag) ให้กับ commit นี้โดยใช้คำสั่ง ```git tag <tag name>```
   * สังเกตุชื่อ repository ในหน้าต่าง git bash ตอนท้ายจะมี (<hash number>) 
   * ให้พิมพ์คำสั่ง ```git tag V1``` 
   * สังเกตุชื่อ repository ในหน้าต่าง git bash ตอนท้ายจะมี ((V1))) แสดงว่าระบบได้ทำการสร้างชื่อใหม่ให้กับ commit นี้แล้ว โดนเรากำหนดให้เป็น V1 ซึ่งหมายถึง version 1

5. ให้ branch กลับไปยัง main branch โดยคำสั่ง ```git checkout main```

6. ทดลอง branch กลับไปยัง commit นั้น โดยใช้ ```git checkout V1```
    * เปรียบเทียบผลที่ได้กับการใช้คำสั่ง git branch <hash>
  ![image](https://user-images.githubusercontent.com/92078869/145557009-2c227b6b-0cf6-4e1f-b082-0b4288a0377e.png)


7. ถึงแม้จะใช้ tag name แต่การ branch มาที่ commit จะทำให้เกิดการตัดจากหัว (HEAD) ของ link การกระทำใดๆ ที่ commit นี้อาจจะก่อให้เกิดปัญหาได้ ดังนั้นเพื่อความปลอดภัย ให้ branch กลับไปที่ main โดยคำสั่ง ```git checkout main```

8. เราสามารถเรียกดูรายการ tag ได้โดยใช้คำสั่ง ```git tag```

9. เราสามารถเรียกดูรายการ commit ในแต่ละ tag ได้โดยใช้คำสั่ง 


 ```git log <tag name|branch name> --pretty=format:'%h %ad | %s%d [%an]' --date=short```
  ![image](https://user-images.githubusercontent.com/92078869/145557570-74934a5e-fcdf-4550-bb3a-2e3e0f6d044a.png)

