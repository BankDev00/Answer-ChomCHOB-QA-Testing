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
