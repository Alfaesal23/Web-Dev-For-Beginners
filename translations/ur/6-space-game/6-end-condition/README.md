<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7be341decc162fb251a9e0851b6600f6",
  "translation_date": "2025-10-20T20:57:08+00:00",
  "source_file": "6-space-game/6-end-condition/README.md",
  "language_code": "ur"
}
-->
# خلائی کھیل بنائیں حصہ 6: اختتام اور دوبارہ شروع کریں

## لیکچر سے پہلے کا کوئز

[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/39)

کھیل میں *اختتام کی حالت* کو ظاہر کرنے کے مختلف طریقے ہیں۔ یہ آپ پر منحصر ہے کہ آپ کھیل کے تخلیق کار کے طور پر فیصلہ کریں کہ کھیل کیوں ختم ہوا۔ یہاں کچھ وجوہات ہیں، اگر ہم فرض کریں کہ ہم اس خلائی کھیل کے بارے میں بات کر رہے ہیں جو آپ نے اب تک بنایا ہے:

- **`N` دشمن جہاز تباہ ہو چکے ہیں**: یہ کافی عام ہے کہ اگر آپ کھیل کو مختلف سطحوں میں تقسیم کریں تو آپ کو ایک سطح مکمل کرنے کے لیے `N` دشمن جہاز تباہ کرنے کی ضرورت ہو۔
- **آپ کا جہاز تباہ ہو گیا ہے**: یقینی طور پر ایسے کھیل موجود ہیں جہاں اگر آپ کا جہاز تباہ ہو جائے تو آپ کھیل ہار جاتے ہیں۔ ایک اور عام طریقہ یہ ہے کہ آپ کے پاس زندگیوں کا تصور ہو۔ ہر بار جب آپ کا جہاز تباہ ہوتا ہے تو یہ ایک زندگی کم کر دیتا ہے۔ جب تمام زندگیاں ختم ہو جاتی ہیں تو آپ کھیل ہار جاتے ہیں۔
- **آپ نے `N` پوائنٹس جمع کیے ہیں**: ایک اور عام اختتام کی حالت یہ ہے کہ آپ پوائنٹس جمع کریں۔ آپ پوائنٹس کیسے حاصل کرتے ہیں یہ آپ پر منحصر ہے لیکن یہ کافی عام ہے کہ مختلف سرگرمیوں جیسے دشمن جہاز کو تباہ کرنے یا شاید ان اشیاء کو جمع کرنے پر پوائنٹس دیے جائیں جو اشیاء تباہ ہونے پر *گرتی* ہیں۔
- **ایک سطح مکمل کریں**: اس میں کئی شرائط شامل ہو سکتی ہیں جیسے `X` دشمن جہاز تباہ، `Y` پوائنٹس جمع کیے گئے یا شاید ایک مخصوص شے جمع کی گئی ہو۔

## دوبارہ شروع کرنا

اگر لوگ آپ کے کھیل سے لطف اندوز ہوتے ہیں تو وہ ممکنہ طور پر اسے دوبارہ کھیلنا چاہیں گے۔ جب کھیل کسی بھی وجہ سے ختم ہو جائے تو آپ کو دوبارہ شروع کرنے کا متبادل پیش کرنا چاہیے۔

✅ تھوڑا سوچیں کہ کن حالات میں آپ کو لگتا ہے کہ کھیل ختم ہوتا ہے، اور پھر آپ کو دوبارہ شروع کرنے کے لیے کیسے کہا جاتا ہے۔

## کیا بنانا ہے

آپ اپنے کھیل میں یہ اصول شامل کریں گے:

1. **کھیل جیتنا**۔ جب تمام دشمن جہاز تباہ ہو جائیں، تو آپ کھیل جیت جاتے ہیں۔ اس کے علاوہ، کسی قسم کا فتح کا پیغام دکھائیں۔
1. **دوبارہ شروع کریں**۔ جب آپ کی تمام زندگیاں ختم ہو جائیں یا کھیل جیت لیا جائے، تو آپ کو کھیل دوبارہ شروع کرنے کا ایک طریقہ پیش کرنا چاہیے۔ یاد رکھیں! آپ کو کھیل کو دوبارہ شروع کرنے کی ضرورت ہوگی اور پچھلی کھیل کی حالت کو صاف کرنا ہوگا۔

## تجویز کردہ مراحل

`your-work` سب فولڈر میں وہ فائلیں تلاش کریں جو آپ کے لیے بنائی گئی ہیں۔ اس میں درج ذیل شامل ہونا چاہیے:

```bash
-| assets
  -| enemyShip.png
  -| player.png
  -| laserRed.png
  -| life.png
-| index.html
-| app.js
-| package.json
```

آپ اپنے پروجیکٹ کو `your_work` فولڈر میں درج ذیل کمانڈ کے ذریعے شروع کریں:

```bash
cd your-work
npm start
```

اوپر دی گئی کمانڈ HTTP سرور کو ایڈریس `http://localhost:5000` پر شروع کرے گی۔ ایک براؤزر کھولیں اور اس ایڈریس کو درج کریں۔ آپ کا کھیل کھیلنے کے قابل حالت میں ہونا چاہیے۔

> ٹپ: Visual Studio Code میں وارننگز سے بچنے کے لیے، `window.onload` فنکشن کو `gameLoopId` کو بغیر `let` کے کال کرنے کے لیے ایڈٹ کریں، اور فائل کے اوپر `let gameLoopId;` کو الگ سے ڈکلیئر کریں۔

### کوڈ شامل کریں

1. **اختتام کی حالت کا ٹریک رکھیں**۔ کوڈ شامل کریں جو دشمنوں کی تعداد کا ٹریک رکھے، یا اگر ہیرو کا جہاز تباہ ہو گیا ہو، ان دو فنکشنز کو شامل کریں:

    ```javascript
    function isHeroDead() {
      return hero.life <= 0;
    }

    function isEnemiesDead() {
      const enemies = gameObjects.filter((go) => go.type === "Enemy" && !go.dead);
      return enemies.length === 0;
    }
    ```

1. **پیغام ہینڈلرز میں منطق شامل کریں**۔ `eventEmitter` کو ان حالات کو ہینڈل کرنے کے لیے ایڈٹ کریں:

    ```javascript
    eventEmitter.on(Messages.COLLISION_ENEMY_LASER, (_, { first, second }) => {
        first.dead = true;
        second.dead = true;
        hero.incrementPoints();

        if (isEnemiesDead()) {
          eventEmitter.emit(Messages.GAME_END_WIN);
        }
    });

    eventEmitter.on(Messages.COLLISION_ENEMY_HERO, (_, { enemy }) => {
        enemy.dead = true;
        hero.decrementLife();
        if (isHeroDead())  {
          eventEmitter.emit(Messages.GAME_END_LOSS);
          return; // loss before victory
        }
        if (isEnemiesDead()) {
          eventEmitter.emit(Messages.GAME_END_WIN);
        }
    });
    
    eventEmitter.on(Messages.GAME_END_WIN, () => {
        endGame(true);
    });
      
    eventEmitter.on(Messages.GAME_END_LOSS, () => {
      endGame(false);
    });
    ```

1. **نئے پیغام کی اقسام شامل کریں**۔ ان پیغامات کو constants object میں شامل کریں:

    ```javascript
    GAME_END_LOSS: "GAME_END_LOSS",
    GAME_END_WIN: "GAME_END_WIN",
    ```

2. **دوبارہ شروع کرنے کا کوڈ شامل کریں**۔ ایسا کوڈ شامل کریں جو منتخب کردہ بٹن کے دبانے پر کھیل کو دوبارہ شروع کرے۔

   1. **کلید دبانے پر سنیں `Enter`**۔ اپنے ونڈو کے eventListener کو اس دبانے کے لیے سننے کے لیے ایڈٹ کریں:

    ```javascript
     else if(evt.key === "Enter") {
        eventEmitter.emit(Messages.KEY_EVENT_ENTER);
      }
    ```

   1. **دوبارہ شروع کرنے کا پیغام شامل کریں**۔ اس پیغام کو اپنے Messages constant میں شامل کریں:

        ```javascript
        KEY_EVENT_ENTER: "KEY_EVENT_ENTER",
        ```

1. **کھیل کے اصول نافذ کریں**۔ درج ذیل کھیل کے اصول نافذ کریں:

   1. **کھلاڑی کی جیت کی حالت**۔ جب تمام دشمن جہاز تباہ ہو جائیں، تو فتح کا پیغام دکھائیں۔

      1. پہلے، ایک `displayMessage()` فنکشن بنائیں:

        ```javascript
        function displayMessage(message, color = "red") {
          ctx.font = "30px Arial";
          ctx.fillStyle = color;
          ctx.textAlign = "center";
          ctx.fillText(message, canvas.width / 2, canvas.height / 2);
        }
        ```

      1. ایک `endGame()` فنکشن بنائیں:

        ```javascript
        function endGame(win) {
          clearInterval(gameLoopId);
        
          // set a delay so we are sure any paints have finished
          setTimeout(() => {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = "black";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            if (win) {
              displayMessage(
                "Victory!!! Pew Pew... - Press [Enter] to start a new game Captain Pew Pew",
                "green"
              );
            } else {
              displayMessage(
                "You died !!! Press [Enter] to start a new game Captain Pew Pew"
              );
            }
          }, 200)  
        }
        ```

   1. **دوبارہ شروع کرنے کی منطق**۔ جب تمام زندگیاں ختم ہو جائیں یا کھلاڑی نے کھیل جیت لیا ہو، تو دکھائیں کہ کھیل دوبارہ شروع کیا جا سکتا ہے۔ اس کے علاوہ، جب *دوبارہ شروع کرنے* کی کلید دبائی جائے تو کھیل دوبارہ شروع کریں (آپ فیصلہ کر سکتے ہیں کہ کون سی کلید دوبارہ شروع کرنے کے لیے میپ کی جائے)۔

      1. `resetGame()` فنکشن بنائیں:

        ```javascript
        function resetGame() {
          if (gameLoopId) {
            clearInterval(gameLoopId);
            eventEmitter.clear();
            initGame();
            gameLoopId = setInterval(() => {
              ctx.clearRect(0, 0, canvas.width, canvas.height);
              ctx.fillStyle = "black";
              ctx.fillRect(0, 0, canvas.width, canvas.height);
              drawPoints();
              drawLife();
              updateGameObjects();
              drawGameObjects(ctx);
            }, 100);
          }
        }
        ```

     1. `initGame()` میں کھیل کو دوبارہ شروع کرنے کے لیے `eventEmitter` کو کال شامل کریں:

        ```javascript
        eventEmitter.on(Messages.KEY_EVENT_ENTER, () => {
          resetGame();
        });
        ```

     1. EventEmitter میں ایک `clear()` فنکشن شامل کریں:

        ```javascript
        clear() {
          this.listeners = {};
        }
        ```

👽 💥 🚀 مبارک ہو، کپتان! آپ کا کھیل مکمل ہو گیا ہے! شاباش! 🚀 💥 👽

---

## GitHub Copilot Agent Challenge 🚀

Agent mode استعمال کریں تاکہ درج ذیل چیلنج مکمل کریں:

**تفصیل:** خلائی کھیل کو بہتر بنائیں تاکہ ایک سطحی ترقی کا نظام نافذ کریں جس میں بڑھتی ہوئی مشکل اور اضافی خصوصیات ہوں۔

**پرومپٹ:** ایک کثیر سطحی خلائی کھیل کا نظام بنائیں جہاں ہر سطح میں زیادہ دشمن جہاز ہوں جن کی رفتار اور صحت میں اضافہ ہو۔ ایک اسکورنگ ملٹی پلائر شامل کریں جو ہر سطح کے ساتھ بڑھتا ہے، اور پاور اپس (جیسے تیز فائر یا شیلڈ) نافذ کریں جو دشمنوں کے تباہ ہونے پر تصادفی طور پر ظاہر ہوں۔ سطح مکمل کرنے کا بونس شامل کریں اور موجودہ سطح کو اسکرین پر موجودہ اسکور اور زندگیاں کے ساتھ دکھائیں۔

## 🚀 چیلنج

آواز شامل کریں! کیا آپ اپنے کھیل کو بہتر بنانے کے لیے آواز شامل کر سکتے ہیں، شاید جب کوئی لیزر ہٹ ہو، یا ہیرو مر جائے یا جیت جائے؟ اس [sandbox](https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_audio_play) کو دیکھیں تاکہ جاوا اسکرپٹ کا استعمال کرتے ہوئے آواز چلانے کا طریقہ سیکھ سکیں۔

## لیکچر کے بعد کا کوئز

[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/40)

## جائزہ اور خود مطالعہ

آپ کا کام ایک نیا نمونہ کھیل بنانا ہے، لہذا کچھ دلچسپ کھیلوں کو دریافت کریں تاکہ دیکھ سکیں کہ آپ کس قسم کا کھیل بنا سکتے ہیں۔

## اسائنمنٹ

[نمونہ کھیل بنائیں](assignment.md)

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔