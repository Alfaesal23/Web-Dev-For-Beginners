<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "03f5022615bbc23417d5af42943d12f5",
  "translation_date": "2025-10-20T20:56:30+00:00",
  "source_file": "6-space-game/3-moving-elements-around/README.md",
  "language_code": "ur"
}
-->
# خلائی کھیل بنائیں حصہ 3: حرکت شامل کرنا

## لیکچر سے پہلے کا کوئز

[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/33)

کھیل تب تک زیادہ دلچسپ نہیں ہوتا جب تک کہ اس میں خلائی مخلوق اسکرین پر حرکت نہ کرے! اس کھیل میں ہم دو قسم کی حرکت کا استعمال کریں گے:

- **کی بورڈ/ماؤس کی حرکت**: جب صارف کی بورڈ یا ماؤس کے ذریعے اسکرین پر کسی چیز کو حرکت دیتا ہے۔
- **کھیل کی طرف سے پیدا کردہ حرکت**: جب کھیل کسی چیز کو ایک خاص وقت کے وقفے سے حرکت دیتا ہے۔

تو اسکرین پر چیزوں کو کیسے حرکت دی جائے؟ یہ سب کارٹیسین کوآرڈینیٹس کے بارے میں ہے: ہم چیز کی جگہ (x,y) کو تبدیل کرتے ہیں اور پھر اسکرین کو دوبارہ بناتے ہیں۔

عام طور پر اسکرین پر *حرکت* حاصل کرنے کے لیے آپ کو درج ذیل مراحل کی ضرورت ہوتی ہے:

1. **چیز کے لیے نئی جگہ مقرر کریں**؛ یہ ضروری ہے تاکہ چیز کو حرکت کرتے ہوئے محسوس کیا جا سکے۔
2. **اسکرین صاف کریں**، اسکرین کو دوبارہ بنانے کے درمیان صاف کرنا ضروری ہے۔ ہم اسے پس منظر کے رنگ سے بھرے ہوئے مستطیل کو بنا کر صاف کر سکتے ہیں۔
3. **چیز کو نئی جگہ پر دوبارہ بنائیں**۔ ایسا کرنے سے ہم آخر کار چیز کو ایک جگہ سے دوسری جگہ منتقل کرنے میں کامیاب ہوتے ہیں۔

یہ کوڈ میں کچھ اس طرح نظر آ سکتا ہے:

```javascript
//set the hero's location
hero.x += 5;
// clear the rectangle that hosts the hero
ctx.clearRect(0, 0, canvas.width, canvas.height);
// redraw the game background and hero
ctx.fillRect(0, 0, canvas.width, canvas.height)
ctx.fillStyle = "black";
ctx.drawImage(heroImg, hero.x, hero.y);
```

✅ کیا آپ سوچ سکتے ہیں کہ آپ کے ہیرو کو ہر سیکنڈ میں کئی فریمز پر دوبارہ بنانے سے کارکردگی کے اخراجات کیوں بڑھ سکتے ہیں؟ [اس پیٹرن کے متبادل کے بارے میں پڑھیں](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Optimizing_canvas)۔

## کی بورڈ ایونٹس کو ہینڈل کریں

آپ ایونٹس کو مخصوص کوڈ کے ساتھ منسلک کرکے ہینڈل کرتے ہیں۔ کی بورڈ ایونٹس پورے ونڈو پر ٹرگر ہوتے ہیں جبکہ ماؤس ایونٹس جیسے `click` کو کسی خاص عنصر پر کلک کرنے سے منسلک کیا جا سکتا ہے۔ ہم اس پروجیکٹ میں کی بورڈ ایونٹس کا استعمال کریں گے۔

ایونٹ کو ہینڈل کرنے کے لیے آپ کو ونڈو کے `addEventListener()` میتھڈ کا استعمال کرنا ہوگا اور اسے دو ان پٹ پیرامیٹرز فراہم کرنے ہوں گے۔ پہلا پیرامیٹر ایونٹ کا نام ہے، جیسے `keyup`۔ دوسرا پیرامیٹر وہ فنکشن ہے جو ایونٹ ہونے کے نتیجے میں چلایا جانا چاہیے۔

یہاں ایک مثال ہے:

```javascript
window.addEventListener('keyup', (evt) => {
  // `evt.key` = string representation of the key
  if (evt.key === 'ArrowUp') {
    // do something
  }
})
```

کی ایونٹس کے لیے ایونٹ پر دو پراپرٹیز ہوتی ہیں جنہیں آپ دیکھ سکتے ہیں کہ کونسی کی دبائی گئی:

- `key`، یہ دبائی گئی کی کی سٹرنگ نمائندگی ہے، جیسے `ArrowUp`
- `keyCode`، یہ ایک عددی نمائندگی ہے، جیسے `37`، جو `ArrowLeft` کے مطابق ہے۔

✅ کی ایونٹ کی ہیرا پھیری کھیل کی ترقی کے علاوہ بھی مفید ہے۔ اس تکنیک کے لیے آپ اور کیا استعمال سوچ سکتے ہیں؟

### خاص کیز: ایک انتباہ

کچھ *خاص* کیز ہیں جو ونڈو کو متاثر کرتی ہیں۔ اس کا مطلب ہے کہ اگر آپ `keyup` ایونٹ سن رہے ہیں اور آپ ان خاص کیز کا استعمال کرتے ہوئے اپنے ہیرو کو حرکت دیتے ہیں تو یہ افقی اسکرولنگ بھی کرے گا۔ اسی وجہ سے آپ اپنے کھیل کو بناتے وقت اس بلٹ ان براؤزر کے رویے کو *بند* کرنا چاہیں گے۔ آپ کو اس طرح کا کوڈ چاہیے:

```javascript
let onKeyDown = function (e) {
  console.log(e.keyCode);
  switch (e.keyCode) {
    case 37:
    case 39:
    case 38:
    case 40: // Arrow keys
    case 32:
      e.preventDefault();
      break; // Space
    default:
      break; // do not block other keys
  }
};

window.addEventListener('keydown', onKeyDown);
```

اوپر دیا گیا کوڈ یقینی بنائے گا کہ ایرو کیز اور اسپیس کی کا *ڈیفالٹ* رویہ بند ہو جائے۔ *بند* کرنے کا طریقہ کار اس وقت ہوتا ہے جب ہم `e.preventDefault()` کو کال کرتے ہیں۔

## کھیل کی طرف سے پیدا کردہ حرکت

ہم چیزوں کو خود سے حرکت دے سکتے ہیں جیسے `setTimeout()` یا `setInterval()` فنکشن کا استعمال کرکے جو ہر ٹک یا وقت کے وقفے پر چیز کی جگہ کو اپ ڈیٹ کرتا ہے۔ یہ کچھ اس طرح نظر آ سکتا ہے:

```javascript
let id = setInterval(() => {
  //move the enemy on the y axis
  enemy.y += 10;
})
```

## کھیل کا لوپ

کھیل کا لوپ ایک تصور ہے جو بنیادی طور پر ایک فنکشن ہے جو باقاعدہ وقفوں پر چلایا جاتا ہے۔ اسے کھیل کا لوپ کہا جاتا ہے کیونکہ جو کچھ بھی صارف کو نظر آنا چاہیے وہ لوپ میں بنایا جاتا ہے۔ کھیل کا لوپ کھیل کے تمام اشیاء کا استعمال کرتا ہے جو کھیل کا حصہ ہیں، ان سب کو بناتا ہے جب تک کہ کسی وجہ سے وہ کھیل کا حصہ نہ رہیں۔ مثال کے طور پر اگر کوئی چیز دشمن ہے جسے لیزر نے مارا اور وہ پھٹ گیا، تو وہ موجودہ کھیل کے لوپ کا حصہ نہیں رہتا (آپ اس کے بارے میں مزید اگلے اسباق میں سیکھیں گے)۔

یہاں ایک کھیل کا لوپ عام طور پر کوڈ میں کچھ اس طرح نظر آ سکتا ہے:

```javascript
let gameLoopId = setInterval(() =>
  function gameLoop() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = "black";
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    drawHero();
    drawEnemies();
    drawStaticObjects();
}, 200);
```

اوپر دیا گیا لوپ ہر `200` ملی سیکنڈ میں کینوس کو دوبارہ بناتا ہے۔ آپ کے پاس اپنے کھیل کے لیے مناسب وقفہ منتخب کرنے کی صلاحیت ہے۔

## خلائی کھیل جاری رکھنا

آپ موجودہ کوڈ کو لے کر اسے بڑھائیں گے۔ یا تو اس کوڈ سے شروع کریں جو آپ نے حصہ I کے دوران مکمل کیا تھا یا [حصہ II- اسٹارٹر](../../../../6-space-game/3-moving-elements-around/your-work) میں کوڈ استعمال کریں۔

- **ہیرو کو حرکت دینا**: آپ کوڈ شامل کریں گے تاکہ آپ ایرو کیز کا استعمال کرتے ہوئے ہیرو کو حرکت دے سکیں۔
- **دشمنوں کو حرکت دینا**: آپ کوڈ بھی شامل کریں گے تاکہ دشمن ایک مقررہ رفتار سے اوپر سے نیچے کی طرف حرکت کریں۔

## تجویز کردہ مراحل

ان فائلوں کو تلاش کریں جو آپ کے لیے `your-work` سب فولڈر میں بنائی گئی ہیں۔ اس میں درج ذیل شامل ہونا چاہیے:

```bash
-| assets
  -| enemyShip.png
  -| player.png
-| index.html
-| app.js
-| package.json
```

آپ اپنے پروجیکٹ کو `your_work` فولڈر میں شروع کریں گے:

```bash
cd your-work
npm start
```

اوپر دیا گیا HTTP سرور ایڈریس `http://localhost:5000` پر شروع کرے گا۔ ایک براؤزر کھولیں اور اس ایڈریس کو درج کریں، اس وقت یہ ہیرو اور تمام دشمنوں کو ظاہر کرے گا؛ ابھی کچھ حرکت نہیں ہو رہی ہے!

### کوڈ شامل کریں

1. **ہیرو، دشمن اور کھیل کی چیزوں کے لیے مخصوص اشیاء شامل کریں**، ان میں `x` اور `y` پراپرٹیز ہونی چاہئیں۔ (یاد رکھیں [وراثت یا کمپوزیشن](../README.md) کے حصے کو)۔

   *اشارہ* `کھیل کی چیز` وہ ہونی چاہیے جس میں `x` اور `y` ہوں اور خود کو کینوس پر بنانے کی صلاحیت ہو۔

   >اشارہ: ایک نیا GameObject کلاس شامل کریں جس کا کنسٹرکٹر نیچے دیا گیا ہو، اور پھر اسے کینوس پر بنائیں:

    ```javascript
        
    class GameObject {
      constructor(x, y) {
        this.x = x;
        this.y = y;
        this.dead = false;
        this.type = "";
        this.width = 0;
        this.height = 0;
        this.img = undefined;
      }
    
      draw(ctx) {
        ctx.drawImage(this.img, this.x, this.y, this.width, this.height);
      }
    }
    ```

    اب، اس GameObject کو بڑھا کر ہیرو اور دشمن بنائیں۔

    ```javascript
    class Hero extends GameObject {
      constructor(x, y) {
        ...it needs an x, y, type, and speed
      }
    }
    ```

    ```javascript
    class Enemy extends GameObject {
      constructor(x, y) {
        super(x, y);
        (this.width = 98), (this.height = 50);
        this.type = "Enemy";
        let id = setInterval(() => {
          if (this.y < canvas.height - this.height) {
            this.y += 5;
          } else {
            console.log('Stopped at', this.y)
            clearInterval(id);
          }
        }, 300)
      }
    }
    ```

2. **کی ایونٹ ہینڈلرز شامل کریں** تاکہ کی نیویگیشن کو ہینڈل کیا جا سکے (ہیرو کو اوپر/نیچے، بائیں/دائیں حرکت دیں)

   *یاد رکھیں* یہ ایک کارٹیسین سسٹم ہے، اوپر-بائیں `0,0` ہے۔ ڈیفالٹ رویے کو بند کرنے کے لیے کوڈ شامل کرنا بھی یاد رکھیں۔

   >اشارہ: اپنی onKeyDown فنکشن بنائیں اور اسے ونڈو سے منسلک کریں:

   ```javascript
    let onKeyDown = function (e) {
	      console.log(e.keyCode);
	        ...add the code from the lesson above to stop default behavior
	      }
    };

    window.addEventListener("keydown", onKeyDown);
   ```
    
   اس وقت اپنے براؤزر کنسول کو چیک کریں، اور دیکھیں کہ کی اسٹروکس لاگ ہو رہی ہیں۔

3. **[پب سب پیٹرن](../README.md) نافذ کریں**، یہ آپ کے کوڈ کو صاف رکھے گا جیسے آپ باقی حصے مکمل کریں گے۔

   ایسا کرنے کے لیے، آپ:

   1. **ونڈو پر ایک ایونٹ لسٹنر شامل کریں**:

       ```javascript
        window.addEventListener("keyup", (evt) => {
          if (evt.key === "ArrowUp") {
            eventEmitter.emit(Messages.KEY_EVENT_UP);
          } else if (evt.key === "ArrowDown") {
            eventEmitter.emit(Messages.KEY_EVENT_DOWN);
          } else if (evt.key === "ArrowLeft") {
            eventEmitter.emit(Messages.KEY_EVENT_LEFT);
          } else if (evt.key === "ArrowRight") {
            eventEmitter.emit(Messages.KEY_EVENT_RIGHT);
          }
        });
        ```

    1. **ایک EventEmitter کلاس بنائیں** تاکہ پیغامات کو شائع اور سبسکرائب کیا جا سکے:

        ```javascript
        class EventEmitter {
          constructor() {
            this.listeners = {};
          }
        
          on(message, listener) {
            if (!this.listeners[message]) {
              this.listeners[message] = [];
            }
            this.listeners[message].push(listener);
          }
        
          emit(message, payload = null) {
            if (this.listeners[message]) {
              this.listeners[message].forEach((l) => l(message, payload));
            }
          }
        }
        ```

    1. **کانسٹینٹس شامل کریں** اور EventEmitter کو سیٹ اپ کریں:

        ```javascript
        const Messages = {
          KEY_EVENT_UP: "KEY_EVENT_UP",
          KEY_EVENT_DOWN: "KEY_EVENT_DOWN",
          KEY_EVENT_LEFT: "KEY_EVENT_LEFT",
          KEY_EVENT_RIGHT: "KEY_EVENT_RIGHT",
        };
        
        let heroImg, 
            enemyImg, 
            laserImg,
            canvas, ctx, 
            gameObjects = [], 
            hero, 
            eventEmitter = new EventEmitter();
        ```

    1. **کھیل کو شروع کریں**

    ```javascript
    function initGame() {
      gameObjects = [];
      createEnemies();
      createHero();
    
      eventEmitter.on(Messages.KEY_EVENT_UP, () => {
        hero.y -=5 ;
      })
    
      eventEmitter.on(Messages.KEY_EVENT_DOWN, () => {
        hero.y += 5;
      });
    
      eventEmitter.on(Messages.KEY_EVENT_LEFT, () => {
        hero.x -= 5;
      });
    
      eventEmitter.on(Messages.KEY_EVENT_RIGHT, () => {
        hero.x += 5;
      });
    }
    ```

1. **کھیل کا لوپ سیٹ اپ کریں**

   ونڈو.onload فنکشن کو ریفیکٹر کریں تاکہ کھیل کو شروع کریں اور ایک اچھے وقفے پر کھیل کا لوپ سیٹ اپ کریں۔ آپ لیزر بیم بھی شامل کریں گے:

    ```javascript
    window.onload = async () => {
      canvas = document.getElementById("canvas");
      ctx = canvas.getContext("2d");
      heroImg = await loadTexture("assets/player.png");
      enemyImg = await loadTexture("assets/enemyShip.png");
      laserImg = await loadTexture("assets/laserRed.png");
    
      initGame();
      let gameLoopId = setInterval(() => {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        ctx.fillStyle = "black";
        ctx.fillRect(0, 0, canvas.width, canvas.height);
        drawGameObjects(ctx);
      }, 100)
      
    };
    ```

5. **کوڈ شامل کریں** تاکہ دشمنوں کو ایک خاص وقفے پر حرکت دی جا سکے

    `createEnemies()` فنکشن کو ریفیکٹر کریں تاکہ دشمنوں کو بنائیں اور انہیں نئے gameObjects کلاس میں دھکیلیں:

    ```javascript
    function createEnemies() {
      const MONSTER_TOTAL = 5;
      const MONSTER_WIDTH = MONSTER_TOTAL * 98;
      const START_X = (canvas.width - MONSTER_WIDTH) / 2;
      const STOP_X = START_X + MONSTER_WIDTH;
    
      for (let x = START_X; x < STOP_X; x += 98) {
        for (let y = 0; y < 50 * 5; y += 50) {
          const enemy = new Enemy(x, y);
          enemy.img = enemyImg;
          gameObjects.push(enemy);
        }
      }
    }
    ```
    
    اور ایک `createHero()` فنکشن شامل کریں تاکہ ہیرو کے لیے اسی طرح کا عمل کیا جا سکے۔

    ```javascript
    function createHero() {
      hero = new Hero(
        canvas.width / 2 - 45,
        canvas.height - canvas.height / 4
      );
      hero.img = heroImg;
      gameObjects.push(hero);
    }
    ```

    اور آخر میں، ایک `drawGameObjects()` فنکشن شامل کریں تاکہ ڈرائنگ شروع کی جا سکے:

    ```javascript
    function drawGameObjects(ctx) {
      gameObjects.forEach(go => go.draw(ctx));
    }
    ```

    آپ کے دشمن آپ کے ہیرو اسپیس شپ پر حملہ کرنا شروع کر دیں گے!

---

## GitHub Copilot ایجنٹ چیلنج 🚀

ایجنٹ موڈ کا استعمال کرتے ہوئے درج ذیل چیلنج مکمل کریں:

**تفصیل:** خلائی کھیل کو بہتر بنائیں تاکہ باؤنڈری ڈیٹیکشن اور ہموار حرکت کنٹرولز نافذ کریں۔ یہ چیلنج آپ کو کھیل کی چیزوں کی ہیرا پھیری، ایونٹ ہینڈلنگ، اور کینوس رینڈرنگ تکنیکوں کی مشق کرنے میں مدد دے گا۔

**پرومپٹ:** ایک باؤنڈری ڈیٹیکشن سسٹم بنائیں جو ہیرو اسپیس شپ کو کینوس کی حدود سے باہر جانے سے روکے۔ اس کے علاوہ، ایک ہموار حرکت کا نظام نافذ کریں جہاں ایرو کیز کو دبائے رکھنے سے مسلسل حرکت ہو بجائے ایک قدمی حرکت کے۔ یقینی بنائیں کہ ہیرو فوراً رک جائے جب کیز چھوڑ دی جائیں اور جب ہیرو باؤنڈری سے ٹکرائے تو بصری فیڈبیک شامل کریں (جیسے مختصر رنگ کی تبدیلی یا چمک کا اثر)۔

## 🚀 چیلنج

جیسا کہ آپ دیکھ سکتے ہیں، آپ کا کوڈ 'اسپاگٹی کوڈ' میں تبدیل ہو سکتا ہے جب آپ فنکشنز، ویریبلز اور کلاسز شامل کرنا شروع کرتے ہیں۔ آپ اپنے کوڈ کو زیادہ قابل مطالعہ بنانے کے لیے اسے بہتر طریقے سے کیسے منظم کر سکتے ہیں؟ اپنے کوڈ کو منظم کرنے کے لیے ایک نظام کا خاکہ بنائیں، چاہے وہ ابھی بھی ایک فائل میں موجود ہو۔

## لیکچر کے بعد کا کوئز

[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/34)

## جائزہ اور خود مطالعہ

جبکہ ہم اپنے کھیل کو فریم ورک کے بغیر لکھ رہے ہیں، کھیل کی ترقی کے لیے بہت سے جاوا اسکرپٹ پر مبنی کینوس فریم ورک موجود ہیں۔ ان کے بارے میں کچھ وقت لے کر [پڑھائی کریں](https://github.com/collections/javascript-game-engines)۔

## اسائنمنٹ

[اپنے کوڈ پر تبصرہ کریں](assignment.md)

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔