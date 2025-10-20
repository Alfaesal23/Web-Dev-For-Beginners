<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b5774007ae6ee4fc35e1023c593c761",
  "translation_date": "2025-10-20T20:56:50+00:00",
  "source_file": "6-space-game/2-drawing-to-canvas/README.md",
  "language_code": "ur"
}
-->
# خلائی کھیل بنائیں حصہ 2: ہیرو اور مونسٹرز کو کینوس پر بنائیں

## لیکچر سے پہلے کا کوئز

[لیکچر سے پہلے کا کوئز](https://ff-quizzes.netlify.app/web/quiz/31)

## کینوس

کینوس ایک HTML عنصر ہے جو ڈیفالٹ میں خالی ہوتا ہے؛ یہ ایک خالی تختہ ہے۔ آپ کو اس پر کچھ بنانے کے لیے اس پر ڈرائنگ کرنی ہوگی۔

✅ [کینوس API کے بارے میں مزید پڑھیں](https://developer.mozilla.org/docs/Web/API/Canvas_API) MDN پر۔

یہ عام طور پر صفحے کے باڈی کے حصے کے طور پر اس طرح اعلان کیا جاتا ہے:

```html
<canvas id="myCanvas" width="200" height="100"></canvas>
```

اوپر ہم نے `id`, `width` اور `height` سیٹ کیے ہیں۔

- `id`: اسے سیٹ کریں تاکہ آپ اس کا حوالہ حاصل کر سکیں جب آپ کو اس کے ساتھ تعامل کرنے کی ضرورت ہو۔
- `width`: یہ عنصر کی چوڑائی ہے۔
- `height`: یہ عنصر کی اونچائی ہے۔

## سادہ جیومیٹری ڈرائنگ

کینوس چیزوں کو ڈرائنگ کرنے کے لیے کارٹیسین کوآرڈینیٹ سسٹم استعمال کرتا ہے۔ اس لیے یہ کسی چیز کے مقام کو ظاہر کرنے کے لیے x-axis اور y-axis استعمال کرتا ہے۔ مقام `0,0` اوپر بائیں طرف ہوتا ہے اور نیچے دائیں وہ جگہ ہوتی ہے جو آپ نے کینوس کی چوڑائی اور اونچائی کے طور پر مقرر کی ہے۔

![کینوس کا گرڈ](../../../../translated_images/canvas_grid.5f209da785ded492a01ece440e3032afe51efa500cc2308e5ea4252487ceaf0b.ur.png)
> تصویر [MDN](https://developer.mozilla.org/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes) سے

کینوس عنصر پر ڈرائنگ کرنے کے لیے آپ کو درج ذیل مراحل سے گزرنا ہوگا:

1. **حوالہ حاصل کریں** کینوس عنصر کا۔
1. **حوالہ حاصل کریں** کینوس عنصر پر موجود کانٹیکسٹ عنصر کا۔
1. **ڈرائنگ آپریشن انجام دیں** کانٹیکسٹ عنصر کا استعمال کرتے ہوئے۔

اوپر کے مراحل کے لیے کوڈ عام طور پر اس طرح نظر آتا ہے:

```javascript
// draws a red rectangle
//1. get the canvas reference
canvas = document.getElementById("myCanvas");

//2. set the context to 2D to draw basic shapes
ctx = canvas.getContext("2d");

//3. fill it with the color red
ctx.fillStyle = 'red';

//4. and draw a rectangle with these parameters, setting location and size
ctx.fillRect(0,0, 200, 200) // x,y,width, height
```

✅ کینوس API زیادہ تر 2D شکلوں پر مرکوز ہے، لیکن آپ ویب سائٹ پر 3D عناصر بھی بنا سکتے ہیں؛ اس کے لیے آپ [WebGL API](https://developer.mozilla.org/docs/Web/API/WebGL_API) استعمال کر سکتے ہیں۔

آپ کینوس API کے ساتھ مختلف چیزیں بنا سکتے ہیں جیسے:

- **جیومیٹریکل شکلیں**، ہم نے پہلے ہی دکھایا ہے کہ مستطیل کیسے بنائی جائے، لیکن آپ اور بھی بہت کچھ بنا سکتے ہیں۔
- **متن**، آپ اپنی مرضی کے کسی بھی فونٹ اور رنگ کے ساتھ متن بنا سکتے ہیں۔
- **تصاویر**، آپ کسی تصویر کے اثاثے جیسے .jpg یا .png کی بنیاد پر تصویر بنا سکتے ہیں۔

✅ اسے آزمائیں! آپ جانتے ہیں کہ مستطیل کیسے بنائی جائے، کیا آپ صفحے پر دائرہ بنا سکتے ہیں؟ CodePen پر کچھ دلچسپ کینوس ڈرائنگز دیکھیں۔ یہاں ایک [خاص طور پر متاثر کن مثال](https://codepen.io/dissimulate/pen/KrAwx) ہے۔

## تصویر کے اثاثے کو لوڈ کریں اور بنائیں

آپ تصویر کے اثاثے کو `Image` آبجیکٹ بنا کر اور اس کی `src` پراپرٹی سیٹ کر کے لوڈ کرتے ہیں۔ پھر آپ `load` ایونٹ کو سنتے ہیں تاکہ معلوم ہو سکے کہ یہ استعمال کے لیے تیار ہے۔ کوڈ اس طرح نظر آتا ہے:

### اثاثہ لوڈ کریں

```javascript
const img = new Image();
img.src = 'path/to/my/image.png';
img.onload = () => {
  // image loaded and ready to be used
}
```

### اثاثہ لوڈ کرنے کا پیٹرن

اوپر دیے گئے کوڈ کو اس طرح کے کنسٹرکٹ میں لپیٹنے کی سفارش کی جاتی ہے تاکہ اسے استعمال کرنا آسان ہو اور آپ صرف اس وقت اس میں تبدیلی کریں جب یہ مکمل طور پر لوڈ ہو جائے:

```javascript
function loadAsset(path) {
  return new Promise((resolve) => {
    const img = new Image();
    img.src = path;
    img.onload = () => {
      // image loaded and ready to be used
      resolve(img);
    }
  })
}

// use like so

async function run() {
  const heroImg = await loadAsset('hero.png')
  const monsterImg = await loadAsset('monster.png')
}

```

گیم کے اثاثے کو اسکرین پر بنانے کے لیے، آپ کا کوڈ اس طرح نظر آئے گا:

```javascript
async function run() {
  const heroImg = await loadAsset('hero.png')
  const monsterImg = await loadAsset('monster.png')

  canvas = document.getElementById("myCanvas");
  ctx = canvas.getContext("2d");
  ctx.drawImage(heroImg, canvas.width/2,canvas.height/2);
  ctx.drawImage(monsterImg, 0,0);
}
```

## اب وقت ہے کہ آپ اپنا گیم بنانا شروع کریں

### کیا بنانا ہے

آپ کو ایک ویب صفحہ بنانا ہوگا جس میں کینوس عنصر ہو۔ یہ ایک سیاہ اسکرین `1024*768` رینڈر کرے گا۔ ہم نے آپ کو دو تصاویر فراہم کی ہیں:

- ہیرو شپ

   ![ہیرو شپ](../../../../translated_images/player.dd24c1afa8c71e9b82b2958946d4bad13308681392d4b5ddcc61a0e818ef8088.ur.png)

- 5*5 مونسٹر

   ![مونسٹر شپ](../../../../translated_images/enemyShip.5df2a822c16650c2fb3c06652e8ec8120cdb9122a6de46b9a1a56d54db22657f.ur.png)

### ترقی شروع کرنے کے لیے تجویز کردہ مراحل

ان فائلوں کو تلاش کریں جو آپ کے لیے `your-work` سب فولڈر میں بنائی گئی ہیں۔ اس میں درج ذیل ہونا چاہیے:

```bash
-| assets
  -| enemyShip.png
  -| player.png
-| index.html
-| app.js
-| package.json
```

Visual Studio Code میں اس فولڈر کی ایک کاپی کھولیں۔ آپ کو ایک مقامی ترقیاتی ماحول ترتیب دینا ہوگا، ترجیحاً Visual Studio Code کے ساتھ NPM اور Node انسٹال کریں۔ اگر آپ کے کمپیوٹر پر `npm` سیٹ اپ نہیں ہے، [یہاں دیکھیں کہ یہ کیسے کریں](https://www.npmjs.com/get-npm)۔

اپنے پروجیکٹ کو شروع کریں اور `your_work` فولڈر پر جائیں:

```bash
cd your-work
npm start
```

اوپر دیے گئے کوڈ سے ایچ ٹی ٹی پی سرور ایڈریس `http://localhost:5000` پر شروع ہوگا۔ ایک براؤزر کھولیں اور اس ایڈریس کو درج کریں۔ یہ ابھی ایک خالی صفحہ ہے، لیکن یہ جلد ہی تبدیل ہو جائے گا۔

> نوٹ: اپنی اسکرین پر تبدیلیاں دیکھنے کے لیے، اپنے براؤزر کو ریفریش کریں۔

### کوڈ شامل کریں

`your-work/app.js` میں ضروری کوڈ شامل کریں تاکہ نیچے دیے گئے مسائل کو حل کیا جا سکے:

1. **کینوس بنائیں** سیاہ پس منظر کے ساتھ
   > ٹپ: `/app.js` میں مناسب TODO کے تحت دو لائنیں شامل کریں، `ctx` عنصر کو سیاہ سیٹ کریں اور اوپر/بائیں کوآرڈینیٹس کو 0,0 پر سیٹ کریں اور کینوس کی اونچائی اور چوڑائی کے برابر سیٹ کریں۔
2. **ٹیکسچرز لوڈ کریں**
   > ٹپ: کھلاڑی اور دشمن کی تصاویر کو `await loadTexture` کا استعمال کرتے ہوئے اور تصویر کے راستے کو پاس کرتے ہوئے شامل کریں۔ آپ انہیں ابھی اسکرین پر نہیں دیکھیں گے!
3. **ہیرو کو اسکرین کے نیچے کے نصف حصے کے مرکز میں بنائیں**
   > ٹپ: `drawImage` API کا استعمال کرتے ہوئے heroImg کو اسکرین پر بنائیں، `canvas.width / 2 - 45` اور `canvas.height - canvas.height / 4)` سیٹ کریں۔
4. **5*5 مونسٹرز بنائیں**
   > ٹپ: اب آپ اسکرین پر دشمنوں کو بنانے کے کوڈ کو ان کومنٹ کر سکتے ہیں۔ پھر، `createEnemies` فنکشن پر جائیں اور اسے مکمل کریں۔

   پہلے، کچھ کانسٹینٹس سیٹ کریں:

    ```javascript
    const MONSTER_TOTAL = 5;
    const MONSTER_WIDTH = MONSTER_TOTAL * 98;
    const START_X = (canvas.width - MONSTER_WIDTH) / 2;
    const STOP_X = START_X + MONSTER_WIDTH;
    ```

    پھر، ایک لوپ بنائیں تاکہ مونسٹرز کی array کو اسکرین پر بنایا جا سکے:

    ```javascript
    for (let x = START_X; x < STOP_X; x += 98) {
        for (let y = 0; y < 50 * 5; y += 50) {
          ctx.drawImage(enemyImg, x, y);
        }
      }
    ```

## نتیجہ

مکمل نتیجہ اس طرح نظر آنا چاہیے:

![سیاہ اسکرین جس پر ایک ہیرو اور 5*5 مونسٹرز ہیں](../../../../translated_images/partI-solution.36c53b48c9ffae2a5e15496b23b604ba5393433e4bf91608a7a0a020eb7a2691.ur.png)

## حل

براہ کرم پہلے خود اسے حل کرنے کی کوشش کریں لیکن اگر آپ پھنس جائیں تو [حل](../../../../6-space-game/2-drawing-to-canvas/solution/app.js) دیکھیں۔

---

## GitHub Copilot Agent چیلنج 🚀

Agent موڈ کا استعمال کرتے ہوئے درج ذیل چیلنج مکمل کریں:

**تفصیل:** اپنے خلائی کھیل کے کینوس کو Canvas API تکنیکوں کا استعمال کرتے ہوئے بصری اثرات اور انٹرایکٹو عناصر کے ساتھ بہتر بنائیں۔

**پرومپٹ:** ایک نئی فائل بنائیں جس کا نام `enhanced-canvas.html` ہو جس میں ایک کینوس ہو جو پس منظر میں متحرک ستارے دکھائے، ہیرو شپ کے لیے ایک پلسنگ ہیلتھ بار ہو، اور دشمن کے جہاز جو آہستہ آہستہ نیچے کی طرف حرکت کریں۔ جاوا اسکرپٹ کوڈ شامل کریں جو تصادفی پوزیشنز اور اوپیسٹی کا استعمال کرتے ہوئے چمکتے ستارے بنائے، ہیلتھ بار کو صحت کی سطح کے مطابق رنگ تبدیل کرنے کے لیے نافذ کرے (سبز > پیلا > سرخ)، اور دشمن کے جہازوں کو مختلف رفتار سے اسکرین کے نیچے حرکت دینے کے لیے متحرک کرے۔

## 🚀 چیلنج

آپ نے 2D پر مرکوز Canvas API کے ساتھ ڈرائنگ کے بارے میں سیکھا ہے؛ [WebGL API](https://developer.mozilla.org/docs/Web/API/WebGL_API) پر ایک نظر ڈالیں، اور 3D آبجیکٹ بنانے کی کوشش کریں۔

## لیکچر کے بعد کا کوئز

[لیکچر کے بعد کا کوئز](https://ff-quizzes.netlify.app/web/quiz/32)

## جائزہ اور خود مطالعہ

Canvas API کے بارے میں مزید جاننے کے لیے [اس کے بارے میں پڑھیں](https://developer.mozilla.org/docs/Web/API/Canvas_API)۔

## اسائنمنٹ

[Canvas API کے ساتھ کھیلیں](assignment.md)

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا غیر درستیاں ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ ہم اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے ذمہ دار نہیں ہیں۔