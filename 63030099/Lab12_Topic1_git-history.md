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
![image](https://user-images.githubusercontent.com/92079514/143554958-a8bd40c0-bec8-4a3c-9d2a-b86518a8b6bf.png)

### ดูประวัติบรรทัดเดียว (one line history) ###

จากข้อ 4 จะเห็นว่าระบบมีการแสดงข้อความของแต่ละ commit ออกมาเป็นจำนวนมาก 

เราสามารถสั่งให้แสดงแต่ละ commit เพียงบรรทัดเดียวได้

5. พิมพ์คำสั่ง  ```git log --pretty=oneline``` หน้าจอจะแสดงคล้ายตัวอย่างนี้ 

![](./images/Lab12-fig5.png)

   - ให้ capture หน้าจอนักศึกษามาวางในใบงาน
   **_คำแนะนำ_** ถ้าข้อความล้นบรรทัด ระบบจะปัดลงมา ทำให้ดูลำบาก สามารถปรับความกว้างของ git bash ให้มากขึ้น แล้ว พิมพ์คำสั่ง  ```git log --pretty=oneline``` อีกครั้ง
![image](https://user-images.githubusercontent.com/92079514/143555269-672d97c9-5148-481c-8a45-33dd2863625d.png)


### ควบคุมการดูประวัติบรรทัดเดียว (one line history) แบบต่าง ๆ ###
เราสามารถควบคุมให้ ```git log --pretty=oneline``` แสดงผลในรูปแบบที่กำหนดได้ เช่น

___แสดงเพียง 2 commit___

```git
    git log --pretty=oneline --max-count=2
```
![image](https://user-images.githubusercontent.com/92079514/143556003-3d32a374-a30d-495b-97dd-9ee1eae2c987.png)

___แสดงประวัตินับจาก 5 นาทีที่แล้ว___
```
    git log --pretty=oneline --since='5 minutes ago'
```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92079514/143556717-ac03c169-2833-4797-8f94-ed1f11ecf32b.png)


___แสดงประวัติจนถึง 5 นาทีที่แล้ว___

```git log --pretty=oneline --until='5 minutes ago'```
**_คำแนะนำ_** สามารถเปลี่ยน ```minutes``` เป็นหน้วยเวลาอื่นๆ เช่น ```days```
![image](https://user-images.githubusercontent.com/92079514/143557057-cbd704a5-691c-42c2-ba99-3116df6ca0ed.png)


___แสดงประวัติตามชื่อผู้ commit___

```git log --pretty=oneline --author=<your name>```

![image](https://user-images.githubusercontent.com/92079514/143559325-1f60a27e-deab-450e-93b5-7bd734f987c9.png)


___แสดงประวัติทั้งหมด___
```git log --pretty=oneline --all```
![image](https://user-images.githubusercontent.com/92079514/143559972-dd438e5d-f624-4cea-b8a5-112380cad067.png)



**_คำแนะนำ_** ดูคำสั่ง ``git log`` ทั้งหมดได้โดยการพิมพ์  ```git log --help```
file:///C:/Program%20Files/Git/mingw64/share/doc/git-doc/git-log.html
ตามลิ้งค์นะครับอาจารย์

## _ให้นักศึกษาทดลองคำสั่งข้างบน แล้ว capture หน้าจอมาส่ง โดยแทรกใต้คำสั่งในตัวอย่าง_ ##


### ปรับแต่งการแสดงผล  ###
   
พิมพ์คำสั่งต่อไปนี้ (ครั้งละคำสั่ง) สังเกตุผลที่ได้ บันทึกผลและอธิบาย

1.  ```git log --pretty=format:'%h'```

![image](https://user-images.githubusercontent.com/92079514/143561040-db621a6d-ee5c-40fd-81e4-56daabb4728c.png)

2.  ```git log --pretty=format:'%h %ad'```

![image](https://user-images.githubusercontent.com/92079514/143561194-bb34d85b-f810-46ad-b83a-219abf2e0154.png)

3.  ```git log --pretty=format:'%h %ad' --date=short```

![image](https://user-images.githubusercontent.com/92079514/143561347-ae26e884-cb08-4313-8ae1-b628e58dda5e.png)

4.  ```git log --pretty=format:'%h %ad' --date=short```

![image](https://user-images.githubusercontent.com/92079514/143561501-cd92a9d5-cc51-4c5a-ba50-fbb8795c9772.png)

5.  ```git log --pretty=format:'%h %ad | %s%d' --date=short```

![image](https://user-images.githubusercontent.com/92079514/143561571-07ee876a-adb2-407b-a409-17fde6db0849.png)

6.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short```

![image](https://user-images.githubusercontent.com/92079514/143561656-1f7d8f81-dc41-4366-b6ee-0b8ff2e00d8e.png)

7.  ```git log --pretty=format:'%h %ad | %s%d [%an]' --date=short --graph```

![image](https://user-images.githubusercontent.com/92079514/143561735-a7e9a28c-bf3b-4577-a578-a44c3ed929ff.png)


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
