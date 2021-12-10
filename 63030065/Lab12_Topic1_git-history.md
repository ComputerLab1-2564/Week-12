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
   ![image](https://user-images.githubusercontent.com/92078869/145552829-4fb8e7e9-7c21-4ae9-a2ae-9e1d5df3eabf.png)
![image](https://user-images.githubusercontent.com/92078869/145552891-295c403e-4b28-4e98-bac5-4e65cd436bff.png)
![image](https://user-images.githubusercontent.com/92078869/145552963-a224f9ed-7d44-4533-a3e6-0affb25f6866.png)
![image](https://user-images.githubusercontent.com/92078869/145553016-9cd8f832-ccb0-400f-ad19-55ce5e1172e0.png)
![image](https://user-images.githubusercontent.com/92078869/145553057-8db3bf3c-4fa5-43bb-ba88-e88458b1699e.png)


### ดูประวัติบรรทัดเดียว (one line history) ###

จากข้อ 4 จะเห็นว่าระบบมีการแสดงข้อความของแต่ละ commit ออกมาเป็นจำนวนมาก 

เราสามารถสั่งให้แสดงแต่ละ commit เพียงบรรทัดเดียวได้

5. พิมพ์คำสั่ง  ```git log --pretty=oneline``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 

![](./images/Lab12-fig5.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าข้อความล้นบรรทัด ระบบจะปัดลงมา ทำให้ดูลำบาก สามารถปรับความกว้างของ git bash ให้มากขึ้น แล้ว พิมพ์คำสั่ง  ```git log --pretty=oneline``` อีกครั้ง
   ![image](https://user-images.githubusercontent.com/92078869/145553395-944b6163-da4a-49e1-95bd-7a282cf9b6ba.png)



### ควบคุมการดูประวัติบรรทัดเดียว (one line history) แบบต่าง ๆ ###
เราสามารถควบคุมให้ ```git log --pretty=oneline``` แสดงผลในรูปแบบที่กำหนดได้ เช่น

___แสดงเพียง 2 commit___

```git
    git log --pretty=oneline --max-count=2
```
![image](https://user-images.githubusercontent.com/92078869/145553565-e918c8bb-ac32-44ab-88c9-518d8a889860.png)


___แสดงประวัตินับจาก 5 นาทีที่แล้ว___
```
    git log --pretty=oneline --since='5 minutes ago'
```
![image](https://user-images.githubusercontent.com/92078869/145553712-92b890d9-2c7f-4b41-92bc-386efdaf5ff4.png)

**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```


___แสดงประวัติจนถึง 5 นาทีที่แล้ว___

```git log --pretty=oneline --until='5 minutes ago'```
![image](https://user-images.githubusercontent.com/92078869/145553938-8567bfb8-5788-4cbf-b004-417e35532b50.png)

**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```


___แสดงประวัติตามชื่อผู้ commit___

```git log --pretty=oneline --author=<your name>```
![image](https://user-images.githubusercontent.com/92078869/145554140-a7575d4a-5f7a-44bc-a24f-91db73a53c78.png)



___แสดงประวัติทั้งหมด___
```git log --pretty=oneline --all```
![image](https://user-images.githubusercontent.com/92078869/145554255-d6d98098-3f91-4220-bdab-d304e24ebd66.png)



**_คำแนะนำ_** ดูคำสั่ง ``git log`` ทั้งหมดได้โดยการพิมพ์  ```git log --help```


## _ให้นักศึกษาทดลองคำสั่งข้างบน แล้ว capture หน้าจอมาส่ง โดยแทรกใต้คำสั่งในตัวอย่าง_ ##


### ปรับแต่งการแสดงผล  ###
   
พิมพ์คำสั่งต่อไปนี้ (ครั้งละคำสั่ง) สังเกตุผลที่ได้ บันทึกผลและอธิบาย

1.  ```git log --pretty=format:'%h'```
![image](https://user-images.githubusercontent.com/92078869/145554426-1f0a7c73-a5cc-4d6a-a2af-39902d3a3d63.png)

2.  ```git log --pretty=format:'%h %ad'```
![image](https://user-images.githubusercontent.com/92078869/145554511-56969ba3-ef1f-4b6d-852d-2072799c4a30.png)

3.  ```git log --pretty=format:'%h %ad' --date=short```
![image](https://user-images.githubusercontent.com/92078869/145554592-a7ca8256-c013-4c89-af7e-629033460222.png)

4.  ```git log --pretty=format:'%h %ad | %s%d' --date=short```
![image](https://user-images.githubusercontent.com/92078869/145555031-74db70dc-bd76-457a-a5ba-2f1fe9a029e3.png)

5.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```
![image](https://user-images.githubusercontent.com/92078869/145555178-f55cd500-b1ac-4cdb-938c-abbee72f3335.png)

6.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph```
![image](https://user-images.githubusercontent.com/92078869/145555292-0920d200-9ccd-494b-ab3b-46863effbfff.png)



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
