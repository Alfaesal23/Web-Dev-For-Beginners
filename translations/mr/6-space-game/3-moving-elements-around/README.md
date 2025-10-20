<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "03f5022615bbc23417d5af42943d12f5",
  "translation_date": "2025-10-20T21:26:58+00:00",
  "source_file": "6-space-game/3-moving-elements-around/README.md",
  "language_code": "mr"
}
-->
# स्पेस गेम तयार करा भाग ३: गती जोडणे

## प्री-लेक्चर क्विझ

[प्री-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/33)

गेम्स मजेदार होण्यासाठी स्क्रीनवर एलियन्स फिरत असणे आवश्यक आहे! या गेममध्ये, आपण दोन प्रकारच्या गतींचा वापर करू:

- **कीबोर्ड/माऊस गती**: जेव्हा वापरकर्ता कीबोर्ड किंवा माऊस वापरून स्क्रीनवरील वस्तू हलवतो.
- **गेम-प्रेरित गती**: जेव्हा गेम विशिष्ट वेळेच्या अंतराने वस्तू हलवतो.

तर स्क्रीनवर वस्तू कशा हलवायच्या? हे सर्व कार्टेशियन कोऑर्डिनेट्सबद्दल आहे: आपण वस्तूचे स्थान (x, y) बदलतो आणि नंतर स्क्रीन पुन्हा रेखाटतो.

सामान्यतः स्क्रीनवर *गती* साध्य करण्यासाठी आपल्याला खालील चरणांची आवश्यकता असते:

1. वस्तूसाठी **नवीन स्थान सेट करा**; वस्तू हलवली गेली आहे असे जाणवण्यासाठी हे आवश्यक आहे.
2. **स्क्रीन साफ करा**, स्क्रीन पुन्हा रेखाटण्याच्या दरम्यान साफ ​​करणे आवश्यक आहे. आपण पार्श्वभूमी रंगाने भरलेला आयत रेखाटून ते साफ करू शकतो.
3. **वस्तूचे नवीन ठिकाणी पुन्हा रेखाटन करा**. असे केल्याने आपण वस्तू एका ठिकाणाहून दुसऱ्या ठिकाणी हलवणे साध्य करतो.

कोडमध्ये हे असे दिसू शकते:

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

✅ आपल्याला असे का वाटते की आपल्या हिरोला अनेक फ्रेम्स प्रति सेकंद पुन्हा रेखाटल्याने कार्यक्षमतेवर परिणाम होऊ शकतो? [या पॅटर्नच्या पर्यायांबद्दल](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Optimizing_canvas) वाचा.

## कीबोर्ड इव्हेंट्स हाताळा

आपण कोडशी विशिष्ट इव्हेंट्स जोडून इव्हेंट्स हाताळतो. कीबोर्ड इव्हेंट्स संपूर्ण विंडोवर ट्रिगर होतात तर माऊस इव्हेंट्स जसे की `क्लिक` विशिष्ट घटकावर क्लिक करण्याशी जोडले जाऊ शकतात. आपण या प्रकल्पात कीबोर्ड इव्हेंट्स वापरणार आहोत.

इव्हेंट हाताळण्यासाठी, आपल्याला विंडोच्या `addEventListener()` पद्धतीचा वापर करावा लागतो आणि त्याला दोन इनपुट पॅरामीटर्स द्यावे लागतात. पहिला पॅरामीटर इव्हेंटचे नाव आहे, उदाहरणार्थ `keyup`. दुसरा पॅरामीटर म्हणजे इव्हेंट घडल्यावर कॉल होणारी फंक्शन.

उदाहरण येथे आहे:

```javascript
window.addEventListener('keyup', (evt) => {
  // `evt.key` = string representation of the key
  if (evt.key === 'ArrowUp') {
    // do something
  }
})
```

की इव्हेंट्ससाठी, इव्हेंटवर दोन प्रॉपर्टीज असतात ज्याचा वापर आपण कोणती की दाबली आहे हे पाहण्यासाठी करू शकतो:

- `key`, ही दाबलेल्या कीची स्ट्रिंग रिप्रजेंटेशन आहे, उदाहरणार्थ `ArrowUp`
- `keyCode`, ही एक नंबर रिप्रजेंटेशन आहे, उदाहरणार्थ `37`, जे `ArrowLeft` शी संबंधित आहे.

✅ की इव्हेंट मॅनिप्युलेशन गेम डेव्हलपमेंटच्या बाहेर उपयुक्त आहे. या तंत्राचा आणखी कोणत्या उपयोगासाठी विचार करू शकता?

### विशेष की: एक चेतावणी

काही *विशेष* की आहेत ज्या विंडोवर परिणाम करतात. याचा अर्थ असा की जर आपण `keyup` इव्हेंट ऐकत असाल आणि आपण या विशेष कींचा वापर करून आपल्या हिरोला हलवले तर ते क्षैतिज स्क्रोलिंग देखील करेल. त्यामुळे आपण गेम तयार करताना हे अंगभूत ब्राउझर वर्तन *बंद* करू इच्छित असाल. आपल्याला अशा प्रकारचा कोड आवश्यक आहे:

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

वरील कोड सुनिश्चित करेल की अॅरो-की आणि स्पेस कीचे *डिफॉल्ट* वर्तन बंद केले जाईल. *बंद* यंत्रणा तेव्हा होते जेव्हा आपण `e.preventDefault()` कॉल करतो.

## गेम-प्रेरित गती

आम्ही `setTimeout()` किंवा `setInterval()` सारख्या टाइमर्सचा वापर करून वस्तू स्वतःच हलवू शकतो, जे प्रत्येक टिक किंवा वेळेच्या अंतराने वस्तूचे स्थान अपडेट करतात. हे कसे दिसू शकते:

```javascript
let id = setInterval(() => {
  //move the enemy on the y axis
  enemy.y += 10;
})
```

## गेम लूप

गेम लूप ही एक संकल्पना आहे जी मूलतः एक फंक्शन आहे जी नियमित अंतराने कॉल केली जाते. याला गेम लूप म्हणतात कारण वापरकर्त्याला दिसणारे सर्व काही लूपमध्ये रेखाटले जाते. गेम लूप गेमचा भाग असलेल्या सर्व गेम ऑब्जेक्ट्सचा वापर करते, त्यापैकी सर्व रेखाटते, जोपर्यंत काही कारणास्तव गेमचा भाग राहू नये. उदाहरणार्थ, जर एखादी वस्तू शत्रू असेल जी लेसरने हिट झाली आणि फुटली, तर ती सध्याच्या गेम लूपचा भाग राहणार नाही (याबद्दल पुढील धड्यांमध्ये अधिक शिकाल).

गेम लूप कोडमध्ये सामान्यतः कसे दिसते:

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

वरील लूप प्रत्येक `200` मिलिसेकंदांमध्ये कॅनव्हास पुन्हा रेखाटण्यासाठी कॉल केला जातो. आपल्या गेमसाठी योग्य वाटणारे सर्वोत्तम अंतर निवडण्याची क्षमता आपल्याला आहे.

## स्पेस गेम सुरू ठेवणे

आपण विद्यमान कोड घेऊन त्याचा विस्तार कराल. भाग I मध्ये पूर्ण केलेल्या कोडसह प्रारंभ करा किंवा [भाग II- स्टार्टर](../../../../6-space-game/3-moving-elements-around/your-work) मधील कोड वापरा.

- **हिरो हलवणे**: आपण अॅरो की वापरून हिरो हलवू शकता याची खात्री करण्यासाठी कोड जोडाल.
- **शत्रू हलवा**: आपण शत्रू वरून खाली दिलेल्या दराने हलवू शकता याची खात्री करण्यासाठी कोड देखील जोडणे आवश्यक आहे.

## शिफारस केलेले चरण

`your-work` सब फोल्डरमध्ये तयार केलेल्या फाइल्स शोधा. त्यात खालील गोष्टी असाव्यात:

```bash
-| assets
  -| enemyShip.png
  -| player.png
-| index.html
-| app.js
-| package.json
```

आपण आपला प्रकल्प `your_work` फोल्डरमध्ये खालीलप्रमाणे सुरू करता:

```bash
cd your-work
npm start
```

वरील HTTP सर्व्हर पत्ता `http://localhost:5000` वर सुरू करेल. ब्राउझर उघडा आणि तो पत्ता इनपुट करा, सध्या तो हिरो आणि सर्व शत्रूंना रेंडर करेल; काहीही हलत नाही - अजून!

### कोड जोडा

1. **हिरो**, **शत्रू**, आणि **गेम ऑब्जेक्ट** साठी समर्पित ऑब्जेक्ट्स जोडा, त्यांच्याकडे `x` आणि `y` प्रॉपर्टीज असाव्यात. ([इनहेरिटन्स किंवा कंपोझिशन](../README.md) याबद्दलच्या भागाची आठवण ठेवा).

   *सूचना* `गेम ऑब्जेक्ट` हा `x` आणि `y` असलेला आणि स्वतःला कॅनव्हासवर रेखाटण्याची क्षमता असलेला असावा.

   >टीप: खाली दिलेल्या प्रकारे त्याचा कन्स्ट्रक्टर परिभाषित करून नवीन GameObject क्लास जोडणे सुरू करा आणि नंतर कॅनव्हासवर रेखाटणे:

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

    आता, या GameObject ला विस्तार करून हिरो आणि शत्रू तयार करा.

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

2. **की-इव्हेंट हँडलर्स जोडा** की नेव्हिगेशन हाताळण्यासाठी (हिरो वर/खाली डाव्या/उजव्या बाजूला हलवा)

   *लक्षात ठेवा* हे एक कार्टेशियन सिस्टम आहे, टॉप-लेफ्ट `0,0` आहे. तसेच *डिफॉल्ट वर्तन* थांबवण्यासाठी कोड जोडणे लक्षात ठेवा.

   >टीप: आपले onKeyDown फंक्शन तयार करा आणि ते विंडोशी जोडा:

   ```javascript
    let onKeyDown = function (e) {
	      console.log(e.keyCode);
	        ...add the code from the lesson above to stop default behavior
	      }
    };

    window.addEventListener("keydown", onKeyDown);
   ```
    
   या टप्प्यावर आपला ब्राउझर कन्सोल तपासा आणि कीस्ट्रोक्स लॉग होत असल्याचे पहा.

3. **अंमलात आणा** [Pub sub pattern](../README.md), उर्वरित भागांचे अनुसरण करताना आपला कोड स्वच्छ ठेवेल.

   हे शेवटचे भाग करण्यासाठी, आपण:

   1. **विंडोवर इव्हेंट लिसनर जोडा**:

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

    1. **EventEmitter क्लास तयार करा** संदेश प्रकाशित आणि सबस्क्राइब करण्यासाठी:

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

    1. **कॉन्स्टंट्स जोडा** आणि EventEmitter सेट करा:

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

    1. **गेम प्रारंभ करा**

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

1. **गेम लूप सेट करा**

   विंडो.onload फंक्शनला रिफॅक्टर करा गेम प्रारंभ करण्यासाठी आणि चांगल्या अंतरावर गेम लूप सेट करण्यासाठी. आपण लेसर बीम देखील जोडाल:

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

5. **कोड जोडा** शत्रूंना विशिष्ट अंतरावर हलवण्यासाठी

    `createEnemies()` फंक्शनला रिफॅक्टर करा शत्रू तयार करण्यासाठी आणि त्यांना नवीन gameObjects क्लासमध्ये पुश करण्यासाठी:

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
    
    आणि हिरोसाठी समान प्रक्रिया करण्यासाठी `createHero()` फंक्शन जोडा.

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

    आणि शेवटी, गेम ऑब्जेक्ट्स रेखाटणे सुरू करण्यासाठी `drawGameObjects()` फंक्शन जोडा:

    ```javascript
    function drawGameObjects(ctx) {
      gameObjects.forEach(go => go.draw(ctx));
    }
    ```

    आपले शत्रू आपल्या हिरो स्पेसशिपवर हल्ला करण्यास सुरुवात करतील!

---

## GitHub Copilot Agent Challenge 🚀

Agent मोड वापरून खालील आव्हान पूर्ण करा:

**वर्णन:** कॅनव्हासच्या सीमांच्या बाहेर हिरो स्पेसशिप हलवण्यापासून प्रतिबंधित करणारी बाउंडरी डिटेक्शन प्रणाली अंमलात आणा आणि स्मूथ मूव्हमेंट कंट्रोल्स लागू करा. हे आव्हान आपल्याला गेम ऑब्जेक्ट मॅनिप्युलेशन, इव्हेंट हँडलिंग, आणि कॅनव्हास रेंडरिंग तंत्रांचा सराव करण्यास मदत करेल.

**प्रॉम्प्ट:** अशी बाउंडरी डिटेक्शन प्रणाली तयार करा जी हिरो स्पेसशिपला कॅनव्हासच्या सीमांच्या बाहेर हलवण्यापासून प्रतिबंधित करते. याशिवाय, स्मूथ मूव्हमेंट प्रणाली अंमलात आणा जिथे अॅरो की दाबून ठेवल्याने सतत गती निर्माण होते, एकाच पायरीच्या गतीऐवजी. हिरो की सोडताच लगेच थांबला पाहिजे आणि सीमेला धडक दिल्यास व्हिज्युअल फीडबॅक द्या (जसे की थोडा रंग बदल किंवा ग्लो इफेक्ट).

## 🚀 आव्हान

जसे आपण पाहू शकता, जेव्हा आपण फंक्शन्स, व्हेरिएबल्स आणि क्लासेस जोडायला सुरुवात करता तेव्हा आपला कोड 'स्पॅगेटी कोड' मध्ये बदलू शकतो. आपला कोड अधिक वाचनीय होण्यासाठी आपण तो कसा चांगल्या प्रकारे आयोजित करू शकता? आपला कोड कसा आयोजित करायचा याची प्रणाली रेखाटून ठेवा, जरी तो अजूनही एका फाइलमध्ये असेल.

## पोस्ट-लेक्चर क्विझ

[पोस्ट-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/34)

## पुनरावलोकन आणि स्व-अभ्यास

जरी आपण फ्रेमवर्क्स वापरल्याशिवाय आपला गेम लिहित आहोत, तरी गेम डेव्हलपमेंटसाठी अनेक जावास्क्रिप्ट-आधारित कॅनव्हास फ्रेमवर्क्स आहेत. याबद्दल [वाचनासाठी वेळ काढा](https://github.com/collections/javascript-game-engines).

## असाइनमेंट

[आपल्या कोडवर टिप्पणी द्या](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात ठेवा की स्वयंचलित भाषांतरांमध्ये त्रुटी किंवा अचूकतेचा अभाव असू शकतो. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून उद्भवलेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार राहणार नाही.