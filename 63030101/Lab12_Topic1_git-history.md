# การทดลองสัปดาห์ที่ 12 #
# เจาะลึกการใช้งาน git #


---
### ดูประวัติการทำงานบน  git ###

การทำงานต่างๆ บน git repository จะถูกบันทึกไว้ใน log เราสามารถเรียกดูด้วยคำสั่ง ```git log```

## ขั้นตอนการทดลอง ##

1. เปิด file explorer ของ repository 
ในใบงานนี้ จะใช้ repository ของ [ใบงานที่ 10](https://github.com/ComputerLab1-2564/Week-10)

#### _ส่วนของนักศึกษา เพื่อให้เห็นการทำ branch ให้เลือก repository ที่ทำ MyTranscript ในการทดลองที่แล้ว_ ####

![](./images/Lab12-fig1.png)![143556061-a6156a51-c12f-41d1-907f-0965aba84df8](https://user-images.githubusercontent.com/92081596/143556089-877a5814-a6e8-4b12-87f3-80cdb8c34ac8.png)


2.  เรียก  git bash command line โดยการคลิกขวาตรงพื้นที่ว่าง เลือก ```Git bash here```

![](./images/Lab12-fig2.png)

3.  ให้สังเกตุว่าในหน้าต่าง git bash จะต้องแสดง path ไปยังที่ตั้งของ repository และมีชื่อ branch ปัจจุบันในวงเล็บ

![](./images/Lab12-fig3.png)


### ดูประวัติด้วยคำสั่ง git log ###

4.  พิมพ์คำสั่ง  ```git log``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 
   
![](./images/Lab12-fig4.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าประวัติมีความยาวมาก ที่บรรทัดสุดท้าย จะมีเครื่องหมาย colon  ```:``` แสดงว่าระบบยังแสดงประวัติไม่หมด ให้เคาะ space bar ไปจนกว่าจะหมดข้อความ (มีคำว่า ```(END)```) ตรงนี้เมื่อกดปุ่มใดๆ จะไม่มีการตอบสนอง ให้กด ```Shift``` ค้างไว้และกดปุ่ม ```z``` สองครั้ง  
![image](https://user-images.githubusercontent.com/92081596/143554737-96f91c6d-13aa-4eca-afe5-a348fd6343ba.png)

### ดูประวัติบรรทัดเดียว (one line history) ###

จากข้อ 4 จะเห็นว่าระบบมีการแสดงข้อความของแต่ละ commit ออกมาเป็นจำนวนมาก 

เราสามารถสั่งให้แสดงแต่ละ commit เพียงบรรทัดเดียวได้

5. พิมพ์คำสั่ง  ```git log --pretty=oneline``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 

![](./images/Lab12-fig5.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าข้อความล้นบรรทัด ระบบจะปัดลงมา ทำให้ดูลำบาก สามารถปรับความกว้างของ git bash ให้มากขึ้น แล้ว พิมพ์คำสั่ง  ```git log --pretty=oneline``` อีกครั้ง
![image](https://user-images.githubusercontent.com/92081596/143555144-55bd4bbc-92f3-49a7-b24c-aa5604bf5664.png)


### ควบคุมการดูประวัติบรรทัดเดียว (one line history) แบบต่าง ๆ ###
เราสามารถควบคุมให้ ```git log --pretty=oneline``` แสดงผลในรูปแบบที่กำหนดได้ เช่น

___แสดงเพียง 2 commit___

```git
    git log --pretty=oneline --max-count=2
```
![image](https://user-images.githubusercontent.com/92081596/143556061-a6156a51-c12f-41d1-907f-0965aba84df8.png)

___แสดงประวัตินับจาก 5 นาทีที่แล้ว___
```
    git log --pretty=oneline --since='5 minutes ago'
```
![image](https://user-images.githubusercontent.com/92081596/143556172-f43c625f-1977-448c-8d67-631c8bc33e67.png)

**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92081596/143556695-f8836f4d-a87c-4bd0-9b3e-6f2ebc20b8c2.png)


___แสดงประวัติจนถึง 5 นาทีที่แล้ว___

```git log --pretty=oneline --until='5 minutes ago'```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92081596/143556993-5c9ab3fd-a4ad-44d3-bf7b-0e4594293568.png)


___แสดงประวัติตามชื่อผู้ commit___

```git log --pretty=oneline --author=<your name>```
![image](https://user-images.githubusercontent.com/92081596/143559662-d99362af-1431-4a35-a176-414a2c76fe40.png)



___แสดงประวัติทั้งหมด___
```git log --pretty=oneline --all```
![image](https://user-images.githubusercontent.com/92081596/143557683-c8556618-ee21-4e1b-ba14-52852847e468.png)


**_คำแนะนำ_** ดูคำสั่ง ``git log`` ทั้งหมดได้โดยการพิมพ์  ```git log --help```

แสดงตามลิ้งค์นี้นะครับ : 
file:///E:/New%20folder/Git/mingw64/share/doc/git-doc/git-log.html

## _ให้นักศึกษาทดลองคำสั่งข้างบน แล้ว capture หน้าจอมาส่ง โดยแทรกใต้คำสั่งในตัวอย่าง_ ##


### ปรับแต่งการแสดงผล  ###
   
พิมพ์คำสั่งต่อไปนี้ (ครั้งละคำสั่ง) สังเกตุผลที่ได้ บันทึกผลและอธิบาย

1.  ```git log --pretty=format:'%h'```

![image](https://user-images.githubusercontent.com/92081596/143561041-b63b016d-f1ac-4536-b564-dba2dc8454b4.png)

2.  ```git log --pretty=format:'%h %ad'```

![image](https://user-images.githubusercontent.com/92081596/143561144-e6ca2fbb-e54a-4685-b5fe-8512d39d0f9f.png)

3.  ```git log --pretty=format:'%h %ad' --date=short```
![image](https://user-images.githubusercontent.com/92081596/143561554-fbddf529-8872-45d6-8d63-42e91caa9c61.png)

4.  ```git log --pretty=format:'%h %ad' --date=short```
![image](https://user-images.githubusercontent.com/92081596/143561605-b3620c24-51e9-4dff-9324-30db4826c895.png)

5.  ```git log --pretty=format:'%h %ad | %s%d' --date=short```
![image](https://user-images.githubusercontent.com/92081596/143561657-0f0f647a-ee1e-4f6b-9ffe-f56bdcddcdd4.png)

6.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```
![image](https://user-images.githubusercontent.com/92081596/143561752-12a7b91e-a2d9-4135-a939-bb6f411502d1.png)

7.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph```
![image](https://user-images.githubusercontent.com/92081596/143561801-ffde9949-33cd-4dc4-8bf6-6308c8c91696.png)



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
