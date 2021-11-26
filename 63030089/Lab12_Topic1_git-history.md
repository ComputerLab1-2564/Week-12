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
   ![image](https://user-images.githubusercontent.com/92081957/143554789-b322cd0c-ce54-41f7-bd58-ef86d84884f4.png)


### ดูประวัติบรรทัดเดียว (one line history) ###

จากข้อ 4 จะเห็นว่าระบบมีการแสดงข้อความของแต่ละ commit ออกมาเป็นจำนวนมาก 

เราสามารถสั่งให้แสดงแต่ละ commit เพียงบรรทัดเดียวได้

5. พิมพ์คำสั่ง  ```git log --pretty=oneline``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 

![](./images/Lab12-fig5.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าข้อความล้นบรรทัด ระบบจะปัดลงมา ทำให้ดูลำบาก สามารถปรับความกว้างของ git bash ให้มากขึ้น แล้ว พิมพ์คำสั่ง  ```git log --pretty=oneline``` อีกครั้ง
![image](https://user-images.githubusercontent.com/92081957/143555190-a8d722cd-bd42-4835-a687-8c6b9e3aecfd.png)


### ควบคุมการดูประวัติบรรทัดเดียว (one line history) แบบต่าง ๆ ###
เราสามารถควบคุมให้ ```git log --pretty=oneline``` แสดงผลในรูปแบบที่กำหนดได้ เช่น

___แสดงเพียง 2 commit___

```git
    git log --pretty=oneline --max-count=2
```
![image](https://user-images.githubusercontent.com/92081957/143556194-3eea1661-11d7-4b08-bf7e-a0eebca21b31.png)


___แสดงประวัตินับจาก 5 นาทีที่แล้ว___
```
    git log --pretty=oneline --since='5 minutes ago'
```
![image](https://user-images.githubusercontent.com/92081957/143556027-a39ff621-fb8e-404c-82c3-93dbfba5d9ba.png)

**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```


___แสดงประวัติจนถึง 5 นาทีที่แล้ว___

```git log --pretty=oneline --until='5 minutes ago'```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92081957/143556860-420d80bc-1015-4efc-9ea3-a45ef0f4fe5c.png)


___แสดงประวัติตามชื่อผู้ commit___

```git log --pretty=oneline --author=<your name>```
![image](https://user-images.githubusercontent.com/92081957/143562197-530e2182-6190-4f86-9569-6d71be18bc56.png)


___แสดงประวัติทั้งหมด___
```git log --pretty=oneline --all```
![image](https://user-images.githubusercontent.com/92081957/143557664-a53737d3-1c8b-43ec-a075-183e9210776a.png)


**_คำแนะนำ_** ดูคำสั่ง ``git log`` ทั้งหมดได้โดยการพิมพ์  ```git log --help```
file:///D:/Git/mingw64/share/doc/git-doc/git-log.html
ตามลิงค์นี้นะครับ

## _ให้นักศึกษาทดลองคำสั่งข้างบน แล้ว capture หน้าจอมาส่ง โดยแทรกใต้คำสั่งในตัวอย่าง_ ##


### ปรับแต่งการแสดงผล  ###
   
พิมพ์คำสั่งต่อไปนี้ (ครั้งละคำสั่ง) สังเกตุผลที่ได้ บันทึกผลและอธิบาย

1.  ```git log --pretty=format:'%h'```
![image](https://user-images.githubusercontent.com/92081957/143561126-f37e311a-6c68-49a8-82b9-9a0f5c58b063.png)

2.  ```git log --pretty=format:'%h %ad'```
![image](https://user-images.githubusercontent.com/92081957/143561293-cf4a348e-fed3-43be-93b8-9f9ba5fe3bab.png)

3.  ```git log --pretty=format:'%h %ad' --date=short```
![image](https://user-images.githubusercontent.com/92081957/143561482-fad1f0ad-bf92-43c2-91b2-cd2cbdc9a4f8.png)

4.  ```git log --pretty=format:'%h %ad' --date=short```
![image](https://user-images.githubusercontent.com/92081957/143561619-811c94cb-c8e7-4ea9-a494-e1f0371123b7.png)

5.  ```git log --pretty=format:'%h %ad | %s%d' --date=short```
![image](https://user-images.githubusercontent.com/92081957/143561738-a9ec695b-47e6-4c34-941a-3771f4eefc7d.png)

6.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```
![image](https://user-images.githubusercontent.com/92081957/143561876-1640be50-de27-4ba2-abbe-6115ac07d2ab.png)

7.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph```
![image](https://user-images.githubusercontent.com/92081957/143562025-eaccae4b-902c-48e8-b8ec-2ff2e07eee36.png)



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
