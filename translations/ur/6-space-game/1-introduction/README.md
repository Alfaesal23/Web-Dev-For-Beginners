<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T15:11:27+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ur"
}
-->
# اسپیس گیم بنائیں حصہ 1: تعارف

![اسپیس گیم کی اینیمیشن گیم پلے دکھا رہی ہے](../../../../6-space-game/images/pewpew.gif)

بالکل ناسا کے مشن کنٹرول کی طرح جو اسپیس لانچ کے دوران مختلف سسٹمز کو مربوط کرتا ہے، ہم ایک اسپیس گیم بنائیں گے جو یہ دکھائے گا کہ کس طرح ایک پروگرام کے مختلف حصے بغیر کسی رکاوٹ کے ایک ساتھ کام کر سکتے ہیں۔ کچھ ایسا بناتے ہوئے جسے آپ واقعی کھیل سکیں، آپ بنیادی پروگرامنگ تصورات سیکھیں گے جو کسی بھی سافٹ ویئر پروجیکٹ پر لاگو ہوتے ہیں۔

ہم کوڈ کو منظم کرنے کے دو بنیادی طریقوں کا جائزہ لیں گے: وراثت (inheritance) اور ترکیب (composition)۔ یہ صرف تعلیمی تصورات نہیں ہیں – یہ وہی پیٹرنز ہیں جو ویڈیو گیمز سے لے کر بینکنگ سسٹمز تک سب کچھ طاقتور بناتے ہیں۔ ہم ایک کمیونیکیشن سسٹم بھی نافذ کریں گے جسے پب/سب کہا جاتا ہے، جو خلائی جہازوں میں استعمال ہونے والے کمیونیکیشن نیٹ ورکس کی طرح کام کرتا ہے، اور مختلف اجزاء کو بغیر کسی انحصار کے معلومات شیئر کرنے کی اجازت دیتا ہے۔

اس سیریز کے اختتام تک، آپ یہ سمجھ جائیں گے کہ ایسے ایپلیکیشنز کیسے بنائی جائیں جو بڑھ سکیں اور ترقی کر سکیں – چاہے آپ گیمز، ویب ایپلیکیشنز، یا کوئی اور سافٹ ویئر سسٹم تیار کر رہے ہوں۔

## لیکچر سے پہلے کا کوئز

[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/29)

## گیم ڈیولپمنٹ میں وراثت اور ترکیب

جب پروجیکٹس پیچیدہ ہوتے ہیں تو کوڈ کو منظم کرنا بہت اہم ہو جاتا ہے۔ جو ایک سادہ اسکرپٹ کے طور پر شروع ہوتا ہے وہ مناسب ساخت کے بغیر برقرار رکھنا مشکل ہو سکتا ہے – بالکل جیسے اپولو مشنز کو ہزاروں اجزاء کے درمیان محتاط ہم آہنگی کی ضرورت ہوتی ہے۔

ہم کوڈ کو منظم کرنے کے دو بنیادی طریقوں کا جائزہ لیں گے: وراثت اور ترکیب۔ ہر ایک کے اپنے الگ فوائد ہیں، اور دونوں کو سمجھنا مختلف حالات کے لیے صحیح طریقہ منتخب کرنے میں مدد کرتا ہے۔ ہم ان تصورات کو اپنے اسپیس گیم کے ذریعے ظاہر کریں گے، جہاں ہیروز، دشمن، پاور اپس، اور دیگر اشیاء کو مؤثر طریقے سے تعامل کرنا ہوگا۔

✅ سب سے مشہور پروگرامنگ کتابوں میں سے ایک [ڈیزائن پیٹرنز](https://en.wikipedia.org/wiki/Design_Patterns) کے بارے میں ہے۔

کسی بھی گیم میں، آپ کے پاس `گیم آبجیکٹس` ہوتے ہیں – وہ انٹرایکٹو عناصر جو آپ کی گیم کی دنیا کو آباد کرتے ہیں۔ ہیروز، دشمن، پاور اپس، اور بصری اثرات سب گیم آبجیکٹس ہیں۔ ہر ایک مخصوص اسکرین کوآرڈینیٹس پر موجود ہوتا ہے جو `x` اور `y` ویلیوز کا استعمال کرتے ہوئے، بالکل جیسے کوآرڈینیٹ پلین پر پوائنٹس کو پلاٹ کرنا۔

ان کے بصری اختلافات کے باوجود، یہ اشیاء اکثر بنیادی رویے شیئر کرتی ہیں:

- **یہ کہیں موجود ہیں** – ہر آبجیکٹ کے پاس x اور y کوآرڈینیٹس ہوتے ہیں تاکہ گیم جان سکے کہ اسے کہاں ڈرائنگ کرنا ہے
- **بہت سے حرکت کر سکتے ہیں** – ہیروز دوڑتے ہیں، دشمن پیچھا کرتے ہیں، گولیاں اسکرین پر اڑتی ہیں
- **ان کی زندگی کی مدت ہوتی ہے** – کچھ ہمیشہ کے لیے رہتے ہیں، دوسرے (جیسے دھماکے) مختصر وقت کے لیے ظاہر ہوتے ہیں اور غائب ہو جاتے ہیں
- **یہ چیزوں پر ردعمل دیتے ہیں** – جب چیزیں ٹکراتی ہیں، پاور اپس جمع کیے جاتے ہیں، صحت کے بارز اپ ڈیٹ ہوتے ہیں

✅ Pac-Man جیسے گیم کے بارے میں سوچیں۔ کیا آپ اس گیم میں درج بالا چار آبجیکٹ اقسام کی شناخت کر سکتے ہیں؟

### کوڈ کے ذریعے رویے کا اظہار

اب جب کہ آپ سمجھ گئے ہیں کہ گیم آبجیکٹس کے مشترکہ رویے کیا ہیں، آئیے دیکھتے ہیں کہ ان رویوں کو جاوا اسکرپٹ میں کیسے نافذ کیا جائے۔ آپ آبجیکٹ کے رویے کو کلاسز یا انفرادی آبجیکٹس سے منسلک طریقوں کے ذریعے ظاہر کر سکتے ہیں، اور منتخب کرنے کے لیے کئی طریقے ہیں۔

**کلاس پر مبنی طریقہ**

کلاسز اور وراثت گیم آبجیکٹس کو منظم کرنے کے لیے ایک منظم طریقہ فراہم کرتے ہیں۔ کارل لینیئس کے تیار کردہ ٹیکسونومک کلاسیفیکیشن سسٹم کی طرح، آپ ایک بنیادی کلاس سے شروع کرتے ہیں جس میں عام خصوصیات ہوتی ہیں، پھر خصوصی کلاسز بناتے ہیں جو ان بنیادی اصولوں کو وراثت میں لے کر مخصوص صلاحیتیں شامل کرتے ہیں۔

✅ وراثت ایک اہم تصور ہے جسے سمجھنا ضروری ہے۔ [MDN کے وراثت پر مضمون](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) پر مزید جانیں۔

یہاں یہ ہے کہ آپ کلاسز اور وراثت کا استعمال کرتے ہوئے گیم آبجیکٹس کو کیسے نافذ کر سکتے ہیں:

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

**آئیے اسے مرحلہ وار توڑتے ہیں:**
- ہم ایک بنیادی ٹیمپلیٹ بنا رہے ہیں جسے ہر گیم آبجیکٹ استعمال کر سکتا ہے
- کنسٹرکٹر محفوظ کرتا ہے کہ آبجیکٹ کہاں ہے (`x`, `y`) اور یہ کس قسم کی چیز ہے
- یہ وہ بنیاد بن جاتی ہے جس پر آپ کے تمام گیم آبجیکٹس تعمیر ہوں گے

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

**اوپر میں، ہم نے:**
- **گیم آبجیکٹ کلاس کو بڑھایا** تاکہ حرکت کی فعالیت شامل کی جا سکے
- **پیرنٹ کنسٹرکٹر کو `super()` کے ذریعے کال کیا** تاکہ وراثت میں لی گئی خصوصیات کو ابتدائی بنایا جا سکے
- **ایک `moveTo()` طریقہ شامل کیا** جو آبجیکٹ کی پوزیشن کو اپ ڈیٹ کرتا ہے

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

**ان تصورات کو سمجھنا:**
- **مخصوص آبجیکٹ اقسام بناتا ہے** جو مناسب رویے وراثت میں لیتے ہیں
- **دکھاتا ہے** کہ وراثت منتخب خصوصیات کو شامل کرنے کی اجازت دیتی ہے
- **ظاہر کرتا ہے** کہ ہیروز حرکت کر سکتے ہیں جبکہ درخت ساکن رہتے ہیں
- **وضاحت کرتا ہے** کہ کلاس ہائیرارکی نامناسب اعمال کو روکتی ہے

✅ چند منٹ نکال کر Pac-Man کے ہیرو (مثلاً Inky، Pinky یا Blinky) کو دوبارہ تصور کریں اور یہ کیسے جاوا اسکرپٹ میں لکھا جائے گا۔

**ترکیب کا طریقہ**

ترکیب ایک ماڈیولر ڈیزائن فلسفہ کی پیروی کرتی ہے، بالکل جیسے انجینئرز خلائی جہاز کو قابل تبادلہ اجزاء کے ساتھ ڈیزائن کرتے ہیں۔ پیرنٹ کلاس سے وراثت لینے کے بجائے، آپ مخصوص رویوں کو یکجا کرتے ہیں تاکہ ایسے آبجیکٹس بنائیں جن میں بالکل وہی فعالیت ہو جس کی انہیں ضرورت ہو۔ یہ طریقہ سخت درجہ بندی کی حدود کے بغیر لچک فراہم کرتا ہے۔

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

**یہ کوڈ کیا کرتا ہے:**
- **ایک بنیادی `gameObject` کی وضاحت کرتا ہے** جس میں پوزیشن اور قسم کی خصوصیات ہیں
- **ایک الگ `movable` رویے کا آبجیکٹ بناتا ہے** جس میں حرکت کی فعالیت ہے
- **تشویشات کو الگ کرتا ہے** پوزیشن ڈیٹا اور حرکت کی منطق کو آزاد رکھ کر

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

**اوپر میں، ہم نے:**
- **بیس آبجیکٹ کی خصوصیات کو حرکت کے رویے کے ساتھ یکجا کیا** اسپریڈ سینٹیکس کا استعمال کرتے ہوئے
- **فیکٹری فنکشنز بنائے** جو حسب ضرورت آبجیکٹس واپس کرتے ہیں
- **لچکدار آبجیکٹ تخلیق کو فعال کیا** بغیر سخت کلاس ہائیرارکی کے
- **آبجیکٹس کو بالکل وہی رویے رکھنے کی اجازت دی** جس کی انہیں ضرورت ہے

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**یاد رکھنے کے اہم نکات:**
- **آبجیکٹس کو ترکیب کرتا ہے** رویوں کو مکس کر کے بجائے وراثت لینے کے
- **زیادہ لچک فراہم کرتا ہے** سخت وراثتی درجہ بندی کے مقابلے میں
- **آبجیکٹس کو بالکل وہی خصوصیات رکھنے کی اجازت دیتا ہے** جس کی انہیں ضرورت ہے
- **جدید جاوا اسکرپٹ اسپریڈ سینٹیکس کا استعمال کرتا ہے** صاف آبجیکٹ کے امتزاج کے لیے
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

**یہاں کیا ہوتا ہے اسے توڑتے ہیں:**
- **ایک مرکزی ایونٹ مینجمنٹ سسٹم بناتا ہے** ایک سادہ کلاس کا استعمال کرتے ہوئے
- **لسنرز کو ایک آبجیکٹ میں ذخیرہ کرتا ہے** پیغام کی قسم کے لحاظ سے منظم
- **نئے لسنرز کو رجسٹر کرتا ہے** `on()` طریقہ استعمال کرتے ہوئے
- **پیغامات کو تمام دلچسپی رکھنے والے لسنرز تک نشر کرتا ہے** `emit()` طریقہ استعمال کرتے ہوئے
- **اختیاری ڈیٹا پے لوڈز کی حمایت کرتا ہے** متعلقہ معلومات پاس کرنے کے لیے

### سب کچھ ایک ساتھ رکھنا: ایک عملی مثال

ٹھیک ہے، آئیے اسے عملی طور پر دیکھتے ہیں! ہم ایک سادہ حرکت کا نظام بنائیں گے جو دکھائے گا کہ پب/سب کس طرح صاف اور لچکدار ہو سکتا ہے:

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

**یہ کوڈ کیا کرتا ہے:**
- **ایک کانسٹنٹس آبجیکٹ کی وضاحت کرتا ہے** پیغام کے ناموں میں غلطیوں کو روکنے کے لیے
- **ایک ایونٹ ایمیٹر انسٹینس بناتا ہے** تمام کمیونیکیشن کو ہینڈل کرنے کے لیے
- **ہیرو آبجیکٹ کو ابتدائی پوزیشن پر شروع کرتا ہے**

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

**اوپر میں، ہم نے:**
- **ایونٹ لسنرز رجسٹر کیے** جو حرکت کے پیغامات پر ردعمل دیتے ہیں
- **ہیرو کی پوزیشن کو اپ ڈیٹ کیا** حرکت کی سمت کی بنیاد پر
- **کنسول لاگنگ شامل کی** ہیرو کی پوزیشن میں تبدیلیوں کو ٹریک کرنے کے لیے
- **حرکت کی منطق کو ان پٹ ہینڈلنگ سے الگ کیا**

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

**ان تصورات کو سمجھنا:**
- **کی بورڈ ان پٹ کو گیم ایونٹس سے جوڑتا ہے** بغیر سخت جوڑ کے
- **ان پٹ سسٹم کو گیم آبجیکٹس کے ساتھ بالواسطہ بات چیت کرنے کی اجازت دیتا ہے**
- **متعدد سسٹمز کو ایک ہی کی بورڈ ایونٹس پر ردعمل دینے کی اجازت دیتا ہے**
- **کی بائنڈنگ کو تبدیل کرنا یا نئے ان پٹ طریقے شامل کرنا آسان بناتا ہے**

> 💡 **پرو ٹپ**: اس پیٹرن کی خوبصورتی لچک میں ہے! آپ آسانی سے مزید ایونٹ لسنرز شامل کر کے ساؤنڈ ایفیکٹس، اسکرین شیک، یا پارٹیکل ایفیکٹس شامل کر سکتے ہیں – موجودہ کی بورڈ یا حرکت کے کوڈ کو تبدیل کرنے کی ضرورت نہیں۔
> 
**یہ طریقہ آپ کو کیوں پسند آئے گا:**
- نئی خصوصیات شامل کرنا بہت آسان ہو جاتا ہے – بس ان ایونٹس کو سنیں جن کی آپ کو پرواہ ہے
- ایک ہی ایونٹ پر متعدد چیزیں ردعمل دے سکتی ہیں بغیر ایک دوسرے پر اثر ڈالے
- ٹیسٹنگ بہت آسان ہو جاتی ہے کیونکہ ہر حصہ آزادانہ طور پر کام کرتا ہے
- جب کچھ خراب ہوتا ہے، تو آپ کو بالکل معلوم ہوتا ہے کہ کہاں دیکھنا ہے

### پب/سب مؤثر طریقے سے کیسے اسکیل کرتا ہے

پب/سب پیٹرن ایپلیکیشنز کے پیچیدہ ہونے کے ساتھ سادگی کو برقرار رکھتا ہے۔ چاہے درجنوں دشمنوں کا انتظام کرنا ہو، متحرک UI اپ ڈیٹس، یا ساؤنڈ سسٹمز، پیٹرن بغیر کسی آرکیٹیکچرل تبدیلی کے بڑھتی ہوئی اسکیل کو ہینڈل کرتا ہے۔ نئی خصوصیات موجودہ ایونٹ سسٹم میں بغیر کسی اثر کے ضم ہو جاتی ہیں۔

> ⚠️ **عام غلطی**: شروع میں بہت زیادہ مخصوص پیغام کی اقسام نہ بنائیں۔ وسیع اقسام سے شروع کریں اور جیسے جیسے آپ کے گیم کی ضروریات واضح ہوں، انہیں بہتر بنائیں۔
> 
**بہترین طریقے جو اپنانے چاہئیں:**
- **متعلقہ پیغامات کو منطقی اقسام میں گروپ کرتا ہے**
- **وضاحتی نام استعمال کرتا ہے** جو واضح طور پر بتاتے ہیں کہ کیا ہوا
- **پیغام کے پے لوڈز کو سادہ اور مرکوز رکھتا ہے**
- **اپنے پیغام کی اقسام کو دستاویزی بناتا ہے** ٹیم کے تعاون کے لیے

---

## GitHub Copilot ایجنٹ چیلنج 🚀

ایجنٹ موڈ کا استعمال کرتے ہوئے درج ذیل چیلنج مکمل کریں:

**تفصیل:** وراثت اور پب/سب پیٹرن دونوں کا استعمال کرتے ہوئے ایک سادہ گیم آبجیکٹ سسٹم بنائیں۔ آپ ایک بنیادی گیم نافذ کریں گے جہاں مختلف آبجیکٹس ایونٹس کے ذریعے ایک دوسرے کے بارے میں براہ راست جانے بغیر بات چیت کر سکتے ہیں۔

**پرومپٹ:** درج ذیل ضروریات کے ساتھ جاوا اسکرپٹ گیم سسٹم بنائیں: 1) x, y کوآرڈینیٹس اور ایک قسم کی خصوصیت کے ساتھ ایک بنیادی GameObject کلاس بنائیں۔ 2) ایک Hero کلاس بنائیں جو GameObject کو بڑھائے اور حرکت کر سکے۔ 3) ایک Enemy کلاس بنائیں جو GameObject کو بڑھائے اور ہیرو کا پیچھا کر سکے۔ 4) پب/سب پیٹرن کے لیے ایک EventEmitter کلاس نافذ کریں۔ 5) ایونٹ لسنرز سیٹ کریں تاکہ جب ہیرو حرکت کرے، قریبی دشمن 'HERO_MOVED' ایونٹ وصول کریں اور ہیرو کی طرف حرکت کرنے کے لیے اپنی پوزیشن اپ ڈیٹ کریں۔ کنسول لاگ اسٹیٹمنٹس شامل کریں تاکہ آبجیکٹس کے درمیان کمیونیکیشن دکھائی دے۔

[ایجنٹ موڈ](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) کے بارے میں مزید جانیں۔

## 🚀 چیلنج

سوچیں کہ پب-سب پیٹرن گیم آرکیٹیکچر کو کیسے بہتر بنا سکتا ہے۔ شناخت کریں کہ کون سے اجزاء ایونٹس نشر کریں اور سسٹم کو کیسے ردعمل دینا چاہیے۔ ایک گیم کا تصور کریں اور اس کے اجزاء کے درمیان کمیونیکیشن پیٹرنز کا نقشہ بنائیں۔

## لیکچر کے بعد کا کوئز

[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/30)

## جائزہ اور خود مطالعہ

پب/سب کے بارے میں مزید جانیں [اسے پڑھ کر](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon)۔

## اسائنمنٹ

[ایک گیم کا خاکہ بنائیں](assignment.md)

---

**اعلانِ لاتعلقی**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے لیے ہم ذمہ دار نہیں ہیں۔