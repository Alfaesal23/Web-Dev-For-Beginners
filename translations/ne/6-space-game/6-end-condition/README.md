<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7be341decc162fb251a9e0851b6600f6",
  "translation_date": "2025-10-20T21:44:26+00:00",
  "source_file": "6-space-game/6-end-condition/README.md",
  "language_code": "ne"
}
-->
# स्पेस गेम बनाउनुहोस् भाग ६: अन्त्य र पुनः सुरु गर्नुहोस्

## प्रि-लेक्चर क्विज

[प्रि-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/39)

खेलमा *अन्त्यको अवस्था* व्यक्त गर्ने विभिन्न तरिकाहरू छन्। खेलको सृष्टिकर्ताको रूपमा, खेल किन समाप्त भएको हो भन्ने निर्णय गर्नु तपाईंको हातमा हुन्छ। यहाँ केही कारणहरू छन्, यदि हामीले तपाईंले अहिलेसम्म बनाउँदै आएको स्पेस गेमको बारेमा कुरा गरिरहेको छौं भने:

- **`N` शत्रु जहाजहरू नष्ट भएका छन्**: यदि तपाईंले खेललाई विभिन्न स्तरहरूमा विभाजन गर्नुभएको छ भने, `N` शत्रु जहाजहरू नष्ट गर्नुपर्ने सामान्य कुरा हो।
- **तपाईंको जहाज नष्ट भएको छ**: तपाईंको जहाज नष्ट भएमा खेल हार्ने खेलहरू पनि पक्कै छन्। अर्को सामान्य तरिका भनेको जीवनको अवधारणा हो। तपाईंको जहाज प्रत्येक पटक नष्ट हुँदा एक जीवन घट्छ। जब सबै जीवन समाप्त हुन्छ, तब तपाईं खेल हार्नुहुन्छ।
- **तपाईंले `N` अंक संकलन गर्नुभएको छ**: अर्को सामान्य अन्त्यको अवस्था भनेको तपाईंले अंक संकलन गर्नु हो। कसरी अंक प्राप्त गर्ने भन्ने कुरा तपाईंको हातमा हुन्छ, तर शत्रु जहाज नष्ट गर्दा वा नष्ट हुँदा वस्तुहरू संकलन गर्दा अंक दिनु सामान्य कुरा हो।
- **स्तर पूरा गर्नुहोस्**: यसले `X` शत्रु जहाजहरू नष्ट गर्नु, `Y` अंक संकलन गर्नु वा विशेष वस्तु संकलन गर्नु जस्ता विभिन्न अवस्थाहरू समावेश गर्न सक्छ।

## पुनः सुरु गर्नु

यदि मानिसहरूले तपाईंको खेल मन पराउँछन् भने, उनीहरूले यसलाई पुनः खेल्न चाहन सक्छन्। खेल कुनै पनि कारणले समाप्त भएपछि, तपाईंले पुनः सुरु गर्ने विकल्प दिनुपर्छ।

✅ सोच्नुहोस् कि कुन अवस्थाहरूमा खेल समाप्त हुन्छ, र त्यसपछि कसरी तपाईंलाई पुनः सुरु गर्न प्रेरित गरिन्छ।

## के निर्माण गर्ने

तपाईंले यी नियमहरू आफ्नो खेलमा थप्नु पर्नेछ:

1. **खेल जित्नुहोस्**। सबै शत्रु जहाजहरू नष्ट भएपछि, तपाईं खेल जित्नुहुन्छ। साथै, कुनै प्रकारको विजय सन्देश देखाउनुहोस्।
1. **पुनः सुरु गर्नुहोस्**। जब सबै जीवन समाप्त हुन्छ वा खेल जितिन्छ, तपाईंले खेल पुनः सुरु गर्ने तरिका दिनुपर्छ। सम्झनुहोस्! तपाईंले खेललाई पुनः आरम्भ गर्नुपर्नेछ र अघिल्लो खेलको अवस्था हटाउनु पर्नेछ।

## सिफारिस गरिएका चरणहरू

`your-work` उप फोल्डरमा तपाईंको लागि सिर्जना गरिएका फाइलहरू पत्ता लगाउनुहोस्। यसले निम्न समावेश गर्नुपर्छ:

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

तपाईं आफ्नो परियोजना `your_work` फोल्डरमा निम्न टाइप गरेर सुरु गर्नुहोस्:

```bash
cd your-work
npm start
```

माथिको कमाण्डले `http://localhost:5000` ठेगानामा HTTP सर्भर सुरु गर्नेछ। ब्राउजर खोल्नुहोस् र उक्त ठेगाना इनपुट गर्नुहोस्। तपाईंको खेल खेल्न योग्य अवस्थामा हुनुपर्छ।

> टिप: Visual Studio Code मा चेतावनीहरू रोक्नको लागि, `window.onload` फङ्सनलाई `gameLoopId` कल गर्न सम्पादन गर्नुहोस् (बिना `let`), र फाइलको माथि `let gameLoopId;` स्वतन्त्र रूपमा घोषणा गर्नुहोस्।

### कोड थप्नुहोस्

1. **अन्त्यको अवस्था ट्र्याक गर्नुहोस्**। शत्रुहरूको संख्या ट्र्याक गर्ने वा नायक जहाज नष्ट भएको छ कि छैन भनेर ट्र्याक गर्ने कोड थप्नुहोस्। यी दुई फङ्सनहरू थप्नुहोस्:

    ```javascript
    function isHeroDead() {
      return hero.life <= 0;
    }

    function isEnemiesDead() {
      const enemies = gameObjects.filter((go) => go.type === "Enemy" && !go.dead);
      return enemies.length === 0;
    }
    ```

1. **सन्देश ह्यान्डलरहरूमा तर्क थप्नुहोस्**। `eventEmitter` सम्पादन गरेर यी अवस्थाहरू ह्यान्डल गर्नुहोस्:

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

1. **नयाँ सन्देश प्रकारहरू थप्नुहोस्**। यी सन्देशहरू constants वस्तुमा थप्नुहोस्:

    ```javascript
    GAME_END_LOSS: "GAME_END_LOSS",
    GAME_END_WIN: "GAME_END_WIN",
    ```

2. **पुनः सुरु गर्ने कोड थप्नुहोस्**। चयन गरिएको बटन थिच्दा खेल पुनः सुरु गर्ने कोड थप्नुहोस्।

   1. **कुञ्जी थिच्ने सुन्नुहोस् `Enter`**। तपाईंको विन्डोको eventListener सम्पादन गरेर यो थिच्ने सुन्नुहोस्:

    ```javascript
     else if(evt.key === "Enter") {
        eventEmitter.emit(Messages.KEY_EVENT_ENTER);
      }
    ```

   1. **पुनः सुरु सन्देश थप्नुहोस्**। यो सन्देश तपाईंको Messages constant मा थप्नुहोस्:

        ```javascript
        KEY_EVENT_ENTER: "KEY_EVENT_ENTER",
        ```

1. **खेलका नियमहरू कार्यान्वयन गर्नुहोस्**। निम्न खेलका नियमहरू कार्यान्वयन गर्नुहोस्:

   1. **खेल जित्ने अवस्था**। सबै शत्रु जहाजहरू नष्ट भएपछि, विजय सन्देश देखाउनुहोस्।

      1. पहिलो, `displayMessage()` फङ्सन सिर्जना गर्नुहोस्:

        ```javascript
        function displayMessage(message, color = "red") {
          ctx.font = "30px Arial";
          ctx.fillStyle = color;
          ctx.textAlign = "center";
          ctx.fillText(message, canvas.width / 2, canvas.height / 2);
        }
        ```

      1. `endGame()` फङ्सन सिर्जना गर्नुहोस्:

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

   1. **पुनः सुरु गर्ने तर्क**। जब सबै जीवन समाप्त हुन्छ वा खेल जितिन्छ, खेल पुनः सुरु गर्न सकिने सन्देश देखाउनुहोस्। साथै, *पुनः सुरु* कुञ्जी थिच्दा खेल पुनः सुरु गर्नुहोस् (तपाईंले कुन कुञ्जी पुनः सुरु गर्न म्याप गर्नुपर्छ भन्ने निर्णय गर्न सक्नुहुन्छ)।

      1. `resetGame()` फङ्सन सिर्जना गर्नुहोस्:

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

     1. `initGame()` मा खेल पुनः सेट गर्न `eventEmitter` मा कल थप्नुहोस्:

        ```javascript
        eventEmitter.on(Messages.KEY_EVENT_ENTER, () => {
          resetGame();
        });
        ```

     1. EventEmitter मा `clear()` फङ्सन थप्नुहोस्:

        ```javascript
        clear() {
          this.listeners = {};
        }
        ```

👽 💥 🚀 बधाई छ, कप्तान! तपाईंको खेल पूरा भयो! राम्रो काम! 🚀 💥 👽

---

## GitHub Copilot Agent Challenge 🚀

Agent मोड प्रयोग गरेर निम्न चुनौती पूरा गर्नुहोस्:

**विवरण:** स्तर प्रगति प्रणाली लागू गरेर स्पेस गेमलाई सुधार गर्नुहोस् जसमा बढ्दो कठिनाइ र बोनस सुविधाहरू समावेश छन्।

**प्रेरणा:** बहु-स्तरीय स्पेस गेम प्रणाली सिर्जना गर्नुहोस् जहाँ प्रत्येक स्तरमा बढी शत्रु जहाजहरू हुन्छन् जसको गति र स्वास्थ्य बढ्दो हुन्छ। प्रत्येक स्तरसँग स्कोरिङ गुणक थप्नुहोस्, र पावर-अपहरू (जस्तै, द्रुत फायर वा शिल्ड) लागू गर्नुहोस् जुन शत्रुहरू नष्ट हुँदा अनियमित रूपमा देखा पर्छ। स्तर पूरा गर्ने बोनस समावेश गर्नुहोस् र हालको स्तर स्कोर र जीवनसँगै स्क्रिनमा देखाउनुहोस्।

## 🚀 चुनौती

ध्वनि थप्नुहोस्! के तपाईं आफ्नो खेल खेललाई सुधार गर्न ध्वनि थप्न सक्नुहुन्छ, जस्तै लेजर हिट हुँदा, वा नायक मर्दा वा जित्दा? [sandbox](https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_audio_play) हेरेर JavaScript प्रयोग गरेर ध्वनि कसरी बजाउने सिक्नुहोस्।

## पोस्ट-लेक्चर क्विज

[पोस्ट-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/40)

## समीक्षा र आत्म अध्ययन

तपाईंको असाइनमेन्ट भनेको नयाँ नमूना खेल सिर्जना गर्नु हो, त्यसैले तपाईंले निर्माण गर्न सक्ने खेलको प्रकार हेर्न केही रोचक खेलहरू अन्वेषण गर्नुहोस्।

## असाइनमेन्ट

[नमूना खेल बनाउनुहोस्](assignment.md)

---

**अस्वीकरण**:  
यो दस्तावेज़ AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको छ। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादहरूमा त्रुटिहरू वा अशुद्धताहरू हुन सक्छ। यसको मूल भाषा मा रहेको मूल दस्तावेज़लाई आधिकारिक स्रोत मानिनुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न हुने कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुने छैनौं।