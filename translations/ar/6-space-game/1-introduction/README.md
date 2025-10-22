<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T14:27:55+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ar"
}
-->
# بناء لعبة فضاء الجزء الأول: المقدمة

![رسوم متحركة للعبة الفضاء تظهر طريقة اللعب](../../../../6-space-game/images/pewpew.gif)

تمامًا كما تنسق وحدة التحكم في مهام ناسا بين أنظمة متعددة أثناء إطلاق الفضاء، سنقوم ببناء لعبة فضاء تُظهر كيف يمكن لأجزاء مختلفة من البرنامج أن تعمل معًا بسلاسة. أثناء إنشاء شيء يمكنك فعلاً اللعب به، ستتعلم مفاهيم البرمجة الأساسية التي تنطبق على أي مشروع برمجي.

سنستكشف نهجين أساسيين لتنظيم الكود: الوراثة والتركيب. هذه ليست مجرد مفاهيم أكاديمية – إنها نفس الأنماط التي تدعم كل شيء من ألعاب الفيديو إلى أنظمة البنوك. سنقوم أيضًا بتنفيذ نظام اتصال يسمى pub/sub يعمل مثل شبكات الاتصال المستخدمة في المركبات الفضائية، مما يسمح للمكونات المختلفة بمشاركة المعلومات دون إنشاء تبعيات.

بنهاية هذه السلسلة، ستفهم كيفية بناء تطبيقات يمكنها التوسع والتطور – سواء كنت تطور ألعابًا، تطبيقات ويب، أو أي نظام برمجي آخر.

## اختبار ما قبل المحاضرة

[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/29)

## الوراثة والتركيب في تطوير الألعاب

مع نمو المشاريع في التعقيد، يصبح تنظيم الكود أمرًا بالغ الأهمية. ما يبدأ كبرنامج بسيط يمكن أن يصبح صعب الصيانة بدون هيكل مناسب – تمامًا كما تطلبت مهام أبولو تنسيقًا دقيقًا بين آلاف المكونات.

سنستكشف نهجين أساسيين لتنظيم الكود: الوراثة والتركيب. لكل منهما مزايا مميزة، وفهم كلاهما يساعدك على اختيار النهج المناسب لمواقف مختلفة. سنوضح هذه المفاهيم من خلال لعبة الفضاء الخاصة بنا، حيث يجب أن يتفاعل الأبطال، الأعداء، التعزيزات، والأشياء الأخرى بكفاءة.

✅ أحد أشهر كتب البرمجة على الإطلاق يتعلق بـ [أنماط التصميم](https://en.wikipedia.org/wiki/Design_Patterns).

في أي لعبة، لديك `كائنات اللعبة` – العناصر التفاعلية التي تملأ عالم اللعبة. الأبطال، الأعداء، التعزيزات، والتأثيرات البصرية كلها كائنات لعبة. كل منها موجود في إحداثيات شاشة محددة باستخدام قيم `x` و `y`، مشابهة لتحديد النقاط على مستوى إحداثي.

على الرغم من اختلافاتها البصرية، غالبًا ما تشترك هذه الكائنات في سلوكيات أساسية:

- **توجد في مكان ما** – كل كائن لديه إحداثيات x و y حتى تعرف اللعبة مكان رسمه
- **يمكن للكثير منها التحرك** – الأبطال يركضون، الأعداء يطاردون، الرصاص يطير عبر الشاشة
- **لديها عمر محدد** – بعضها يبقى للأبد، والبعض الآخر (مثل الانفجارات) يظهر لفترة وجيزة ويختفي
- **تتفاعل مع الأشياء** – عندما تصطدم الأشياء، يتم جمع التعزيزات، يتم تحديث شريط الصحة

✅ فكر في لعبة مثل Pac-Man. هل يمكنك تحديد الأنواع الأربعة من الكائنات المذكورة أعلاه في هذه اللعبة؟

### التعبير عن السلوك من خلال الكود

الآن بعد أن فهمت السلوكيات المشتركة التي تشترك فيها كائنات اللعبة، دعنا نستكشف كيفية تنفيذ هذه السلوكيات في JavaScript. يمكنك التعبير عن سلوك الكائن من خلال طرق مرتبطة بالفئات أو الكائنات الفردية، وهناك عدة طرق للاختيار من بينها.

**النهج القائم على الفئات**

توفر الفئات والوراثة نهجًا منظمًا لتنظيم كائنات اللعبة. مثل نظام التصنيف الذي طوره كارل لينيوس، تبدأ بفئة أساسية تحتوي على الخصائص المشتركة، ثم تنشئ فئات متخصصة ترث هذه الأساسيات مع إضافة قدرات محددة.

✅ الوراثة مفهوم مهم لفهمه. تعرف على المزيد في [مقالة MDN حول الوراثة](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

إليك كيفية تنفيذ كائنات اللعبة باستخدام الفئات والوراثة:

```javascript
// Step 1: Create the base GameObject class
class GameObject {
  constructor(x, y, type) {
    this.x = x;
    this.y = y;
    this.type = type;
  }
}
```

**لنقم بتفصيل هذا خطوة بخطوة:**
- نحن ننشئ قالبًا أساسيًا يمكن لكل كائن لعبة استخدامه
- يقوم المُنشئ بحفظ مكان وجود الكائن (`x`, `y`) ونوعه
- يصبح هذا الأساس الذي ستبني عليه جميع كائنات اللعبة الخاصة بك

```javascript
// Step 2: Add movement capability through inheritance
class Movable extends GameObject {
  constructor(x, y, type) {
    super(x, y, type); // Call parent constructor
  }

  // Add the ability to move to a new position
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}
```

**في المثال أعلاه، قمنا بـ:**
- **تمديد** فئة GameObject لإضافة وظيفة الحركة
- **استدعاء** المُنشئ الرئيسي باستخدام `super()` لتهيئة الخصائص الموروثة
- **إضافة** طريقة `moveTo()` التي تقوم بتحديث موقع الكائن

```javascript
// Step 3: Create specific game object types
class Hero extends Movable {
  constructor(x, y) {
    super(x, y, 'Hero'); // Set type automatically
  }
}

class Tree extends GameObject {
  constructor(x, y) {
    super(x, y, 'Tree'); // Trees don't need movement
  }
}

// Step 4: Use your game objects
const hero = new Hero(0, 0);
hero.moveTo(5, 5); // Hero can move!

const tree = new Tree(10, 15);
// tree.moveTo() would cause an error - trees can't move
```

**فهم هذه المفاهيم:**
- **إنشاء** أنواع كائنات متخصصة ترث السلوكيات المناسبة
- **إظهار** كيف تسمح الوراثة بتضمين الميزات بشكل انتقائي
- **توضيح** أن الأبطال يمكنهم التحرك بينما تبقى الأشجار ثابتة
- **إظهار** كيف تمنع التسلسل الهرمي للفئات الإجراءات غير المناسبة

✅ خذ بضع دقائق لإعادة تصور بطل Pac-Man (مثل Inky، Pinky أو Blinky) وكيف يمكن كتابته في JavaScript.

**نهج التركيب**

يتبع التركيب فلسفة التصميم المعيارية، مشابهة لكيفية تصميم المهندسين للمركبات الفضائية بمكونات قابلة للتبديل. بدلاً من الوراثة من فئة رئيسية، تقوم بدمج سلوكيات محددة لإنشاء كائنات تحتوي على الوظائف التي تحتاجها بالضبط. يوفر هذا النهج مرونة دون قيود هرمية صارمة.

```javascript
// Step 1: Create base behavior objects
const gameObject = {
  x: 0,
  y: 0,
  type: ''
};

const movable = {
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
};
```

**إليك ما يفعله هذا الكود:**
- **تعريف** كائن لعبة أساسي مع خصائص الموقع والنوع
- **إنشاء** كائن سلوك منفصل قابل للحركة مع وظيفة الحركة
- **فصل** الاهتمامات من خلال الحفاظ على بيانات الموقع ومنطق الحركة مستقلين

```javascript
// Step 2: Compose objects by combining behaviors
const movableObject = { ...gameObject, ...movable };

// Step 3: Create factory functions for different object types
function createHero(x, y) {
  return {
    ...movableObject,
    x,
    y,
    type: 'Hero'
  };
}

function createStatic(x, y, type) {
  return {
    ...gameObject,
    x,
    y,
    type
  };
}
```

**في المثال أعلاه، قمنا بـ:**
- **دمج** خصائص الكائن الأساسي مع سلوك الحركة باستخدام بناء الجملة المنتشر
- **إنشاء** وظائف المصنع التي تعيد كائنات مخصصة
- **تمكين** إنشاء كائنات مرنة دون تسلسل هرمي صارم للفئات
- **السماح** للكائنات بالحصول على السلوكيات التي تحتاجها بالضبط

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**نقاط رئيسية يجب تذكرها:**
- **تكوين** الكائنات من خلال مزج السلوكيات بدلاً من وراثتها
- **توفير** مرونة أكثر من التسلسل الهرمي الصارم للوراثة
- **السماح** للكائنات بالحصول على الميزات التي تحتاجها بالضبط
- **استخدام** بناء الجملة المنتشر الحديث في JavaScript لتجميع الكائنات بشكل نظيف

```

**Which Pattern Should You Choose?**

> 💡 **Pro Tip**: Both patterns have their place in modern JavaScript development. Classes work well for clearly defined hierarchies, while composition shines when you need maximum flexibility.
> 
**Here's when to use each approach:**
- **Choose** inheritance when you have clear "is-a" relationships (a Hero *is-a* Movable object)
- **Select** composition when you need "has-a" relationships (a Hero *has* movement abilities)
- **Consider** your team's preferences and project requirements
- **Remember** that you can mix both approaches in the same application

## Communication Patterns: The Pub/Sub System

As applications grow complex, managing communication between components becomes challenging. The publish-subscribe pattern (pub/sub) solves this problem using principles similar to radio broadcasting – one transmitter can reach multiple receivers without knowing who's listening.

Consider what happens when a hero takes damage: the health bar updates, sound effects play, visual feedback appears. Rather than coupling the hero object directly to these systems, pub/sub allows the hero to broadcast a "damage taken" message. Any system that needs to respond can subscribe to this message type and react accordingly.

✅ **Pub/Sub** stands for 'publish-subscribe'

### Understanding the Pub/Sub Architecture

The pub/sub pattern keeps different parts of your application loosely coupled, meaning they can work together without being directly dependent on each other. This separation makes your code more maintainable, testable, and flexible to changes.

**The key players in pub/sub:**
- **Messages** – Simple text labels like `'PLAYER_SCORED'` that describe what happened (plus any extra info)
- **Publishers** – The objects that shout out "Something happened!" to anyone who's listening
- **Subscribers** – The objects that say "I care about that event" and react when it happens
- **Event System** – The middleman that makes sure messages get to the right listeners

### Building an Event System

Let's create a simple but powerful event system that demonstrates these concepts:

```javascript
// Step 1: Create the EventEmitter class
class EventEmitter {
  constructor() {
    this.listeners = {}; // Store all event listeners
  }
  
  // Register a listener for a specific message type
  on(message, listener) {
    if (!this.listeners[message]) {
      this.listeners[message] = [];
    }
    this.listeners[message].push(listener);
  }
  
  // Send a message to all registered listeners
  emit(message, payload = null) {
    if (this.listeners[message]) {
      this.listeners[message].forEach(listener => {
        listener(message, payload);
      });
    }
  }
}
```

**تفصيل ما يحدث هنا:**
- **إنشاء** نظام إدارة أحداث مركزي باستخدام فئة بسيطة
- **تخزين** المستمعين في كائن منظم حسب نوع الرسالة
- **تسجيل** مستمعين جدد باستخدام طريقة `on()`
- **إرسال** الرسائل إلى جميع المستمعين المهتمين باستخدام `emit()`
- **دعم** حمولات بيانات اختيارية لتمرير المعلومات ذات الصلة

### جمع كل شيء معًا: مثال عملي

حسنًا، دعنا نرى هذا عمليًا! سنقوم ببناء نظام حركة بسيط يظهر كيف يمكن أن يكون pub/sub نظيفًا ومرنًا:

```javascript
// Step 1: Define your message types
const Messages = {
  HERO_MOVE_LEFT: 'HERO_MOVE_LEFT',
  HERO_MOVE_RIGHT: 'HERO_MOVE_RIGHT',
  ENEMY_SPOTTED: 'ENEMY_SPOTTED'
};

// Step 2: Create your event system and game objects
const eventEmitter = new EventEmitter();
const hero = createHero(0, 0);
```

**إليك ما يفعله هذا الكود:**
- **تعريف** كائن ثابت لمنع الأخطاء الإملائية في أسماء الرسائل
- **إنشاء** مثيل لمُرسل الأحداث للتعامل مع جميع الاتصالات
- **تهيئة** كائن البطل في الموقع الابتدائي

```javascript
// Step 3: Set up event listeners (subscribers)
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.moveTo(hero.x - 5, hero.y);
  console.log(`Hero moved to position: ${hero.x}, ${hero.y}`);
});

eventEmitter.on(Messages.HERO_MOVE_RIGHT, () => {
  hero.moveTo(hero.x + 5, hero.y);
  console.log(`Hero moved to position: ${hero.x}, ${hero.y}`);
});
```

**في المثال أعلاه، قمنا بـ:**
- **تسجيل** مستمعي الأحداث الذين يستجيبون لرسائل الحركة
- **تحديث** موقع البطل بناءً على اتجاه الحركة
- **إضافة** تسجيل في وحدة التحكم لتتبع تغييرات موقع البطل
- **فصل** منطق الحركة عن معالجة الإدخال

```javascript
// Step 4: Connect keyboard input to events (publishers)
window.addEventListener('keydown', (event) => {
  switch(event.key) {
    case 'ArrowLeft':
      eventEmitter.emit(Messages.HERO_MOVE_LEFT);
      break;
    case 'ArrowRight':
      eventEmitter.emit(Messages.HERO_MOVE_RIGHT);
      break;
  }
});
```

**فهم هذه المفاهيم:**
- **ربط** إدخال لوحة المفاتيح بأحداث اللعبة دون اقتران وثيق
- **تمكين** نظام الإدخال من التواصل مع كائنات اللعبة بشكل غير مباشر
- **السماح** لأنظمة متعددة بالاستجابة لنفس أحداث لوحة المفاتيح
- **تسهيل** تغيير روابط المفاتيح أو إضافة طرق إدخال جديدة

> 💡 **نصيحة احترافية**: جمال هذا النمط هو المرونة! يمكنك بسهولة إضافة تأثيرات صوتية، اهتزاز الشاشة، أو تأثيرات الجسيمات ببساطة عن طريق إضافة المزيد من مستمعي الأحداث – لا حاجة لتعديل كود لوحة المفاتيح أو الحركة الحالي.
> 
**إليك لماذا ستحب هذا النهج:**
- يصبح إضافة ميزات جديدة أمرًا سهلاً للغاية – فقط استمع للأحداث التي تهمك
- يمكن لأشياء متعددة أن تتفاعل مع نفس الحدث دون التداخل مع بعضها البعض
- يصبح الاختبار أسهل بكثير لأن كل جزء يعمل بشكل مستقل
- عندما يحدث خطأ ما، تعرف بالضبط أين تبحث

### لماذا يتوسع Pub/Sub بشكل فعال

يحافظ نمط pub/sub على البساطة مع نمو التطبيقات في التعقيد. سواء كان إدارة عشرات الأعداء، تحديثات واجهة المستخدم الديناميكية، أو أنظمة الصوت، يتعامل النمط مع زيادة الحجم دون تغييرات معمارية. تتكامل الميزات الجديدة مع نظام الأحداث الحالي دون التأثير على الوظائف القائمة.

> ⚠️ **خطأ شائع**: لا تنشئ أنواع رسائل محددة جدًا في وقت مبكر. ابدأ بفئات واسعة وقم بتحسينها مع وضوح احتياجات لعبتك.
> 
**أفضل الممارسات التي يجب اتباعها:**
- **تجميع** الرسائل ذات الصلة في فئات منطقية
- **استخدام** أسماء وصفية تشير بوضوح إلى ما حدث
- **الحفاظ** على حمولات الرسائل بسيطة ومركزة
- **توثيق** أنواع الرسائل للتعاون بين الفريق

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع Agent لإكمال التحدي التالي:

**الوصف:** قم بإنشاء نظام كائن لعبة بسيط باستخدام كل من الوراثة ونمط pub/sub. ستقوم بتنفيذ لعبة أساسية حيث يمكن للكائنات المختلفة التواصل من خلال الأحداث دون معرفة مباشرة ببعضها البعض.

**المهمة:** قم بإنشاء نظام لعبة JavaScript مع المتطلبات التالية: 1) إنشاء فئة GameObject الأساسية مع إحداثيات x و y وخصائص النوع. 2) إنشاء فئة Hero التي تمد GameObject ويمكنها التحرك. 3) إنشاء فئة Enemy التي تمد GameObject ويمكنها مطاردة البطل. 4) تنفيذ فئة EventEmitter لنمط pub/sub. 5) إعداد مستمعي الأحداث بحيث عندما يتحرك البطل، يتلقى الأعداء القريبون حدث 'HERO_MOVED' ويحدثون موقعهم للتحرك نحو البطل. قم بتضمين عبارات console.log لإظهار التواصل بين الكائنات.

تعرف على المزيد حول [وضع الوكيل](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) هنا.

## 🚀 التحدي

فكر في كيفية تحسين نمط pub-sub لهندسة اللعبة. حدد أي المكونات يجب أن ترسل الأحداث وكيف يجب أن يستجيب النظام. صمم مفهوم لعبة ورسم أنماط الاتصال بين مكوناتها.

## اختبار ما بعد المحاضرة

[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/30)

## المراجعة والدراسة الذاتية

تعرف على المزيد حول Pub/Sub من خلال [قراءة المزيد عنه](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## الواجب

[تصميم لعبة](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.