<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "90b19cde5b79b29e91babd3138cd8035",
  "translation_date": "2025-10-22T14:09:35+00:00",
  "source_file": "1-getting-started-lessons/3-accessibility/README.md",
  "language_code": "ar"
}
-->
# إنشاء صفحات ويب ميسرة

![كل شيء عن إمكانية الوصول](../../../../translated_images/webdev101-a11y.8ef3025c858d897a403a1a42c0897c76e11b724d9a8a0c0578dd4316f7507622.ar.png)
> رسم توضيحي بواسطة [تومومي إيمورا](https://twitter.com/girlie_mac)

## اختبار ما قبل المحاضرة
[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/)

> قوة الويب تكمن في عالميته. الوصول للجميع بغض النظر عن الإعاقة هو جانب أساسي.
>
> \- السير تيموثي بيرنرز لي، مدير W3C ومخترع شبكة الويب العالمية

إليك شيئًا قد يفاجئك: عندما تقوم بإنشاء مواقع ويب ميسرة، فأنت لا تساعد فقط الأشخاص ذوي الإعاقة - بل تجعل الويب أفضل للجميع!

هل لاحظت تلك المنحدرات عند زوايا الشوارع؟ تم تصميمها في الأصل للكراسي المتحركة، لكنها الآن تساعد الأشخاص الذين يستخدمون عربات الأطفال، وعمال التوصيل الذين يستخدمون العربات، والمسافرين الذين يحملون حقائب بعجلات، وحتى راكبي الدراجات. هذا بالضبط ما تفعله تصميمات الويب الميسرة - الحلول التي تساعد مجموعة واحدة غالبًا ما تفيد الجميع. رائع، أليس كذلك؟

في هذه الدرس، سنستكشف كيفية إنشاء مواقع ويب تعمل حقًا للجميع، بغض النظر عن كيفية تصفحهم للويب. ستتعرف على تقنيات عملية مدمجة بالفعل في معايير الويب، وستجرب أدوات الاختبار بنفسك، وسترى كيف تجعل إمكانية الوصول مواقعك أكثر سهولة لجميع المستخدمين.

بحلول نهاية هذا الدرس، ستكون لديك الثقة لجعل إمكانية الوصول جزءًا طبيعيًا من سير عمل التطوير الخاص بك. مستعد لاستكشاف كيف يمكن للاختيارات التصميمية المدروسة أن تفتح الويب لمليارات المستخدمين؟ لنبدأ!

> يمكنك أخذ هذا الدرس على [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101/accessibility/?WT.mc_id=academic-77807-sagibbon)!

## فهم تقنيات المساعدة

قبل أن نبدأ في البرمجة، دعونا نأخذ لحظة لفهم كيف يتفاعل الأشخاص ذوو القدرات المختلفة مع الويب. هذا ليس مجرد نظرية - فهم أنماط التنقل الواقعية هذه سيجعلك مطورًا أفضل بكثير!

تقنيات المساعدة هي أدوات مذهلة تساعد الأشخاص ذوي الإعاقة على التفاعل مع مواقع الويب بطرق قد تفاجئك. بمجرد أن تفهم كيفية عمل هذه التقنيات، يصبح إنشاء تجارب ويب ميسرة أكثر سهولة. إنه مثل تعلم رؤية الكود الخاص بك من خلال عيون شخص آخر.

### قارئات الشاشة

[قارئات الشاشة](https://en.wikipedia.org/wiki/Screen_reader) هي تقنيات متقدمة تحول النص الرقمي إلى صوت أو إخراج بطريقة برايل. بينما تُستخدم بشكل أساسي من قبل الأشخاص ذوي الإعاقات البصرية، فهي مفيدة أيضًا للمستخدمين الذين يعانون من صعوبات التعلم مثل عسر القراءة.

أحب أن أفكر في قارئ الشاشة كأنه راوي ذكي يقرأ كتابًا لك. يقرأ المحتوى بصوت عالٍ بترتيب منطقي، ويعلن عن العناصر التفاعلية مثل "زر" أو "رابط"، ويوفر اختصارات لوحة المفاتيح للتنقل في الصفحة. ولكن هنا الأمر - يمكن لقارئات الشاشة أن تعمل بسحرها فقط إذا قمنا ببناء مواقع ويب ذات هيكل مناسب ومحتوى ذو معنى. وهنا يأتي دورك كمطور!

**أشهر قارئات الشاشة عبر المنصات:**
- **Windows**: [NVDA](https://www.nvaccess.org/about-nvda/) (مجاني والأكثر شعبية)، [JAWS](https://webaim.org/articles/jaws/)، [Narrator](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1/?WT.mc_id=academic-77807-sagibbon) (مضمن)
- **macOS/iOS**: [VoiceOver](https://support.apple.com/guide/voiceover/welcome/10) (مضمن وقوي جدًا)
- **Android**: [TalkBack](https://support.google.com/accessibility/android/answer/6283677) (مضمن)
- **Linux**: [Orca](https://wiki.gnome.org/Projects/Orca) (مجاني ومفتوح المصدر)

**كيف تتنقل قارئات الشاشة في محتوى الويب:**

توفر قارئات الشاشة طرقًا متعددة للتنقل تجعل التصفح فعالًا للمستخدمين ذوي الخبرة:
- **القراءة المتسلسلة**: قراءة المحتوى من الأعلى إلى الأسفل، مثل متابعة كتاب
- **التنقل عبر المعالم**: الانتقال بين أقسام الصفحة (الرأس، التنقل، الرئيسي، التذييل)
- **التنقل عبر العناوين**: الانتقال بين العناوين لفهم هيكل الصفحة
- **قوائم الروابط**: إنشاء قائمة بجميع الروابط للوصول السريع
- **عناصر التحكم في النماذج**: التنقل مباشرة بين حقول الإدخال والأزرار

> 💡 **إليك شيئًا أدهشني**: 68% من مستخدمي قارئات الشاشة يتنقلون بشكل أساسي عبر العناوين ([استطلاع WebAIM](https://webaim.org/projects/screenreadersurvey9/#finding)). هذا يعني أن هيكل العناوين الخاص بك يشبه خارطة طريق للمستخدمين - عندما تقوم بذلك بشكل صحيح، فإنك تساعد الناس حرفيًا في العثور على طريقهم حول المحتوى الخاص بك بشكل أسرع!

### بناء سير عمل الاختبار الخاص بك

إليك بعض الأخبار الجيدة - لا يجب أن يكون اختبار إمكانية الوصول فعالًا أمرًا مربكًا! ستحتاج إلى الجمع بين الأدوات الآلية (فهي رائعة في اكتشاف المشكلات الواضحة) وبعض الاختبارات اليدوية. إليك نهجًا منهجيًا وجدته يكتشف معظم المشكلات دون أن يستهلك يومك بالكامل:

**سير عمل الاختبار اليدوي الأساسي:**

```mermaid
graph TD
    A[Start Testing] --> B{Keyboard Navigation}
    B --> C[Tab through all interactive elements]
    C --> D{Screen Reader Testing}
    D --> E[Test with NVDA/VoiceOver]
    E --> F{Zoom Testing}
    F --> G[Zoom to 200% and test functionality]
    G --> H{Color/Contrast Check}
    H --> I[Verify all text meets contrast ratios]
    I --> J{Focus Management}
    J --> K[Ensure focus indicators are visible]
    K --> L[Testing Complete]
```

**قائمة التحقق خطوة بخطوة للاختبار:**
1. **التنقل باستخدام لوحة المفاتيح**: استخدم فقط Tab، Shift+Tab، Enter، Space، ومفاتيح الأسهم
2. **اختبار قارئ الشاشة**: قم بتفعيل NVDA أو VoiceOver أو Narrator وتصفح مع إغلاق عينيك
3. **اختبار التكبير**: اختبر عند مستويات تكبير 200% و400%
4. **التحقق من تباين الألوان**: تحقق من جميع النصوص ومكونات واجهة المستخدم
5. **اختبار مؤشر التركيز**: تأكد من أن جميع العناصر التفاعلية لها حالات تركيز مرئية

✅ **ابدأ بـ Lighthouse**: افتح أدوات المطور في متصفحك، قم بتشغيل تدقيق إمكانية الوصول في Lighthouse، ثم استخدم النتائج لتوجيه تركيزك في الاختبار اليدوي.

### أدوات التكبير والتصغير

تعرف كيف تقوم أحيانًا بتكبير الشاشة على هاتفك عندما يكون النص صغيرًا جدًا، أو تحاول قراءة شاشة الكمبيوتر المحمول في ضوء الشمس الساطع؟ العديد من المستخدمين يعتمدون على أدوات التكبير لجعل المحتوى قابلاً للقراءة كل يوم. يشمل ذلك الأشخاص ذوي الرؤية الضعيفة، كبار السن، وأي شخص حاول قراءة موقع ويب في الهواء الطلق.

تطورت تقنيات التكبير الحديثة لتتجاوز مجرد تكبير الأشياء. فهم كيفية عمل هذه الأدوات سيساعدك على إنشاء تصميمات متجاوبة تظل وظيفية وجذابة عند أي مستوى من التكبير.

**قدرات التكبير الحديثة في المتصفحات:**
- **تكبير الصفحة**: يوسع كل المحتوى بشكل متناسب (النصوص، الصور، التخطيط) - هذه هي الطريقة المفضلة
- **تكبير النص فقط**: يزيد حجم الخط مع الحفاظ على التخطيط الأصلي
- **التكبير بالقرص**: دعم إيماءات الهاتف المحمول للتكبير المؤقت
- **دعم المتصفح**: جميع المتصفحات الحديثة تدعم التكبير حتى 500% دون كسر الوظائف

**برامج التكبير المتخصصة:**
- **Windows**: [Magnifier](https://support.microsoft.com/windows/use-magnifier-to-make-things-on-the-screen-easier-to-see-414948ba-8b1c-d3bd-8615-0e5e32204198) (مضمن)، [ZoomText](https://www.freedomscientific.com/training/zoomtext/getting-started/)
- **macOS/iOS**: [Zoom](https://www.apple.com/accessibility/mac/vision/) (مضمن مع ميزات متقدمة)

> ⚠️ **اعتبار التصميم**: تتطلب WCAG أن يظل المحتوى وظيفيًا عند تكبيره إلى 200%. عند هذا المستوى، يجب أن يكون التمرير الأفقي محدودًا، ويجب أن تظل جميع العناصر التفاعلية قابلة للوصول.

✅ **اختبر تصميمك المتجاوب**: قم بتكبير متصفحك إلى 200% و400%. هل يتكيف تخطيطك بشكل جيد؟ هل لا يزال بإمكانك الوصول إلى جميع الوظائف دون تمرير مفرط؟

## أدوات اختبار إمكانية الوصول الحديثة

الآن بعد أن فهمت كيف يتنقل الناس في الويب باستخدام تقنيات المساعدة، دعونا نستكشف الأدوات التي تساعدك في بناء واختبار مواقع ويب ميسرة.

فكر في الأمر بهذه الطريقة: الأدوات الآلية رائعة في اكتشاف المشكلات الواضحة (مثل النصوص البديلة المفقودة)، بينما يساعدك الاختبار اليدوي في ضمان أن موقعك يشعر بالراحة عند الاستخدام في العالم الحقيقي. معًا، يمنحك الثقة بأن مواقعك تعمل للجميع.

### اختبار تباين الألوان

إليك بعض الأخبار الجيدة: تباين الألوان هو أحد أكثر مشكلات إمكانية الوصول شيوعًا، ولكنه أيضًا من أسهل المشكلات التي يمكن حلها. التباين الجيد يفيد الجميع - من المستخدمين ذوي الإعاقات البصرية إلى الأشخاص الذين يحاولون قراءة هواتفهم على الشاطئ.

**متطلبات تباين WCAG:**

| نوع النص | WCAG AA (الحد الأدنى) | WCAG AAA (المعزز) |
|----------|-----------------------|-------------------|
| **النص العادي** (أقل من 18pt) | نسبة تباين 4.5:1 | نسبة تباين 7:1 |
| **النص الكبير** (18pt+ أو 14pt+ بخط عريض) | نسبة تباين 3:1 | نسبة تباين 4.5:1 |
| **مكونات واجهة المستخدم** (الأزرار، حدود النماذج) | نسبة تباين 3:1 | نسبة تباين 3:1 |

**أدوات الاختبار الأساسية:**
- [Colour Contrast Analyser](https://www.tpgi.com/color-contrast-checker/) - تطبيق سطح المكتب مع منتقي الألوان
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/) - أداة ويب مع ردود فعل فورية
- [Stark](https://www.getstark.co/) - إضافة أدوات التصميم لـ Figma، Sketch، Adobe XD
- [Accessible Colors](https://accessible-colors.com/) - العثور على لوحات ألوان ميسرة

✅ **قم ببناء لوحات ألوان أفضل**: ابدأ بألوان علامتك التجارية واستخدم أدوات التباين لإنشاء تنويعات ميسرة. وثق هذه كرموز ألوان ميسرة في نظام التصميم الخاص بك.

### التدقيق الشامل لإمكانية الوصول

أكثر طرق اختبار إمكانية الوصول فعالية تجمع بين عدة أساليب. لا توجد أداة واحدة تكتشف كل شيء، لذا فإن بناء روتين اختبار باستخدام طرق متنوعة يضمن تغطية شاملة.

**اختبار المستعرض (مضمن في أدوات المطور):**
- **Chrome/Edge**: تدقيق إمكانية الوصول في Lighthouse + لوحة إمكانية الوصول
- **Firefox**: مفتش إمكانية الوصول مع عرض شجرة مفصل
- **Safari**: علامة التدقيق في Web Inspector مع محاكاة VoiceOver

**إضافات الاختبار الاحترافية:**
- [axe DevTools](https://www.deque.com/axe/devtools/) - اختبار آلي قياسي في الصناعة
- [WAVE](https://wave.webaim.org/extension/) - ردود فعل مرئية مع تسليط الضوء على الأخطاء
- [Accessibility Insights](https://accessibilityinsights.io/) - مجموعة اختبار شاملة من Microsoft

**التكامل مع سطر الأوامر وCI/CD:**
- [axe-core](https://github.com/dequelabs/axe-core) - مكتبة JavaScript للاختبار الآلي
- [Pa11y](https://pa11y.org/) - أداة اختبار إمكانية الوصول عبر سطر الأوامر
- [Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci) - تسجيل إمكانية الوصول الآلي

> 🎯 **هدف الاختبار**: استهدف الحصول على درجة إمكانية الوصول في Lighthouse تبلغ 95+ كخط أساس. تذكر، الأدوات الآلية تكتشف حوالي 30-40% فقط من مشكلات إمكانية الوصول - الاختبار اليدوي لا يزال ضروريًا!

## بناء إمكانية الوصول من البداية

مفتاح النجاح في إمكانية الوصول هو تضمينه في الأساس منذ اليوم الأول. أعلم أنه من المغري التفكير "سأضيف إمكانية الوصول لاحقًا"، لكن هذا يشبه محاولة إضافة منحدر إلى منزل بعد بنائه بالفعل. هل يمكن؟ نعم. هل هو سهل؟ ليس حقًا.

فكر في إمكانية الوصول كالتخطيط لمنزل - من الأسهل بكثير تضمين إمكانية الوصول للكراسي المتحركة في خططك المعمارية الأولية بدلاً من تعديل كل شيء لاحقًا.

### مبادئ POUR: أساس إمكانية الوصول الخاص بك

تستند إرشادات محتوى الويب (WCAG) إلى أربعة مبادئ أساسية تُعرف باسم POUR. لا تقلق - هذه ليست مفاهيم أكاديمية مملة! إنها في الواقع إرشادات عملية لإنشاء محتوى يعمل للجميع.

بمجرد أن تفهم POUR، يصبح اتخاذ قرارات إمكانية الوصول أكثر سهولة. إنه مثل وجود قائمة تحقق ذهنية توجه اختياراتك التصميمية. دعونا نوضحها:

**🔍 قابل للإدراك**: يجب تقديم المعلومات بطرق يمكن للمستخدمين إدراكها من خلال حواسهم المتاحة

- توفير بدائل نصية للمحتوى غير النصي (الصور، الفيديوهات، الصوت)
- ضمان تباين ألوان كافٍ لجميع النصوص ومكونات واجهة المستخدم
- تقديم تسميات توضيحية ونصوص للمحتوى متعدد الوسائط
- تصميم محتوى يظل وظيفيًا عند تكبيره حتى 200%
- استخدام خصائص حسية متعددة (ليس فقط اللون) لنقل المعلومات

**🎮 قابل للتشغيل**: يجب أن تكون جميع مكونات الواجهة قابلة للتشغيل من خلال طرق الإدخال المتاحة

- جعل جميع الوظائف قابلة للوصول عبر التنقل باستخدام لوحة المفاتيح
- توفير وقت كافٍ للمستخدمين لقراءة والتفاعل مع المحتوى
- تجنب المحتوى الذي يسبب نوبات أو اضطرابات في الجهاز الدهليزي
- مساعدة المستخدمين على التنقل بكفاءة من خلال هيكل واضح ومعالم
- ضمان أن تكون العناصر التفاعلية ذات أحجام مستهدفة كافية (44px كحد أدنى)

**📖 مفهوم**: يجب أن تكون المعلومات وتشغيل واجهة المستخدم واضحة ومفهومة

- استخدام لغة واضحة وبسيطة مناسبة لجمهورك
- ضمان ظهور المحتوى وتشغيله بطرق متوقعة ومتسقة
- تقديم تعليمات واضحة ورسائل خطأ لإدخال المستخدم
- مساعدة المستخدمين على فهم وتصحيح الأخطاء في النماذج
- تنظيم المحتوى بترتيب قراءة منطقي وتسلسل هرمي للمعلومات

**💪 قوي**: يجب أن يعمل المحتوى بشكل موثوق عبر التقنيات المختلفة والأجهزة المساعدة

- استخدام HTML صالح ودلالي كأساس
- ضمان التوافق مع التقنيات المساعدة الحالية والمستقبلية
- اتباع معايير الويب وأفضل الممارسات للعلامات
- اختبار عبر المتصفحات المختلفة والأجهزة والأدوات المساعدة
- هيكلة المحتوى بحيث يتحلل بشكل جيد عندما لا تكون الميزات المتقدمة مدعومة

## إنشاء تصميم بصري ميسر

التصميم البصري الجيد وإمكانية الوصول يسيران جنبًا إلى جنب. عندما تصمم مع مراعاة إمكانية الوصول، غالبًا ما تكتشف أن هذه القيود تؤدي إلى حلول أنظف وأكثر أناقة تفيد جميع المستخدمين.

دعونا نستكشف كيفية إنشاء تصميمات جذابة بصريًا تعمل للجميع، بغض النظر عن قدراتهم البصرية أو الظروف التي يشاهدون فيها المحتوى الخاص بك.

### استراتيجيات اللون وإمكانية الوصول البصري
اللون أداة قوية للتواصل، لكنه لا يجب أن يكون الطريقة الوحيدة لنقل المعلومات المهمة. التصميم الذي يتجاوز اللون يخلق تجارب أكثر شمولية وقوة تعمل في مختلف الظروف.

**التصميم لمراعاة اختلافات رؤية الألوان:**

حوالي 8% من الرجال و0.5% من النساء يعانون من نوع من اختلافات رؤية الألوان (غالبًا ما يُطلق عليه "عمى الألوان"). الأنواع الأكثر شيوعًا هي:
- **Deuteranopia**: صعوبة في التمييز بين الأحمر والأخضر
- **Protanopia**: يظهر اللون الأحمر بشكل باهت
- **Tritanopia**: صعوبة في التمييز بين الأزرق والأصفر (نادر)

**استراتيجيات شاملة للألوان:**

```css
/* ❌ Bad: Using only color to indicate status */
.error { color: red; }
.success { color: green; }

/* ✅ Good: Color plus icons and context */
.error {
  color: #d32f2f;
  border-left: 4px solid #d32f2f;
}
.error::before {
  content: "⚠️";
  margin-right: 8px;
}

.success {
  color: #2e7d32;
  border-left: 4px solid #2e7d32;
}
.success::before {
  content: "✅";
  margin-right: 8px;
}
```

**ما يتجاوز متطلبات التباين الأساسية:**
- اختبر اختياراتك للألوان باستخدام محاكيات عمى الألوان
- استخدم الأنماط أو القوام أو الأشكال بجانب الترميز اللوني
- تأكد من أن الحالات التفاعلية تظل مميزة بدون الاعتماد على اللون
- فكر في كيفية ظهور تصميمك في وضع التباين العالي

✅ **اختبر إمكانية الوصول للألوان**: استخدم أدوات مثل [Coblis](https://www.color-blindness.com/coblis-color-blindness-simulator/) لمعرفة كيف يظهر موقعك للمستخدمين الذين يعانون من أنواع مختلفة من رؤية الألوان.

### مؤشرات التركيز وتصميم التفاعل

مؤشرات التركيز هي المكافئ الرقمي للمؤشر—تُظهر لمستخدمي لوحة المفاتيح مكان وجودهم على الصفحة. مؤشرات التركيز المصممة جيدًا تعزز التجربة للجميع من خلال جعل التفاعلات واضحة وقابلة للتنبؤ.

**أفضل ممارسات مؤشرات التركيز الحديثة:**

```css
/* Enhanced focus styles that work across browsers */
button:focus-visible {
  outline: 2px solid #0066cc;
  outline-offset: 2px;
  box-shadow: 0 0 0 4px rgba(0, 102, 204, 0.25);
}

/* Remove focus outline for mouse users, preserve for keyboard users */
button:focus:not(:focus-visible) {
  outline: none;
}

/* Focus-within for complex components */
.card:focus-within {
  box-shadow: 0 0 0 3px rgba(74, 144, 164, 0.5);
  border-color: #4A90A4;
}

/* Ensure focus indicators meet contrast requirements */
.custom-focus:focus-visible {
  outline: 3px solid #ffffff;
  outline-offset: 2px;
  box-shadow: 0 0 0 6px #000000;
}
```

**متطلبات مؤشرات التركيز:**
- **الرؤية**: يجب أن يكون لها نسبة تباين لا تقل عن 3:1 مع العناصر المحيطة
- **العرض**: سمك لا يقل عن 2px حول العنصر بالكامل
- **الاستمرارية**: يجب أن تظل مرئية حتى ينتقل التركيز إلى مكان آخر
- **التمييز**: يجب أن تكون مختلفة بصريًا عن حالات واجهة المستخدم الأخرى

> 💡 **نصيحة تصميم**: غالبًا ما تستخدم مؤشرات التركيز الرائعة مزيجًا من الخطوط الخارجية، الظلال، وتغييرات اللون لضمان الرؤية عبر خلفيات وسياقات مختلفة.

✅ **راجع مؤشرات التركيز**: تنقل عبر موقعك باستخدام لوحة المفاتيح ولاحظ العناصر التي تحتوي على مؤشرات تركيز واضحة. هل هناك أي عناصر يصعب رؤيتها أو مفقودة تمامًا؟

### HTML الدلالي: أساس الوصول

HTML الدلالي يشبه إعطاء تقنيات المساعدة نظام GPS لموقعك. عندما تستخدم عناصر HTML الصحيحة لغرضها المقصود، فإنك تقدم لقارئات الشاشة ولوحات المفاتيح وغيرها من الأدوات خارطة طريق مفصلة لمساعدة المستخدمين على التنقل بفعالية.

إليك تشبيهًا أحببته: HTML الدلالي هو الفرق بين مكتبة منظمة جيدًا بها فئات واضحة ولافتات مفيدة مقابل مستودع حيث الكتب متناثرة بشكل عشوائي. كلا المكانين يحتويان على نفس الكتب، لكن أيهما تفضل البحث فيه؟ بالضبط!

**أسس هيكل الصفحة القابل للوصول:**

```html
<!-- Landmark elements provide page navigation structure -->
<header>
  <h1>Your Site Name</h1>
  <nav aria-label="Main navigation">
    <ul>
      <li><a href="/home">Home</a></li>
      <li><a href="/about">About</a></li>
      <li><a href="/services">Services</a></li>
    </ul>
  </nav>
</header>

<main>
  <article>
    <header>
      <h1>Article Title</h1>
      <p>Published on <time datetime="2024-10-14">October 14, 2024</time></p>
    </header>
    
    <section>
      <h2>First Section</h2>
      <p>Content that relates to this section...</p>
    </section>
    
    <section>
      <h2>Second Section</h2>
      <p>More related content...</p>
    </section>
  </article>
  
  <aside>
    <h2>Related Links</h2>
    <nav aria-label="Related articles">
      <ul>
        <li><a href="/related-1">First related article</a></li>
        <li><a href="/related-2">Second related article</a></li>
      </ul>
    </nav>
  </aside>
</main>

<footer>
  <p>&copy; 2024 Your Site Name. All rights reserved.</p>
  <nav aria-label="Footer links">
    <ul>
      <li><a href="/privacy">Privacy Policy</a></li>
      <li><a href="/contact">Contact Us</a></li>
    </ul>
  </nav>
</footer>
```

**لماذا يحول HTML الدلالي إمكانية الوصول:**

| العنصر الدلالي | الغرض | فائدة لقارئ الشاشة |
|------------------|---------|----------------------|
| `<header>` | رأس الصفحة أو القسم | "معلم البانر" - التنقل السريع إلى الأعلى |
| `<nav>` | روابط التنقل | "معلم التنقل" - قائمة أقسام التنقل |
| `<main>` | المحتوى الأساسي للصفحة | "معلم الرئيسي" - الانتقال مباشرة إلى المحتوى |
| `<article>` | محتوى مستقل | يعلن حدود المقالة |
| `<section>` | مجموعات محتوى ذات موضوع | يوفر هيكلًا للمحتوى |
| `<aside>` | محتوى الشريط الجانبي ذو الصلة | "معلم تكميلي" |
| `<footer>` | تذييل الصفحة أو القسم | "معلم معلومات المحتوى" |

**قدرات قارئ الشاشة مع HTML الدلالي:**
- **التنقل بين المعالم**: الانتقال بين أقسام الصفحة الرئيسية فورًا
- **مخططات العناوين**: إنشاء جدول محتويات من هيكل العناوين الخاص بك
- **قوائم العناصر**: إنشاء قوائم بجميع الروابط، الأزرار، أو عناصر التحكم في النماذج
- **وعي السياق**: فهم العلاقات بين أقسام المحتوى

> 🎯 **اختبار سريع**: حاول التنقل في موقعك باستخدام قارئ شاشة باستخدام اختصارات المعالم (D للمعلم، H للعناوين، K للرابط في NVDA/JAWS). هل التنقل منطقي؟

✅ **راجع هيكلك الدلالي**: استخدم لوحة إمكانية الوصول في أدوات المطور في متصفحك لعرض شجرة إمكانية الوصول والتأكد من أن الترميز الخاص بك يخلق هيكلًا منطقيًا.

### تسلسل العناوين: إنشاء مخطط محتوى منطقي

العناوين ضرورية للغاية للمحتوى القابل للوصول—إنها مثل العمود الفقري الذي يربط كل شيء معًا. يعتمد مستخدمو قارئات الشاشة بشكل كبير على العناوين لفهم المحتوى والتنقل فيه. فكر في الأمر كأنك تقدم جدول محتويات لصفحتك.

**إليك القاعدة الذهبية للعناوين:**
لا تتخطى المستويات. تقدم دائمًا بشكل منطقي من `<h1>` إلى `<h2>` إلى `<h3>`، وهكذا. تذكر إنشاء المخططات في المدرسة؟ إنها نفس المبدأ تمامًا—لن تقفز من "I. النقطة الرئيسية" مباشرة إلى "C. النقطة الفرعية الفرعية" دون وجود "A. النقطة الفرعية" بينهما، أليس كذلك؟

**مثال على هيكل عناوين مثالي:**

```html
<!-- ✅ Excellent: Logical, hierarchical progression -->
<main>
  <h1>Complete Guide to Web Accessibility</h1>
  
  <section>
    <h2>Understanding Screen Readers</h2>
    <p>Introduction to screen reader technology...</p>
    
    <h3>Popular Screen Reader Software</h3>
    <p>NVDA, JAWS, and VoiceOver comparison...</p>
    
    <h3>Testing with Screen Readers</h3>
    <p>Step-by-step testing instructions...</p>
  </section>
  
  <section>
    <h2>Color and Contrast Guidelines</h2>
    <p>Designing with sufficient contrast...</p>
    
    <h3>WCAG Contrast Requirements</h3>
    <p>Understanding the different contrast levels...</p>
    
    <h3>Testing Tools and Techniques</h3>
    <p>Tools for verifying contrast ratios...</p>
  </section>
</main>
```

```html
<!-- ❌ Problematic: Skipping levels, inconsistent structure -->
<h1>Page Title</h1>
<h3>Subsection</h3> <!-- Skipped h2 -->
<h2>This should come before h3</h2>
<h1>Another main heading?</h1> <!-- Multiple h1s -->
```

**أفضل ممارسات العناوين:**
- **عنوان واحد `<h1>` لكل صفحة**: عادةً ما يكون عنوان الصفحة الرئيسي أو عنوان المحتوى الأساسي
- **تقدم منطقي**: لا تتخطى المستويات (h1 → h2 → h3، وليس h1 → h3)
- **محتوى وصفي**: اجعل العناوين ذات معنى عند قراءتها خارج السياق
- **تنسيق بصري باستخدام CSS**: استخدم CSS للمظهر، ومستويات HTML للهيكل

**إحصائيات التنقل باستخدام قارئ الشاشة:**
- 68% من مستخدمي قارئات الشاشة يتنقلون باستخدام العناوين ([WebAIM Survey](https://webaim.org/projects/screenreadersurvey9/#finding))
- يتوقع المستخدمون العثور على مخطط عناوين منطقي
- توفر العناوين أسرع طريقة لفهم هيكل الصفحة

> 💡 **نصيحة احترافية**: استخدم إضافات المتصفح مثل "HeadingsMap" لتصور هيكل العناوين الخاص بك. يجب أن يقرأ مثل جدول محتويات منظم جيدًا.

✅ **اختبر هيكل العناوين الخاص بك**: استخدم التنقل بالعناوين في قارئ الشاشة (مفتاح H في NVDA) للتنقل عبر العناوين. هل التقدم يروي قصة المحتوى بشكل منطقي؟

### تقنيات متقدمة لإمكانية الوصول البصري

ما يتجاوز أساسيات التباين واللون، هناك تقنيات متطورة تساعد في إنشاء تجارب بصرية شاملة حقًا. تضمن هذه الأساليب أن يعمل المحتوى الخاص بك عبر ظروف المشاهدة المختلفة وتقنيات المساعدة.

**استراتيجيات التواصل البصري الأساسية:**

- **التغذية الراجعة متعددة الوسائط**: اجمع بين الإشارات البصرية والنصية وأحيانًا الصوتية
- **الإفصاح التدريجي**: قدم المعلومات على شكل أجزاء قابلة للهضم
- **أنماط التفاعل المتسقة**: استخدم اتفاقيات واجهة المستخدم المألوفة
- **الطباعة المتجاوبة**: قم بتوسيع النص بشكل مناسب عبر الأجهزة
- **حالات التحميل والخطأ**: قدم تغذية راجعة واضحة لجميع الإجراءات

**أدوات CSS لتحسين إمكانية الوصول:**

```css
/* Screen reader only text - visually hidden but accessible */
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border: 0;
}

/* Skip link for keyboard navigation */
.skip-link {
  position: absolute;
  top: -40px;
  left: 6px;
  background: #000000;
  color: #ffffff;
  padding: 8px 16px;
  text-decoration: none;
  border-radius: 4px;
  font-weight: bold;
  transition: top 0.3s ease;
  z-index: 1000;
}

.skip-link:focus {
  top: 6px;
}

/* Reduced motion respect */
@media (prefers-reduced-motion: reduce) {
  .skip-link {
    transition: none;
  }
  
  * {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}

/* High contrast mode support */
@media (prefers-contrast: high) {
  .button {
    border: 2px solid;
  }
}
```

> 🎯 **نمط إمكانية الوصول**: "رابط التخطي" ضروري لمستخدمي لوحة المفاتيح. يجب أن يكون العنصر الأول القابل للتركيز على صفحتك ويقفز مباشرة إلى منطقة المحتوى الرئيسي.

✅ **قم بتنفيذ تخطي التنقل**: أضف روابط التخطي إلى صفحاتك واختبرها بالضغط على Tab بمجرد تحميل الصفحة. يجب أن تظهر وتسمح لك بالقفز إلى المحتوى الرئيسي.

## صياغة نصوص روابط ذات معنى

الروابط هي بمثابة الطرق السريعة للويب، لكن النصوص المكتوبة بشكل سيئ للروابط تشبه وجود علامات طريق تقول فقط "مكان" بدلًا من "وسط مدينة شيكاغو". ليس مفيدًا جدًا، أليس كذلك؟

إليك شيء أدهشني عندما تعلمته لأول مرة: يمكن لقارئات الشاشة استخراج جميع الروابط من الصفحة وعرضها كقائمة كبيرة واحدة. تخيل لو أعطاك أحدهم دليلًا لكل رابط على صفحتك. هل سيبدو كل واحد منطقيًا بمفرده؟ هذا هو الاختبار الذي يجب أن يجتازه نص الرابط الخاص بك!

### فهم أنماط التنقل عبر الروابط

توفر قارئات الشاشة ميزات تنقل قوية تعتمد على نصوص الروابط المكتوبة جيدًا:

**طرق التنقل عبر الروابط:**
- **القراءة المتسلسلة**: تُقرأ الروابط في سياقها كجزء من تدفق المحتوى
- **إنشاء قائمة الروابط**: جميع روابط الصفحة تُجمع في دليل قابل للبحث
- **التنقل السريع**: الانتقال بين الروابط باستخدام اختصارات لوحة المفاتيح (K في NVDA)
- **وظيفة البحث**: العثور على روابط محددة عن طريق كتابة نص جزئي

**لماذا السياق مهم:**
عندما يقوم مستخدمو قارئات الشاشة بإنشاء قائمة روابط، يرون شيئًا مثل هذا:
- "تحميل التقرير"
- "تعرف على المزيد"
- "اضغط هنا"
- "سياسة الخصوصية"
- "اضغط هنا"

فقط اثنان من هذه الروابط يوفران معلومات مفيدة عند قراءتها خارج السياق!

> 📊 **تأثير المستخدم**: يقوم مستخدمو قارئات الشاشة بمسح قوائم الروابط لفهم محتوى الصفحة بسرعة. النصوص العامة للروابط تجبرهم على العودة إلى سياق كل رابط، مما يبطئ تجربة التصفح بشكل كبير.

### أخطاء شائعة في نصوص الروابط يجب تجنبها

فهم ما لا يعمل يساعدك على التعرف على مشكلات إمكانية الوصول وإصلاحها في المحتوى الحالي.

**❌ نصوص روابط عامة لا توفر سياقًا:**

```html
<!-- Meaningless when read from a link list -->
<p>Our sustainability efforts are detailed in our recent report. 
   <a href="/sustainability-2024.pdf">Click here</a> to view it.</p>

<!-- Repeated generic text throughout the page -->
<div class="article-card">
  <h3>Web Accessibility Guide</h3>
  <p>Learn the fundamentals...</p>
  <a href="/accessibility-guide">Read more</a>
</div>
<div class="article-card">
  <h3>Color Contrast Tips</h3>
  <p>Improve your design...</p>
  <a href="/color-contrast">Read more</a>
</div>

<!-- URLs as link text (difficult for screen readers to announce) -->
<p>Visit https://www.w3.org/WAI/WCAG21/quickref/ for WCAG guidelines.</p>

<!-- Vague action words -->
<a href="/contact">Go</a> | <a href="/about">See</a> | <a href="/help">View</a>
```

**لماذا تفشل هذه الأنماط:**
- **"اضغط هنا"** لا تخبر المستخدمين شيئًا عن الوجهة
- **"اقرأ المزيد"** المكررة عدة مرات تسبب ارتباكًا
- **عناوين URL الخام** يصعب على قارئات الشاشة نطقها بوضوح
- **كلمات فردية** مثل "اذهب" أو "شاهد" تفتقر إلى السياق الوصفي

### كتابة نصوص روابط ممتازة

نصوص الروابط الوصفية تفيد الجميع—يمكن للمستخدمين المبصرين مسح الروابط بسرعة، ومستخدمو قارئات الشاشة يفهمون الوجهات فورًا.

**✅ أمثلة على نصوص روابط واضحة ووصفية:**

```html
<!-- Descriptive text that explains the destination -->
<p>Our comprehensive <a href="/sustainability-2024.pdf">2024 sustainability report (PDF, 2.1MB)</a> details our environmental initiatives.</p>

<!-- Specific, unique link text for each card -->
<div class="article-card">
  <h3>Web Accessibility Guide</h3>
  <p>Learn the fundamentals of inclusive design...</p>
  <a href="/accessibility-guide">Read our complete web accessibility guide</a>
</div>
<div class="article-card">
  <h3>Color Contrast Tips</h3>
  <p>Improve your design with better color choices...</p>
  <a href="/color-contrast">Explore color contrast best practices</a>
</div>

<!-- Meaningful text instead of raw URLs -->
<p>The <a href="https://www.w3.org/WAI/WCAG21/quickref/">WCAG 2.1 Quick Reference guide</a> provides comprehensive accessibility guidelines.</p>

<!-- Descriptive action links -->
<a href="/contact">Contact our support team</a> | 
<a href="/about">About our company</a> | 
<a href="/help">Get help with your account</a>
```

**أفضل ممارسات نصوص الروابط:**
- **كن محددًا**: "تحميل التقرير المالي الفصلي" مقابل "تحميل"
- **تضمين نوع الملف والحجم**: "(PDF، 1.2MB)" للملفات القابلة للتنزيل
- **ذكر إذا كانت الروابط تفتح خارجيًا**: "(تفتح في نافذة جديدة)" عند الاقتضاء
- **استخدام لغة نشطة**: "اتصل بنا" مقابل "صفحة الاتصال"
- **اجعلها موجزة**: حاول أن تكون بين 2-8 كلمات عند الإمكان

### أنماط متقدمة لإمكانية الوصول للروابط

أحيانًا تتطلب قيود التصميم البصري أو المتطلبات التقنية حلولًا خاصة. إليك تقنيات متطورة لسيناريوهات شائعة صعبة:

**استخدام ARIA للسياق المحسن:**

```html
<!-- When button text must be short but needs more context -->
<a href="/report.pdf" 
   aria-label="Download 2024 annual financial report, PDF format, 2.3MB">
  Download Report
</a>

<!-- When the full context comes from surrounding content -->
<h3 id="sustainability-heading">Sustainability Initiative</h3>
<p>Our efforts to reduce environmental impact...</p>
<a href="/sustainability-details" 
   aria-labelledby="sustainability-heading"
   aria-describedby="sustainability-summary">
  Learn more
</a>
<p id="sustainability-summary">Detailed breakdown of our 2024 environmental goals and achievements</p>
```

**الإشارة إلى أنواع الملفات والوجهات الخارجية:**

```html
<!-- Method 1: Include information in visible link text -->
<a href="/annual-report.pdf">
  Download our 2024 annual report (PDF, 2.3MB)
</a>

<!-- Method 2: Use screen reader-only text for file details -->
<a href="/annual-report.pdf">
  Download our 2024 annual report
  <span class="sr-only">(PDF format, 2.3MB)</span>
</a>

<!-- Method 3: External link indication -->
<a href="https://example.com" 
   target="_blank" 
   aria-describedby="external-link-warning">
  Visit external resource
</a>
<span id="external-link-warning" class="sr-only">
  (opens in new window)
</span>

<!-- Method 4: Using CSS for visual indicators -->
<a href="https://example.com" class="external-link">
  External resource
</a>
```

```css
/* Visual indicator for external links */
.external-link::after {
  content: " ↗";
  font-size: 0.8em;
  color: #666;
}

/* Screen reader announcement for external links */
.external-link::before {
  content: "External link: ";
  position: absolute;
  left: -10000px;
  width: 1px;
  height: 1px;
  overflow: hidden;
}
```

> ⚠️ **مهم**: عند استخدام `target="_blank"`، دائمًا أبلغ المستخدمين أن الرابط يفتح في نافذة أو علامة تبويب جديدة. التغييرات غير المتوقعة في التنقل يمكن أن تكون مربكة.

✅ **اختبر سياق الروابط الخاصة بك**: استخدم أدوات المطور في متصفحك لإنشاء قائمة بجميع الروابط على صفحتك. هل يمكنك فهم غرض كل رابط بدون أي سياق محيط؟

## ARIA: تعزيز إمكانية الوصول لـ HTML

[تطبيقات الإنترنت الغنية القابلة للوصول (ARIA)](https://developer.mozilla.org/docs/Web/Accessibility/ARIA) تشبه وجود مترجم عالمي بين تطبيقات الويب المعقدة وتقنيات المساعدة. عندما لا يستطيع HTML وحده التعبير عن كل ما تفعله مكوناتك التفاعلية، تتدخل ARIA لملء تلك الفجوات.

أحب أن أفكر في ARIA كإضافة تعليقات مفيدة إلى HTML الخاص بك—مثل تعليمات المسرح في نص مسرحي تساعد الممثلين على فهم أدوارهم وعلاقاتهم.

**إليك القاعدة الأهم حول ARIA**: استخدم دائمًا HTML الدلالي أولاً، ثم أضف ARIA لتعزيزه. فكر في ARIA كالتوابل، وليس الطبق الرئيسي. يجب أن توضح وتعزز هيكل HTML الخاص بك، ولا تحل محله أبدًا. احصل على الأساس الصحيح أولاً!

### تنفيذ استراتيجي لـ ARIA

ARIA قوية، ولكن مع القوة تأتي المسؤولية. يمكن أن تجعل ARIA غير الصحيحة إمكانية الوصول أسوأ من عدم وجودها على الإطلاق. إليك متى وكيف تستخدمها بفعالية:

**✅ استخدم ARIA عندما:**
- إنشاء عناصر واجهة مستخدم تفاعلية مخصصة (الأكورديونات، علامات التبويب، الكاروسيل)
- بناء محتوى ديناميكي يتغير دون إعادة تحميل الصفحة
- توفير سياق إضافي للعلاقات المعقدة في واجهة المستخدم
- الإشارة إلى حالات التحميل أو تحديثات المحتوى الحية
- إنشاء واجهات تشبه التطبيقات بعناصر تحكم مخصصة

**❌ تجنب ARIA عندما:**
- توفر عناصر HTML القياسية بالفعل الدلالات المطلوبة
- لست متأكدًا من كيفية تنفيذها بشكل صحيح
- تكرر المعلومات التي توفرها HTML الدلالي بالفعل
- لم تختبرها باستخدام تقنيات المساعدة الفعلية

> 🎯 **القاعدة الذهبية لـ ARIA**: "لا تغير الدلالات إلا إذا كنت مضطرًا تمامًا، تأكد دائمًا من إمكانية الوصول عبر لوحة المفاتيح، واختبر باستخدام تقنيات المساعدة الحقيقية."

**الفئات الخمس لـ ARIA:**

1. **الأدوار**: ما هو هذا العنصر؟ (`button`, `tab`, `dialog`)
2. **الخصائص**: ما هي ميزاته؟ (`aria-required`, `aria-haspopup`)
3. **الحالات**: ما هي حالته الحالية؟ (`aria-expanded`, `aria-checked`)
4. **المعالم**: أين هو في هيكل الصفحة؟ (`banner`, `navigation`, `main`)
5. **المناطق الحية**: كيف يجب الإعلان عن التغييرات؟ (`aria-live`, `aria-atomic`)

### أنماط ARIA الأساسية لتطبيقات الويب الحديثة

تساعد هذه الأنماط في حل التحديات الأكثر شيوعًا في تطبيقات الويب التفاعلية:

**تسمية ووصف العناصر:**

```html
<!-- aria-label: Provides accessible name when visible text isn't sufficient -->
<button aria-label="Close newsletter subscription dialog">×</button>

<!-- aria-labelledby: References existing text as the accessible name -->
<section aria-labelledby="news-heading">
  <h2 id="news-heading">Latest News</h2>
  <!-- news content -->
</section>

<!-- aria-describedby: Links to additional descriptive text -->
<input type="password" 
       aria-describedby="pwd-requirements pwd-strength"
       required>
<div id="pwd-requirements">
  Password must contain at least 8 characters, including uppercase, lowercase, and numbers.
</div>
<div id="pwd-strength" aria-live="polite">
  <!-- Dynamic password strength indicator -->
</div>
```

**المناطق الحية للمحتوى الديناميكي:**

```html
<!-- Polite announcements (don't interrupt current speech) -->
<div aria-live="polite" id="status-updates">
  <!-- Status messages appear here -->
</div>

<!-- Assertive announcements (interrupt and announce immediately) -->
<div aria-live="assertive" id="urgent-alerts">
  <!-- Error messages and critical alerts -->
</div>

<!-- Loading states with live regions -->
<button id="submit-btn" aria-describedby="loading-status">
  Submit Application
</button>
<div id="loading-status" aria-live="polite" aria-atomic="true">
  <!-- "Processing your application..." appears here -->
</div>
```

**مثال على عنصر واجهة مستخدم تفاعلي (الأكورديون):**

```html
<div class="accordion">
  <h3>
    <button aria-expanded="false" 
            aria-controls="panel-1" 
            id="accordion-trigger-1"
            class="accordion-trigger">
      Accessibility Guidelines
    </button>
  </h3>
  <div id="panel-1" 
       role="region"
       aria-labelledby="accordion-trigger-1" 
       hidden>
    <p>WCAG 2.1 provides comprehensive guidelines...</p>
  </div>
</div>
```

```javascript
// JavaScript to manage accordion state
function toggleAccordion(trigger) {
  const panel = document.getElementById(trigger.getAttribute('aria-controls'));
  const isExpanded = trigger.getAttribute('aria-expanded') === 'true';
  
  // Toggle states
  trigger.setAttribute('aria-expanded', !isExpanded);
  panel.hidden = isExpanded;
  
  // Announce change to screen readers
  const status = document.getElementById('status-updates');
  status.textContent = isExpanded ? 'Section collapsed' : 'Section expanded';
}
```

### أفضل ممارسات تنفيذ ARIA

ARIA قوية ولكنها تتطلب تنفيذًا دقيقًا. يساعد اتباع هذه الإرشادات في ضمان أن ARIA تعزز إمكانية الوصول بدلاً من أن تعيقها:

**🛡️ المبادئ الأساسية:**

1. **HTML الدلالي أولاً**: اختر دائمًا `<button>` بدلاً من `<div role="button">`
2. **لا تكسر الدلالات**: لا تتجاوز المعنى الموجود بالفعل في HTML (تجنب `<h1 role="button">`)
3. **الحفاظ على إمكانية الوصول عبر لوحة المفاتيح**: يجب أن تكون جميع عناصر ARIA التفاعلية قابلة للوصول بالكامل عبر لوحة المفاتيح
4. **اختبر مع المستخدمين الحقيقيين**: دعم ARIA يختلف بشكل كبير بين تقنيات المساعدة
5. **ابدأ ببساطة**: تنفيذات ARIA المعقدة أكثر عرضة للأخطاء

**🔍 سير عمل الاختبار:**

```mermaid
graph TD
    A[Write ARIA code] --> B[Validate HTML]
    B --> C[Test with keyboard only]
    C --> D[Test with screen reader]
    D --> E[Test across browsers]
    E --> F{Issues found?}
    F -->|Yes| G[Fix and re-test]
    F -->|No| H[Implementation complete]
    G --> B
```

**🚫 أخطاء شائعة في ARIA يجب تجنبها:**

- **معلومات متضاربة**: لا تتناقض مع دلالات HTML
- **الإفراط في التسمية**: الكثير من معلومات ARIA يربك المستخدمين
- **ARIA ثابتة**: نسيان تحديث حالات ARIA عند تغيير المحتوى
- **تنفيذات غير مختبرة**: ARIA تعمل نظريًا ولكنها تفشل عمليًا
- **غياب دعم لوحة المفاتيح**: أدوار ARIA بدون تفاعلات لوحة المفاتيح المناسبة

> 💡 **موارد الاختبار**: استخدم أدوات مثل [accessibility-checker](https://www.npmjs.com/package/accessibility-checker) للتحقق التلقائي من ARIA، ولكن اختبر دائمًا باستخدام قارئات الشاشة الحقيقية للحصول على تجربة كاملة.

✅ **تعلم من الخبراء**: ادرس [دليل ممارسات تأليف ARIA](https://w3c.github.io/aria-practices/) للحصول على أنماط وتنفيذات مجربة لعناصر واجهة تفاعلية معقدة.

## جعل الصور والوسائط قابلة للوصول

المحتوى البصري والصوتي جزء أساسي من تجارب الويب الحديثة، ولكنه قد يخلق حواجز إذا لم يتم تنفيذه بعناية. الهدف هو ضمان وصول المعلومات والتأثير العاطفي لوسائطك إلى كل مستخدم. بمجرد أن تتقن ذلك، يصبح الأمر طبيعيًا.

أنواع الوسائط المختلفة تحتاج إلى نهج وصول مختلف. الأمر يشبه الطهي - لن تتعامل مع سمكة حساسة بنفس الطريقة التي تتعامل بها مع شريحة لحم قوية. فهم هذه الفروقات يساعدك في اختيار الحل المناسب لكل حالة.

### استراتيجية الوصول إلى الصور

كل صورة على موقعك تخدم غرضًا. فهم هذا الغرض يساعدك في كتابة نص بديل أفضل وخلق تجارب أكثر شمولية.

**أنواع الصور الأربعة واستراتيجيات النص البديل الخاصة بها:**

**الصور المعلوماتية** - تنقل معلومات مهمة:
```html
<img src="../../../../translated_images/chart.31c7eb0eb5c4450deba10b6f236732dfee8e8a11f6c0d8f31d2c2efb9d4c00ef.ar.png" alt="Sales increased 25% from Q1 to Q2 2024">
```

**الصور الزخرفية** - بصرية بحتة بدون قيمة معلوماتية:
```html
<img src="../../../../translated_images/decorative-border.b2f3c4d6634fb79d57fb6357835906c16938df3d5651c1314c196c3b1c52df98.ar.png" alt="" role="presentation">
```

**الصور الوظيفية** - تعمل كأزرار أو عناصر تحكم:
```html
<button>
  <img src="search-icon.svg" alt="Search">
</button>
```

**الصور المعقدة** - الرسوم البيانية، المخططات، الإنفوجرافيك:
```html
<img src="../../../../translated_images/complex-chart.c831f461a363b446a688be5ccacde20d011221758c902cb082cfd4293534ef17.ar.png" alt="Quarterly sales data" aria-describedby="chart-description">
<div id="chart-description">
  <p>Detailed description: Sales data shows a steady increase across all quarters...</p>
</div>
```

### الوصول إلى الفيديو والصوت

**متطلبات الفيديو:**
- **التسميات التوضيحية**: نسخة نصية للمحتوى المنطوق والمؤثرات الصوتية
- **الوصف الصوتي**: سرد العناصر البصرية للمستخدمين المكفوفين
- **النصوص**: نسخة نصية كاملة لكل المحتوى الصوتي والبصري

```html
<video controls>
  <source src="video.mp4" type="video/mp4">
  <track kind="captions" src="captions.vtt" srclang="en" label="English">
  <track kind="descriptions" src="descriptions.vtt" srclang="en" label="Audio descriptions">
</video>
```

**متطلبات الصوت:**
- **النصوص**: نسخة نصية لكل المحتوى المنطوق
- **مؤشرات بصرية**: للمحتوى الصوتي فقط، قدم إشارات بصرية

### تقنيات الصور الحديثة

**استخدام CSS للصور الزخرفية:**
```css
.hero-section {
  background-image: url('decorative-hero.jpg');
  /* Decorative images in CSS don't need alt text */
}
```

**الصور المستجيبة مع إمكانية الوصول:**
```html
<picture>
  <source media="(min-width: 800px)" srcset="large-chart.png">
  <source media="(min-width: 400px)" srcset="medium-chart.png">
  <img src="../../../../translated_images/small-chart.c50c7b1bbcce43d8d24fbfbab8f691fe47d8f25fb7c70857c9eae21d5f22862e.ar.png" alt="Website traffic increased 40% after accessibility improvements">
</picture>
```

✅ **اختبر إمكانية الوصول إلى الصور**: استخدم قارئ شاشة للتنقل في صفحة تحتوي على صور. هل تحصل على معلومات كافية لفهم المحتوى؟

## التنقل باستخدام لوحة المفاتيح وإدارة التركيز

العديد من المستخدمين يتنقلون في الويب باستخدام لوحات المفاتيح فقط. يشمل ذلك الأشخاص ذوي الإعاقات الحركية، والمستخدمين المحترفين الذين يجدون لوحات المفاتيح أسرع من الفأرة، وأي شخص توقفت فأرته عن العمل. ضمان عمل موقعك بشكل جيد مع إدخال لوحة المفاتيح أمر ضروري وغالبًا ما يجعل موقعك أكثر كفاءة للجميع.

### أنماط التنقل الأساسية باستخدام لوحة المفاتيح

**تفاعلات لوحة المفاتيح القياسية:**
- **Tab**: نقل التركيز للأمام عبر العناصر التفاعلية
- **Shift + Tab**: نقل التركيز للخلف
- **Enter**: تفعيل الأزرار والروابط
- **Space**: تفعيل الأزرار، تحديد مربعات الاختيار
- **مفاتيح الأسهم**: التنقل داخل مجموعات المكونات (أزرار الراديو، القوائم)
- **Escape**: إغلاق النوافذ المنبثقة، القوائم المنسدلة، أو إلغاء العمليات

### أفضل ممارسات إدارة التركيز

**مؤشرات التركيز المرئية:**
```css
/* Ensure focus is always visible */
button:focus-visible {
  outline: 2px solid #4A90A4;
  outline-offset: 2px;
}

/* Custom focus styles for different components */
.card:focus-within {
  box-shadow: 0 0 0 3px rgba(74, 144, 164, 0.5);
}
```

**روابط التخطي للتنقل الفعال:**
```html
<a href="#main-content" class="skip-link">Skip to main content</a>
<a href="#navigation" class="skip-link">Skip to navigation</a>

<nav id="navigation">
  <!-- navigation content -->
</nav>
<main id="main-content">
  <!-- main content -->
</main>
```

**ترتيب علامات التبويب المناسب:**
```html
<!-- Use semantic HTML for natural tab order -->
<form>
  <label for="name">Name:</label>
  <input type="text" id="name" tabindex="0">
  
  <label for="email">Email:</label>
  <input type="email" id="email" tabindex="0">
  
  <button type="submit" tabindex="0">Submit</button>
</form>
```

### حصر التركيز في النوافذ المنبثقة

عند فتح نوافذ منبثقة، يجب حصر التركيز داخل النافذة:

```javascript
// Modern focus trap implementation
function trapFocus(element) {
  const focusableElements = element.querySelectorAll(
    'button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])'
  );
  
  const firstElement = focusableElements[0];
  const lastElement = focusableElements[focusableElements.length - 1];

  element.addEventListener('keydown', (e) => {
    if (e.key === 'Tab') {
      if (e.shiftKey && document.activeElement === firstElement) {
        e.preventDefault();
        lastElement.focus();
      } else if (!e.shiftKey && document.activeElement === lastElement) {
        e.preventDefault();
        firstElement.focus();
      }
    }
    
    if (e.key === 'Escape') {
      closeModal();
    }
  });
  
  // Focus first element when modal opens
  firstElement.focus();
}
```

✅ **اختبر التنقل باستخدام لوحة المفاتيح**: حاول التنقل في موقعك باستخدام مفتاح Tab فقط. هل يمكنك الوصول إلى كل العناصر التفاعلية؟ هل ترتيب التركيز منطقي؟ هل مؤشرات التركيز واضحة؟

## إمكانية الوصول إلى النماذج

النماذج ضرورية لتفاعل المستخدم وتتطلب اهتمامًا خاصًا بإمكانية الوصول.

### ارتباط التسمية وعناصر التحكم بالنموذج

**كل عنصر تحكم في النموذج يحتاج إلى تسمية:**
```html
<!-- Explicit labeling (preferred) -->
<label for="username">Username:</label>
<input type="text" id="username" name="username" required>

<!-- Implicit labeling -->
<label>
  Password:
  <input type="password" name="password" required>
</label>

<!-- Using aria-label when visual label isn't desired -->
<input type="search" aria-label="Search products" placeholder="Search...">
```

### معالجة الأخطاء والتحقق

**رسائل الخطأ القابلة للوصول:**
```html
<label for="email">Email Address:</label>
<input type="email" id="email" name="email" 
       aria-describedby="email-error" 
       aria-invalid="true" required>
<div id="email-error" role="alert">
  Please enter a valid email address
</div>
```

**أفضل ممارسات التحقق من النموذج:**
- استخدم `aria-invalid` للإشارة إلى الحقول غير الصالحة
- قدم رسائل خطأ واضحة ومحددة
- استخدم `role="alert"` للإعلانات المهمة عن الأخطاء
- أظهر الأخطاء فورًا وعند إرسال النموذج

### المجموعات والحقول

**جمع عناصر التحكم ذات الصلة بالنموذج:**
```html
<fieldset>
  <legend>Shipping Address</legend>
  <label for="street">Street Address:</label>
  <input type="text" id="street" name="street">
  
  <label for="city">City:</label>
  <input type="text" id="city" name="city">
</fieldset>

<fieldset>
  <legend>Preferred Contact Method</legend>
  <input type="radio" id="contact-email" name="contact" value="email">
  <label for="contact-email">Email</label>
  
  <input type="radio" id="contact-phone" name="contact" value="phone">
  <label for="contact-phone">Phone</label>
</fieldset>
```

## رحلتك في إمكانية الوصول: النقاط الرئيسية

تهانينا! لقد اكتسبت الآن المعرفة الأساسية لإنشاء تجارب ويب شاملة حقًا. هذا أمر مثير للغاية! إمكانية الوصول إلى الويب ليست مجرد التزام بمعايير الامتثال - إنها تتعلق بفهم الطرق المتنوعة التي يتفاعل بها الناس مع المحتوى الرقمي وتصميم تلك التعقيدات الرائعة.

أنت الآن جزء من مجتمع متنامٍ من المطورين الذين يفهمون أن التصميم الرائع يعمل للجميع. مرحبًا بك في النادي!

**🎯 أدواتك لإمكانية الوصول الآن تشمل:**

| المبدأ الأساسي | التنفيذ | التأثير |
|----------------|----------------|---------|
| **أساس HTML الدلالي** | استخدم عناصر HTML المناسبة لغرضها المقصود | يمكن لقارئات الشاشة التنقل بكفاءة، تعمل لوحات المفاتيح تلقائيًا |
| **تصميم بصري شامل** | تباين كافٍ، استخدام الألوان بشكل هادف، مؤشرات التركيز المرئية | واضح للجميع في أي ظروف إضاءة |
| **محتوى وصفي** | نصوص روابط ذات معنى، نصوص بديلة، عناوين | يفهم المستخدمون المحتوى بدون سياق بصري |
| **إمكانية الوصول باستخدام لوحة المفاتيح** | ترتيب علامات التبويب، اختصارات لوحة المفاتيح، إدارة التركيز | إمكانية الوصول الحركية وكفاءة المستخدم المحترف |
| **تعزيز ARIA** | استخدام استراتيجي لسد الفجوات الدلالية | التطبيقات المعقدة تعمل مع تقنيات المساعدة |
| **اختبار شامل** | أدوات تلقائية + تحقق يدوي + اختبار المستخدم الحقيقي | اكتشاف المشكلات قبل أن تؤثر على المستخدمين |

**🚀 خطواتك التالية:**

1. **دمج إمكانية الوصول في سير عملك**: اجعل الاختبار جزءًا طبيعيًا من عملية التطوير
2. **تعلم من المستخدمين الحقيقيين**: ابحث عن ملاحظات من الأشخاص الذين يستخدمون تقنيات المساعدة
3. **ابقَ على اطلاع**: تتطور تقنيات إمكانية الوصول مع التقنيات والمعايير الجديدة
4. **الدعوة إلى الشمولية**: شارك معرفتك واجعل إمكانية الوصول أولوية الفريق

> 💡 **تذكر**: قيود إمكانية الوصول غالبًا ما تؤدي إلى حلول مبتكرة وأنيقة تفيد الجميع. المنحدرات، التسميات التوضيحية، وعناصر التحكم الصوتية بدأت كميزات إمكانية الوصول وأصبحت تحسينات رئيسية.

**الحجة التجارية واضحة تمامًا**: مواقع الويب القابلة للوصول تصل إلى المزيد من المستخدمين، تحتل مرتبة أفضل في محركات البحث، تكلفتها أقل في الصيانة، وتتجنب المخاطر القانونية. ولكن بصراحة؟ السبب الحقيقي للاهتمام بإمكانية الوصول أعمق بكثير. مواقع الويب القابلة للوصول تجسد أفضل قيم الويب - الانفتاح، الشمولية، وفكرة أن الجميع يستحقون الوصول المتساوي إلى المعلومات.

أنت الآن مجهز لبناء مستقبل ويب شامل. كل موقع قابل للوصول تقوم بإنشائه يجعل الإنترنت مكانًا أكثر ترحيبًا للجميع. هذا أمر مذهل حقًا عندما تفكر فيه!

## موارد إضافية

واصل رحلتك التعليمية في إمكانية الوصول باستخدام هذه الموارد الأساسية:

**📚 المعايير والإرشادات الرسمية:**
- [إرشادات WCAG 2.1](https://www.w3.org/WAI/WCAG21/quickref/) - المعيار الرسمي لإمكانية الوصول مع مرجع سريع
- [دليل ممارسات تأليف ARIA](https://w3c.github.io/aria-practices/) - أنماط شاملة لعناصر واجهة تفاعلية
- [إرشادات WebAIM](https://webaim.org/) - إرشادات عملية وسهلة للمبتدئين حول إمكانية الوصول

**🛠️ أدوات وموارد الاختبار:**
- [axe DevTools](https://www.deque.com/axe/devtools/) - أداة اختبار إمكانية الوصول القياسية في الصناعة
- [قائمة التحقق من مشروع A11y](https://www.a11yproject.com/checklist/) - تحقق خطوة بخطوة من إمكانية الوصول
- [Accessibility Insights](https://accessibilityinsights.io/) - مجموعة اختبار شاملة من Microsoft
- [Color Oracle](https://colororacle.org/) - محاكي عمى الألوان لاختبار التصميم

**🎓 التعلم والمجتمع:**
- [استطلاع قارئ الشاشة WebAIM](https://webaim.org/projects/screenreadersurvey9/) - تفضيلات وسلوكيات المستخدمين الحقيقيين
- [مكونات شاملة](https://inclusive-components.design/) - أنماط مكونات حديثة قابلة للوصول
- [A11y Coffee](https://a11y.coffee/) - نصائح ورؤى سريعة حول إمكانية الوصول
- [مبادرة إمكانية الوصول إلى الويب (WAI)](https://www.w3.org/WAI/) - موارد شاملة لإمكانية الوصول من W3C

**🎥 التعلم العملي:**
- [دليل مطور إمكانية الوصول](https://www.accessibility-developer-guide.com/) - إرشادات عملية للتنفيذ
- [جامعة Deque](https://dequeuniversity.com/) - دورات تدريبية احترافية حول إمكانية الوصول

## تحدي GitHub Copilot Agent 🚀

استخدم وضع الوكيل لإكمال التحدي التالي:

**الوصف:** قم بإنشاء مكون نافذة منبثقة قابلة للوصول توضح إدارة التركيز المناسبة، سمات ARIA، وأنماط التنقل باستخدام لوحة المفاتيح.

**المهمة:** قم ببناء مكون نافذة منبثقة كاملة باستخدام HTML، CSS، وJavaScript يتضمن: حصر التركيز بشكل صحيح، مفتاح ESC للإغلاق، النقر خارج النافذة للإغلاق، سمات ARIA لقارئات الشاشة، ومؤشرات تركيز مرئية. يجب أن تحتوي النافذة على نموذج مع تسميات مناسبة ومعالجة الأخطاء. تأكد من أن المكون يفي بمعايير WCAG 2.1 AA.

## 🚀 التحدي

خذ هذا HTML وأعد كتابته ليكون قابلاً للوصول قدر الإمكان، بناءً على الاستراتيجيات التي تعلمتها.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Turtle Ipsum - The World's Premier Turtle Fan Club</title>
    <link href='../assets/style.css' rel='stylesheet' type='text/css'>
  </head>
  <body>
    <header class="site-header">
      <h1 class="site-title">Turtle Ipsum</h1>
      <p class="site-subtitle">The World's Premier Turtle Fan Club</p>
    </header>
    
    <nav class="main-nav" aria-label="Main navigation">
      <h2 class="nav-header">Resources</h2>
      <ul class="nav-list">
        <li><a href="https://www.youtube.com/watch?v=CMNry4PE93Y">"I like turtles" video</a></li>
        <li><a href="https://en.wikipedia.org/wiki/Turtle">Basic turtle information</a></li>
        <li><a href="https://en.wikipedia.org/wiki/Turtles_(chocolate)">Chocolate turtles candy</a></li>
      </ul>
    </nav>
    
    <main class="main-content">
      <article>
        <h1>Welcome to Turtle Ipsum</h1>
        <p class="intro">
          <a href="/about">Learn more about our turtle community</a> and discover fascinating facts about these amazing creatures.
        </p>
        <p class="article-text">
          Turtle ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
        </p>
      </article>
    </main>
    
    <footer class="footer">
      <section class="newsletter-signup">
        <h2>Stay Updated</h2>
        <button type="button" onclick="showNewsletterForm()">Sign up for turtle news</button>
      </section>
      
      <nav class="footer-nav" aria-label="Footer navigation">
        <h2>Site Pages</h2>
        <ul>
          <li><a href="../">Home</a></li>
          <li><a href="../semantic">Semantic HTML example</a></li>
        </ul>
      </nav>
      
      <p class="footer-copyright">&copy; 2024 Instrument. All rights reserved.</p>
    </footer>
  </body>
</html>
```

**التحسينات الرئيسية التي تم إجراؤها:**
- إضافة هيكل HTML دلالي مناسب
- إصلاح تسلسل العناوين (عنوان h1 واحد، تقدم منطقي)
- استبدال نصوص الروابط بمعنى بدلاً من "اضغط هنا"
- تضمين تسميات ARIA المناسبة للتنقل
- إضافة سمة lang وعلامات meta المناسبة
- استخدام عنصر الزر للعناصر التفاعلية
- هيكلة محتوى التذييل بمعالم مناسبة

## اختبار ما بعد المحاضرة
[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/en/)

## المراجعة والدراسة الذاتية

لدى العديد من الحكومات قوانين بشأن متطلبات إمكانية الوصول. اقرأ عن قوانين إمكانية الوصول في بلدك. ما الذي يتم تغطيته، وما الذي لا يتم تغطيته؟ مثال على ذلك [هذا الموقع الحكومي](https://accessibility.blog.gov.uk/).

## المهمة

[تحليل موقع ويب غير قابل للوصول](assignment.md)

الحقوق: [Turtle Ipsum](https://github.com/Instrument/semantic-html-sample) بواسطة Instrument

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.