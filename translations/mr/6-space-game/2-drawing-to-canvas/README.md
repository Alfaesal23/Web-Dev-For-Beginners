<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8b5774007ae6ee4fc35e1023c593c761",
  "translation_date": "2025-10-20T21:27:21+00:00",
  "source_file": "6-space-game/2-drawing-to-canvas/README.md",
  "language_code": "mr"
}
-->
# स्पेस गेम तयार करा भाग 2: हिरो आणि मॉन्स्टर्स कॅनव्हासवर कसे काढायचे

## प्री-लेक्चर क्विझ

[प्री-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/31)

## कॅनव्हास

कॅनव्हास हा एक HTML घटक आहे ज्यामध्ये डीफॉल्टने कोणताही कंटेंट नसतो; तो एक कोरा पृष्ठभाग असतो. तुम्हाला त्यावर काहीतरी काढून त्यात भर घालावी लागते.

✅ [कॅनव्हास API बद्दल अधिक वाचा](https://developer.mozilla.org/docs/Web/API/Canvas_API) MDN वर.

हे सामान्यतः पृष्ठाच्या बॉडीचा भाग म्हणून घोषित केले जाते:

```html
<canvas id="myCanvas" width="200" height="100"></canvas>
```

वरील कोडमध्ये आपण `id`, `width` आणि `height` सेट करत आहोत.

- `id`: हे सेट करा जेणेकरून तुम्हाला त्यावर काम करताना संदर्भ मिळू शकेल.
- `width`: हा घटकाचा रुंदी आहे.
- `height`: हा घटकाचा उंची आहे.

## सोपी आकृती काढणे

कॅनव्हासवर गोष्टी काढण्यासाठी कार्टेशियन कोऑर्डिनेट सिस्टम वापरली जाते. त्यामुळे x-अक्ष आणि y-अक्ष वापरून एखादी गोष्ट कुठे आहे हे व्यक्त केले जाते. स्थान `0,0` हे वरच्या डाव्या बाजूला असते आणि कॅनव्हासची WIDTH आणि HEIGHT तुम्ही सेट केलेल्या तळाच्या उजव्या बाजूला असते.

![कॅनव्हासचा ग्रिड](../../../../translated_images/canvas_grid.5f209da785ded492a01ece440e3032afe51efa500cc2308e5ea4252487ceaf0b.mr.png)
> प्रतिमा [MDN](https://developer.mozilla.org/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes) वरून

कॅनव्हास घटकावर काढण्यासाठी तुम्हाला खालील चरणांमधून जावे लागेल:

1. **संदर्भ मिळवा** कॅनव्हास घटकाचा.
2. **संदर्भ मिळवा** कॅनव्हास घटकावर असलेल्या Context घटकाचा.
3. **ड्रॉइंग ऑपरेशन करा** Context घटक वापरून.

वरील चरणांसाठी कोड साधारणपणे असा दिसतो:

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

✅ कॅनव्हास API मुख्यतः 2D आकारांवर लक्ष केंद्रित करते, परंतु तुम्ही वेबसाइटवर 3D घटक देखील काढू शकता; यासाठी तुम्ही [WebGL API](https://developer.mozilla.org/docs/Web/API/WebGL_API) वापरू शकता.

कॅनव्हास API वापरून तुम्ही विविध गोष्टी काढू शकता जसे की:

- **ज्यामितीय आकार**, आम्ही आधीच आयत कसा काढायचा ते दाखवले आहे, परंतु तुम्ही आणखी बरेच काही काढू शकता.
- **मजकूर**, तुम्ही कोणत्याही फॉन्ट आणि रंगासह मजकूर काढू शकता.
- **प्रतिमा**, तुम्ही .jpg किंवा .png सारख्या प्रतिमा फाइलवर आधारित प्रतिमा काढू शकता.

✅ प्रयत्न करा! तुम्हाला आयत कसा काढायचा हे माहित आहे, तुम्ही पृष्ठावर वर्तुळ काढू शकता का? CodePen वर काही मनोरंजक कॅनव्हास रेखाटन पहा. येथे एक [खूप प्रभावी उदाहरण](https://codepen.io/dissimulate/pen/KrAwx) आहे.

## प्रतिमा ऍसेट लोड करा आणि काढा

तुम्ही `Image` ऑब्जेक्ट तयार करून आणि त्याच्या `src` प्रॉपर्टी सेट करून प्रतिमा ऍसेट लोड करता. नंतर तुम्ही `load` इव्हेंट ऐकता जेणेकरून ते वापरण्यास तयार असल्याचे तुम्हाला कळेल. कोड असा दिसतो:

### ऍसेट लोड करा

```javascript
const img = new Image();
img.src = 'path/to/my/image.png';
img.onload = () => {
  // image loaded and ready to be used
}
```

### ऍसेट लोड पॅटर्न

वरील कोड एका संरचनेत गुंडाळणे शिफारसीय आहे, त्यामुळे ते वापरण्यास सोपे होते आणि ते पूर्णपणे लोड झाल्यावरच तुम्ही त्यावर काम करू शकता:

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

गेम ऍसेट स्क्रीनवर काढण्यासाठी तुमचा कोड असा दिसेल:

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

## आता तुमचा गेम तयार करण्याची वेळ आली आहे

### काय तयार करायचे

तुम्ही कॅनव्हास घटकासह एक वेब पृष्ठ तयार कराल. ते काळ्या स्क्रीनवर `1024*768` रेंडर करेल. आम्ही तुम्हाला दोन प्रतिमा दिल्या आहेत:

- हिरो शिप

   ![हिरो शिप](../../../../translated_images/player.dd24c1afa8c71e9b82b2958946d4bad13308681392d4b5ddcc61a0e818ef8088.mr.png)

- 5*5 मॉन्स्टर

   ![मॉन्स्टर शिप](../../../../translated_images/enemyShip.5df2a822c16650c2fb3c06652e8ec8120cdb9122a6de46b9a1a56d54db22657f.mr.png)

### विकास सुरू करण्यासाठी शिफारस केलेले चरण

`your-work` सब फोल्डरमध्ये तयार केलेल्या फाइल्स शोधा. त्यात खालील गोष्टी असाव्यात:

```bash
-| assets
  -| enemyShip.png
  -| player.png
-| index.html
-| app.js
-| package.json
```

Visual Studio Code मध्ये या फोल्डरची कॉपी उघडा. तुम्हाला स्थानिक विकास वातावरण सेटअप करणे आवश्यक आहे, प्राधान्याने Visual Studio Code सह NPM आणि Node स्थापित केलेले असावे. जर तुमच्या संगणकावर `npm` सेट केले नसेल, तर [ते कसे करायचे ते येथे आहे](https://www.npmjs.com/get-npm).

तुमचा प्रोजेक्ट सुरू करण्यासाठी `your_work` फोल्डरमध्ये जा:

```bash
cd your-work
npm start
```

वरील कोड `http://localhost:5000` या पत्त्यावर HTTP सर्व्हर सुरू करेल. ब्राउझर उघडा आणि तो पत्ता टाका. सध्या हे रिक्त पृष्ठ आहे, परंतु ते बदलले जाईल.

> टीप: स्क्रीनवरील बदल पाहण्यासाठी, तुमचा ब्राउझर रीफ्रेश करा.

### कोड जोडा

`your-work/app.js` मध्ये आवश्यक कोड जोडा आणि खालील सोडवा:

1. **काढा** काळ्या पार्श्वभूमीसह कॅनव्हास
   > टीप: `/app.js` मधील योग्य TODO अंतर्गत दोन ओळी जोडा, `ctx` घटक काळा सेट करा आणि वर/डाव्या कोऑर्डिनेट्स 0,0 वर सेट करा आणि कॅनव्हासची उंची आणि रुंदी समान ठेवा.
2. **लोड करा** टेक्सचर्स
   > टीप: `await loadTexture` वापरून आणि प्रतिमा पथ पास करून प्लेयर आणि शत्रू प्रतिमा जोडा. तुम्हाला त्या स्क्रीनवर अद्याप दिसणार नाहीत!
3. **हिरो काढा** स्क्रीनच्या मध्यभागी तळाच्या अर्ध्या भागात
   > टीप: हिरोImg स्क्रीनवर काढण्यासाठी `drawImage` API वापरा, `canvas.width / 2 - 45` आणि `canvas.height - canvas.height / 4)` सेट करा.
4. **5*5 मॉन्स्टर्स काढा**
   > टीप: आता तुम्ही स्क्रीनवर शत्रूंना काढण्यासाठी कोड अनकॉमेंट करू शकता. नंतर, `createEnemies` फंक्शनकडे जा आणि ते तयार करा.

   प्रथम, काही स्थिरांक सेट करा:

    ```javascript
    const MONSTER_TOTAL = 5;
    const MONSTER_WIDTH = MONSTER_TOTAL * 98;
    const START_X = (canvas.width - MONSTER_WIDTH) / 2;
    const STOP_X = START_X + MONSTER_WIDTH;
    ```

    नंतर, मॉन्स्टर्सच्या ऍरेला स्क्रीनवर काढण्यासाठी एक लूप तयार करा:

    ```javascript
    for (let x = START_X; x < STOP_X; x += 98) {
        for (let y = 0; y < 50 * 5; y += 50) {
          ctx.drawImage(enemyImg, x, y);
        }
      }
    ```

## परिणाम

पूर्ण झालेला परिणाम असा दिसावा:

![काळ्या स्क्रीनवर हिरो आणि 5*5 मॉन्स्टर्स](../../../../translated_images/partI-solution.36c53b48c9ffae2a5e15496b23b604ba5393433e4bf91608a7a0a020eb7a2691.mr.png)

## सोल्यूशन

कृपया प्रथम स्वतः सोडवण्याचा प्रयत्न करा, परंतु जर तुम्हाला अडचण आली तर [सोल्यूशन](../../../../6-space-game/2-drawing-to-canvas/solution/app.js) पहा.

---

## GitHub Copilot Agent Challenge 🚀

Agent मोड वापरून खालील चॅलेंज पूर्ण करा:

**वर्णन:** तुम्ही शिकलेल्या Canvas API तंत्रांचा वापर करून तुमच्या स्पेस गेम कॅनव्हासमध्ये व्हिज्युअल इफेक्ट्स आणि इंटरॅक्टिव्ह घटक जोडा.

**प्रॉम्प्ट:** `enhanced-canvas.html` नावाची नवीन फाइल तयार करा ज्यामध्ये कॅनव्हास असेल जो पार्श्वभूमीवर अॅनिमेटेड तारे, हिरो शिपसाठी पल्सिंग हेल्थ बार आणि हळूहळू खाली जाणारे शत्रू शिप्स दाखवेल. यादृश्ट कोड लिहा जो कॅनव्हासवर रँडम पोझिशन्स आणि अपॅसिटी वापरून तारे काढतो, हेल्थ बार लागू करतो जो हेल्थ लेव्हलनुसार रंग बदलतो (हिरवा > पिवळा > लाल), आणि शत्रू शिप्स वेगवेगळ्या गतीने स्क्रीनवर खाली हलवतो.

## 🚀 चॅलेंज

तुम्ही 2D-केंद्रित Canvas API बद्दल शिकला आहात; [WebGL API](https://developer.mozilla.org/docs/Web/API/WebGL_API) बद्दल वाचा आणि 3D ऑब्जेक्ट काढण्याचा प्रयत्न करा.

## पोस्ट-लेक्चर क्विझ

[पोस्ट-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/32)

## पुनरावलोकन आणि स्व-अभ्यास

Canvas API बद्दल अधिक जाणून घ्या [याबद्दल वाचून](https://developer.mozilla.org/docs/Web/API/Canvas_API).

## असाइनमेंट

[Canvas API सह खेळा](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपयास लक्षात ठेवा की स्वयंचलित भाषांतरांमध्ये त्रुटी किंवा अचूकतेचा अभाव असू शकतो. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून उद्भवलेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार नाही.