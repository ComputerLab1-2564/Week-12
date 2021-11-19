# การทดลองสัปดาห์ที่ 12 #
# เจาะลึกการใช้งาน git #


---
### ดูประวัติการทำงานบน  git ###

การทำงานต่างๆ บน git repository จะถูกบันทึกไว้ใน log เราสามารถเรียกดูด้วยคำสั่ง ```git log```

## ขั้นตอนการทดลอง ##

1. เปิด file explorer ของ repository 
ในใบงานนี้ จะใช้ repository ของ [ใบงานที่ 10](https://github.com/ComputerLab1-2564/Week-10)

#### _ส่วนของนักศึกษา เพื่อให้เห็นการทำ branch ให้เลือก repository ที่ทำ MyTranscript ในการทดลองที่แล้ว_ ####

![](./images/Lab12-fig1.png)

2.  เรียก  git bash command line โดยการคลิกขวาตรงพื้นที่ว่าง เลือก ```Git bash here```

![](./images/Lab12-fig2.png)

3.  ให้สังเกตุว่าในหน้าต่าง git bash จะต้องแสดง path ไปยังที่ตั้งของ repository และมีชื่อ branch ปัจจุบันในวงเล็บ

![](./images/Lab12-fig3.png)


### ดูประวัติด้วยคำสั่ง git log ###

4.  พิมพ์คำสั่ง  ```git log``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 
   
![](./images/Lab12-fig4.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าประวัติมีความยาวมาก ที่บรรทัดสุดท้าย จะมีเครื่องหมาย colon  ```:``` แสดงว่าระบบยังแสดงประวัติไม่หมด ให้เคาะ space bar ไปจนกว่าจะหมดข้อความ (มีคำว่า ```(END)```) ตรงนี้เมื่อกดปุ่มใดๆ จะไม่มีการตอบสนอง ให้กด ```Shift``` ค้างไว้และกดปุ่ม ```z``` สองครั้ง  
   ![image](https://user-images.githubusercontent.com/92082233/142029858-1c7598d8-6304-4f11-a0d1-978f9aeb4e89.png)


### ดูประวัติบรรทัดเดียว (one line history) ###

จากข้อ 4 จะเห็นว่าระบบมีการแสดงข้อความของแต่ละ commit ออกมาเป็นจำนวนมาก 

เราสามารถสั่งให้แสดงแต่ละ commit เพียงบรรทัดเดียวได้

5. พิมพ์คำสั่ง  ```git log --pretty=oneline``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 

![](./images/Lab12-fig5.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าข้อความล้นบรรทัด ระบบจะปัดลงมา ทำให้ดูลำบาก สามารถปรับความกว้างของ git bash ให้มากขึ้น แล้ว พิมพ์คำสั่ง  ```git log --pretty=oneline``` อีกครั้ง
![image](https://user-images.githubusercontent.com/92082233/142029953-edfb7059-f322-49b9-b03f-6a56e44509f4.png)


### ควบคุมการดูประวัติบรรทัดเดียว (one line history) แบบต่าง ๆ ###
เราสามารถควบคุมให้ ```git log --pretty=oneline``` แสดงผลในรูปแบบที่กำหนดได้ เช่น

___แสดงเพียง 2 commit___

```git
    git log --pretty=oneline --max-count=2
```
![image](https://user-images.githubusercontent.com/92082233/142030266-8696722e-e308-48f0-8d9c-de7f0a161268.png)

___แสดงประวัตินับจาก 5 นาทีที่แล้ว___
```
    git log --pretty=oneline --since='5 minutes ago'
```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92082233/142030345-aba0b759-b8b4-45c8-b3c9-bacc4148fa35.png)


___แสดงประวัติจนถึง 5 นาทีที่แล้ว___

```git log --pretty=oneline --until='5 minutes ago'```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```

![image](https://user-images.githubusercontent.com/92082233/142030456-ea20abd5-6c6e-49ae-ba08-9f3176f8d8be.png)

___แสดงประวัติตามชื่อผู้ commit___

```git log --pretty=oneline --author=<your name>```
![image](https://user-images.githubusercontent.com/92082233/142030497-f71e972b-926b-4b3c-9ef2-d43126e52990.png)


___แสดงประวัติทั้งหมด___
```git log --pretty=oneline --all```

![image](https://user-images.githubusercontent.com/92082233/142030584-7fa82443-2dd2-4950-8bca-1f75ade5b7de.png)

**_คำแนะนำ_** ดูคำสั่ง ``git log`` ทั้งหมดได้โดยการพิมพ์  ```git log --help```
![image](https://user-images.githubusercontent.com/92082233/142030849-0c5f2845-f9b6-48a8-a405-1ab3dcc01a58.png)


## _ให้นักศึกษาทดลองคำสั่งข้างบน แล้ว capture หน้าจอมาส่ง โดยแทรกใต้คำสั่งในตัวอย่าง_ ##


### ปรับแต่งการแสดงผล  ###
   
พิมพ์คำสั่งต่อไปนี้ (ครั้งละคำสั่ง) สังเกตุผลที่ได้ บันทึกผลและอธิบาย

1.  ```git log --pretty=format:'%h'```  
2.  ![image](https://user-images.githubusercontent.com/92082233/142031574-91eac3e2-c2f5-4230-8753-c1022466177e.png)

3.  ```git log --pretty=format:'%h %ad'```
4.  ![image](https://user-images.githubusercontent.com/92082233/142031660-a7c185a3-7932-4935-a9b0-6a2b6b9cc3f3.png)

5.  ```git log --pretty=format:'%h %ad' --date=short```
6.  ![image](https://user-images.githubusercontent.com/92082233/142031724-a89fb399-1062-4838-a32e-1e9920f6b343.png)

7.  ```git log --pretty=format:'%h %ad' --date=short```
8.  ![image](https://user-images.githubusercontent.com/92082233/142031954-44555e0b-6354-4912-a57a-4cf2a4dd7359.png)

9.  ```git log --pretty=format:'%h %ad | %s%d' --date=short```
10.  ![image](https://user-images.githubusercontent.com/92082233/142032002-38d7da97-6eca-4b9b-9636-b1ddb8d3cf30.png)

11.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```
12.  ![image](https://user-images.githubusercontent.com/92082233/142032064-cd78f686-a5c8-4b4e-946b-d45cc8a910ee.png)

13.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph```
14.  ![image](https://user-images.githubusercontent.com/92082233/142032130-94af2167-caf4-4b40-8dd9-cd46520c7b41.png)



#### รูปแบบคำสั่งควบคุมการแสดงผล ####

```git
--pretty="..." defines the format of the output.
    %h is the abbreviated hash of the commit
    %d are any decorations on that commit (e.g. branch heads or tags)
    %ad is the author date
    %s is the comment
    %an is the author name
--graph informs git to display the commit tree in an ASCII graph layout
--date=short keeps the date format nice and short 
