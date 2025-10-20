<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "beea52254102e11a70f4a3e7f66af5e3",
  "translation_date": "2025-10-20T20:30:16+00:00",
  "source_file": "2-js-basics/3-making-decisions/README.md",
  "language_code": "ar"
}
-->
# أساسيات JavaScript: اتخاذ القرارات

![أساسيات JavaScript - اتخاذ القرارات](../../../../translated_images/webdev101-js-decisions.69e1b20f272dd1f0b1cb2f8adaff3ed2a77c4f91db96d8a0594132a353fa189a.ar.png)

> رسم توضيحي بواسطة [Tomomi Imura](https://twitter.com/girlie_mac)

## اختبار ما قبل المحاضرة

[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/11)

اتخاذ القرارات والتحكم في ترتيب تشغيل الكود يجعل الكود قابلًا لإعادة الاستخدام وقويًا. يغطي هذا القسم صياغة التحكم في تدفق البيانات في JavaScript وأهميتها عند استخدامها مع أنواع البيانات المنطقية (Boolean).

[![اتخاذ القرارات](https://img.youtube.com/vi/SxTp8j-fMMY/0.jpg)](https://youtube.com/watch?v=SxTp8j-fMMY "اتخاذ القرارات")

> 🎥 انقر على الصورة أعلاه لمشاهدة فيديو حول اتخاذ القرارات.

> يمكنك أخذ هذه الدرس على [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-if-else/?WT.mc_id=academic-77807-sagibbon)!

## ملخص سريع عن Booleans

يمكن أن تحتوي Booleans على قيمتين فقط: `true` أو `false`. تساعد Booleans في اتخاذ القرارات حول أي سطور من الكود يجب تشغيلها عند استيفاء شروط معينة.

قم بتعيين Boolean ليكون true أو false بهذه الطريقة:

`let myTrueBool = true`  
`let myFalseBool = false`

✅ تم تسمية Booleans على اسم عالم الرياضيات والفيلسوف والمنطقي الإنجليزي جورج بول (1815–1864).

## عوامل المقارنة و Booleans

تُستخدم العوامل لتقييم الشروط من خلال إجراء مقارنات تؤدي إلى إنشاء قيمة Boolean. فيما يلي قائمة بالعوامل التي تُستخدم بشكل متكرر.

| الرمز | الوصف                                                                                                                                                   | المثال             |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------ |
| `<`    | **أقل من**: يقارن بين قيمتين ويعيد نوع البيانات Boolean `true` إذا كانت القيمة على الجانب الأيسر أقل من الجانب الأيمن                              | `5 < 6 // true`    |
| `<=`   | **أقل من أو يساوي**: يقارن بين قيمتين ويعيد نوع البيانات Boolean `true` إذا كانت القيمة على الجانب الأيسر أقل من أو تساوي الجانب الأيمن      | `5 <= 6 // true`   |
| `>`    | **أكبر من**: يقارن بين قيمتين ويعيد نوع البيانات Boolean `true` إذا كانت القيمة على الجانب الأيسر أكبر من الجانب الأيمن                         | `5 > 6 // false`   |
| `>=`   | **أكبر من أو يساوي**: يقارن بين قيمتين ويعيد نوع البيانات Boolean `true` إذا كانت القيمة على الجانب الأيسر أكبر من أو تساوي الجانب الأيمن | `5 >= 6 // false`  |
| `===`  | **المساواة الصارمة**: يقارن بين قيمتين ويعيد نوع البيانات Boolean `true` إذا كانت القيم على اليمين واليسار متساوية وتكون من نفس نوع البيانات.       | `5 === 6 // false` |
| `!==`  | **عدم المساواة**: يقارن بين قيمتين ويعيد القيمة Boolean المعاكسة لما سيعيده عامل المساواة الصارمة                                    | `5 !== 6 // true`  |

✅ تحقق من معرفتك بكتابة بعض المقارنات في وحدة التحكم في المتصفح. هل تفاجأت بأي بيانات تم إرجاعها؟

## جملة If

ستقوم جملة if بتشغيل الكود بين الكتل إذا كان الشرط صحيحًا.

```javascript
if (condition) {
  //Condition is true. Code in this block will run.
}
```
  
غالبًا ما تُستخدم العوامل المنطقية لتشكيل الشرط.

```javascript
let currentMoney;
let laptopPrice;

if (currentMoney >= laptopPrice) {
  //Condition is true. Code in this block will run.
  console.log("Getting a new laptop!");
}
```
  
## جملة If..Else

ستقوم جملة `else` بتشغيل الكود بين الكتل عندما يكون الشرط خاطئًا. وهي اختيارية مع جملة `if`.

```javascript
let currentMoney;
let laptopPrice;

if (currentMoney >= laptopPrice) {
  //Condition is true. Code in this block will run.
  console.log("Getting a new laptop!");
} else {
  //Condition is false. Code in this block will run.
  console.log("Can't afford a new laptop, yet!");
}
```
  
✅ اختبر فهمك لهذا الكود والكود التالي عن طريق تشغيله في وحدة التحكم في المتصفح. قم بتغيير قيم المتغيرات currentMoney و laptopPrice لتغيير النتيجة المعادة من `console.log()`.

## جملة Switch

تُستخدم جملة `switch` لتنفيذ إجراءات مختلفة بناءً على شروط مختلفة. استخدم جملة `switch` لاختيار واحدة من بين العديد من كتل الكود ليتم تنفيذها.

```javascript
switch (expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
  // code block
}
```
  
```javascript
// program using switch statement
let a = 2;

switch (a) {
  case 1:
    a = "one";
    break;
  case 2:
    a = "two";
    break;
  default:
    a = "not found";
    break;
}
console.log(`The value is ${a}`);
```
  
✅ اختبر فهمك لهذا الكود والكود التالي عن طريق تشغيله في وحدة التحكم في المتصفح. قم بتغيير قيم المتغير a لتغيير النتيجة المعادة من `console.log()`.

## العوامل المنطقية و Booleans

قد تتطلب القرارات أكثر من مقارنة واحدة، ويمكن ربطها معًا باستخدام العوامل المنطقية لإنتاج قيمة Boolean.

| الرمز | الوصف                                                                                     | المثال                                                                 |
| ------ | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `&&`   | **AND المنطقي**: يقارن بين تعبيرين منطقيين. يعيد true **فقط** إذا كان كلا الجانبين صحيحًا | `(5 > 6) && (5 < 6 ) // أحد الجانبين خاطئ، والآخر صحيح. يعيد false` |
| `\|\|` | **OR المنطقي**: يقارن بين تعبيرين منطقيين. يعيد true إذا كان على الأقل أحد الجانبين صحيحًا     | `(5 > 6) \|\| (5 < 6) // أحد الجانبين خاطئ، والآخر صحيح. يعيد true` |
| `!`    | **NOT المنطقي**: يعيد القيمة المعاكسة لتعبير منطقي                             | `!(5 > 6) // 5 ليس أكبر من 6، ولكن "!" سيعيد true`         |

## الشروط والقرارات باستخدام العوامل المنطقية

يمكن استخدام العوامل المنطقية لتشكيل شروط في جمل if..else.

```javascript
let currentMoney;
let laptopPrice;
let laptopDiscountPrice = laptopPrice - laptopPrice * 0.2; //Laptop price at 20 percent off

if (currentMoney >= laptopPrice || currentMoney >= laptopDiscountPrice) {
  //Condition is true. Code in this block will run.
  console.log("Getting a new laptop!");
} else {
  //Condition is true. Code in this block will run.
  console.log("Can't afford a new laptop, yet!");
}
```
  
### عامل النفي

لقد رأيت حتى الآن كيف يمكنك استخدام جملة `if...else` لإنشاء منطق شرطي. أي شيء يدخل في جملة `if` يجب أن يتم تقييمه إلى true/false. باستخدام العامل `!` يمكنك _نفي_ التعبير. سيبدو الأمر كما يلي:

```javascript
if (!condition) {
  // runs if condition is false
} else {
  // runs if condition is true
}
```
  
### التعبيرات الثلاثية

جملة `if...else` ليست الطريقة الوحيدة للتعبير عن منطق القرار. يمكنك أيضًا استخدام شيء يسمى العامل الثلاثي. يبدو شكله كما يلي:

```javascript
let variable = condition ? <return this if true> : <return this if false>
```
  
فيما يلي مثال أكثر وضوحًا:

```javascript
let firstNumber = 20;
let secondNumber = 10;
let biggestNumber = firstNumber > secondNumber ? firstNumber : secondNumber;
```
  
✅ خذ دقيقة لقراءة هذا الكود عدة مرات. هل تفهم كيف تعمل هذه العوامل؟

ما سبق ينص على:

- إذا كان `firstNumber` أكبر من `secondNumber`
- قم بتعيين `firstNumber` إلى `biggestNumber`
- وإلا قم بتعيين `secondNumber`.

التعبير الثلاثي هو مجرد طريقة مختصرة لكتابة الكود أدناه:

```javascript
let biggestNumber;
if (firstNumber > secondNumber) {
  biggestNumber = firstNumber;
} else {
  biggestNumber = secondNumber;
}
```
  
---

## 🚀 تحدي

قم بإنشاء برنامج مكتوب أولاً باستخدام العوامل المنطقية، ثم أعد كتابته باستخدام تعبير ثلاثي. ما هي الصياغة المفضلة لديك؟

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع Agent لإكمال التحدي التالي:

**الوصف:** قم بإنشاء آلة حاسبة شاملة للدرجات تعرض مفاهيم اتخاذ القرارات المتعددة من هذا الدرس، بما في ذلك جمل if-else، وجمل switch، والعوامل المنطقية، والتعبيرات الثلاثية.

**المهمة:** اكتب برنامج JavaScript يأخذ درجة الطالب الرقمية (0-100) ويحدد درجته الحرفية باستخدام المعايير التالية:  
- A: 90-100  
- B: 80-89  
- C: 70-79  
- D: 60-69  
- F: أقل من 60  

المتطلبات:  
1. استخدم جملة if-else لتحديد الدرجة الحرفية  
2. استخدم العوامل المنطقية للتحقق مما إذا كان الطالب ناجحًا (الدرجة >= 60) وأيضًا لديه تفوق (الدرجة >= 90)  
3. استخدم جملة switch لتقديم ملاحظات محددة لكل درجة حرفية  
4. استخدم العامل الثلاثي لتحديد ما إذا كان الطالب مؤهلًا للدورة التالية (الدرجة >= 70)  
5. قم بتضمين التحقق من صحة الإدخال للتأكد من أن الدرجة بين 0 و 100  

اختبر برنامجك مع درجات مختلفة بما في ذلك الحالات الحدية مثل 59، 60، 89، 90، ومدخلات غير صالحة.

## اختبار ما بعد المحاضرة

[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/12)

## المراجعة والدراسة الذاتية

اقرأ المزيد عن العديد من العوامل المتاحة للمستخدم [على MDN](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Operators).

استعرض دليل [البحث عن العوامل](https://joshwcomeau.com/operator-lookup/) الرائع لجوش كومو!

## الواجب

[العوامل](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الموثوق. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.