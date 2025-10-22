<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9197f8af0fef9be6e81d4dbda23c7e7d",
  "translation_date": "2025-10-22T14:33:06+00:00",
  "source_file": "2-js-basics/4-arrays-loops/README.md",
  "language_code": "ur"
}
-->
# جاوا اسکرپٹ کی بنیادی باتیں: Arrays اور Loops

![جاوا اسکرپٹ کی بنیادی باتیں - Arrays](../../../../translated_images/webdev101-js-arrays.439d7528b8a294558d0e4302e448d193f8ad7495cc407539cc81f1afe904b470.ur.png)
> اسکیچ نوٹ [Tomomi Imura](https://twitter.com/girlie_mac) کی جانب سے

## لیکچر سے پہلے کا کوئز
[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/13)

کبھی سوچا ہے کہ ویب سائٹس شاپنگ کارٹ آئٹمز کو کیسے ٹریک کرتی ہیں یا آپ کے دوستوں کی فہرست کیسے دکھاتی ہیں؟ یہی وہ جگہ ہے جہاں arrays اور loops کام آتے ہیں۔ Arrays ڈیجیٹل کنٹینرز کی طرح ہیں جو کئی معلومات کو ایک ساتھ رکھتے ہیں، جبکہ loops آپ کو اس ڈیٹا کے ساتھ مؤثر طریقے سے کام کرنے دیتے ہیں بغیر بار بار کوڈ لکھے۔

یہ دونوں تصورات مل کر آپ کے پروگرامز میں معلومات کو سنبھالنے کی بنیاد بناتے ہیں۔ آپ سیکھیں گے کہ ہر قدم کو دستی طور پر لکھنے سے لے کر ذہین اور مؤثر کوڈ بنانے تک کیسے جائیں جو سیکڑوں یا ہزاروں آئٹمز کو جلدی سے پروسیس کر سکے۔

اس سبق کے اختتام تک، آپ سمجھ جائیں گے کہ پیچیدہ ڈیٹا کے کاموں کو صرف چند لائنوں کے کوڈ کے ذریعے کیسے انجام دیا جا سکتا ہے۔ آئیے ان ضروری پروگرامنگ تصورات کو دریافت کریں۔

[![Arrays](https://img.youtube.com/vi/1U4qTyq02Xw/0.jpg)](https://youtube.com/watch?v=1U4qTyq02Xw "Arrays")

[![Loops](https://img.youtube.com/vi/Eeh7pxtTZ3k/0.jpg)](https://www.youtube.com/watch?v=Eeh7pxtTZ3k "Loops")

> 🎥 اوپر دی گئی تصاویر پر کلک کریں arrays اور loops کے بارے میں ویڈیوز دیکھنے کے لیے۔

> آپ یہ سبق [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-arrays/?WT.mc_id=academic-77807-sagibbon) پر لے سکتے ہیں!

## Arrays

Arrays کو ایک ڈیجیٹل فائلنگ کابینہ کے طور پر سوچیں - ایک دراز میں ایک دستاویز رکھنے کے بجائے، آپ کئی متعلقہ آئٹمز کو ایک ہی منظم کنٹینر میں ترتیب دے سکتے ہیں۔ پروگرامنگ کی زبان میں، arrays آپ کو کئی معلومات کو ایک منظم پیکج میں رکھنے دیتے ہیں۔

چاہے آپ فوٹو گیلری بنا رہے ہوں، ٹو ڈو لسٹ کا انتظام کر رہے ہوں، یا گیم میں ہائی اسکورز کو ٹریک کر رہے ہوں، arrays ڈیٹا کی تنظیم کے لیے بنیاد فراہم کرتے ہیں۔ آئیے دیکھتے ہیں کہ یہ کیسے کام کرتے ہیں۔

✅ Arrays ہر جگہ موجود ہیں! کیا آپ arrays کی کوئی حقیقی زندگی کی مثال دے سکتے ہیں، جیسے کہ سولر پینل array؟

### Arrays بنانا

Array بنانا بہت آسان ہے - بس مربع بریکٹس استعمال کریں!

```javascript
// Empty array - like an empty shopping cart waiting for items
const myArray = [];
```

**یہاں کیا ہو رہا ہے؟**
آپ نے ابھی مربع بریکٹس `[]` استعمال کر کے ایک خالی کنٹینر بنایا ہے۔ اسے ایک خالی لائبریری شیلف کی طرح سوچیں - یہ تیار ہے کہ آپ جو کتابیں وہاں ترتیب دینا چاہیں۔

آپ اپنے array کو شروع سے ہی ابتدائی اقدار سے بھر سکتے ہیں:

```javascript
// Your ice cream shop's flavor menu
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// A user's profile info (mixing different types of data)
const userData = ["John", 25, true, "developer"];

// Test scores for your favorite class
const scores = [95, 87, 92, 78, 85];
```

**نوٹ کرنے کے لیے دلچسپ چیزیں:**
- آپ ایک ہی array میں متن، نمبر، یا حتیٰ کہ true/false اقدار کو بھی رکھ سکتے ہیں
- ہر آئٹم کو ایک کاما سے الگ کریں - آسان!
- Arrays متعلقہ معلومات کو ایک ساتھ رکھنے کے لیے بہترین ہیں

### Array Indexing

یہاں ایک چیز ہے جو شروع میں غیر معمولی لگ سکتی ہے: arrays اپنے آئٹمز کو 0 سے شروع کر کے نمبر دیتے ہیں، 1 سے نہیں۔ یہ zero-based indexing کمپیوٹر میموری کے کام کرنے کے طریقے کی جڑوں میں ہے - یہ پروگرامنگ کی روایت ہے جو C جیسی کمپیوٹنگ زبانوں کے ابتدائی دنوں سے چلی آ رہی ہے۔ array میں ہر جگہ کو ایک ایڈریس نمبر ملتا ہے جسے **index** کہا جاتا ہے۔

| Index | Value | Description |
|-------|-------|-------------|
| 0 | "Chocolate" | پہلا عنصر |
| 1 | "Strawberry" | دوسرا عنصر |
| 2 | "Vanilla" | تیسرا عنصر |
| 3 | "Pistachio" | چوتھا عنصر |
| 4 | "Rocky Road" | پانچواں عنصر |

✅ کیا یہ آپ کو حیران کرتا ہے کہ arrays 0 index سے شروع ہوتے ہیں؟ کچھ پروگرامنگ زبانوں میں indexes 1 سے شروع ہوتے ہیں۔ اس کے پیچھے دلچسپ تاریخ ہے، جسے آپ [Wikipedia پر پڑھ سکتے ہیں](https://en.wikipedia.org/wiki/Zero-based_numbering)۔

**Array عناصر تک رسائی حاصل کرنا:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// Access individual elements using bracket notation
console.log(iceCreamFlavors[0]); // "Chocolate" - first element
console.log(iceCreamFlavors[2]); // "Vanilla" - third element
console.log(iceCreamFlavors[4]); // "Rocky Road" - last element
```

**یہاں کیا ہو رہا ہے:**
- **استعمال کرتا ہے** مربع بریکٹ نوٹیشن کے ساتھ index نمبر عناصر تک رسائی حاصل کرنے کے لیے
- **واپس کرتا ہے** array میں اس مخصوص پوزیشن پر محفوظ کردہ قدر
- **شروع کرتا ہے** 0 سے گنتی، پہلا عنصر index 0 بناتا ہے

**Array عناصر میں ترمیم کرنا:**

```javascript
// Change an existing value
iceCreamFlavors[4] = "Butter Pecan";
console.log(iceCreamFlavors[4]); // "Butter Pecan"

// Add a new element at the end
iceCreamFlavors[5] = "Cookie Dough";
console.log(iceCreamFlavors[5]); // "Cookie Dough"
```

**اوپر، ہم نے:**
- **ترمیم کی** عنصر index 4 پر "Rocky Road" سے "Butter Pecan" میں
- **ایک نیا عنصر شامل کیا** "Cookie Dough" index 5 پر
- **خود بخود** array کی لمبائی کو موجودہ حدود سے آگے شامل کرنے پر بڑھایا

### Array کی لمبائی اور عام طریقے

Arrays میں بلٹ ان خصوصیات اور طریقے ہوتے ہیں جو ڈیٹا کے ساتھ کام کرنا بہت آسان بنا دیتے ہیں۔

**Array کی لمبائی معلوم کرنا:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
console.log(iceCreamFlavors.length); // 5

// Length updates automatically as array changes
iceCreamFlavors.push("Mint Chip");
console.log(iceCreamFlavors.length); // 6
```

**یاد رکھنے کے اہم نکات:**
- **واپس کرتا ہے** array میں عناصر کی کل تعداد
- **خود بخود اپ ڈیٹ ہوتا ہے** جب عناصر شامل یا ہٹائے جاتے ہیں
- **فراہم کرتا ہے** ایک متحرک شمار جو loops اور validation کے لیے مفید ہے

**ضروری Array طریقے:**

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

**ان طریقوں کو سمجھنا:**
- **شامل کرتا ہے** عناصر کو `push()` (آخر میں) اور `unshift()` (شروع میں)
- **ہٹاتا ہے** عناصر کو `pop()` (آخر میں) اور `shift()` (شروع میں)
- **مقام کا پتہ لگاتا ہے** `indexOf()` کے ساتھ اور موجودگی کو `includes()` کے ساتھ چیک کرتا ہے
- **واپس کرتا ہے** مفید اقدار جیسے ہٹائے گئے عناصر یا پوزیشن indexes

✅ خود آزمائیں! اپنے براؤزر کے کنسول میں ایک array بنائیں اور اس میں ترمیم کریں۔

## Loops

چارلس ڈکنز کے ناولز میں مشہور سزا کے بارے میں سوچیں جہاں طلباء کو بار بار تختی پر لائنیں لکھنی پڑتی تھیں۔ تصور کریں کہ اگر آپ کسی کو صرف یہ ہدایت دے سکیں کہ "یہ جملہ 100 بار لکھو" اور یہ خود بخود ہو جائے۔ یہی کام loops آپ کے کوڈ کے لیے کرتے ہیں۔

Loops ایک تھکے نہ جانے والے معاون کی طرح ہیں جو کاموں کو بغیر کسی غلطی کے دہرا سکتے ہیں۔ چاہے آپ کو شاپنگ کارٹ میں ہر آئٹم کو چیک کرنا ہو یا البم میں تمام تصاویر دکھانی ہوں، loops مؤثر طریقے سے تکرار کو سنبھالتے ہیں۔

جاوا اسکرپٹ کئی قسم کے loops فراہم کرتا ہے جن میں سے آپ انتخاب کر سکتے ہیں۔ آئیے ہر ایک کا جائزہ لیتے ہیں اور سمجھتے ہیں کہ کب ان کا استعمال کرنا ہے۔

### For Loop

`for` loop ایک ٹائمر سیٹ کرنے کی طرح ہے - آپ کو بالکل معلوم ہوتا ہے کہ آپ کچھ کتنی بار چاہتے ہیں۔ یہ بہت منظم اور پیش گوئی کے قابل ہے، جو اسے arrays کے ساتھ کام کرنے یا چیزوں کو گننے کے لیے بہترین بناتا ہے۔

**For Loop کا ڈھانچہ:**

| Component | Purpose | Example |
|-----------|---------|----------|
| **Initialization** | شروع کرنے کا نقطہ سیٹ کرتا ہے | `let i = 0` |
| **Condition** | کب جاری رکھنا ہے | `i < 10` |
| **Increment** | کیسے اپ ڈیٹ کرنا ہے | `i++` |

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

**مرحلہ وار، یہاں کیا ہو رہا ہے:**
- **ابتدائیہ** متغیر `i` کو 0 پر سیٹ کرتا ہے شروع میں
- **چیک کرتا ہے** شرط `i < 10` ہر iteration سے پہلے
- **عمل کرتا ہے** کوڈ بلاک جب شرط سچ ہو
- **اضافہ کرتا ہے** `i` کو 1 سے ہر iteration کے بعد `i++` کے ساتھ
- **روکتا ہے** جب شرط جھوٹ ہو جائے (جب `i` 10 تک پہنچ جائے)

✅ اس کوڈ کو براؤزر کنسول میں چلائیں۔ کیا ہوتا ہے جب آپ counter، condition، یا iteration expression میں چھوٹے تبدیلیاں کرتے ہیں؟ کیا آپ اسے الٹا چلا سکتے ہیں، ایک countdown بناتے ہوئے؟

### While Loop

`while` loop ایسا ہے جیسے کہنا "یہ کرتے رہو جب تک کہ..." - آپ کو شاید معلوم نہ ہو کہ یہ کتنی بار چلے گا، لیکن آپ جانتے ہیں کہ کب رکنا ہے۔ یہ ان چیزوں کے لیے بہترین ہے جیسے صارف سے ان پٹ مانگنا جب تک کہ وہ آپ کو مطلوبہ چیز نہ دے، یا ڈیٹا میں تلاش کرنا جب تک کہ آپ کو مطلوبہ چیز نہ مل جائے۔

**While Loop کی خصوصیات:**
- **جاری رکھتا ہے** جب تک کہ شرط سچ ہو
- **ضرورت ہوتی ہے** کسی بھی counter متغیر کا دستی انتظام
- **چیک کرتا ہے** شرط ہر iteration سے پہلے
- **خطرہ ہوتا ہے** لامتناہی loops کا اگر شرط کبھی جھوٹ نہ ہو

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

**ان مثالوں کو سمجھنا:**
- **منظم کرتا ہے** counter متغیر `i` کو دستی طور پر loop body کے اندر
- **اضافہ کرتا ہے** counter کو لامتناہی loops کو روکنے کے لیے
- **عملی استعمال کا مظاہرہ کرتا ہے** صارف ان پٹ اور کوششوں کی حد بندی کے ساتھ
- **شامل کرتا ہے** حفاظتی میکانزم لامتناہی عمل کو روکنے کے لیے

### جدید Loop متبادل

جاوا اسکرپٹ جدید loop syntax فراہم کرتا ہے جو آپ کے کوڈ کو زیادہ پڑھنے کے قابل اور کم غلطی کا شکار بنا سکتا ہے۔

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

**For...of کے اہم فوائد:**
- **ختم کرتا ہے** index کے انتظام اور ممکنہ off-by-one غلطیوں کو
- **فراہم کرتا ہے** array عناصر تک براہ راست رسائی
- **بہتر بناتا ہے** کوڈ readability اور syntax complexity کو کم کرتا ہے

**forEach طریقہ:**

```javascript
const prices = [9.99, 15.50, 22.75, 8.25];

// Using forEach for functional programming style
prices.forEach((price, index) => {
  console.log(`Item ${index + 1}: $${price.toFixed(2)}`);
});

// forEach with arrow functions for simple operations
prices.forEach(price => console.log(`Price: $${price}`));
```

**forEach کے بارے میں جاننے کے لیے:**
- **عمل کرتا ہے** ایک فنکشن ہر array عنصر کے لیے
- **فراہم کرتا ہے** عنصر کی قدر اور index دونوں کو پیرامیٹرز کے طور پر
- **روکا نہیں جا سکتا** جلدی (روایتی loops کے برعکس)
- **واپس کرتا ہے** undefined (نیا array نہیں بناتا)

✅ آپ for loop اور while loop میں سے کیوں انتخاب کریں گے؟ StackOverflow پر 17K ناظرین کے پاس یہی سوال تھا، اور کچھ آراء [آپ کے لیے دلچسپ ہو سکتی ہیں](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript)۔

## Loops اور Arrays

Arrays کے ساتھ loops کو جوڑنا طاقتور ڈیٹا پروسیسنگ صلاحیتیں پیدا کرتا ہے۔ یہ جوڑی بہت سے پروگرامنگ کاموں کے لیے بنیادی ہے، جیسے فہرستیں دکھانا یا شماریات کا حساب لگانا۔

**روایتی Array پروسیسنگ:**

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

**آئیے ہر طریقہ کو سمجھتے ہیں:**
- **استعمال کرتا ہے** array کی لمبائی کی خصوصیت loop کی حد کا تعین کرنے کے لیے
- **رسائی حاصل کرتا ہے** عناصر کو index کے ذریعے روایتی for loops میں
- **فراہم کرتا ہے** براہ راست عنصر تک رسائی for...of loops میں
- **پروسیس کرتا ہے** ہر array عنصر کو بالکل ایک بار

**عملی ڈیٹا پروسیسنگ مثال:**

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

**یہ کوڈ کیسے کام کرتا ہے:**
- **ابتدائیہ کرتا ہے** tracking متغیرات کو sum اور extremes کے لیے
- **پروسیس کرتا ہے** ہر grade کو ایک مؤثر loop کے ساتھ
- **جمع کرتا ہے** کل کو اوسط حساب کے لیے
- **ٹریک کرتا ہے** سب سے زیادہ اور سب سے کم اقدار iteration کے دوران
- **حساب کرتا ہے** حتمی شماریات loop مکمل ہونے کے بعد

✅ اپنے براؤزر کے کنسول میں اپنے بنائے ہوئے array پر loop کرنے کی مشق کریں۔

---

## GitHub Copilot Agent Challenge 🚀

Agent mode استعمال کریں درج ذیل چیلنج مکمل کرنے کے لیے:

**تفصیل:** ایک جامع ڈیٹا پروسیسنگ فنکشن بنائیں جو arrays اور loops کو جوڑ کر ایک dataset کا تجزیہ کرے اور معنی خیز insights پیدا کرے۔

**Prompt:** ایک فنکشن بنائیں جس کا نام `analyzeGrades` ہو جو ایک array لے جس میں طالب علموں کے grade objects ہوں (ہر ایک میں name اور score کی خصوصیات ہوں) اور ایک object واپس کرے جس میں شماریات شامل ہوں جیسے سب سے زیادہ score، سب سے کم score، اوسط score، پاس ہونے والے طلباء کی تعداد (score >= 70)، اور ایک array ان طالب علموں کے ناموں کا جو اوسط سے زیادہ score رکھتے ہوں۔ اپنے حل میں کم از کم دو مختلف loop اقسام استعمال کریں۔

Agent mode کے بارے میں مزید جانیں [یہاں](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)۔

## 🚀 چیلنج

جاوا اسکرپٹ کئی جدید array طریقے پیش کرتا ہے جو مخصوص کاموں کے لیے روایتی loops کی جگہ لے سکتے ہیں۔ [forEach](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)، [for-of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)، [map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map)، [filter](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)، اور [reduce](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) کو دریافت کریں۔

**آپ کا چیلنج:** طالب علموں کے grades کی مثال کو کم از کم تین مختلف array طریقوں کا استعمال کرتے ہوئے دوبارہ لکھیں۔ نوٹ کریں کہ جدید جاوا اسکرپٹ syntax کے ساتھ کوڈ کتنا صاف اور زیادہ پڑھنے کے قابل ہو جاتا ہے۔

## لیکچر کے بعد کا کوئز
[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/14)

## جائزہ اور خود مطالعہ

جاوا اسکرپٹ میں arrays کے ساتھ کئی طریقے منسلک ہیں، جو ڈیٹا کی ہیرا پھیری کے لیے انتہائی مفید ہیں۔ [ان طریقوں کے بارے میں پڑھیں](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array) اور ان میں سے کچھ کو آزمائیں (جیسے push، pop، slice اور splice) اپنے بنائے ہوئے array پر۔

## اسائنمنٹ

[Loop an Array](assignment.md)

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔