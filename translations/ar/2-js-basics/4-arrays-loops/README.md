<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9197f8af0fef9be6e81d4dbda23c7e7d",
  "translation_date": "2025-10-22T14:04:59+00:00",
  "source_file": "2-js-basics/4-arrays-loops/README.md",
  "language_code": "ar"
}
-->
# أساسيات JavaScript: المصفوفات والحلقات

![أساسيات JavaScript - المصفوفات](../../../../translated_images/webdev101-js-arrays.439d7528b8a294558d0e4302e448d193f8ad7495cc407539cc81f1afe904b470.ar.png)
> رسم توضيحي بواسطة [Tomomi Imura](https://twitter.com/girlie_mac)

## اختبار ما قبل المحاضرة
[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/13)

هل تساءلت يومًا كيف تحتفظ المواقع الإلكترونية بعناصر سلة التسوق أو تعرض قائمة أصدقائك؟ هنا تأتي أهمية المصفوفات والحلقات. المصفوفات تشبه الحاويات الرقمية التي تحتفظ بمعلومات متعددة، بينما تتيح لك الحلقات العمل مع كل تلك البيانات بكفاءة دون الحاجة إلى كتابة كود متكرر.

معًا، يشكل هذان المفهومان الأساس للتعامل مع المعلومات في برامجك. ستتعلم كيف تنتقل من كتابة كل خطوة يدويًا إلى إنشاء كود ذكي وفعال يمكنه معالجة مئات أو حتى آلاف العناصر بسرعة.

بنهاية هذه الدرس، ستفهم كيفية إنجاز مهام البيانات المعقدة باستخدام بضعة أسطر فقط من الكود. دعونا نستكشف هذه المفاهيم البرمجية الأساسية.

[![المصفوفات](https://img.youtube.com/vi/1U4qTyq02Xw/0.jpg)](https://youtube.com/watch?v=1U4qTyq02Xw "المصفوفات")

[![الحلقات](https://img.youtube.com/vi/Eeh7pxtTZ3k/0.jpg)](https://www.youtube.com/watch?v=Eeh7pxtTZ3k "الحلقات")

> 🎥 اضغط على الصور أعلاه لمشاهدة فيديوهات عن المصفوفات والحلقات.

> يمكنك أخذ هذا الدرس على [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-arrays/?WT.mc_id=academic-77807-sagibbon)!

## المصفوفات

فكر في المصفوفات كأنها خزانة ملفات رقمية - بدلاً من تخزين مستند واحد في كل درج، يمكنك تنظيم عناصر متعددة ذات صلة في حاوية واحدة منظمة. بلغة البرمجة، تتيح لك المصفوفات تخزين معلومات متعددة في حزمة واحدة منظمة.

سواء كنت تبني معرض صور، أو تدير قائمة مهام، أو تتابع أعلى الدرجات في لعبة، فإن المصفوفات توفر الأساس لتنظيم البيانات. دعونا نرى كيف تعمل.

✅ المصفوفات موجودة في كل مكان! هل يمكنك التفكير في مثال حقيقي على المصفوفة، مثل مصفوفة الألواح الشمسية؟

### إنشاء المصفوفات

إنشاء مصفوفة أمر بسيط للغاية - فقط استخدم الأقواس المربعة!

```javascript
// Empty array - like an empty shopping cart waiting for items
const myArray = [];
```

**ما الذي يحدث هنا؟**
لقد أنشأت للتو حاوية فارغة باستخدام تلك الأقواس المربعة `[]`. فكر فيها كأنها رف مكتبة فارغ - جاهز لحمل أي كتب تريد تنظيمها هناك.

يمكنك أيضًا ملء المصفوفة بقيم أولية من البداية:

```javascript
// Your ice cream shop's flavor menu
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// A user's profile info (mixing different types of data)
const userData = ["John", 25, true, "developer"];

// Test scores for your favorite class
const scores = [95, 87, 92, 78, 85];
```

**أشياء رائعة يجب ملاحظتها:**
- يمكنك تخزين نصوص، أرقام، أو حتى قيم صحيحة/خاطئة في نفس المصفوفة
- فقط افصل كل عنصر بفاصلة - الأمر بسيط!
- المصفوفات مثالية للحفاظ على المعلومات ذات الصلة معًا

### فهرسة المصفوفات

هناك شيء قد يبدو غير مألوف في البداية: المصفوفات ترقم عناصرها بدءًا من 0، وليس 1. هذا الفهرس الذي يبدأ من الصفر له جذوره في كيفية عمل ذاكرة الكمبيوتر - وهو تقليد برمجي منذ الأيام الأولى للغات البرمجة مثل C. كل موقع في المصفوفة يحصل على رقم عنوان خاص به يسمى **الفهرس**.

| الفهرس | القيمة | الوصف |
|-------|-------|-------------|
| 0 | "Chocolate" | العنصر الأول |
| 1 | "Strawberry" | العنصر الثاني |
| 2 | "Vanilla" | العنصر الثالث |
| 3 | "Pistachio" | العنصر الرابع |
| 4 | "Rocky Road" | العنصر الخامس |

✅ هل يفاجئك أن المصفوفات تبدأ بالفهرس صفر؟ في بعض لغات البرمجة، تبدأ الفهارس من 1. هناك تاريخ مثير للاهتمام حول هذا الموضوع، يمكنك [قراءته على ويكيبيديا](https://en.wikipedia.org/wiki/Zero-based_numbering).

**الوصول إلى عناصر المصفوفة:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

// Access individual elements using bracket notation
console.log(iceCreamFlavors[0]); // "Chocolate" - first element
console.log(iceCreamFlavors[2]); // "Vanilla" - third element
console.log(iceCreamFlavors[4]); // "Rocky Road" - last element
```

**تفصيل ما يحدث هنا:**
- **يستخدم** تدوين الأقواس المربعة مع رقم الفهرس للوصول إلى العناصر
- **يعيد** القيمة المخزنة في ذلك الموقع المحدد في المصفوفة
- **يبدأ** العد من 0، مما يجعل العنصر الأول فهرسه 0

**تعديل عناصر المصفوفة:**

```javascript
// Change an existing value
iceCreamFlavors[4] = "Butter Pecan";
console.log(iceCreamFlavors[4]); // "Butter Pecan"

// Add a new element at the end
iceCreamFlavors[5] = "Cookie Dough";
console.log(iceCreamFlavors[5]); // "Cookie Dough"
```

**في المثال أعلاه، قمنا بـ:**
- **تعديل** العنصر عند الفهرس 4 من "Rocky Road" إلى "Butter Pecan"
- **إضافة** عنصر جديد "Cookie Dough" عند الفهرس 5
- **توسيع** طول المصفوفة تلقائيًا عند الإضافة خارج الحدود الحالية

### طول المصفوفة والطرق الشائعة

تأتي المصفوفات مع خصائص وطرق مدمجة تجعل العمل مع البيانات أسهل بكثير.

**إيجاد طول المصفوفة:**

```javascript
const iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
console.log(iceCreamFlavors.length); // 5

// Length updates automatically as array changes
iceCreamFlavors.push("Mint Chip");
console.log(iceCreamFlavors.length); // 6
```

**نقاط رئيسية يجب تذكرها:**
- **يعيد** العدد الإجمالي للعناصر في المصفوفة
- **يتحدث** تلقائيًا عند إضافة أو إزالة العناصر
- **يوفر** عدًا ديناميكيًا مفيدًا للحلقات والتحقق

**طرق المصفوفة الأساسية:**

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

**فهم هذه الطرق:**
- **يضيف** عناصر باستخدام `push()` (النهاية) و `unshift()` (البداية)
- **يزيل** عناصر باستخدام `pop()` (النهاية) و `shift()` (البداية)
- **يحدد** مواقع العناصر باستخدام `indexOf()` ويتحقق من وجودها باستخدام `includes()`
- **يعيد** قيمًا مفيدة مثل العناصر المزالة أو مواقع الفهارس

✅ جرب بنفسك! استخدم وحدة التحكم في متصفحك لإنشاء وتعديل مصفوفة من صنعك.

## الحلقات

فكر في العقوبة الشهيرة في روايات تشارلز ديكنز حيث كان الطلاب يكتبون الجمل مرارًا وتكرارًا على لوح. تخيل لو كان بإمكانك ببساطة أن تطلب من شخص ما "اكتب هذه الجملة 100 مرة" ويتم ذلك تلقائيًا. هذا بالضبط ما تفعله الحلقات في الكود.

الحلقات تشبه وجود مساعد لا يكل يمكنه تكرار المهام دون خطأ. سواء كنت بحاجة إلى التحقق من كل عنصر في سلة التسوق أو عرض جميع الصور في ألبوم، فإن الحلقات تتعامل مع التكرار بكفاءة.

يوفر JavaScript عدة أنواع من الحلقات للاختيار من بينها. دعونا نفحص كل نوع ونفهم متى نستخدمه.

### حلقة For

حلقة `for` تشبه ضبط مؤقت - تعرف بالضبط عدد المرات التي تريد أن يحدث فيها شيء ما. إنها منظمة للغاية ويمكن التنبؤ بها، مما يجعلها مثالية عند العمل مع المصفوفات أو الحاجة إلى عد الأشياء.

**هيكل حلقة For:**

| المكون | الغرض | المثال |
|-----------|---------|----------|
| **التهيئة** | تحديد نقطة البداية | `let i = 0` |
| **الشرط** | متى تستمر | `i < 10` |
| **الزيادة** | كيفية التحديث | `i++` |

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

**خطوة بخطوة، إليك ما يحدث:**
- **يهيئ** متغير العداد `i` إلى 0 في البداية
- **يتحقق** من الشرط `i < 10` قبل كل تكرار
- **ينفذ** كتلة الكود عندما يكون الشرط صحيحًا
- **يزيد** `i` بمقدار 1 بعد كل تكرار باستخدام `i++`
- **يتوقف** عندما يصبح الشرط خاطئًا (عندما يصل `i` إلى 10)

✅ قم بتشغيل هذا الكود في وحدة التحكم في المتصفح. ماذا يحدث عندما تقوم بإجراء تغييرات صغيرة على العداد أو الشرط أو تعبير التكرار؟ هل يمكنك جعله يعمل بالعكس، مما ينشئ عد تنازلي؟

### حلقة While

حلقة `while` تشبه قول "استمر في فعل هذا حتى..." - قد لا تعرف بالضبط عدد المرات التي ستعمل فيها، لكنك تعرف متى تتوقف. إنها مثالية لأشياء مثل طلب إدخال المستخدم حتى يعطيك ما تحتاجه، أو البحث في البيانات حتى تجد ما تبحث عنه.

**خصائص حلقة While:**
- **تستمر** في التنفيذ طالما أن الشرط صحيح
- **تتطلب** إدارة يدوية لأي متغيرات عداد
- **تتحقق** من الشرط قبل كل تكرار
- **تخاطر** بحلقات لا نهائية إذا لم يصبح الشرط خاطئًا أبدًا

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

**فهم هذه الأمثلة:**
- **يدير** متغير العداد `i` يدويًا داخل جسم الحلقة
- **يزيد** العداد لمنع الحلقات اللانهائية
- **يوضح** حالة استخدام عملية مع إدخال المستخدم وتحديد المحاولات
- **يتضمن** آليات أمان لمنع التنفيذ اللامتناهي

### البدائل الحديثة للحلقات

يوفر JavaScript بناء جملة حديث للحلقات يمكن أن يجعل الكود الخاص بك أكثر قابلية للقراءة وأقل عرضة للأخطاء.

**حلقة For...of (ES6+):**

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

**المزايا الرئيسية لـ For...of:**
- **يلغي** إدارة الفهارس وأخطاء الفهرس
- **يوفر** وصولًا مباشرًا إلى عناصر المصفوفة
- **يحسن** قابلية قراءة الكود ويقلل من تعقيد بناء الجملة

**طريقة forEach:**

```javascript
const prices = [9.99, 15.50, 22.75, 8.25];

// Using forEach for functional programming style
prices.forEach((price, index) => {
  console.log(`Item ${index + 1}: $${price.toFixed(2)}`);
});

// forEach with arrow functions for simple operations
prices.forEach(price => console.log(`Price: $${price}`));
```

**ما تحتاج إلى معرفته عن forEach:**
- **ينفذ** وظيفة لكل عنصر في المصفوفة
- **يوفر** قيمة العنصر والفهرس كمعلمات
- **لا يمكن** إيقافه مبكرًا (على عكس الحلقات التقليدية)
- **يعيد** undefined (لا ينشئ مصفوفة جديدة)

✅ لماذا تختار حلقة for مقابل حلقة while؟ 17 ألف مشاهد كان لديهم نفس السؤال على StackOverflow، وبعض الآراء [قد تكون مثيرة للاهتمام بالنسبة لك](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript).

## الحلقات والمصفوفات

دمج المصفوفات مع الحلقات يخلق قدرات معالجة بيانات قوية. هذا الاقتران أساسي للعديد من المهام البرمجية، من عرض القوائم إلى حساب الإحصائيات.

**معالجة المصفوفات التقليدية:**

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

**دعونا نفهم كل نهج:**
- **يستخدم** خاصية طول المصفوفة لتحديد حدود الحلقة
- **يصل** إلى العناصر بواسطة الفهرس في الحلقات التقليدية
- **يوفر** وصولًا مباشرًا للعناصر في حلقات For...of
- **يعالج** كل عنصر في المصفوفة مرة واحدة بالضبط

**مثال عملي لمعالجة البيانات:**

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

**إليك كيفية عمل هذا الكود:**
- **يهيئ** متغيرات التتبع للمجموع والقيم القصوى
- **يعالج** كل درجة باستخدام حلقة واحدة فعالة
- **يجمع** الإجمالي لحساب المتوسط
- **يتتبع** أعلى وأدنى القيم أثناء التكرار
- **يحسب** الإحصائيات النهائية بعد اكتمال الحلقة

✅ جرب التكرار على مصفوفة من صنعك في وحدة التحكم في المتصفح.

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع الوكيل لإكمال التحدي التالي:

**الوصف:** قم ببناء وظيفة معالجة بيانات شاملة تجمع بين المصفوفات والحلقات لتحليل مجموعة بيانات وتوليد رؤى مفيدة.

**المهمة:** أنشئ وظيفة تسمى `analyzeGrades` تأخذ مصفوفة من كائنات درجات الطلاب (كل منها يحتوي على خصائص الاسم والدرجة) وتعيد كائنًا يحتوي على إحصائيات تشمل أعلى درجة، أدنى درجة، متوسط الدرجات، عدد الطلاب الذين اجتازوا (درجة >= 70)، ومصفوفة بأسماء الطلاب الذين حصلوا على درجات أعلى من المتوسط. استخدم نوعين مختلفين على الأقل من الحلقات في الحل.

تعرف على المزيد حول [وضع الوكيل](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) هنا.

## 🚀 التحدي

يقدم JavaScript عدة طرق حديثة للمصفوفات يمكن أن تحل محل الحلقات التقليدية لمهام محددة. استكشف [forEach](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)، [for-of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of)، [map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map)، [filter](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)، و [reduce](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce). 

**تحديك:** أعد صياغة مثال درجات الطلاب باستخدام ثلاث طرق مختلفة على الأقل للمصفوفات. لاحظ كيف يصبح الكود أكثر نظافة وقابلية للقراءة باستخدام بناء الجملة الحديث لـ JavaScript.

## اختبار ما بعد المحاضرة
[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/14)


## المراجعة والدراسة الذاتية

المصفوفات في JavaScript لديها العديد من الطرق المرتبطة بها، والتي تكون مفيدة للغاية لمعالجة البيانات. [اقرأ عن هذه الطرق](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array) وجرب بعضها (مثل push، pop، slice و splice) على مصفوفة من صنعك.

## الواجب

[تكرار مصفوفة](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسير خاطئ ينشأ عن استخدام هذه الترجمة.