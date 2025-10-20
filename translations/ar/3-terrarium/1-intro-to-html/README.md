<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "f6235d42b9e6862267e92c53f1be2655",
  "translation_date": "2025-10-20T20:36:30+00:00",
  "source_file": "3-terrarium/1-intro-to-html/README.md",
  "language_code": "ar"
}
-->
# مشروع التيراريوم الجزء الأول: مقدمة إلى HTML

![مقدمة إلى HTML](../../../../translated_images/webdev101-html.4389c2067af68e98280c1bde52b6c6269f399eaae3659b7c846018d8a7b0bbd9.ar.png)
> رسم توضيحي بواسطة [Tomomi Imura](https://twitter.com/girlie_mac)

## اختبار ما قبل المحاضرة

[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/15)

> شاهد الفيديو

> 
> [![فيديو أساسيات Git و GitHub](https://img.youtube.com/vi/1TvxJKBzhyQ/0.jpg)](https://www.youtube.com/watch?v=1TvxJKBzhyQ)

### المقدمة

HTML، أو لغة ترميز النص التشعبي، هي "الهيكل العظمي" للويب. إذا كانت CSS "تزين" HTML و JavaScript تضيف الحياة إليه، فإن HTML هو جسم تطبيق الويب الخاص بك. حتى أن صياغة HTML تعكس هذه الفكرة، حيث تتضمن علامات "head"، "body"، و "footer".

في هذه الدرس، سنستخدم HTML لتصميم "الهيكل العظمي" لواجهة التيراريوم الافتراضية الخاصة بنا. ستحتوي على عنوان وثلاثة أعمدة: عمود على اليمين وآخر على اليسار حيث تعيش النباتات القابلة للسحب، ومنطقة مركزية ستكون التيراريوم الزجاجي. بنهاية هذا الدرس، ستتمكن من رؤية النباتات في الأعمدة، ولكن ستبدو الواجهة غريبة بعض الشيء؛ لا تقلق، في القسم التالي ستضيف أنماط CSS لتحسين مظهر الواجهة.

### المهمة

على جهاز الكمبيوتر الخاص بك، قم بإنشاء مجلد يسمى "terrarium" وداخله ملف يسمى "index.html". يمكنك القيام بذلك في Visual Studio Code بعد إنشاء مجلد التيراريوم الخاص بك عن طريق فتح نافذة جديدة من VS Code، والنقر على "فتح مجلد"، والانتقال إلى المجلد الجديد. انقر على زر "ملف" الصغير في لوحة المستكشف وقم بإنشاء الملف الجديد:

![المستكشف في VS Code](../../../../translated_images/vs-code-index.e2986cf919471eb984a0afef231380c8b132b000635105f2397bd2754d1b689c.ar.png)

أو

استخدم هذه الأوامر في Git Bash:
* `mkdir terrarium`
* `cd terrarium`
* `touch index.html`
* `code index.html` أو `nano index.html`

> ملفات index.html تشير إلى المتصفح بأنها الملف الافتراضي في المجلد؛ قد يتم بناء عناوين URL مثل `https://anysite.com/test` باستخدام هيكل مجلد يتضمن مجلدًا يسمى `test` بداخله ملف `index.html`; لا يجب أن يظهر `index.html` في عنوان URL.

---

## نوع المستند وعلامات html

السطر الأول من ملف HTML هو نوع المستند الخاص به. من المدهش قليلاً أنك بحاجة إلى وضع هذا السطر في أعلى الملف، ولكنه يخبر المتصفحات القديمة بأن الصفحة يجب أن تُعرض في وضع قياسي، وفقًا لمواصفات HTML الحالية.

> نصيحة: في VS Code، يمكنك تمرير المؤشر فوق العلامة للحصول على معلومات حول استخدامها من أدلة مرجعية MDN.

السطر الثاني يجب أن يكون علامة الفتح `<html>`، متبوعة الآن بعلامة الإغلاق الخاصة بها `</html>`. هذه العلامات هي العناصر الجذرية لواجهتك.

### المهمة

أضف هذه السطور في أعلى ملف `index.html` الخاص بك:

```HTML
<!DOCTYPE html>
<html></html>
```

✅ هناك أوضاع مختلفة يمكن تحديدها عن طريق تعيين نوع المستند باستخدام سلسلة استعلام: [وضع الشذوذ ووضع المعايير](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode). كانت هذه الأوضاع تدعم المتصفحات القديمة جدًا التي لا تُستخدم عادةً في الوقت الحاضر (مثل Netscape Navigator 4 و Internet Explorer 5). يمكنك الالتزام بإعلان نوع المستند القياسي.

---

## 'الرأس' في المستند

منطقة 'الرأس' في مستند HTML تتضمن معلومات حيوية حول صفحة الويب الخاصة بك، والمعروفة أيضًا باسم [البيانات الوصفية](https://developer.mozilla.org/docs/Web/HTML/Element/meta). في حالتنا، نخبر خادم الويب الذي سيتم إرسال هذه الصفحة إليه ليتم عرضها، هذه الأشياء الأربعة:

-   عنوان الصفحة
-   بيانات وصفية للصفحة تشمل:
    -   'مجموعة الأحرف'، التي تخبر عن نوع ترميز الأحرف المستخدم في الصفحة
    -   معلومات المتصفح، بما في ذلك `x-ua-compatible` التي تشير إلى دعم متصفح IE=edge
    -   معلومات حول كيفية تصرف نافذة العرض عند تحميلها. تعيين نافذة العرض لتكون بمقياس أولي 1 يتحكم في مستوى التكبير عند تحميل الصفحة لأول مرة.

### المهمة

أضف كتلة 'الرأس' إلى مستندك بين علامات الفتح والإغلاق `<html>`.

```html
<head>
	<title>Welcome to my Virtual Terrarium</title>
	<meta charset="utf-8" />
	<meta http-equiv="X-UA-Compatible" content="IE=edge" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
</head>
```

✅ ماذا سيحدث إذا قمت بتعيين علامة نافذة العرض مثل هذه: `<meta name="viewport" content="width=600">`؟ اقرأ المزيد عن [نافذة العرض](https://developer.mozilla.org/docs/Web/HTML/Viewport_meta_tag).

---

## 'الجسم' في المستند

### علامات HTML

في HTML، تضيف علامات إلى ملف .html الخاص بك لإنشاء عناصر صفحة ويب. عادةً ما تحتوي كل علامة على علامة فتح وعلامة إغلاق، مثل: `<p>hello</p>` للإشارة إلى فقرة. قم بإنشاء جسم واجهتك عن طريق إضافة مجموعة من علامات `<body>` داخل زوج علامات `<html>`؛ الآن يبدو الترميز الخاص بك كالتالي:

### المهمة

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Welcome to my Virtual Terrarium</title>
		<meta charset="utf-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
	</head>
	<body></body>
</html>
```

الآن، يمكنك البدء في بناء صفحتك. عادةً، تستخدم علامات `<div>` لإنشاء العناصر المنفصلة في الصفحة. سنقوم بإنشاء سلسلة من عناصر `<div>` التي ستحتوي على صور.

### الصور

إحدى علامات HTML التي لا تحتاج إلى علامة إغلاق هي علامة `<img>`، لأنها تحتوي على عنصر `src` الذي يحتوي على جميع المعلومات التي تحتاجها الصفحة لعرض العنصر.

قم بإنشاء مجلد في تطبيقك يسمى `images` وأضف فيه جميع الصور الموجودة في [مجلد كود المصدر](../../../../3-terrarium/solution/images); (هناك 14 صورة للنباتات).

### المهمة

أضف صور النباتات تلك إلى عمودين بين علامات `<body></body>`:

```html
<div id="page">
	<div id="left-container" class="container">
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant1" src="../../../../translated_images/plant1.d87946a2ca70cc4316bda6e6c3af7210fbe9ada5539a7885141a9ce0efaf7be3.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant2" src="../../../../translated_images/plant2.8daa1606c9c1ad896bb171212c7d1d882e504b76b8ec3a2d1c337d775cf50dc3.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant3" src="../../../../translated_images/plant3.8b0d484381a2a2a77c5c06ad97ab6ae5b7023da8c6c7678b0183bc0e46ea17a7.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant4" src="../../../../translated_images/plant4.656e16ae1df37be2af5f4e7b5ab6c5decc432c3d3ec2eb98b904ddbecad49db0.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant5" src="../../../../translated_images/plant5.2b41b9355f11ebccd62d327f5f14e56531ecda9c6f970bc89e386ee9f0273bb0.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant6" src="../../../../translated_images/plant6.3d1827d03b6569946be13ae5da1f32947ae56732638a43757a7c616a6adccc5d.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant7" src="../../../../translated_images/plant7.8152c302ac97f621a6c595bdf3939103568f9efc7d3b06a0f02a1ea66f479de0.ar.png" />
		</div>
	</div>
	<div id="right-container" class="container">
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant8" src="../../../../translated_images/plant8.38d6428174ffa850a47cd1b81d528fa528adda7d23f3ae0bb42f4a27356ca5e6.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant9" src="../../../../translated_images/plant9.f0e38d3327c37fc29cd2734d48d20c2cf69300898ece6d46708829e02ce540e3.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant10" src="../../../../translated_images/plant10.b159d6d6e985595f56d86b4b38061b8e7b4c9969c210c199fe967269cf935e7f.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant11" src="../../../../translated_images/plant11.2a03a1c2ec8ea84ef3a80c06cc6883f3960fbb669f2c0b0bd824ba33d7eb7d32.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant12" src="../../../../translated_images/plant12.60e9b53e538fbaf3e5797ebf800acb483baf5639e6cf378292ac2321ab8a5ea9.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant13" src="../../../../translated_images/plant13.07a51543c820bcf57f67a9a6c0acbd6211ff795e2e67a42a9718224534e95fab.ar.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant14" src="../../../../translated_images/plant14.6e486371ba7d36ba3520d9828887993cb4c3edad8bdd8ff9b1b315717ff8cb63.ar.png" />
		</div>
	</div>
</div>
```

> ملاحظة: الفرق بين Spans و Divs. تعتبر Divs عناصر 'كتلة'، بينما Spans تعتبر 'خطية'. ماذا سيحدث إذا قمت بتحويل هذه الـ Divs إلى Spans؟

مع هذا الترميز، تظهر النباتات الآن على الشاشة. يبدو الأمر سيئًا، لأنهم لم يتم تنسيقهم بعد باستخدام CSS، وسنقوم بذلك في الدرس التالي.

كل صورة تحتوي على نص بديل يظهر حتى إذا لم تتمكن من رؤية الصورة أو عرضها. هذه خاصية مهمة يجب تضمينها لضمان الوصول. تعرف على المزيد حول الوصول في الدروس المستقبلية؛ في الوقت الحالي، تذكر أن خاصية alt توفر معلومات بديلة للصورة إذا لم يتمكن المستخدم من رؤيتها لأي سبب (بسبب اتصال بطيء، خطأ في خاصية src، أو إذا كان المستخدم يستخدم قارئ الشاشة).

✅ هل لاحظت أن كل صورة تحتوي على نفس النص البديل؟ هل هذا ممارسة جيدة؟ لماذا أو لماذا لا؟ هل يمكنك تحسين هذا الكود؟

---

## الترميز الدلالي

بشكل عام، من الأفضل استخدام 'الدلالات' ذات المعنى عند كتابة HTML. ماذا يعني ذلك؟ يعني أنك تستخدم علامات HTML لتمثيل نوع البيانات أو التفاعل الذي تم تصميمها من أجله. على سبيل المثال، النص الرئيسي في الصفحة يجب أن يستخدم علامة `<h1>`.

أضف السطر التالي مباشرةً أسفل علامة الفتح `<body>`:

```html
<h1>My Terrarium</h1>
```

استخدام الترميز الدلالي مثل وجود العناوين كـ `<h1>` والقوائم غير المرتبة كـ `<ul>` يساعد قارئات الشاشة على التنقل عبر الصفحة. بشكل عام، يجب كتابة الأزرار كـ `<button>` والقوائم كـ `<li>`. بينما من الممكن استخدام عناصر `<span>` ذات أنماط خاصة مع معالجات النقر لتقليد الأزرار، من الأفضل للمستخدمين ذوي الإعاقة استخدام تقنيات لتحديد مكان الزر في الصفحة والتفاعل معه، إذا ظهر العنصر كزر. لهذا السبب، حاول استخدام الترميز الدلالي قدر الإمكان.

✅ ألقِ نظرة على قارئ الشاشة و[كيف يتفاعل مع صفحة ويب](https://www.youtube.com/watch?v=OUDV1gqs9GA). هل ترى لماذا قد يسبب الترميز غير الدلالي إحباطًا للمستخدم؟

## التيراريوم

الجزء الأخير من هذه الواجهة يتضمن إنشاء ترميز سيتم تنسيقه لإنشاء تيراريوم.

### المهمة:

أضف هذا الترميز فوق علامة `</div>` الأخيرة:

```html
<div id="terrarium">
	<div class="jar-top"></div>
	<div class="jar-walls">
		<div class="jar-glossy-long"></div>
		<div class="jar-glossy-short"></div>
	</div>
	<div class="dirt"></div>
	<div class="jar-bottom"></div>
</div>
```

✅ على الرغم من أنك أضفت هذا الترميز إلى الشاشة، إلا أنك لا ترى أي شيء يتم عرضه. لماذا؟

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع الوكيل لإكمال التحدي التالي:

**الوصف:** قم بإنشاء هيكل HTML دلالي لقسم دليل العناية بالنباتات الذي يمكن إضافته إلى مشروع التيراريوم.

**الموجه:** قم بإنشاء قسم HTML دلالي يتضمن عنوانًا رئيسيًا "دليل العناية بالنباتات"، وثلاثة أقسام فرعية بعناوين "الري"، "متطلبات الضوء"، و"العناية بالتربة"، يحتوي كل منها على فقرة من معلومات العناية بالنباتات. استخدم علامات HTML الدلالية المناسبة مثل `<section>`، `<h2>`، `<h3>`، و `<p>` لتنظيم المحتوى بشكل صحيح.

## 🚀التحدي

هناك بعض العلامات 'القديمة' في HTML التي لا تزال ممتعة للتجربة، على الرغم من أنه لا يجب استخدام العلامات المهملة مثل [هذه العلامات](https://developer.mozilla.org/docs/Web/HTML/Element#Obsolete_and_deprecated_elements) في الترميز الخاص بك. مع ذلك، هل يمكنك استخدام العلامة القديمة `<marquee>` لجعل عنوان h1 يتحرك أفقيًا؟ (إذا فعلت ذلك، لا تنسَ إزالته بعد ذلك)

## اختبار ما بعد المحاضرة

[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/16)

## المراجعة والدراسة الذاتية

HTML هو نظام بناء 'مجرب وصحيح' ساعد في بناء الويب إلى ما هو عليه اليوم. تعرف قليلاً على تاريخه من خلال دراسة بعض العلامات القديمة والجديدة. هل يمكنك معرفة لماذا تم إهمال بعض العلامات وإضافة أخرى؟ ما العلامات التي قد يتم تقديمها في المستقبل؟

تعرف على المزيد حول بناء المواقع للويب والأجهزة المحمولة في [Microsoft Learn](https://docs.microsoft.com/learn/modules/build-simple-website/?WT.mc_id=academic-77807-sagibbon).

## الواجب

[تمرن على HTML: قم ببناء نموذج مدونة](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.