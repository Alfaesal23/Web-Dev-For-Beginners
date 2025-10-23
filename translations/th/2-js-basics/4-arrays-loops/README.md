<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9197f8af0fef9be6e81d4dbda23c7e7d",
  "translation_date": "2025-10-23T20:44:10+00:00",
  "source_file": "2-js-basics/4-arrays-loops/README.md",
  "language_code": "th"
}
-->
# พื้นฐาน JavaScript: อาร์เรย์และลูป

![JavaScript Basics - Arrays](../../../../translated_images/webdev101-js-arrays.439d7528b8a294558d0e4302e448d193f8ad7495cc407539cc81f1afe904b470.th.png)
> สเก็ตโน้ตโดย [Tomomi Imura](https://twitter.com/girlie_mac)

## แบบทดสอบก่อนเรียน
[แบบทดสอบก่อนเรียน](https://ff-quizzes.netlify.app/web/quiz/13)

เคยสงสัยไหมว่าเว็บไซต์ติดตามรายการในตะกร้าสินค้าหรือแสดงรายชื่อเพื่อนของคุณได้อย่างไร? นั่นคือที่มาของอาร์เรย์และลูป อาร์เรย์เปรียบเสมือนภาชนะดิจิทัลที่เก็บข้อมูลหลายชิ้นไว้ด้วยกัน ส่วนลูปช่วยให้คุณทำงานกับข้อมูลเหล่านั้นได้อย่างมีประสิทธิภาพโดยไม่ต้องเขียนโค้ดซ้ำซาก

เมื่อรวมสองแนวคิดนี้เข้าด้วยกัน จะเป็นพื้นฐานสำคัญในการจัดการข้อมูลในโปรแกรมของคุณ คุณจะได้เรียนรู้วิธีการเปลี่ยนจากการเขียนโค้ดทีละขั้นตอนมาเป็นการสร้างโค้ดที่ฉลาดและมีประสิทธิภาพ ซึ่งสามารถประมวลผลข้อมูลหลายร้อยหรือหลายพันรายการได้อย่างรวดเร็ว

เมื่อจบบทเรียนนี้ คุณจะเข้าใจวิธีการจัดการงานข้อมูลที่ซับซ้อนด้วยโค้ดเพียงไม่กี่บรรทัด มาเริ่มสำรวจแนวคิดการเขียนโปรแกรมที่สำคัญเหล่านี้กันเถอะ

[![Arrays](https://img.youtube.com/vi/1U4qTyq02Xw/0.jpg)](https://youtube.com/watch?v=1U4qTyq02Xw "Arrays")

[![Loops](https://img.youtube.com/vi/Eeh7pxtTZ3k/0.jpg)](https://www.youtube.com/watch?v=Eeh7pxtTZ3k "Loops")

> 🎥 คลิกที่ภาพด้านบนเพื่อดูวิดีโอเกี่ยวกับอาร์เรย์และลูป

> คุณสามารถเรียนบทเรียนนี้ได้ที่ [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-arrays/?WT.mc_id=academic-77807-sagibbon)!

## อาร์เรย์

ลองนึกถึงอาร์เรย์เหมือนตู้เก็บเอกสารดิจิทัล - แทนที่จะเก็บเอกสารหนึ่งฉบับต่อหนึ่งลิ้นชัก คุณสามารถจัดระเบียบรายการที่เกี่ยวข้องหลายรายการในภาชนะที่มีโครงสร้างเดียว ในแง่ของการเขียนโปรแกรม อาร์เรย์ช่วยให้คุณเก็บข้อมูลหลายชิ้นไว้ในแพ็คเกจที่จัดระเบียบเดียว

ไม่ว่าคุณจะสร้างแกลเลอรีภาพถ่าย จัดการรายการสิ่งที่ต้องทำ หรือเก็บคะแนนสูงสุดในเกม อาร์เรย์เป็นพื้นฐานสำหรับการจัดระเบียบข้อมูล ลองมาดูกันว่าอาร์เรย์ทำงานอย่างไร

✅ อาร์เรย์มีอยู่รอบตัวเรา! คุณสามารถคิดถึงตัวอย่างอาร์เรย์ในชีวิตจริงได้ไหม เช่น แผงโซลาร์เซลล์?

### การสร้างอาร์เรย์

การสร้างอาร์เรย์นั้นง่ายมาก - เพียงแค่ใช้วงเล็บเหลี่ยม!

```javascript
// Empty array - like an empty shopping cart waiting for items
const myArray = [];
```

**เกิดอะไรขึ้นที่นี่?**
คุณเพิ่งสร้างภาชนะเปล่าด้วยวงเล็บเหลี่ยม `[]` ลองนึกถึงมันเหมือนชั้นวางหนังสือเปล่า - พร้อมที่จะเก็บหนังสืออะไรก็ได้ที่คุณต้องการจัดระเบียบไว้ที่นั่น

คุณยังสามารถเติมค่าเริ่มต้นในอาร์เรย์ได้ตั้งแต่เริ่มต้น:

```javascript
// Your ice cream shop's flavor menu
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// A user's profile info (mixing different types of data)
const userData = ["John", 25, true, "developer"];

// Test scores for your favorite class
const scores = [95, 87, 92, 78, 85];
```

**สิ่งที่น่าสังเกต:**
- คุณสามารถเก็บข้อความ ตัวเลข หรือแม้กระทั่งค่าจริง/เท็จในอาร์เรย์เดียวกัน
- เพียงแค่แยกแต่ละรายการด้วยเครื่องหมายจุลภาค - ง่ายมาก!
- อาร์เรย์เหมาะสำหรับการเก็บข้อมูลที่เกี่ยวข้องไว้ด้วยกัน

### การเข้าถึงอาร์เรย์ด้วยดัชนี

นี่คือสิ่งที่อาจดูแปลกในตอนแรก: อาร์เรย์จะเริ่มนับรายการจาก 0 ไม่ใช่ 1 การนับดัชนีเริ่มจากศูนย์นี้มีรากฐานมาจากวิธีการทำงานของหน่วยความจำคอมพิวเตอร์ - เป็นธรรมเนียมปฏิบัติของการเขียนโปรแกรมตั้งแต่ยุคแรกของภาษาโปรแกรมอย่าง C แต่ละตำแหน่งในอาร์เรย์จะได้รับหมายเลขที่อยู่ของตัวเองเรียกว่า **ดัชนี**

| ดัชนี | ค่า | คำอธิบาย |
|-------|-------|-------------|
| 0 | "Chocolate" | องค์ประกอบแรก |
| 1 | "Strawberry" | องค์ประกอบที่สอง |
| 2 | "Vanilla" | องค์ประกอบที่สาม |
| 3 | "Pistachio" | องค์ประกอบที่สี่ |
| 4 | "Rocky Road" | องค์ประกอบที่ห้า |

✅ คุณแปลกใจไหมที่อาร์เรย์เริ่มต้นดัชนีที่ศูนย์? ในบางภาษาโปรแกรม ดัชนีเริ่มต้นที่ 1 มีประวัติที่น่าสนใจเกี่ยวกับเรื่องนี้ ซึ่งคุณสามารถ [อ่านเพิ่มเติมได้ที่ Wikipedia](https://en.wikipedia.org/wiki/Zero-based_numbering)

**การเข้าถึงองค์ประกอบในอาร์เรย์:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// Access individual elements using bracket notation
console.log(iceCreamFlavors[0]); // "Chocolate" - first element
console.log(iceCreamFlavors[2]); // "Vanilla" - third element
console.log(iceCreamFlavors[4]); // "Rocky Road" - last element
```

**การทำงานที่เกิดขึ้น:**
- **ใช้** สัญลักษณ์วงเล็บเหลี่ยมพร้อมหมายเลขดัชนีเพื่อเข้าถึงองค์ประกอบ
- **คืนค่า** ที่เก็บไว้ในตำแหน่งเฉพาะในอาร์เรย์
- **เริ่มต้น** นับจาก 0 ทำให้องค์ประกอบแรกมีดัชนีเป็น 0

**การแก้ไของค์ประกอบในอาร์เรย์:**

```javascript
// Change an existing value
iceCreamFlavors[4] = "Butter Pecan";
console.log(iceCreamFlavors[4]); // "Butter Pecan"

// Add a new element at the end
iceCreamFlavors[5] = "Cookie Dough";
console.log(iceCreamFlavors[5]); // "Cookie Dough"
```

**ในตัวอย่างข้างต้น เราได้:**
- **แก้ไข** องค์ประกอบที่ดัชนี 4 จาก "Rocky Road" เป็น "Butter Pecan"
- **เพิ่ม** องค์ประกอบใหม่ "Cookie Dough" ที่ดัชนี 5
- **ขยาย** ความยาวของอาร์เรย์โดยอัตโนมัติเมื่อเพิ่มเกินขอบเขตปัจจุบัน

### ความยาวของอาร์เรย์และเมธอดที่ใช้บ่อย

อาร์เรย์มาพร้อมกับคุณสมบัติและเมธอดในตัวที่ทำให้การทำงานกับข้อมูลง่ายขึ้นมาก

**การหาความยาวของอาร์เรย์:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
console.log(iceCreamFlavors.length); // 5

// Length updates automatically as array changes
iceCreamFlavors.push("Mint Chip");
console.log(iceCreamFlavors.length); // 6
```

**จุดสำคัญที่ควรจำ:**
- **คืนค่า** จำนวนองค์ประกอบทั้งหมดในอาร์เรย์
- **อัปเดต** โดยอัตโนมัติเมื่อมีการเพิ่มหรือลบองค์ประกอบ
- **ให้** จำนวนที่เปลี่ยนแปลงได้ซึ่งมีประโยชน์สำหรับลูปและการตรวจสอบ

**เมธอดสำคัญของอาร์เรย์:**

```javascript
const fruits = ["apple", "banana", "orange"];

// Add elements
fruits.push("grape");           // Adds to end: ["apple", "banana", "orange", "grape"]
fruits.unshift("strawberry");   // Adds to beginning: ["strawberry", "apple", "banana", "orange", "grape"]

// Remove elements
const lastFruit = fruits.pop();        // Removes and returns "grape"
const firstFruit = fruits.shift();     // Removes and returns "strawberry"

// Find elements
const index = fruits.indexOf("banana"); // Returns 1 (position of "banana")
const hasApple = fruits.includes("apple"); // Returns true
```

**การทำความเข้าใจเมธอดเหล่านี้:**
- **เพิ่ม** องค์ประกอบด้วย `push()` (ท้าย) และ `unshift()` (ต้น)
- **ลบ** องค์ประกอบด้วย `pop()` (ท้าย) และ `shift()` (ต้น)
- **ค้นหา** องค์ประกอบด้วย `indexOf()` และตรวจสอบการมีอยู่ด้วย `includes()`
- **คืนค่า** ค่าที่มีประโยชน์ เช่น องค์ประกอบที่ถูกลบหรือดัชนีตำแหน่ง

✅ ลองทำด้วยตัวเอง! ใช้คอนโซลในเบราว์เซอร์ของคุณเพื่อสร้างและจัดการอาร์เรย์ที่คุณสร้างขึ้นเอง

## ลูป

ลองนึกถึงการลงโทษที่มีชื่อเสียงในนิยายของ Charles Dickens ที่นักเรียนต้องเขียนประโยคซ้ำๆ บนกระดานชนวน ลองจินตนาการว่าคุณสามารถสั่งให้ใครสักคน "เขียนประโยคนี้ 100 ครั้ง" และให้มันทำโดยอัตโนมัติ นั่นคือสิ่งที่ลูปทำให้โค้ดของคุณ

ลูปเปรียบเสมือนผู้ช่วยที่ไม่รู้จักเหนื่อยซึ่งสามารถทำงานซ้ำๆ ได้โดยไม่มีข้อผิดพลาด ไม่ว่าคุณจะต้องตรวจสอบทุกรายการในตะกร้าสินค้าหรือแสดงภาพทั้งหมดในอัลบั้ม ลูปจะจัดการการทำงานซ้ำได้อย่างมีประสิทธิภาพ

JavaScript มีลูปหลายประเภทให้เลือกใช้ ลองมาดูแต่ละประเภทและเข้าใจว่าเมื่อใดควรใช้

### For Loop

`for` loop เปรียบเสมือนการตั้งเวลานับถอยหลัง - คุณรู้แน่ชัดว่าต้องการให้บางสิ่งเกิดขึ้นกี่ครั้ง มันมีการจัดระเบียบและคาดการณ์ได้ดีมาก ซึ่งทำให้เหมาะสำหรับการทำงานกับอาร์เรย์หรือการนับสิ่งต่างๆ

**โครงสร้าง For Loop:**

| องค์ประกอบ | วัตถุประสงค์ | ตัวอย่าง |
|-----------|---------|----------|
| **การเริ่มต้น** | กำหนดจุดเริ่มต้น | `let i = 0` |
| **เงื่อนไข** | เมื่อใดที่จะดำเนินการต่อ | `i < 10` |
| **การเพิ่มค่า** | วิธีการอัปเดต | `i++` |

```javascript
// Counting from 0 to 9
for (let i = 0; i < 10; i++) {
  console.log(`Count: ${i}`);
}

// More practical example: processing scores
const testScores = [85, 92, 78, 96, 88];
for (let i = 0; i < testScores.length; i++) {
  console.log(`Student ${i + 1}: ${testScores[i]}%`);
}
```

**ทีละขั้นตอน สิ่งที่เกิดขึ้น:**
- **เริ่มต้น** ตัวแปรตัวนับ `i` เป็น 0 ตั้งแต่เริ่มต้น
- **ตรวจสอบ** เงื่อนไข `i < 10` ก่อนการวนซ้ำแต่ละครั้ง
- **ดำเนินการ** โค้ดบล็อกเมื่อเงื่อนไขเป็นจริง
- **เพิ่มค่า** `i` ทีละ 1 หลังการวนซ้ำแต่ละครั้งด้วย `i++`
- **หยุด** เมื่อเงื่อนไขกลายเป็นเท็จ (เมื่อ `i` ถึง 10)

✅ รันโค้ดนี้ในคอนโซลเบราว์เซอร์ของคุณ เกิดอะไรขึ้นเมื่อคุณเปลี่ยนแปลงตัวนับ เงื่อนไข หรือการแสดงออกการวนซ้ำเล็กน้อย? คุณสามารถทำให้มันนับถอยหลังได้ไหม?

### While Loop

`while` loop เปรียบเสมือนการพูดว่า "ทำสิ่งนี้ต่อไปจนกว่า..." - คุณอาจไม่รู้แน่ชัดว่ามันจะรันกี่ครั้ง แต่คุณรู้ว่าเมื่อใดควรหยุด มันเหมาะสำหรับสิ่งต่างๆ เช่น การขอข้อมูลจากผู้ใช้จนกว่าพวกเขาจะให้สิ่งที่คุณต้องการ หรือการค้นหาข้อมูลจนกว่าคุณจะพบสิ่งที่คุณกำลังมองหา

**ลักษณะของ While Loop:**
- **ดำเนินการต่อ** ตราบใดที่เงื่อนไขเป็นจริง
- **ต้องการ** การจัดการตัวแปรตัวนับด้วยตนเอง
- **ตรวจสอบ** เงื่อนไขก่อนการวนซ้ำแต่ละครั้ง
- **เสี่ยง** การวนซ้ำไม่สิ้นสุดหากเงื่อนไขไม่เคยกลายเป็นเท็จ

```javascript
// Basic counting example
let i = 0;
while (i < 10) {
  console.log(`While count: ${i}`);
  i++; // Don't forget to increment!
}

// More practical example: processing user input
let userInput = "";
let attempts = 0;
const maxAttempts = 3;

while (userInput !== "quit" && attempts < maxAttempts) {
  userInput = prompt(`Enter 'quit' to exit (attempt ${attempts + 1}):`);
  attempts++;
}

if (attempts >= maxAttempts) {
  console.log("Maximum attempts reached!");
}
```

**การทำความเข้าใจตัวอย่างเหล่านี้:**
- **จัดการ** ตัวแปรตัวนับ `i` ด้วยตนเองภายในบล็อกลูป
- **เพิ่มค่า** ตัวนับเพื่อป้องกันการวนซ้ำไม่สิ้นสุด
- **แสดง** กรณีการใช้งานจริงด้วยการป้อนข้อมูลจากผู้ใช้และการจำกัดจำนวนครั้ง
- **รวม** กลไกความปลอดภัยเพื่อป้องกันการดำเนินการไม่สิ้นสุด

### ทางเลือกใหม่สำหรับลูป

JavaScript มีไวยากรณ์ลูปที่ทันสมัยซึ่งสามารถทำให้โค้ดของคุณอ่านง่ายขึ้นและลดข้อผิดพลาด

**For...of Loop (ES6+):**

```javascript
const colors = ["red", "green", "blue", "yellow"];

// Modern approach - cleaner and safer
for (const color of colors) {
  console.log(`Color: ${color}`);
}

// Compare with traditional for loop
for (let i = 0; i < colors.length; i++) {
  console.log(`Color: ${colors[i]}`);
}
```

**ข้อดีของ for...of:**
- **กำจัด** การจัดการดัชนีและข้อผิดพลาดที่อาจเกิดขึ้น
- **ให้** การเข้าถึงองค์ประกอบในอาร์เรย์โดยตรง
- **ปรับปรุง** ความสามารถในการอ่านโค้ดและลดความซับซ้อนของไวยากรณ์

**เมธอด forEach:**

```javascript
const prices = [9.99, 15.50, 22.75, 8.25];

// Using forEach for functional programming style
prices.forEach((price, index) => {
  console.log(`Item ${index + 1}: $${price.toFixed(2)}`);
});

// forEach with arrow functions for simple operations
prices.forEach(price => console.log(`Price: $${price}`));
```

**สิ่งที่คุณต้องรู้เกี่ยวกับ forEach:**
- **ดำเนินการ** ฟังก์ชันสำหรับองค์ประกอบแต่ละตัวในอาร์เรย์
- **ให้** ค่าองค์ประกอบและดัชนีเป็นพารามิเตอร์
- **ไม่สามารถ** หยุดก่อนเวลา (ไม่เหมือนลูปแบบดั้งเดิม)
- **คืนค่า** undefined (ไม่ได้สร้างอาร์เรย์ใหม่)

✅ ทำไมคุณถึงเลือกใช้ for loop แทน while loop? มีผู้ชม 17K คนที่มีคำถามเดียวกันใน StackOverflow และบางความคิดเห็น [อาจน่าสนใจสำหรับคุณ](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript)

## ลูปและอาร์เรย์

การรวมอาร์เรย์กับลูปสร้างความสามารถในการประมวลผลข้อมูลที่ทรงพลัง การจับคู่แบบนี้เป็นพื้นฐานของงานการเขียนโปรแกรมหลายอย่าง ตั้งแต่การแสดงรายการไปจนถึงการคำนวณสถิติ

**การประมวลผลอาร์เรย์แบบดั้งเดิม:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// Classic for loop approach
for (let i = 0; i < iceCreamFlavors.length; i++) {
  console.log(`Flavor ${i + 1}: ${iceCreamFlavors[i]}`);
}

// Modern for...of approach
for (const flavor of iceCreamFlavors) {
  console.log(`Available flavor: ${flavor}`);
}
```

**มาทำความเข้าใจแต่ละวิธี:**
- **ใช้** คุณสมบัติความยาวของอาร์เรย์เพื่อกำหนดขอบเขตลูป
- **เข้าถึง** องค์ประกอบโดยดัชนีใน for loop แบบดั้งเดิม
- **ให้** การเข้าถึงองค์ประกอบโดยตรงใน for...of loop
- **ประมวลผล** องค์ประกอบแต่ละตัวในอาร์เรย์เพียงครั้งเดียว

**ตัวอย่างการประมวลผลข้อมูลจริง:**

```javascript
const studentGrades = [85, 92, 78, 96, 88, 73, 89];
let total = 0;
let highestGrade = studentGrades[0];
let lowestGrade = studentGrades[0];

// Process all grades with a single loop
for (let i = 0; i < studentGrades.length; i++) {
  const grade = studentGrades[i];
  total += grade;
  
  if (grade > highestGrade) {
    highestGrade = grade;
  }
  
  if (grade < lowestGrade) {
    lowestGrade = grade;
  }
}

const average = total / studentGrades.length;
console.log(`Average: ${average.toFixed(1)}`);
console.log(`Highest: ${highestGrade}`);
console.log(`Lowest: ${lowestGrade}`);
```

**นี่คือวิธีการทำงานของโค้ดนี้:**
- **เริ่มต้น** ตัวแปรติดตามสำหรับผลรวมและค่าที่สุดขั้ว
- **ประมวลผล** คะแนนแต่ละตัวด้วยลูปที่มีประสิทธิภาพเดียว
- **สะสม** ผลรวมสำหรับการคำนวณค่าเฉลี่ย
- **ติดตาม** ค่าสูงสุดและต่ำสุดระหว่างการวนซ้ำ
- **คำนวณ** สถิติสุดท้ายหลังจากการวนซ้ำเสร็จสิ้น

✅ ทดลองวนซ้ำอาร์เรย์ที่คุณสร้างขึ้นเองในคอนโซลเบราว์เซอร์ของคุณ

---

## GitHub Copilot Agent Challenge 🚀

ใช้โหมด Agent เพื่อทำภารกิจต่อไปนี้:

**คำอธิบาย:** สร้างฟังก์ชันการประมวลผลข้อมูลที่ครอบคลุมซึ่งรวมอาร์เรย์และลูปเพื่อวิเคราะห์ชุดข้อมูลและสร้างข้อมูลเชิงลึกที่มีความหมาย

**คำสั่ง:** สร้างฟังก์ชันชื่อ `analyzeGrades` ที่รับอาร์เรย์ของออบเจ็กต์คะแนนนักเรียน (แต่ละออบเจ็กต์มีคุณสมบัติ name และ score) และคืนค่าออบเจ็กต์ที่มีสถิติรวมถึงคะแนนสูงสุด คะแนนต่ำสุด คะแนนเฉลี่ย จำนวนของนักเรียนที่ผ่าน (คะแนน >= 70) และอาร์เรย์ของชื่อนักเรียนที่ได้คะแนนสูงกว่าค่าเฉลี่ย ใช้ลูปอย่างน้อยสองประเภทในโซลูชันของคุณ

เรียนรู้เพิ่มเติมเกี่ยวกับ [โหมด Agent](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) ที่นี่

## 🚀 ภารกิจ

JavaScript มีเมธอดอาร์เรย์ที่ทันสมัยหลายตัวที่สามารถแทนที่ลูปแบบดั้งเดิมสำหรับงานเฉพาะ ลองสำรวจ [forEach](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach), [for-of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of), [map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [filter](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), และ [reduce](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)

**ภารกิจของคุณ:** ปรับปรุงตัวอย่างคะแนนนักเรียนโดยใช้เมธอดอาร์เรย์อย่างน้อยสามตัว สังเกตว่าโค้ดสะอาดและอ่านง่ายขึ้นมากด้วยไวยากรณ์ JavaScript ที่ทันสมัย

## แบบทดสอบหลังเรียน
[แบบทดสอบหลังเรียน](https://ff-quizzes.netlify.app/web/quiz/14)

## ทบทวนและศึกษาด้วยตนเอง

อาร์เรย์ใน JavaScript มีเมธอดมากมายที่มีประโยชน์อย่างยิ่งสำหรับการจัดการข้อมูล [อ่านเพิ่มเติมเกี่ยวกับเมธอดเหล่านี้](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array) และลองใช้บางเมธอด (เช่น push, pop, slice และ splice) กับอาร์เรย์ที่คุณสร้างขึ้นเอง

## งานที่ได้รับมอบหมาย

[วนซ้ำอาร์เรย์](assignment.md)

---

**ข้อจำกัดความรับผิดชอบ**:  
เอกสารนี้ได้รับการแปลโดยใช้บริการแปลภาษา AI [Co-op Translator](https://github.com/Azure/co-op-translator) แม้ว่าเราจะพยายามให้การแปลมีความถูกต้อง แต่โปรดทราบว่าการแปลอัตโนมัติอาจมีข้อผิดพลาดหรือความไม่ถูกต้อง เอกสารต้นฉบับในภาษาดั้งเดิมควรถือเป็นแหล่งข้อมูลที่เชื่อถือได้ สำหรับข้อมูลที่สำคัญ ขอแนะนำให้ใช้บริการแปลภาษามืออาชีพ เราไม่รับผิดชอบต่อความเข้าใจผิดหรือการตีความผิดที่เกิดจากการใช้การแปลนี้