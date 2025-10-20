<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "38777f8c81874368d3b4b9b8a54aa242",
  "translation_date": "2025-10-20T20:40:00+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ar"
}
-->
# بناء لعبة فضاء الجزء الأول: المقدمة

![video](../../../../6-space-game/images/pewpew.gif)

## اختبار ما قبل المحاضرة

[اختبار ما قبل المحاضرة](https://ff-quizzes.netlify.app/web/quiz/29)

### الوراثة والتركيب في تطوير الألعاب

في الدروس السابقة، لم يكن هناك حاجة كبيرة للقلق بشأن تصميم هيكل التطبيقات التي قمت ببنائها، حيث كانت المشاريع صغيرة النطاق. ومع ذلك، عندما تنمو تطبيقاتك في الحجم والنطاق، تصبح القرارات المعمارية أكثر أهمية. هناك نهجان رئيسيان لإنشاء تطبيقات أكبر في JavaScript: *التركيب* أو *الوراثة*. لكل منهما إيجابيات وسلبيات، ولكن دعونا نشرحها في سياق لعبة.

✅ أحد أشهر الكتب البرمجية على الإطلاق يتعلق بـ [أنماط التصميم](https://en.wikipedia.org/wiki/Design_Patterns).

في اللعبة، لديك `كائنات اللعبة` وهي الكائنات التي تظهر على الشاشة. هذا يعني أن لها موقعًا على نظام الإحداثيات الديكارتية، يتميز بوجود إحداثيات `x` و `y`. أثناء تطوير اللعبة، ستلاحظ أن جميع كائنات اللعبة لها خصائص قياسية، مشتركة في كل لعبة تقوم بإنشائها، وهي عناصر:

- **تعتمد على الموقع** معظم، إن لم يكن كل، عناصر اللعبة تعتمد على الموقع. وهذا يعني أن لها موقعًا، إحداثيات `x` و `y`.
- **قابلة للحركة** هذه كائنات يمكنها التحرك إلى موقع جديد. عادةً ما تكون بطلًا، أو وحشًا، أو شخصية غير لاعبة (NPC)، ولكن ليس على سبيل المثال، كائنًا ثابتًا مثل شجرة.
- **تدمير ذاتي** هذه الكائنات موجودة فقط لفترة زمنية محددة قبل أن يتم إعدادها للحذف. عادةً ما يتم تمثيل ذلك بواسطة متغير منطقي `dead` أو `destroyed` يشير إلى محرك اللعبة بأن هذا الكائن يجب ألا يتم عرضه بعد الآن.
- **فترة تهدئة** "فترة التهدئة" هي خاصية نموذجية بين الكائنات قصيرة العمر. مثال نموذجي هو قطعة نص أو تأثير رسومي مثل انفجار يجب أن يُرى فقط لبضع ميلي ثانية.

✅ فكر في لعبة مثل باك-مان. هل يمكنك تحديد الأنواع الأربعة من الكائنات المذكورة أعلاه في هذه اللعبة؟

### التعبير عن السلوك

كل ما وصفناه أعلاه هو سلوك يمكن أن تمتلكه كائنات اللعبة. إذًا كيف يمكننا ترميز ذلك؟ يمكننا التعبير عن هذا السلوك كطرق مرتبطة إما بالفئات أو الكائنات.

**الفئات**

الفكرة هي استخدام `الفئات` بالتزامن مع `الوراثة` لتحقيق إضافة سلوك معين إلى الفئة.

✅ الوراثة هي مفهوم مهم لفهمه. تعرف على المزيد من خلال [مقال MDN عن الوراثة](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

معبرًا عنه عبر الكود، يمكن أن يبدو كائن اللعبة عادةً هكذا:

```javascript

//set up the class GameObject
class GameObject {
  constructor(x, y, type) {
    this.x = x;
    this.y = y;
    this.type = type;
  }
}

//this class will extend the GameObject's inherent class properties
class Movable extends GameObject {
  constructor(x,y, type) {
    super(x,y, type)
  }

//this movable object can be moved on the screen
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}

//this is a specific class that extends the Movable class, so it can take advantage of all the properties that it inherits
class Hero extends Movable {
  constructor(x,y) {
    super(x,y, 'Hero')
  }
}

//this class, on the other hand, only inherits the GameObject properties
class Tree extends GameObject {
  constructor(x,y) {
    super(x,y, 'Tree')
  }
}

//a hero can move...
const hero = new Hero();
hero.moveTo(5,5);

//but a tree cannot
const tree = new Tree();
```

✅ خذ بضع دقائق لتعيد تصور بطل باك-مان (مثل إنكي، بينكي أو بلينكي) وكيف يمكن كتابته في JavaScript.

**التركيب**

طريقة مختلفة للتعامل مع وراثة الكائنات هي باستخدام *التركيب*. ثم تعبر الكائنات عن سلوكها هكذا:

```javascript
//create a constant gameObject
const gameObject = {
  x: 0,
  y: 0,
  type: ''
};

//...and a constant movable
const movable = {
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}
//then the constant movableObject is composed of the gameObject and movable constants
const movableObject = {...gameObject, ...movable};

//then create a function to create a new Hero who inherits the movableObject properties
function createHero(x, y) {
  return {
    ...movableObject,
    x,
    y,
    type: 'Hero'
  }
}
//...and a static object that inherits only the gameObject properties
function createStatic(x, y, type) {
  return {
    ...gameObject
    x,
    y,
    type
  }
}
//create the hero and move it
const hero = createHero(10,10);
hero.moveTo(5,5);
//and create a static tree which only stands around
const tree = createStatic(0,0, 'Tree'); 
```

**أي نمط يجب أن أستخدم؟**

الأمر متروك لك لتحديد النمط الذي تختاره. JavaScript تدعم كلا النموذجين.

--

نمط آخر شائع في تطوير الألعاب يعالج مشكلة التعامل مع تجربة المستخدم وأداء اللعبة.

## نمط النشر/الاشتراك

✅ يشير Pub/Sub إلى "النشر-الاشتراك"

يعالج هذا النمط فكرة أن الأجزاء المختلفة من تطبيقك لا ينبغي أن تعرف بعضها البعض. لماذا؟ لأن ذلك يجعل من السهل جدًا رؤية ما يجري بشكل عام إذا كانت الأجزاء منفصلة. كما يجعل من السهل تغيير السلوك فجأة إذا لزم الأمر. كيف نحقق ذلك؟ نقوم بذلك من خلال إنشاء بعض المفاهيم:

- **الرسالة**: الرسالة عادةً ما تكون سلسلة نصية مصحوبة ببيانات اختيارية (قطعة بيانات توضح ما تدور حوله الرسالة). يمكن أن تكون الرسالة النموذجية في اللعبة `KEY_PRESSED_ENTER`.
- **الناشر**: هذا العنصر *ينشر* رسالة ويرسلها إلى جميع المشتركين.
- **المشترك**: هذا العنصر *يستمع* إلى رسائل محددة وينفذ مهمة معينة نتيجة تلقي هذه الرسالة، مثل إطلاق الليزر.

التنفيذ صغير الحجم ولكنه نمط قوي جدًا. إليك كيفية تنفيذه:

```javascript
//set up an EventEmitter class that contains listeners
class EventEmitter {
  constructor() {
    this.listeners = {};
  }
//when a message is received, let the listener to handle its payload
  on(message, listener) {
    if (!this.listeners[message]) {
      this.listeners[message] = [];
    }
    this.listeners[message].push(listener);
  }
//when a message is sent, send it to a listener with some payload
  emit(message, payload = null) {
    if (this.listeners[message]) {
      this.listeners[message].forEach(l => l(message, payload))
    }
  }
}

```

لاستخدام الكود أعلاه، يمكننا إنشاء تنفيذ صغير جدًا:

```javascript
//set up a message structure
const Messages = {
  HERO_MOVE_LEFT: 'HERO_MOVE_LEFT'
};
//invoke the eventEmitter you set up above
const eventEmitter = new EventEmitter();
//set up a hero
const hero = createHero(0,0);
//let the eventEmitter know to watch for messages pertaining to the hero moving left, and act on it
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});

//set up the window to listen for the keyup event, specifically if the left arrow is hit, emit a message to move the hero left
window.addEventListener('keyup', (evt) => {
  if (evt.key === 'ArrowLeft') {
    eventEmitter.emit(Messages.HERO_MOVE_LEFT)
  }
});
```

في الأعلى، قمنا بربط حدث لوحة المفاتيح، `ArrowLeft` وأرسلنا رسالة `HERO_MOVE_LEFT`. نستمع إلى تلك الرسالة ونحرك `hero` كنتيجة لذلك. القوة في هذا النمط هي أن مستمع الحدث والبطل لا يعرفان بعضهما البعض. يمكنك إعادة تعيين `ArrowLeft` إلى مفتاح `A`. بالإضافة إلى ذلك، سيكون من الممكن القيام بشيء مختلف تمامًا عند الضغط على `ArrowLeft` من خلال إجراء بعض التعديلات على وظيفة `on` الخاصة بـ eventEmitter:

```javascript
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});
```

مع تعقيد الأمور عندما تنمو لعبتك، يظل هذا النمط ثابتًا في التعقيد ويبقى الكود الخاص بك نظيفًا. يوصى بشدة بتبني هذا النمط.

---

## تحدي GitHub Copilot Agent 🚀

استخدم وضع الوكيل لإكمال التحدي التالي:

**الوصف:** قم بإنشاء نظام كائنات لعبة بسيط باستخدام كل من الوراثة ونمط النشر/الاشتراك. ستقوم بتنفيذ لعبة أساسية حيث يمكن للكائنات المختلفة التواصل عبر الأحداث دون معرفة مباشرة ببعضها البعض.

**المهمة:** قم بإنشاء نظام لعبة JavaScript مع المتطلبات التالية: 1) قم بإنشاء فئة GameObject الأساسية مع إحداثيات x و y وخصائص النوع. 2) قم بإنشاء فئة Hero التي تمتد من GameObject ويمكنها التحرك. 3) قم بإنشاء فئة Enemy التي تمتد من GameObject ويمكنها مطاردة البطل. 4) قم بتنفيذ فئة EventEmitter لنمط النشر/الاشتراك. 5) قم بإعداد مستمعي الأحداث بحيث عندما يتحرك البطل، تتلقى الأعداء القريبة حدث 'HERO_MOVED' وتحدث موقعها للتحرك نحو البطل. قم بتضمين عبارات console.log لإظهار التواصل بين الكائنات.

## 🚀 التحدي

فكر في كيفية تحسين نمط النشر/الاشتراك للعبة. ما هي الأجزاء التي يجب أن تصدر أحداثًا، وكيف يجب أن تتفاعل اللعبة معها؟ الآن لديك فرصة للإبداع، فكر في لعبة جديدة وكيف يمكن أن تتصرف أجزاؤها.

## اختبار ما بعد المحاضرة

[اختبار ما بعد المحاضرة](https://ff-quizzes.netlify.app/web/quiz/30)

## المراجعة والدراسة الذاتية

تعرف على المزيد حول نمط النشر/الاشتراك من خلال [قراءة المزيد عنه](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## الواجب

[تصميم لعبة](assignment.md)

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسيرات خاطئة تنشأ عن استخدام هذه الترجمة.