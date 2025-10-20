<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "1699f24c0210b74fcb592f4414bfa706",
  "translation_date": "2025-10-20T20:40:14+00:00",
  "source_file": "6-space-game/5-keeping-score/README.md",
  "language_code": "ar"
}
-->
# بناء لعبة فضاء الجزء الخامس: النقاط والأرواح

## اختبار ما قبل المحاضرة

[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/37)

في هذه الدرس، ستتعلم كيفية إضافة النقاط إلى اللعبة وحساب الأرواح.

## رسم النص على الشاشة

لكي تتمكن من عرض نقاط اللعبة على الشاشة، تحتاج إلى معرفة كيفية وضع النص على الشاشة. الإجابة هي باستخدام طريقة `fillText()` على كائن الـ canvas. يمكنك أيضًا التحكم في جوانب أخرى مثل نوع الخط المستخدم، لون النص وحتى محاذاته (يسار، يمين، وسط). أدناه يوجد بعض الأكواد لرسم النص على الشاشة.

```javascript
ctx.font = "30px Arial";
ctx.fillStyle = "red";
ctx.textAlign = "right";
ctx.fillText("show this on the screen", 0, 0);
```

✅ اقرأ المزيد عن [كيفية إضافة النص إلى الـ canvas](https://developer.mozilla.org/docs/Web/API/Canvas_API/Tutorial/Drawing_text)، ولا تتردد في جعل النص يبدو أكثر أناقة!

## الحياة كمفهوم في اللعبة

مفهوم وجود حياة في اللعبة هو مجرد رقم. في سياق لعبة الفضاء، من الشائع تخصيص مجموعة من الأرواح التي يتم خصمها واحدة تلو الأخرى عندما تتعرض سفينتك للضرر. من الجميل إذا كان بإمكانك عرض تمثيل رسومي لهذا مثل السفن الصغيرة أو القلوب بدلاً من رقم.

## ما الذي يجب بناؤه

لنقم بإضافة التالي إلى لعبتك:

- **نقاط اللعبة**: لكل سفينة عدو يتم تدميرها، يجب أن يحصل البطل على بعض النقاط، نقترح 100 نقطة لكل سفينة. يجب عرض نقاط اللعبة في الزاوية السفلية اليسرى.
- **الأرواح**: سفينتك لديها ثلاث أرواح. تفقد روحًا كلما اصطدمت سفينة عدو بك. يجب عرض عدد الأرواح في الزاوية السفلية اليمنى ويكون مكونًا من الرسم التالي ![صورة الحياة](../../../../translated_images/life.6fb9f50d53ee0413cd91aa411f7c296e10a1a6de5c4a4197c718b49bf7d63ebf.ar.png).

## الخطوات الموصى بها

حدد الملفات التي تم إنشاؤها لك في المجلد الفرعي `your-work`. يجب أن يحتوي على التالي:

```bash
-| assets
  -| enemyShip.png
  -| player.png
  -| laserRed.png
-| index.html
-| app.js
-| package.json
```

ابدأ مشروعك في مجلد `your_work` عن طريق كتابة:

```bash
cd your-work
npm start
```

سيقوم الأمر أعلاه بتشغيل خادم HTTP على العنوان `http://localhost:5000`. افتح متصفحًا وأدخل هذا العنوان، في الوقت الحالي يجب أن تظهر السفينة الرئيسية وكل الأعداء، وعندما تضغط على الأسهم اليمنى واليسرى، تتحرك السفينة الرئيسية ويمكنها إسقاط الأعداء.

### إضافة الكود

1. **نسخ الأصول المطلوبة** من المجلد `solution/assets/` إلى مجلد `your-work`؛ ستضيف أصل `life.png`. أضف lifeImg إلى وظيفة window.onload:

    ```javascript
    lifeImg = await loadTexture("assets/life.png");
    ```

1. أضف `lifeImg` إلى قائمة الأصول:

    ```javascript
    let heroImg,
    ...
    lifeImg,
    ...
    eventEmitter = new EventEmitter();
    ```
  
2. **إضافة المتغيرات**. أضف الكود الذي يمثل إجمالي النقاط (0) والأرواح المتبقية (3)، واعرض هذه النقاط على الشاشة.

3. **توسيع وظيفة `updateGameObjects()`**. قم بتوسيع وظيفة `updateGameObjects()` لمعالجة اصطدامات الأعداء:

    ```javascript
    enemies.forEach(enemy => {
        const heroRect = hero.rectFromGameObject();
        if (intersectRect(heroRect, enemy.rectFromGameObject())) {
          eventEmitter.emit(Messages.COLLISION_ENEMY_HERO, { enemy });
        }
      })
    ```

4. **إضافة الأرواح والنقاط**. 
   1. **تهيئة المتغيرات**. تحت `this.cooldown = 0` في فئة `Hero`، قم بتعيين الأرواح والنقاط:

        ```javascript
        this.life = 3;
        this.points = 0;
        ```

   1. **رسم المتغيرات على الشاشة**. قم برسم هذه القيم على الشاشة:

        ```javascript
        function drawLife() {
          // TODO, 35, 27
          const START_POS = canvas.width - 180;
          for(let i=0; i < hero.life; i++ ) {
            ctx.drawImage(
              lifeImg, 
              START_POS + (45 * (i+1) ), 
              canvas.height - 37);
          }
        }
        
        function drawPoints() {
          ctx.font = "30px Arial";
          ctx.fillStyle = "red";
          ctx.textAlign = "left";
          drawText("Points: " + hero.points, 10, canvas.height-20);
        }
        
        function drawText(message, x, y) {
          ctx.fillText(message, x, y);
        }

        ```

   1. **إضافة طرق إلى حلقة اللعبة**. تأكد من إضافة هذه الوظائف إلى وظيفة window.onload تحت `updateGameObjects()`:

        ```javascript
        drawPoints();
        drawLife();
        ```

1. **تنفيذ قواعد اللعبة**. قم بتنفيذ قواعد اللعبة التالية:

   1. **لكل اصطدام بين البطل والعدو**، يتم خصم روح.
   
      قم بتوسيع فئة `Hero` لتنفيذ هذا الخصم:

        ```javascript
        decrementLife() {
          this.life--;
          if (this.life === 0) {
            this.dead = true;
          }
        }
        ```

   2. **لكل ليزر يصيب عدواً**، يتم زيادة نقاط اللعبة بمقدار 100 نقطة.

      قم بتوسيع فئة Hero لتنفيذ هذه الزيادة:
    
        ```javascript
          incrementPoints() {
            this.points += 100;
          }
        ```

        أضف هذه الوظائف إلى مرسلات أحداث الاصطدام:

        ```javascript
        eventEmitter.on(Messages.COLLISION_ENEMY_LASER, (_, { first, second }) => {
           first.dead = true;
           second.dead = true;
           hero.incrementPoints();
        })

        eventEmitter.on(Messages.COLLISION_ENEMY_HERO, (_, { enemy }) => {
           enemy.dead = true;
           hero.decrementLife();
        });
        ```

✅ قم ببعض البحث لاكتشاف ألعاب أخرى تم إنشاؤها باستخدام JavaScript/Canvas. ما هي السمات المشتركة بينها؟

بنهاية هذا العمل، يجب أن ترى السفن الصغيرة "الحياة" في الزاوية السفلية اليمنى، النقاط في الزاوية السفلية اليسرى، ويجب أن ترى عدد الأرواح ينخفض عند الاصطدام بالأعداء والنقاط تزداد عند إسقاط الأعداء. أحسنت! لعبتك أصبحت شبه مكتملة.

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع Agent لإكمال التحدي التالي:

**الوصف:** قم بتحسين نظام النقاط في لعبة الفضاء عن طريق تنفيذ ميزة أعلى النقاط مع تخزين دائم وآليات نقاط إضافية.

**المهمة:** قم بإنشاء نظام أعلى النقاط الذي يحفظ أفضل نقاط اللاعب في localStorage. أضف نقاطًا إضافية لقتل الأعداء بشكل متتالي (نظام الكومبو) وقم بتنفيذ قيم نقاط مختلفة لأنواع الأعداء المختلفة. قم بتضمين مؤشر بصري عندما يحقق اللاعب أعلى نقاط جديدة وعرض أعلى النقاط الحالية على شاشة اللعبة.

## 🚀 التحدي

كودك شبه مكتمل. هل يمكنك تصور الخطوات التالية؟

## اختبار ما بعد المحاضرة

[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/38)

## المراجعة والدراسة الذاتية

ابحث عن بعض الطرق التي يمكنك من خلالها زيادة وتقليل نقاط اللعبة والأرواح. هناك بعض محركات الألعاب المثيرة مثل [PlayFab](https://playfab.com). كيف يمكن أن يؤدي استخدام أحد هذه المحركات إلى تحسين لعبتك؟

## الواجب

[بناء لعبة النقاط](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسير خاطئ ينشأ عن استخدام هذه الترجمة.