## Section 1 - Manual Testing Skill and Testing Knowledge

#### Question 1 หากต้องการ Design Test-case มี Technique อะไรบ้างที่สามารถช่วยให้การ Design Test-case เพื่อทดสอบระบบได้ครอบคลุม

Answer 1

             1.Equivalence Partitioning (การแบ่งช่วงค่าเทียบเท่า): การแบ่งช่วงค่าข้อมูลอินพุตเป็นกลุ่มที่เหมือนกัน และสร้าง Test-case โดยเลือกค่าจากแต่ละกลุ่มที่เป็น representant ที่มีความหมายเดียวกัน เพื่อลดจำนวน Test-case แต่ยังครอบคลุมเงื่อนไขทั้งหมดในกลุ่มนั้นๆ
             2.Boundary Value Analysis (การวิเคราะห์ค่าขอบ): การสร้าง Test-case ที่ใช้ค่าข้อมูลที่อยู่ในขอบเขตของช่วงค่าข้อมูล เช่น ค่าต่ำสุด ค่าสูงสุด หรือค่าที่อยู่ระหว่างขอบเขต เพื่อทดสอบความถูกต้องของระบบในส่วนนั้นๆ
             3.Decision Table Testing (การทดสอบด้วยตารางการตัดสินใจ): การสร้าง Test-case โดยใช้ตารางที่แสดงเงื่อนไขและการดำเนินการของระบบ เพื่อให้ครอบคลุมทุกๆ เงื่อนไขและสถานการณ์ที่อาจเกิดขึ้น
             4.State Transition Testing (การทดสอบการเปลี่ยนสถานะ): สร้าง Test-case โดยใช้การวิเคราะห์การเปลี่ยนสถานะของระบบ และสร้าง Test-case เพื่อทดสอบการเปลี่ยนสถานะของระบบในทุกๆ สถานะที่เป็นไปได้
             5.Pairwise Testing (การทดสอบแบบทีมละคู่): การเลือกคู่ของพารามิเตอร์ที่สำคัญที่สุดและสร้าง Test-case ที่ครอบคลุมคู่นี้ ซึ่งช่วยลดจำนวน Test-case ที่ต้องสร้างให้น้อยลง
             6.Risk-based Testing (การทดสอบโดยให้ความสำคัญตามความเสี่ยง): การพิจารณาความเสี่ยงในการทดสอบและสร้าง Test-case ที่เน้นไปที่พื้นที่ที่มีความเสี่ยงสูงสุด หรือคุณลักษณะที่สำคัญที่สุดของระบบ
             7.Exploratory Testing (การทดสอบอย่างสำรวจ): การทดสอบโดยการสำรวจระบบโดยไม่มีแผนการทดสอบที่กำหนดไว้ล่วงหน้า โดยใช้ประสบการณ์และความคิดสร้างสรรค์ของ Tester เพื่อสร้าง Test-case และทดสอบระบบ
             8.User Story Testing (การทดสอบตามเรื่องราวของผู้ใช้): การสร้าง Test-case โดยใช้ User Story หรือความต้องการของผู้ใช้เป็นพื้นฐาน ซึ่งช่วยให้การทดสอบมีการใช้งานที่เข้าใจและเชื่อถือได้มากขึ้น

#### Question 2 Design Test-case จากโจทย์ต่อไปนี้อย่างน้อย 5 Case พร้อมระบุ Technique ที่ใช้ข้อนั้น ๆ

[โจทย์] : ผู้ใช้ต้องการโอน Point จากบัญชีตัวเอง ไปยังบัญชีปลายทาง โดยเงื่อนไขคือ

ขั้นต่ำในการโอน Point คือ 100 / การทำรายการ

สูงสุดในการโอน Point คือ 3,000 / การทำรายการ

หากโอน < ขั้นต่ำ ระบบคิดค่า Fee 8 Point โดยบวกเพิ่มจากค่าที่กรอก

ต้องกรอก Passcode 4 หลัก ให้ถูกต้องจึงทำรายการสำเร็จ

บัญชีปลายทางต้องถูกต้อง จึงจะสามารถกรอก Passcode ได้

Answer 2

            Test Case No.: TC001
            Test Case: การโอน Point โดยจำนวน Point มากกว่าขั้นต่ำ
            Description: ทดสอบการโอน Point โดยจำนวน Point มากกว่าขั้นต่ำที่กำหนด
            Test Data: จำนวน Point = 150, Passcode = 1234
            Test Step: 1.เปิดแอปพลิเคชันและเข้าสู่ระบบ
                       2.เลือกทำรายการโอน Point และระบุจำนวน Point และ Passcode
                       3.กดยืนยันการทำรายการ
            Expect Result: การทำรายการสำเร็จโดยไม่มีการคิดค่า Fee
            Priority: High
            Technique: Boundary Value Analysis (BVA)
            
            Test Case No.: TC002
            Test Case: การโอน Point โดยจำนวน Point น้อยกว่าขั้นต่ำและระบบคิดค่า Fee
            Description: ทดสอบการโอน Point โดยจำนวน Point น้อยกว่าขั้นต่ำที่กำหนด และระบบคิดค่า Fee 8 Point เพิ่มเข้าไป
            Test Data: จำนวน Point = 50, Passcode = 1234
            Test Step: 1.เปิดแอปพลิเคชันและเข้าสู่ระบบ
                       2.เลือกทำรายการโอน Point และระบุจำนวน Point และ Passcode
                       3.กดยืนยันการทำรายการ
            Expect Result: การทำรายการสำเร็จและระบบคิดค่า Fee 8 Point จากจำนวน Point ที่โอน
            Priority: High
            Technique: Boundary Value Analysis (BVA)
            
            Test Case No.: TC003
            Test Case: การโอน Point โดยจำนวน Point เกินขีดจำกัดสูงสุด
            Description: ทดสอบการโอน Point โดยจำนวน Point เกินขีดจำกัดสูงสุดที่กำหนด
            Test Data: จำนวน Point = 3,200, Passcode = 1234
            Test Step: 1.เปิดแอปพลิเคชันและเข้าสู่ระบบ
                       2.เลือกทำรายการโอน Point และกรอกจำนวน Point และ Passcode
                       3.กดยืนยันการทำรายการ
            Expect Result: การทำรายการล้มเหลวเนื่องจากจำนวน Point เกินขีดจำกัดสูงสุด
            Priority: High
            Technique: Boundary Value Analysis (BVA)
            
            Test Case No.: TC004
            Test Case: การโอน Point โดยกรอก Passcode ไม่ถูกต้อง
            Description: ทดสอบการโอน Point โดยกรอก Passcode ไม่ถูกต้อง
            Test Data: จำนวน Point = 200, Passcode = 1111
            Test Step: 1.เปิดแอปพลิเคชันและเข้าสู่ระบบ
                       2.เลือกทำรายการโอน Point และกรอกจำนวน Point และ Passcode
                       3.กดยืนยันการทำรายการ
            Expect Result: การทำรายการล้มเหลวเนื่องจาก Passcode ไม่ถูกต้อง
            Priority: High
            Technique: Equivalence Partitioning
            
            Test Case No.: TC005
            Test Case: การโอน Point โดยจำนวน Point มากกว่าขั้นต่ำและกรอก Passcode ถูกต้อง
            Description: ทดสอบการโอน Point โดยจำนวน Point มากกว่าขั้นต่ำและกรอก Passcode ถูกต้อง
            Test Data: จำนวน Point = 500, Passcode = 1234
            Test Step: 1.เปิดแอปพลิเคชันและเข้าสู่ระบบ
                       2.เลือกทำรายการโอน Point และกรอกจำนวน Point และ Passcode
                       3.กดยืนยันการทำรายการ
            Expect Result: การทำรายการสำเร็จและไม่คิดค่า Fee
            Priority: High
            Technique: Decision Table Testing

#### Question 3 หากทีมต้องการทดสอบ Feature ในข้อ 2 จะต้องมี Test Plan อย่างไร?

Answer 3

              1.การรวบรวมข้อมูล
              -ศึกษาเงื่อนไขและกฎระเบียบที่เกี่ยวข้องกับการโอน Point ตามที่กำหนดใน Feature นี้
              -รวบรวมข้อกำหนดและข้อจำกัดที่เกี่ยวข้อง เช่น ขั้นต่ำและสูงสุดในการโอน Point, การคิดค่า Fee, การยืนยัน Passcode เป็นต้น
              
              2.การกำหนดขอบเขตของการทดสอบ (Test Scope)
              -ระบุ Feature ที่ต้องการทดสอบอย่างชัดเจน
              -ระบุรายละเอียดเกี่ยวกับการทดสอบแต่ละประการ เช่น การโอน Point โดยมีเงื่อนไขต่างๆ ตามที่กำหนดในโจทย์
              
              3.การสร้าง Test Cases
              -สร้าง Test Cases ที่ครอบคลุมและเป็นไปตามข้อกำหนดของ Feature
              -แต่ละ Test Case ควรระบุเงื่อนไขของการทดสอบ ข้อมูลทดสอบที่ใช้ ขั้นตอนการทดสอบ และผลลัพธ์ที่คาดหวัง
              
              4.การกำหนดสภาพแวดล้อมทดสอบ
              -ระบุสภาพแวดล้อมที่จะใช้ในการทดสอบ เช่น อุปกรณ์ที่ใช้, ซอฟต์แวร์ที่ใช้, และข้อมูลทดสอบ
              
              5.การกำหนดแผนการทดสอบ
              -กำหนดระยะเวลาและวันเวลาที่จะทำการทดสอบ
              -กำหนดผู้รับผิดชอบในการทำแต่ละ Test Case
              -จัดการสร้างและจัดทำเอกสารทดสอบอื่นๆ เช่น Test Data, Test Execution Report, และ Test Summary Report
              
              6.การรายงานและประเมินผล
              -รายงานผลการทดสอบเพื่อปรับปรุงแผนการทดสอบในอนาคต
              -ประเมินผลการทดสอบเพื่อปรับปรุง Feature หรือแก้ไขข้อบกพร่องที่พบ
              
              7.การอนุมัติและการทบทวน
              -อนุมัติ Test Plan จากผู้ที่เกี่ยวข้อง
              -ทบทวนและปรับปรุง Test Plan ตามความเหมาะสมและความต้องการของโปรเจค

#### Question 4 Software Testing มีความสำคัญอย่างไรในการพัฒนาระบบ

Answer 4

              1.คุณภาพของซอฟต์แวร์ : การทดสอบช่วยให้สามารถค้นพบและแก้ไขข้อบกพร่องหรือข้อผิดพลาดในระบบซอฟต์แวร์ได้อย่างรวดเร็ว ซึ่งจะช่วยให้ซอฟต์แวร์มีคุณภาพที่ดีและน่าเชื่อถือมากขึ้น
              2.ลดค่าใช้จ่าย : การค้นพบและแก้ไขข้อบกพร่องในระหว่างขั้นตอนการพัฒนานั้นช่วยลดค่าใช้จ่ายในการแก้ไขข้อผิดพลาดหรือปัญหาที่เกิดขึ้นในขั้นตอนหลังการนำระบบไปใช้งาน
              3.ความเชื่อถือในระบบ : การทดสอบที่ดีช่วยให้ผู้ใช้มีความมั่นใจว่าซอฟต์แวร์จะทำงานได้ตามที่คาดหวัง และนำไปสู่ความเชื่อมั่นในระบบ
              4.อุดรูช่องโหว่ที่อาจทำให้ระบบมีข้อบกพร่อง : การทดสอบช่วยลดโอกาสในการล้มเหลวของระบบในขณะที่ใช้งานจริง โดยการค้นพบและแก้ไขข้อบกพร่องในระหว่างการทดสอบจะช่วยป้องกันปัญหาที่อาจเกิดขึ้นในอนาคต
              5.เพิ่มประสิทธิภาพในการพัฒนา : การทดสอบช่วยให้ทีมพัฒนามีข้อมูลที่มีประสิทธิภาพในการปรับปรุงและปรับปรุงซอฟต์แวร์ เช่น การเปรียบเทียบผลลัพธ์จากการทดสอบกับคุณสมบัติที่กำหนดไว้
              6.ความพึงพอใจของผู้ใช้ : การทดสอบช่วยให้ผู้ใช้มีประสิทธิภาพสูงขึ้น และประทับใจกับประสิทธิภาพและคุณภาพของซอฟต์แวร์ที่ใช้งานได้อย่างน่าพอใจ

## Section 2 - Automate Testing WEB Skills

จงใช้ Robot framework หรือ Selenium เพื่อพัฒนา Automate Test system ตาม test case ดังนี้

-เปิด Browser และไปที่ Link https://www.nejavu.com

-ถ้ามี Banner pop-up ขึ้นมาให้กดปิด Modal (แต่ถ้าไม่ทำข้อต่อไปได้เลย)

-Click menu “การ์ตูน”

-Get ชื่อหนังสือทุกเล่มในแถวที่หนึ่ง

-กดปุ่ม “ใส่ตระกร้า” หนังสือทุกเล่มแถวที่หนึ่ง

-กดปุ่ม “รถเข็น / ตระกร้า”

-Verify ชื่อหนังสือทุกเล่ม ที่อยู่ในตระกร้า โดยใช้ชื่อที่ได้มาจากข้อที่แล้ว

-ลบหนังสือทุกเล่มที่อยู่ในตระกร้า

-Verify badge บนรถเข็นว่าเหลือหนังสือเท่ากับ 0

Answer 

## Section 3: Automate Testing API Skills

จงใช้ Postman, Robot framework หรือ Selenium เพื่อพัฒนาระบบทดสอบ API โดยให้ส่ง Request และตรวจสอบ Response แบบ Automate Testing

1.GET - All Users : https://reqres.in/api/users [Status code : 200]

2.GET - User Info : https://reqres.in/api/users/1 [Status code : 200]

3.POST - Create User : https://reqres.in/api/users [Status code : 201]

    //request body example
    {
        "name": "Yourname",
        "job": "Your Position"
    }
  
4.PATCH - Update User : https://reqres.in/api/users/id [Status code : 200]

    //Required id From Create User
    //request body example
    {
        "name": "Your nickname",
        "job": "Your Position"
    }
5.DELETE - Delete User : https://reqres.in/api/users/id [Status code : 204]

    //Required id From Create User
    //request body example
    {
        "name": "Your nickname",
        "job": "Your Position"
    }

Answer
          
            สำหรับการทดสอบ API โดยใช้ Postman สามารถทำได้ตามขั้นตอนดังนี้:           
            1.ดาวน์โหลดและติดตั้ง Postman จาก https://www.postman.com/downloads/
            2.เปิด Postman และสร้าง Collection ใหม่โดยคลิกที่ "New" > "Collection" แล้วตั้งชื่อ Collection เช่น "API Testing"
            3.เพิ่ม Request แต่ละชนิดเข้าไปใน Collection โดยใช้ URL และ Method ตามที่กำหนด
              GET - All Users:
                URL: https://reqres.in/api/users
                Method: GET
              GET - User Info:
                URL: https://reqres.in/api/users/1
                Method: GET
              POST - Create User:
                URL: https://reqres.in/api/users
                Method: POST
                Headers: Content-Type: application/json
                Body (raw JSON):
                
              //json
              {
                  "name": "Yourname",
                  "job": "Your Position"
              }
            
              PATCH - Update User:
                URL: https://reqres.in/api/users/id (Replace "id" with the actual user ID)
                Method: PATCH
                Headers: Content-Type: application/json
                Body (raw JSON):
                
              //json
              {
                  "name": "Your nickname",
                  "job": "Your Position"
              }
            
              DELETE - Delete User:
                URL: https://reqres.in/api/users/id (Replace "id" with the actual user ID)
                Method: DELETE
            4.เพิ่มการตรวจสอบ Response ด้วยการเพิ่ม Tests ในแต่ละ Request ตามความต้องการ เช่น ตรวจสอบ status code หรือเนื้อหาของ Response
            5.รันทุก Request และตรวจสอบผลลัพธ์
            6.สามารถทำการ Export Collection เพื่อนำไปใช้งานหรือแบ่งปันได้
