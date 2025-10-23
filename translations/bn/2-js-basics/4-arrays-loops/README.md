<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9197f8af0fef9be6e81d4dbda23c7e7d",
  "translation_date": "2025-10-22T21:25:59+00:00",
  "source_file": "2-js-basics/4-arrays-loops/README.md",
  "language_code": "bn"
}
-->
# জাভাস্ক্রিপ্টের বুনিয়াদি: অ্যারে এবং লুপ

![জাভাস্ক্রিপ্ট বেসিকস - অ্যারে](../../../../translated_images/webdev101-js-arrays.439d7528b8a294558d0e4302e448d193f8ad7495cc407539cc81f1afe904b470.bn.png)
> স্কেচনোট করেছেন [Tomomi Imura](https://twitter.com/girlie_mac)

## লেকচারের আগে কুইজ
[লেকচারের আগে কুইজ](https://ff-quizzes.netlify.app/web/quiz/13)

কখনো ভেবেছেন কীভাবে ওয়েবসাইটগুলো শপিং কার্টের আইটেম বা আপনার বন্ধু তালিকা ট্র্যাক করে? এখানেই অ্যারে এবং লুপের ভূমিকা। অ্যারে হলো ডিজিটাল কন্টেইনার যা একাধিক তথ্য ধারণ করে, আর লুপ আপনাকে সেই ডেটা দক্ষতার সাথে কাজ করতে সাহায্য করে, বারবার কোড লেখার প্রয়োজন ছাড়াই।

এই দুটি ধারণা একসাথে আপনার প্রোগ্রামে তথ্য পরিচালনার ভিত্তি তৈরি করে। আপনি শিখবেন কীভাবে প্রতিটি ধাপ ম্যানুয়ালি লিখে কাজ করার পরিবর্তে স্মার্ট, দক্ষ কোড তৈরি করবেন যা শত শত বা হাজার হাজার আইটেম দ্রুত প্রক্রিয়া করতে পারে।

এই পাঠ শেষে, আপনি বুঝতে পারবেন কীভাবে জটিল ডেটা কাজ কয়েকটি কোড লাইনের মাধ্যমে সম্পন্ন করা যায়। চলুন এই গুরুত্বপূর্ণ প্রোগ্রামিং ধারণাগুলো অন্বেষণ করি।

[![অ্যারে](https://img.youtube.com/vi/1U4qTyq02Xw/0.jpg)](https://youtube.com/watch?v=1U4qTyq02Xw "অ্যারে")

[![লুপ](https://img.youtube.com/vi/Eeh7pxtTZ3k/0.jpg)](https://www.youtube.com/watch?v=Eeh7pxtTZ3k "লুপ")

> 🎥 উপরের ছবিগুলোতে ক্লিক করুন অ্যারে এবং লুপ সম্পর্কে ভিডিও দেখার জন্য।

> আপনি এই পাঠটি [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-arrays/?WT.mc_id=academic-77807-sagibbon) এ নিতে পারেন!

## অ্যারে

অ্যারে হলো একটি ডিজিটাল ফাইলিং ক্যাবিনেটের মতো - যেখানে এক ড্রয়ারে একটি ডকুমেন্ট সংরক্ষণ করার পরিবর্তে, আপনি একাধিক সম্পর্কিত আইটেম একটি কাঠামোবদ্ধ কন্টেইনারে সংগঠিত করতে পারেন। প্রোগ্রামিংয়ের ভাষায়, অ্যারে আপনাকে একাধিক তথ্য একসাথে সংরক্ষণ করতে দেয়।

আপনি একটি ফটো গ্যালারি তৈরি করছেন, একটি টু-ডু লিস্ট পরিচালনা করছেন, বা একটি গেমে উচ্চ স্কোর ট্র্যাক করছেন, অ্যারে ডেটা সংগঠনের ভিত্তি প্রদান করে। চলুন দেখি এটি কীভাবে কাজ করে।

✅ অ্যারে আমাদের চারপাশে সব জায়গায়! আপনি কি অ্যারের একটি বাস্তব উদাহরণ ভাবতে পারেন, যেমন একটি সোলার প্যানেল অ্যারে?

### অ্যারে তৈরি করা

অ্যারে তৈরি করা খুবই সহজ - শুধু স্কয়ার ব্র্যাকেট ব্যবহার করুন!

```javascript
// Empty array - like an empty shopping cart waiting for items
const myArray = [];
```

**এখানে কী ঘটছে?**
আপনি স্কয়ার ব্র্যাকেট `[]` ব্যবহার করে একটি খালি কন্টেইনার তৈরি করেছেন। এটি একটি খালি লাইব্রেরি শেলফের মতো - এটি প্রস্তুত যে কোনো বই সংগঠিত করার জন্য।

আপনি শুরু থেকেই আপনার অ্যারে প্রাথমিক মান দিয়ে পূরণ করতে পারেন:

```javascript
// Your ice cream shop's flavor menu
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// A user's profile info (mixing different types of data)
const userData = ["John", 25, true, "developer"];

// Test scores for your favorite class
const scores = [95, 87, 92, 78, 85];
```

**মজার বিষয়গুলো লক্ষ্য করুন:**
- আপনি একই অ্যারেতে টেক্সট, সংখ্যা, এমনকি সত্য/মিথ্যা মান সংরক্ষণ করতে পারেন
- প্রতিটি আইটেমকে কমা দিয়ে আলাদা করুন - সহজ!
- সম্পর্কিত তথ্য একসাথে রাখার জন্য অ্যারে নিখুঁত

### অ্যারে ইনডেক্সিং

এখানে একটি বিষয় যা প্রথমে অদ্ভুত মনে হতে পারে: অ্যারে তাদের আইটেমগুলোকে ০ থেকে নম্বর দেয়, ১ থেকে নয়। এই জিরো-বেসড ইনডেক্সিং কম্পিউটার মেমোরি কীভাবে কাজ করে তার সাথে সম্পর্কিত - এটি প্রোগ্রামিংয়ের একটি প্রচলিত রীতি যা C-এর মতো কম্পিউটিং ভাষার প্রথম দিন থেকে চলে আসছে। অ্যারের প্রতিটি স্থানে একটি নিজস্ব ঠিকানা নম্বর থাকে, যাকে **ইনডেক্স** বলা হয়।

| ইনডেক্স | মান | বিবরণ |
|-------|-------|-------------|
| ০ | "চকলেট" | প্রথম উপাদান |
| ১ | "স্ট্রবেরি" | দ্বিতীয় উপাদান |
| ২ | "ভ্যানিলা" | তৃতীয় উপাদান |
| ৩ | "পিস্তাচিও" | চতুর্থ উপাদান |
| ৪ | "রকি রোড" | পঞ্চম উপাদান |

✅ অ্যারে ০ ইনডেক্স থেকে শুরু করে কি আপনাকে অবাক করেছে? কিছু প্রোগ্রামিং ভাষায় ইনডেক্স ১ থেকে শুরু হয়। এর একটি আকর্ষণীয় ইতিহাস রয়েছে, যা আপনি [উইকিপিডিয়ায় পড়তে পারেন](https://en.wikipedia.org/wiki/Zero-based_numbering)।

**অ্যারের উপাদান অ্যাক্সেস করা:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// Access individual elements using bracket notation
console.log(iceCreamFlavors[0]); // "Chocolate" - first element
console.log(iceCreamFlavors[2]); // "Vanilla" - third element
console.log(iceCreamFlavors[4]); // "Rocky Road" - last element
```

**এখানে কী ঘটছে তা ভেঙে দেখা যাক:**
- **ব্যবহার করে** স্কয়ার ব্র্যাকেট নোটেশন ইনডেক্স নম্বর দিয়ে উপাদান অ্যাক্সেস করতে
- **ফিরিয়ে দেয়** নির্দিষ্ট অবস্থানে সংরক্ষিত মান
- **শুরু করে** ০ থেকে গণনা, প্রথম উপাদান ইনডেক্স ০

**অ্যারের উপাদান পরিবর্তন করা:**

```javascript
// Change an existing value
iceCreamFlavors[4] = "Butter Pecan";
console.log(iceCreamFlavors[4]); // "Butter Pecan"

// Add a new element at the end
iceCreamFlavors[5] = "Cookie Dough";
console.log(iceCreamFlavors[5]); // "Cookie Dough"
```

**উপরের উদাহরণে আমরা:**
- **পরিবর্তন করেছি** ইনডেক্স ৪ এর উপাদান "রকি রোড" থেকে "বাটার পেকান"
- **যোগ করেছি** নতুন উপাদান "কুকি ডো" ইনডেক্স ৫ এ
- **স্বয়ংক্রিয়ভাবে** অ্যারের দৈর্ঘ্য বাড়িয়েছি বর্তমান সীমার বাইরে যোগ করার সময়

### অ্যারের দৈর্ঘ্য এবং সাধারণ মেথড

অ্যারে এমন বিল্ট-ইন প্রপার্টি এবং মেথড নিয়ে আসে যা ডেটা নিয়ে কাজ করা অনেক সহজ করে তোলে।

**অ্যারের দৈর্ঘ্য খুঁজে বের করা:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
console.log(iceCreamFlavors.length); // 5

// Length updates automatically as array changes
iceCreamFlavors.push("Mint Chip");
console.log(iceCreamFlavors.length); // 6
```

**মনে রাখার গুরুত্বপূর্ণ বিষয়:**
- **ফিরিয়ে দেয়** অ্যারের মোট উপাদানের সংখ্যা
- **স্বয়ংক্রিয়ভাবে আপডেট হয়** যখন উপাদান যোগ বা সরানো হয়
- **প্রদান করে** একটি গতিশীল গণনা যা লুপ এবং যাচাইয়ের জন্য দরকারী

**অ্যারের গুরুত্বপূর্ণ মেথড:**

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

**এই মেথডগুলো বোঝা:**
- **যোগ করে** `push()` (শেষে) এবং `unshift()` (শুরুতে) দিয়ে উপাদান
- **সরায়** `pop()` (শেষে) এবং `shift()` (শুরুতে) দিয়ে উপাদান
- **সনাক্ত করে** `indexOf()` দিয়ে উপাদানের অবস্থান এবং `includes()` দিয়ে উপস্থিতি পরীক্ষা করে
- **ফিরিয়ে দেয়** দরকারী মান যেমন সরানো উপাদান বা অবস্থান ইনডেক্স

✅ নিজে চেষ্টা করুন! আপনার ব্রাউজারের কনসোলে একটি অ্যারে তৈরি করুন এবং এটি ম্যানিপুলেট করুন।

## লুপ

চার্লস ডিকেন্সের উপন্যাসে বিখ্যাত শাস্তি মনে করুন যেখানে ছাত্রদের বারবার স্লেটে লাইন লিখতে হতো। কল্পনা করুন আপনি যদি কাউকে "এই বাক্যটি ১০০ বার লিখুন" বলে স্বয়ংক্রিয়ভাবে কাজটি সম্পন্ন করতে পারেন। লুপ ঠিক এটাই করে।

লুপ হলো এমন একটি অক্লান্ত সহকারী যা কাজগুলো বারবার ভুল ছাড়াই সম্পন্ন করতে পারে। আপনি যদি শপিং কার্টের প্রতিটি আইটেম পরীক্ষা করতে চান বা একটি অ্যালবামের সব ছবি প্রদর্শন করতে চান, লুপ দক্ষতার সাথে পুনরাবৃত্তি পরিচালনা করে।

জাভাস্ক্রিপ্টে বিভিন্ন ধরনের লুপ রয়েছে। চলুন প্রতিটি লুপ পরীক্ষা করি এবং কখন এগুলো ব্যবহার করতে হয় তা বুঝি।

### ফর লুপ

`for` লুপ হলো একটি টাইমার সেট করার মতো - আপনি জানেন ঠিক কতবার কিছু ঘটতে হবে। এটি খুবই সংগঠিত এবং পূর্বাভাসযোগ্য, যা এটিকে অ্যারে নিয়ে কাজ করার সময় বা কিছু গণনা করার জন্য নিখুঁত করে তোলে।

**ফর লুপের কাঠামো:**

| উপাদান | উদ্দেশ্য | উদাহরণ |
|-----------|---------|----------|
| **ইনিশিয়ালাইজেশন** | শুরু বিন্দু সেট করে | `let i = 0` |
| **শর্ত** | কখন চালিয়ে যেতে হবে | `i < 10` |
| **ইনক্রিমেন্ট** | কীভাবে আপডেট করতে হবে | `i++` |

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

**ধাপে ধাপে এখানে কী ঘটছে:**
- **ইনিশিয়ালাইজ করে** কাউন্টার ভেরিয়েবল `i` কে ০ দিয়ে শুরুতে
- **পরীক্ষা করে** শর্ত `i < 10` প্রতিটি পুনরাবৃত্তির আগে
- **কোড ব্লক সম্পাদন করে** যখন শর্ত সত্য হয়
- **ইনক্রিমেন্ট করে** `i` কে ১ করে প্রতিটি পুনরাবৃত্তির পরে `i++` দিয়ে
- **থামে** যখন শর্ত মিথ্যা হয়ে যায় (যখন `i` ১০ এ পৌঁছায়)

✅ এই কোডটি ব্রাউজারের কনসোলে চালান। যখন আপনি কাউন্টার, শর্ত বা পুনরাবৃত্তি এক্সপ্রেশন পরিবর্তন করেন তখন কী ঘটে? আপনি কি এটি উল্টোভাবে চালাতে পারেন, একটি কাউন্টডাউন তৈরি করতে?

### হোয়াইল লুপ

`while` লুপ হলো "এটি চালিয়ে যান যতক্ষণ না..." বলার মতো - আপনি ঠিক জানেন না এটি কতবার চলবে, তবে আপনি জানেন কখন থামতে হবে। এটি এমন কাজের জন্য নিখুঁত, যেমন ব্যবহারকারীর কাছ থেকে ইনপুট চাওয়া যতক্ষণ না তারা আপনার প্রয়োজনীয় তথ্য দেয়, বা ডেটা অনুসন্ধান করা যতক্ষণ না আপনি যা খুঁজছেন তা খুঁজে পান।

**হোয়াইল লুপের বৈশিষ্ট্য:**
- **চালিয়ে যায়** যতক্ষণ শর্ত সত্য থাকে
- **প্রয়োজন হয়** যে কোনো কাউন্টার ভেরিয়েবল ম্যানুয়ালি পরিচালনা করার
- **পরীক্ষা করে** প্রতিটি পুনরাবৃত্তির আগে শর্ত
- **ঝুঁকি থাকে** অনন্ত লুপের যদি শর্ত কখনো মিথ্যা না হয়

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

**এই উদাহরণগুলো বোঝা:**
- **ম্যানেজ করে** কাউন্টার ভেরিয়েবল `i` ম্যানুয়ালি লুপ বডির ভিতরে
- **ইনক্রিমেন্ট করে** কাউন্টার অনন্ত লুপ প্রতিরোধ করতে
- **প্রদর্শন করে** ব্যবহারকারীর ইনপুট এবং প্রচেষ্টা সীমাবদ্ধ করার ব্যবহারিক ব্যবহার
- **অন্তর্ভুক্ত করে** নিরাপত্তা ব্যবস্থা অনন্ত কার্যকরতা প্রতিরোধ করতে

### আধুনিক লুপের বিকল্প

জাভাস্ক্রিপ্ট আধুনিক লুপ সিনট্যাক্স প্রদান করে যা আপনার কোডকে আরও পাঠযোগ্য এবং কম ত্রুটিপূর্ণ করে তুলতে পারে।

**For...of লুপ (ES6+):**

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

**For...of এর প্রধান সুবিধা:**
- **ইনডেক্স ম্যানেজমেন্ট এবং সম্ভাব্য ভুল এড়ায়**
- **সরাসরি অ্যারে উপাদান অ্যাক্সেস প্রদান করে**
- **কোডের পাঠযোগ্যতা উন্নত করে এবং সিনট্যাক্স জটিলতা কমায়**

**forEach মেথড:**

```javascript
const prices = [9.99, 15.50, 22.75, 8.25];

// Using forEach for functional programming style
prices.forEach((price, index) => {
  console.log(`Item ${index + 1}: $${price.toFixed(2)}`);
});

// forEach with arrow functions for simple operations
prices.forEach(price => console.log(`Price: $${price}`));
```

**forEach সম্পর্কে যা জানা দরকার:**
- **প্রতিটি অ্যারে উপাদানের জন্য একটি ফাংশন সম্পাদন করে**
- **উপাদানের মান এবং ইনডেক্স উভয়ই প্যারামিটার হিসেবে প্রদান করে**
- **প্রথম দিকে থামানো যায় না** (প্রথাগত লুপের মতো নয়)
- **undefined ফেরত দেয়** (নতুন অ্যারে তৈরি করে না)

✅ আপনি কেন একটি ফর লুপের পরিবর্তে একটি হোয়াইল লুপ বেছে নেবেন? StackOverflow-এ ১৭ হাজার দর্শকের একই প্রশ্ন ছিল, এবং কিছু মতামত [আপনার জন্য আকর্ষণীয় হতে পারে](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript)।

## লুপ এবং অ্যারে

অ্যারে এবং লুপ একত্রিত করে শক্তিশালী ডেটা প্রক্রিয়াকরণ ক্ষমতা তৈরি করে। এই জুটি অনেক প্রোগ্রামিং কাজের জন্য মৌলিক, যেমন তালিকা প্রদর্শন করা বা পরিসংখ্যান গণনা করা।

**প্রথাগত অ্যারে প্রক্রিয়াকরণ:**

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

**প্রতিটি পদ্ধতি বুঝি:**
- **ব্যবহার করে** অ্যারের দৈর্ঘ্য প্রপার্টি লুপের সীমা নির্ধারণ করতে
- **অ্যাক্সেস করে** ইনডেক্স দ্বারা উপাদান প্রথাগত ফর লুপে
- **সরাসরি উপাদান অ্যাক্সেস প্রদান করে** For...of লুপে
- **প্রতিটি অ্যারে উপাদান একবার করে প্রক্রিয়া করে**

**প্রায়োগিক ডেটা প্রক্রিয়াকরণ উদাহরণ:**

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

**এই কোড কীভাবে কাজ করে:**
- **ট্র্যাকিং ভেরিয়েবল ইনিশিয়ালাইজ করে** যোগফল এবং চরম মানের জন্য
- **প্রতিটি গ্রেড প্রক্রিয়া করে** একটি একক দক্ষ লুপে
- **মোট যোগফল জমা করে** গড় গণনার জন্য
- **সর্বোচ্চ এবং সর্বনিম্ন মান ট্র্যাক করে** পুনরাবৃত্তির সময়
- **চূড়ান্ত পরিসংখ্যান গণনা করে** লুপ সম্পন্ন হওয়ার পরে

✅ আপনার ব্রাউজারের কনসোলে আপনার নিজের তৈরি একটি অ্যারের উপর লুপিং পরীক্ষা করুন।

---

## GitHub Copilot Agent Challenge 🚀

Agent মোড ব্যবহার করে নিম্নলিখিত চ্যালেঞ্জটি সম্পূর্ণ করুন:

**বর্ণনা:** একটি বিস্তৃত ডেটা প্রক্রিয়াকরণ ফাংশন তৈরি করুন যা অ্যারে এবং লুপ একত্রিত করে একটি ডেটাসেট বিশ্লেষণ করে এবং অর্থপূর্ণ অন্তর্দৃষ্টি তৈরি করে।

**প্রম্পট:** `analyzeGrades` নামে একটি ফাংশন তৈরি করুন যা ছাত্রদের গ্রেড অবজেক্টের একটি অ্যারে (প্রত্যেকটিতে নাম এবং স্কোর প্রপার্টি থাকবে) গ্রহণ করে এবং একটি অবজেক্ট ফেরত দেয় যার মধ্যে পরিসংখ্যান থাকবে যেমন সর্বোচ্চ স্কোর, সর্বনিম্ন স্কোর, গড় স্কোর, পাস করা ছাত্রদের সংখ্যা (স্কোর >= ৭০), এবং গড়ের উপরে স্কোর করা ছাত্রদের নামের একটি অ্যারে। আপনার সমাধানে অন্তত দুটি ভিন্ন লুপ টাইপ ব্যবহার করুন।

Agent মোড সম্পর্কে আরও জানুন [এখানে](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)।

## 🚀 চ্যালেঞ্জ

জাভাস্ক্রিপ্টে কয়েকটি আধুনিক অ্যারে মেথড রয়েছে যা নির্দিষ্ট কাজের জন্য প্রথাগত লুপের পরিবর্তে ব্যবহার করা যেতে পারে। [forEach](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach), [for-of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of), [map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map), [filter](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter), এবং [reduce](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce) সম্পর্কে জানুন। 

**আপনার চ্যালেঞ্জ:** ছাত্রদের গ্রেড উদাহরণটি পুনরায় লিখুন, যেখানে অন্তত তিনটি ভিন্ন অ্যারে মেথড ব্যবহার করা হয়েছে। লক্ষ্য করুন কীভাবে আধুনিক জাভাস্ক্রিপ্ট সিনট্যাক্স দিয়ে কোডটি আরও পরিষ্কার এবং পাঠযোগ্য হয়ে ওঠে।

## লেকচারের পরে কুইজ
[লেকচারের পরে কুইজ](https://ff-quizzes.netlify.app/web/quiz/14)


## পুনরালোচনা ও স্ব-অধ্যয়ন

জাভাস্ক্রিপ্টে অ্যারে অনেক মেথড সংযুক্ত থাকে, যা ডেটা ম্যানিপুলেশনের জন্য অত্যন্ত কার্যকর। [এই মেথডগুলো সম্পর্কে পড়ুন](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array) এবং আপনার তৈরি করা একটি অ্যারেতে কিছু মেথড (যেমন push, pop, slice এবং splice) ব্যবহার করে দেখুন।

## অ্যাসাইনমেন্ট

[অ্যারে লুপ করুন](assignment.md)

---

**অস্বীকৃতি**:  
এই নথিটি AI অনুবাদ পরিষেবা [Co-op Translator](https://github.com/Azure/co-op-translator) ব্যবহার করে অনুবাদ করা হয়েছে। আমরা যথাসম্ভব সঠিকতার জন্য চেষ্টা করি, তবে অনুগ্রহ করে মনে রাখবেন যে স্বয়ংক্রিয় অনুবাদে ত্রুটি বা অসঙ্গতি থাকতে পারে। মূল ভাষায় থাকা নথিটিকে প্রামাণিক উৎস হিসেবে বিবেচনা করা উচিত। গুরুত্বপূর্ণ তথ্যের জন্য, পেশাদার মানব অনুবাদ সুপারিশ করা হয়। এই অনুবাদ ব্যবহারের ফলে কোনো ভুল বোঝাবুঝি বা ভুল ব্যাখ্যার জন্য আমরা দায়ী থাকব না।