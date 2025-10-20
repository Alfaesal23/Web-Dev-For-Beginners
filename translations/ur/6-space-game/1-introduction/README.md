<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "38777f8c81874368d3b4b9b8a54aa242",
  "translation_date": "2025-10-20T20:57:47+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ur"
}
-->
# اسپیس گیم بنائیں حصہ 1: تعارف

![ویڈیو](../../../../6-space-game/images/pewpew.gif)

## لیکچر سے پہلے کا کوئز

[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/29)

### گیم ڈیولپمنٹ میں وراثت اور کمپوزیشن

پچھلے اسباق میں، آپ کے بنائے گئے ایپس کے ڈیزائن آرکیٹیکچر کے بارے میں زیادہ فکر کرنے کی ضرورت نہیں تھی کیونکہ پروجیکٹس کا دائرہ کار بہت چھوٹا تھا۔ تاہم، جب آپ کی ایپلیکیشنز کا سائز اور دائرہ کار بڑھتا ہے، تو آرکیٹیکچرل فیصلے زیادہ اہمیت اختیار کر لیتے ہیں۔ جاوا اسکرپٹ میں بڑی ایپلیکیشنز بنانے کے دو بڑے طریقے ہیں: *کمپوزیشن* یا *وراثت*۔ دونوں کے فوائد اور نقصانات ہیں، لیکن آئیے انہیں گیم کے تناظر میں سمجھتے ہیں۔

✅ سب سے مشہور پروگرامنگ کتابوں میں سے ایک [ڈیزائن پیٹرنز](https://en.wikipedia.org/wiki/Design_Patterns) کے بارے میں ہے۔

ایک گیم میں آپ کے پاس `گیم آبجیکٹس` ہوتے ہیں جو اسکرین پر موجود ہوتے ہیں۔ اس کا مطلب ہے کہ ان کا کارٹیسین کوآرڈینیٹ سسٹم پر ایک مقام ہوتا ہے، جس کی خصوصیت `x` اور `y` کوآرڈینیٹ سے ہوتی ہے۔ جب آپ گیم ڈیولپ کرتے ہیں تو آپ دیکھیں گے کہ آپ کے تمام گیم آبجیکٹس میں ایک معیاری پراپرٹی ہوتی ہے، جو ہر گیم کے لیے عام ہوتی ہے، یعنی وہ عناصر جو:

- **مقام پر مبنی** زیادہ تر، اگر سب نہیں، گیم عناصر مقام پر مبنی ہوتے ہیں۔ اس کا مطلب ہے کہ ان کا ایک مقام ہوتا ہے، `x` اور `y`۔
- **حرکت پذیر** یہ وہ آبجیکٹس ہیں جو ایک نئے مقام پر منتقل ہو سکتے ہیں۔ عام طور پر یہ ہیرو، مونسٹر یا NPC (نان پلیئر کریکٹر) ہوتے ہیں، لیکن مثال کے طور پر، ایک جامد آبجیکٹ جیسے درخت نہیں۔
- **خود کو ختم کرنے والے** یہ آبجیکٹس صرف ایک مقررہ وقت کے لیے موجود ہوتے ہیں اس سے پہلے کہ وہ حذف ہونے کے لیے خود کو سیٹ کریں۔ عام طور پر یہ ایک `dead` یا `destroyed` بولین کے ذریعے ظاہر کیا جاتا ہے جو گیم انجن کو اشارہ دیتا ہے کہ اس آبجیکٹ کو مزید رینڈر نہیں کیا جانا چاہیے۔
- **کول ڈاؤن** 'کول ڈاؤن' ایک عام پراپرٹی ہے جو مختصر مدت کے آبجیکٹس میں پائی جاتی ہے۔ ایک عام مثال ایک ٹیکسٹ یا گرافیکل اثر جیسے دھماکہ ہے جو صرف چند ملی سیکنڈ کے لیے نظر آنا چاہیے۔

✅ ایک گیم جیسے Pac-Man کے بارے میں سوچیں۔ کیا آپ اس گیم میں اوپر دیے گئے چار آبجیکٹ اقسام کی شناخت کر سکتے ہیں؟

### رویے کا اظہار

ہم نے اوپر جو کچھ بیان کیا وہ سب گیم آبجیکٹس کے رویے ہیں۔ تو ہم انہیں کیسے کوڈ کرتے ہیں؟ ہم ان رویوں کو کلاسز یا آبجیکٹس سے منسلک طریقوں کے طور پر ظاہر کر سکتے ہیں۔

**کلاسز**

خیال یہ ہے کہ `کلاسز` کو `وراثت` کے ساتھ استعمال کیا جائے تاکہ کسی کلاس میں ایک خاص رویہ شامل کیا جا سکے۔

✅ وراثت کو سمجھنا ایک اہم تصور ہے۔ [MDN کے وراثت پر مضمون](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) پر مزید جانیں۔

کوڈ کے ذریعے ظاہر کیا گیا، ایک گیم آبجیکٹ عام طور پر اس طرح نظر آ سکتا ہے:

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

✅ چند منٹ نکال کر Pac-Man کے ہیرو (مثال کے طور پر Inky، Pinky یا Blinky) کو دوبارہ تصور کریں اور یہ جاوا اسکرپٹ میں کیسے لکھا جائے گا۔

**کمپوزیشن**

آبجیکٹ وراثت کو ہینڈل کرنے کا ایک مختلف طریقہ *کمپوزیشن* کا استعمال ہے۔ پھر، آبجیکٹس اپنے رویے کو اس طرح ظاہر کرتے ہیں:

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

**مجھے کون سا پیٹرن استعمال کرنا چاہیے؟**

یہ آپ پر منحصر ہے کہ آپ کون سا پیٹرن منتخب کرتے ہیں۔ جاوا اسکرپٹ ان دونوں پیراڈائمز کو سپورٹ کرتا ہے۔

--

گیم ڈیولپمنٹ میں ایک اور عام پیٹرن گیم کے یوزر ایکسپیرینس اور پرفارمنس کو ہینڈل کرنے کے مسئلے کو حل کرتا ہے۔

## پب/سب پیٹرن

✅ پب/سب کا مطلب ہے 'پبلش-سبسکرائب'

یہ پیٹرن اس خیال کو حل کرتا ہے کہ آپ کی ایپلیکیشن کے مختلف حصے ایک دوسرے کے بارے میں نہیں جانتے۔ ایسا کیوں ہے؟ یہ عام طور پر دیکھنا بہت آسان بناتا ہے کہ کیا ہو رہا ہے اگر مختلف حصے الگ الگ ہوں۔ یہ اچانک رویے کو تبدیل کرنا بھی آسان بناتا ہے اگر آپ کو ضرورت ہو۔ ہم یہ کیسے حاصل کرتے ہیں؟ ہم کچھ تصورات قائم کر کے یہ کرتے ہیں:

- **پیغام**: ایک پیغام عام طور پر ایک ٹیکسٹ اسٹرنگ ہوتا ہے جس کے ساتھ ایک اختیاری پے لوڈ (ڈیٹا کا ایک ٹکڑا جو وضاحت کرتا ہے کہ پیغام کس بارے میں ہے) ہوتا ہے۔ گیم میں ایک عام پیغام `KEY_PRESSED_ENTER` ہو سکتا ہے۔
- **پبلشر**: یہ عنصر ایک پیغام *پبلش* کرتا ہے اور اسے تمام سبسکرائبرز کو بھیجتا ہے۔
- **سبسکرائبر**: یہ عنصر مخصوص پیغامات *سنتا* ہے اور اس پیغام کو وصول کرنے کے نتیجے میں کچھ کام انجام دیتا ہے، جیسے کہ لیزر فائر کرنا۔

اس کا نفاذ سائز میں بہت چھوٹا ہے لیکن یہ ایک بہت طاقتور پیٹرن ہے۔ اسے اس طرح نافذ کیا جا سکتا ہے:

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

اوپر دیے گئے کوڈ کو استعمال کرنے کے لیے ہم ایک بہت چھوٹا نفاذ بنا سکتے ہیں:

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

اوپر ہم نے ایک کی بورڈ ایونٹ، `ArrowLeft` کو جوڑا اور `HERO_MOVE_LEFT` پیغام بھیجا۔ ہم اس پیغام کو سنتے ہیں اور اس کے نتیجے میں `ہیرو` کو حرکت دیتے ہیں۔ اس پیٹرن کی طاقت یہ ہے کہ ایونٹ لسٹنر اور ہیرو ایک دوسرے کے بارے میں نہیں جانتے۔ آپ `ArrowLeft` کو `A` کلید پر دوبارہ میپ کر سکتے ہیں۔ اس کے علاوہ، `ArrowLeft` پر کچھ بالکل مختلف کرنا ممکن ہوگا ایونٹ ایمیٹر کے `on` فنکشن میں چند ترمیمات کر کے:

```javascript
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});
```

جب آپ کا گیم بڑھتا ہے اور چیزیں زیادہ پیچیدہ ہو جاتی ہیں، یہ پیٹرن پیچیدگی میں وہی رہتا ہے اور آپ کا کوڈ صاف رہتا ہے۔ اس پیٹرن کو اپنانا واقعی تجویز کیا جاتا ہے۔

---

## GitHub Copilot ایجنٹ چیلنج 🚀

ایجنٹ موڈ کا استعمال کرتے ہوئے درج ذیل چیلنج مکمل کریں:

**تفصیل:** وراثت اور پب/سب پیٹرن دونوں کا استعمال کرتے ہوئے ایک سادہ گیم آبجیکٹ سسٹم بنائیں۔ آپ ایک بنیادی گیم نافذ کریں گے جہاں مختلف آبجیکٹس ایونٹس کے ذریعے ایک دوسرے کے بارے میں براہ راست جانے بغیر بات چیت کر سکتے ہیں۔

**پرومپٹ:** جاوا اسکرپٹ گیم سسٹم بنائیں جس میں درج ذیل ضروریات ہوں: 1) x، y کوآرڈینیٹس اور ایک قسم کی پراپرٹی کے ساتھ ایک بنیادی GameObject کلاس بنائیں۔ 2) ایک Hero کلاس بنائیں جو GameObject کو بڑھائے اور حرکت کر سکے۔ 3) ایک Enemy کلاس بنائیں جو GameObject کو بڑھائے اور ہیرو کا پیچھا کر سکے۔ 4) پب/سب پیٹرن کے لیے ایک EventEmitter کلاس نافذ کریں۔ 5) ایونٹ لسٹنرز سیٹ کریں تاکہ جب ہیرو حرکت کرے، قریبی دشمن 'HERO_MOVED' ایونٹ وصول کریں اور ہیرو کی طرف حرکت کرنے کے لیے اپنی پوزیشن اپ ڈیٹ کریں۔ آبجیکٹس کے درمیان بات چیت کو ظاہر کرنے کے لیے console.log بیانات شامل کریں۔

## 🚀 چیلنج

سوچیں کہ پب-سب پیٹرن گیم کو کیسے بہتر بنا سکتا ہے۔ کون سے حصے ایونٹس کو جاری کریں، اور گیم کو ان پر کیسے ردعمل دینا چاہیے؟ اب آپ کے پاس تخلیقی ہونے کا موقع ہے، ایک نئے گیم کے بارے میں سوچیں اور اس کے حصے کیسے برتاؤ کر سکتے ہیں۔

## لیکچر کے بعد کا کوئز

[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/30)

## جائزہ اور خود مطالعہ

پب/سب کے بارے میں مزید جانیں [اسے پڑھ کر](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon)۔

## اسائنمنٹ

[ایک گیم کا خاکہ بنائیں](assignment.md)

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔