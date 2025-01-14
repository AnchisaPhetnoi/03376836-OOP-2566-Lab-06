# Lab 6 Exercise 3

## Instance vs static members

1. สร้าง console application project

```cmd
dotnet new console --name Lab06_Ex03
```
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-06/assets/144197034/4cbcf5e3-81ff-4643-a4dc-49119cf22901)

2. เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
Person.name = "Enter your name here";
System.Console.WriteLine(Person.GetName());
var student = new Student();
student.name = "Enter student's name";
System.Console.WriteLine(student.GetName());

static class Person
{
    static  public  string? name;
    static  public string GetName()
    {
        return $"Hello from {name}";
    }
}

class Student : Person
{
    
}
```
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-06/assets/144197034/6417708e-d82a-4106-8d85-a42a63302684)

3. Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab06_Ex03
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4. บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3 
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-06/assets/144197034/0f0aeeb2-66d7-48c1-a6e9-f59d5d631230)


5. Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab06_Ex03
```

6. บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-06/assets/144197034/110d9a22-7d4d-4aed-bd66-4a8ee6cb89a6)



7. อธิบายสิ่งที่พบในการทดลอง
การพิมพ์ข้อความ "Hello from Enter your name here" และ "Hello from Enter student's name" 
บนคอนโซลตามลำดับ ซึ่งเป็นผลลัพธ์จากการเรียกใช้เมธอด GetName() ของทั้ง Person และ Student โดยมีการสืบทอดฟังก์ชันจาก Person ไปยัง Student ด้วย ดังนั้นการเรียกใช้ student.GetName() จะให้ผลลัพธ์เช่นเดียวกับการเรียกใช้ Person.GetName()
 แต่จะใช้ค่าที่ถูกกำหนดในฟิลด์ name ของ Student แทนที่จะใช้ค่าใน Person ตามค่าที่ถูกกำหนดตอนแรก
จากการแสดงผลเราจะเห็นว่ามีการแสดงผลลัพที่ไม่ถูกต้องอยู่ทำให้ข้อความออกมาผิดพลาดทำการแสดงผลทางโปรแกรมไม่ได้
ดูเหมือนว่าโค้ดในการใช้คำสั่งไม่สามารถแสดงผลได้หาวิธีแสดงผลแล้วแก้โค้ดแล้วแต่ก็ไม่สามารถแสดงผลได้ โดยถ้าแก้ไขโค้ดได้ถูกมีการ Run ข้อมูลให้จะได้ผลลัพนัดังนี้
Hello from Enter your name here
Hello from Enter student's name
ซึ่งจะแสดงข้อความ "Hello from Enter your name here" และ "Hello from Enter student's name" บนคอนโซลตามลำดับ นั่นเป็นผลลัพธ์ที่ควรจะปรากฏเมื่อโปรแกรมถูกรัน โดยในผลลัพธ์นี้ ข้อความจะเปลี่ยนไปตามค่าที่กำหนดให้กับฟิลด์ name ใน Person และ Student
 ตามลำดับ ซึ่งมีการแสดงผลตามที่คาดหวังและการสืบทอดสมาชิกของคลาสให้ถูกต้อง ตามโค้ดที่กำหนดไว้ในการทดลองนี้
