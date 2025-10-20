<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7be341decc162fb251a9e0851b6600f6",
  "translation_date": "2025-10-20T22:08:23+00:00",
  "source_file": "6-space-game/6-end-condition/README.md",
  "language_code": "pa"
}
-->
# ਸਪੇਸ ਗੇਮ ਬਣਾਓ ਭਾਗ 6: ਖਤਮ ਅਤੇ ਮੁੜ ਸ਼ੁਰੂ

## ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵੀਜ਼

[ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵੀਜ਼](https://ff-quizzes.netlify.app/web/quiz/39)

ਖੇਡ ਵਿੱਚ *ਖਤਮ ਹੋਣ ਦੀ ਸ਼ਰਤ* ਨੂੰ ਵੱਖ-ਵੱਖ ਤਰੀਕਿਆਂ ਨਾਲ ਦਰਸਾਇਆ ਜਾ ਸਕਦਾ ਹੈ। ਇਹ ਤੁਹਾਡੇ ਉੱਤੇ ਨਿਰਭਰ ਕਰਦਾ ਹੈ ਕਿ ਤੁਸੀਂ ਖੇਡ ਦੇ ਰਚਨਾਕਾਰ ਵਜੋਂ ਇਹ ਕਹੋ ਕਿ ਖੇਡ ਕਿਉਂ ਖਤਮ ਹੋਈ। ਹੇਠਾਂ ਕੁਝ ਕਾਰਨ ਦਿੱਤੇ ਗਏ ਹਨ, ਜੇ ਅਸੀਂ ਮੰਨ ਲਵਾਂ ਕਿ ਅਸੀਂ ਉਸ ਸਪੇਸ ਗੇਮ ਬਾਰੇ ਗੱਲ ਕਰ ਰਹੇ ਹਾਂ ਜੋ ਤੁਸੀਂ ਹੁਣ ਤੱਕ ਬਣਾਈ ਹੈ:

- **`N` ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋ ਗਏ ਹਨ**: ਇਹ ਕਾਫ਼ੀ ਆਮ ਹੈ ਜੇ ਤੁਸੀਂ ਖੇਡ ਨੂੰ ਵੱਖ-ਵੱਖ ਪੱਧਰਾਂ ਵਿੱਚ ਵੰਡਦੇ ਹੋ ਕਿ ਤੁਹਾਨੂੰ `N` ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨਸ਼ਟ ਕਰਨੇ ਪੈਂਦੇ ਹਨ ਤਾਂ ਕਿ ਪੱਧਰ ਪੂਰਾ ਹੋ ਸਕੇ।
- **ਤੁਹਾਡਾ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋ ਗਿਆ ਹੈ**: ਕੁਝ ਖੇਡਾਂ ਵਿੱਚ ਜੇ ਤੁਹਾਡਾ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋ ਜਾਂਦਾ ਹੈ ਤਾਂ ਤੁਸੀਂ ਖੇਡ ਹਾਰ ਜਾਂਦੇ ਹੋ। ਇੱਕ ਹੋਰ ਆਮ ਤਰੀਕਾ ਇਹ ਹੈ ਕਿ ਤੁਹਾਡੇ ਕੋਲ ਜ਼ਿੰਦਗੀ ਦਾ ਸੰਕਲਪ ਹੁੰਦਾ ਹੈ। ਹਰ ਵਾਰ ਜਦੋਂ ਤੁਹਾਡਾ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੁੰਦਾ ਹੈ ਤਾਂ ਇਹ ਇੱਕ ਜ਼ਿੰਦਗੀ ਘਟਾ ਦਿੰਦਾ ਹੈ। ਜਦੋਂ ਸਾਰੀਆਂ ਜ਼ਿੰਦਗੀਆਂ ਖਤਮ ਹੋ ਜਾਂਦੀਆਂ ਹਨ ਤਾਂ ਤੁਸੀਂ ਖੇਡ ਹਾਰ ਜਾਂਦੇ ਹੋ।
- **ਤੁਹਾਨੂੰ `N` ਅੰਕ ਮਿਲੇ ਹਨ**: ਇੱਕ ਹੋਰ ਆਮ ਖਤਮ ਹੋਣ ਦੀ ਸ਼ਰਤ ਇਹ ਹੈ ਕਿ ਤੁਸੀਂ ਅੰਕ ਇਕੱਠੇ ਕਰੋ। ਤੁਹਾਨੂੰ ਅੰਕ ਕਿਵੇਂ ਮਿਲਦੇ ਹਨ ਇਹ ਤੁਹਾਡੇ ਉੱਤੇ ਨਿਰਭਰ ਕਰਦਾ ਹੈ ਪਰ ਇਹ ਕਾਫ਼ੀ ਆਮ ਹੈ ਕਿ ਵੱਖ-ਵੱਖ ਗਤੀਵਿਧੀਆਂ ਲਈ ਅੰਕ ਦਿੱਤੇ ਜਾਂਦੇ ਹਨ ਜਿਵੇਂ ਕਿ ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨੂੰ ਨਸ਼ਟ ਕਰਨਾ ਜਾਂ ਸ਼ਾਇਦ ਉਹ ਚੀਜ਼ਾਂ ਇਕੱਠੀਆਂ ਕਰਨਾ ਜੋ ਚੀਜ਼ਾਂ ਨਸ਼ਟ ਹੋਣ 'ਤੇ ਡਿੱਗਦੀਆਂ ਹਨ।
- **ਇੱਕ ਪੱਧਰ ਪੂਰਾ ਕਰੋ**: ਇਹ ਕਈ ਸ਼ਰਤਾਂ ਸ਼ਾਮਲ ਕਰ ਸਕਦਾ ਹੈ ਜਿਵੇਂ ਕਿ `X` ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋਏ, `Y` ਅੰਕ ਇਕੱਠੇ ਕੀਤੇ ਜਾਂਦੇ ਹਨ ਜਾਂ ਸ਼ਾਇਦ ਕੋਈ ਵਿਸ਼ੇਸ਼ ਚੀਜ਼ ਇਕੱਠੀ ਕੀਤੀ ਗਈ ਹੈ।

## ਮੁੜ ਸ਼ੁਰੂ ਕਰਨਾ

ਜੇ ਲੋਕ ਤੁਹਾਡੀ ਖੇਡ ਦਾ ਆਨੰਦ ਲੈਂਦੇ ਹਨ ਤਾਂ ਉਹ ਇਸਨੂੰ ਮੁੜ ਖੇਡਣਾ ਚਾਹੁੰਦੇ ਹਨ। ਜਦੋਂ ਖੇਡ ਕਿਸੇ ਵੀ ਕਾਰਨ ਕਰਕੇ ਖਤਮ ਹੁੰਦੀ ਹੈ ਤਾਂ ਤੁਹਾਨੂੰ ਇਸਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦਾ ਵਿਕਲਪ ਦੇਣਾ ਚਾਹੀਦਾ ਹੈ।

✅ ਸੋਚੋ ਕਿ ਕਿਹੜੀਆਂ ਸ਼ਰਤਾਂ ਦੇ ਤਹਿਤ ਤੁਹਾਨੂੰ ਲੱਗਦਾ ਹੈ ਕਿ ਖੇਡ ਖਤਮ ਹੁੰਦੀ ਹੈ, ਅਤੇ ਫਿਰ ਤੁਹਾਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਲਈ ਕਿਵੇਂ ਪ੍ਰੇਰਿਤ ਕੀਤਾ ਜਾਂਦਾ ਹੈ।

## ਕੀ ਬਣਾਉਣਾ ਹੈ

ਤੁਹਾਨੂੰ ਇਹ ਨਿਯਮ ਆਪਣੀ ਖੇਡ ਵਿੱਚ ਸ਼ਾਮਲ ਕਰਨੇ ਹਨ:

1. **ਖੇਡ ਜਿੱਤਣਾ**। ਜਦੋਂ ਸਾਰੇ ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋ ਜਾਂਦੇ ਹਨ, ਤੁਸੀਂ ਖੇਡ ਜਿੱਤ ਜਾਂਦੇ ਹੋ। ਇਸ ਤੋਂ ਇਲਾਵਾ, ਕਿਸੇ ਤਰ੍ਹਾਂ ਦਾ ਜਿੱਤ ਦਾ ਸੁਨੇਹਾ ਦਿਖਾਓ।
1. **ਮੁੜ ਸ਼ੁਰੂ ਕਰੋ**। ਜਦੋਂ ਤੁਹਾਡੀਆਂ ਸਾਰੀਆਂ ਜ਼ਿੰਦਗੀਆਂ ਖਤਮ ਹੋ ਜਾਂਦੀਆਂ ਹਨ ਜਾਂ ਖੇਡ ਜਿੱਤੀ ਜਾਂਦੀ ਹੈ, ਤਾਂ ਤੁਹਾਨੂੰ ਖੇਡ ਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦਾ ਇੱਕ ਤਰੀਕਾ ਦੇਣਾ ਚਾਹੀਦਾ ਹੈ। ਯਾਦ ਰੱਖੋ! ਤੁਹਾਨੂੰ ਖੇਡ ਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦੀ ਲੋੜ ਹੋਵੇਗੀ ਅਤੇ ਪਿਛਲੇ ਖੇਡ ਦੀ ਸਥਿਤੀ ਨੂੰ ਸਾਫ਼ ਕਰਨਾ ਪਵੇਗਾ।

## ਸਿਫਾਰਸ਼ੀ ਕਦਮ

ਉਹ ਫਾਈਲਾਂ ਲੱਭੋ ਜੋ ਤੁਹਾਡੇ ਲਈ `your-work` ਸਬ ਫੋਲਡਰ ਵਿੱਚ ਬਣਾਈ ਗਈਆਂ ਹਨ। ਇਸ ਵਿੱਚ ਹੇਠਾਂ ਦਿੱਤੇ ਹੋਣੇ ਚਾਹੀਦੇ ਹਨ:

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

ਤੁਸੀਂ ਆਪਣਾ ਪ੍ਰੋਜੈਕਟ `your_work` ਫੋਲਡਰ ਵਿੱਚ ਹੇਠਾਂ ਦਿੱਤੇ ਕਮਾਂਡ ਨਾਲ ਸ਼ੁਰੂ ਕਰਦੇ ਹੋ:

```bash
cd your-work
npm start
```

ਇਹ HTTP ਸਰਵਰ ਪਤਾ `http://localhost:5000` 'ਤੇ ਸ਼ੁਰੂ ਕਰੇਗਾ। ਇੱਕ ਬ੍ਰਾਊਜ਼ਰ ਖੋਲ੍ਹੋ ਅਤੇ ਉਸ ਪਤੇ ਨੂੰ ਦਰਜ ਕਰੋ। ਤੁਹਾਡੀ ਖੇਡ ਖੇਡਣ ਯੋਗ ਹੋਣੀ ਚਾਹੀਦੀ ਹੈ।

> ਟਿਪ: Visual Studio Code ਵਿੱਚ ਚੇਤਾਵਨੀ ਤੋਂ ਬਚਣ ਲਈ, `window.onload` ਫੰਕਸ਼ਨ ਨੂੰ `gameLoopId` ਨੂੰ ਬਿਨਾਂ `let` ਦੇ ਕਾਲ ਕਰਨ ਲਈ ਸੋਧੋ, ਅਤੇ ਫਾਈਲ ਦੇ ਸ਼ੁਰੂ 'ਤੇ gameLoopId ਨੂੰ ਅਲੱਗ-ਅਲੱਗ ਘੋਸ਼ਿਤ ਕਰੋ: `let gameLoopId;`

### ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ

1. **ਖਤਮ ਹੋਣ ਦੀ ਸ਼ਰਤ ਟ੍ਰੈਕ ਕਰੋ**। ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ ਜੋ ਦੁਸ਼ਮਨਾਂ ਦੀ ਗਿਣਤੀ ਜਾਂ ਹੀਰੋ ਜਹਾਜ਼ ਦੇ ਨਸ਼ਟ ਹੋਣ ਨੂੰ ਟ੍ਰੈਕ ਕਰਦਾ ਹੈ, ਇਹ ਦੋ ਫੰਕਸ਼ਨ ਸ਼ਾਮਲ ਕਰਕੇ:

    ```javascript
    function isHeroDead() {
      return hero.life <= 0;
    }

    function isEnemiesDead() {
      const enemies = gameObjects.filter((go) => go.type === "Enemy" && !go.dead);
      return enemies.length === 0;
    }
    ```

1. **ਸੁਨੇਹਾ ਹੈਂਡਲਰ ਵਿੱਚ ਤਰਕ ਸ਼ਾਮਲ ਕਰੋ**। `eventEmitter` ਨੂੰ ਸੋਧੋ ਤਾਂ ਜੋ ਇਹ ਸ਼ਰਤਾਂ ਨੂੰ ਹੈਂਡਲ ਕਰ ਸਕੇ:

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

1. **ਨਵੇਂ ਸੁਨੇਹਾ ਕਿਸਮਾਂ ਸ਼ਾਮਲ ਕਰੋ**। ਇਹ ਸੁਨੇਹੇ constants object ਵਿੱਚ ਸ਼ਾਮਲ ਕਰੋ:

    ```javascript
    GAME_END_LOSS: "GAME_END_LOSS",
    GAME_END_WIN: "GAME_END_WIN",
    ```

2. **ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦਾ ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ**। ਖੇਡ ਨੂੰ ਚੁਣੇ ਗਏ ਬਟਨ ਦੇ ਦਬਾਉਣ 'ਤੇ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦਾ ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ।

   1. **ਕੀ ਦਬਾਉਣ `Enter` ਨੂੰ ਸੁਣੋ**। ਆਪਣੇ window ਦੇ eventListener ਨੂੰ ਸੋਧੋ ਤਾਂ ਜੋ ਇਹ ਦਬਾਉਣ ਨੂੰ ਸੁਣੇ:

    ```javascript
     else if(evt.key === "Enter") {
        eventEmitter.emit(Messages.KEY_EVENT_ENTER);
      }
    ```

   1. **ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦਾ ਸੁਨੇਹਾ ਸ਼ਾਮਲ ਕਰੋ**। ਇਹ ਸੁਨੇਹਾ ਆਪਣੇ Messages constant ਵਿੱਚ ਸ਼ਾਮਲ ਕਰੋ:

        ```javascript
        KEY_EVENT_ENTER: "KEY_EVENT_ENTER",
        ```

1. **ਖੇਡ ਦੇ ਨਿਯਮ ਲਾਗੂ ਕਰੋ**। ਹੇਠਾਂ ਦਿੱਤੇ ਖੇਡ ਦੇ ਨਿਯਮ ਲਾਗੂ ਕਰੋ:

   1. **ਖਿਡਾਰੀ ਜਿੱਤਣ ਦੀ ਸ਼ਰਤ**। ਜਦੋਂ ਸਾਰੇ ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਨਸ਼ਟ ਹੋ ਜਾਂਦੇ ਹਨ, ਜਿੱਤ ਦਾ ਸੁਨੇਹਾ ਦਿਖਾਓ।

      1. ਪਹਿਲਾਂ, ਇੱਕ `displayMessage()` ਫੰਕਸ਼ਨ ਬਣਾਓ:

        ```javascript
        function displayMessage(message, color = "red") {
          ctx.font = "30px Arial";
          ctx.fillStyle = color;
          ctx.textAlign = "center";
          ctx.fillText(message, canvas.width / 2, canvas.height / 2);
        }
        ```

      1. ਇੱਕ `endGame()` ਫੰਕਸ਼ਨ ਬਣਾਓ:

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

   1. **ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਦੀ ਤਰਕ**। ਜਦੋਂ ਸਾਰੀਆਂ ਜ਼ਿੰਦਗੀਆਂ ਖਤਮ ਹੋ ਜਾਂਦੀਆਂ ਹਨ ਜਾਂ ਖਿਡਾਰੀ ਨੇ ਖੇਡ ਜਿੱਤ ਲਈ ਹੈ, ਤਾਂ ਦਿਖਾਓ ਕਿ ਖੇਡ ਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ। ਇਸ ਤੋਂ ਇਲਾਵਾ, ਜਦੋਂ *ਮੁੜ ਸ਼ੁਰੂ* ਕੀ ਦਬਾਈ ਜਾਂਦੀ ਹੈ (ਤੁਸੀਂ ਫੈਸਲਾ ਕਰ ਸਕਦੇ ਹੋ ਕਿ ਕਿਹੜੀ ਕੀ ਮੁੜ ਸ਼ੁਰੂ ਕਰਨ ਲਈ ਮੈਪ ਕੀਤੀ ਜਾਵੇ), ਤਾਂ ਖੇਡ ਨੂੰ ਮੁੜ ਸ਼ੁਰੂ ਕਰੋ।

      1. `resetGame()` ਫੰਕਸ਼ਨ ਬਣਾਓ:

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

     1. `initGame()` ਵਿੱਚ ਖੇਡ ਨੂੰ ਰੀਸੈਟ ਕਰਨ ਲਈ `eventEmitter` ਨੂੰ ਕਾਲ ਸ਼ਾਮਲ ਕਰੋ:

        ```javascript
        eventEmitter.on(Messages.KEY_EVENT_ENTER, () => {
          resetGame();
        });
        ```

     1. EventEmitter ਵਿੱਚ ਇੱਕ `clear()` ਫੰਕਸ਼ਨ ਸ਼ਾਮਲ ਕਰੋ:

        ```javascript
        clear() {
          this.listeners = {};
        }
        ```

👽 💥 🚀 ਵਧਾਈ ਹੋ, ਕੈਪਟਨ! ਤੁਹਾਡੀ ਖੇਡ ਪੂਰੀ ਹੋ ਗਈ ਹੈ! ਸ਼ਾਨਦਾਰ ਕੰਮ! 🚀 💥 👽

---

## GitHub Copilot Agent ਚੈਲੈਂਜ 🚀

Agent ਮੋਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਚੈਲੈਂਜ ਨੂੰ ਪੂਰਾ ਕਰੋ:

**ਵੇਰਵਾ:** ਸਪੇਸ ਗੇਮ ਵਿੱਚ ਪੱਧਰ ਪ੍ਰਗਤੀ ਪ੍ਰਣਾਲੀ ਨੂੰ ਵਧਾਉਣ ਲਈ ਵਧੇਰੇ ਮੁਸ਼ਕਲਾਈ ਅਤੇ ਬੋਨਸ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਲਾਗੂ ਕਰੋ।

**ਪ੍ਰੋੰਪਟ:** ਇੱਕ ਬਹੁ-ਪੱਧਰ ਸਪੇਸ ਗੇਮ ਪ੍ਰਣਾਲੀ ਬਣਾਓ ਜਿੱਥੇ ਹਰ ਪੱਧਰ ਵਿੱਚ ਵਧੇਰੇ ਦੁਸ਼ਮਨ ਜਹਾਜ਼ ਹੋਣ, ਜਿਨ੍ਹਾਂ ਦੀ ਗਤੀ ਅਤੇ ਸਿਹਤ ਵਧਦੀ ਹੈ। ਇੱਕ ਸਕੋਰਿੰਗ ਮਲਟੀਪਲਾਇਰ ਸ਼ਾਮਲ ਕਰੋ ਜੋ ਹਰ ਪੱਧਰ ਨਾਲ ਵਧਦਾ ਹੈ, ਅਤੇ ਪਾਵਰ-ਅਪ (ਜਿਵੇਂ ਕਿ ਰੈਪਿਡ ਫਾਇਰ ਜਾਂ ਸ਼ੀਲਡ) ਲਾਗੂ ਕਰੋ ਜੋ ਦੁਸ਼ਮਨ ਦੇ ਨਸ਼ਟ ਹੋਣ 'ਤੇ ਰੈਂਡਮ ਤੌਰ 'ਤੇ ਆਉਂਦੇ ਹਨ। ਇੱਕ ਪੱਧਰ ਪੂਰਾ ਕਰਨ ਦਾ ਬੋਨਸ ਸ਼ਾਮਲ ਕਰੋ ਅਤੇ ਮੌਜੂਦਾ ਪੱਧਰ ਨੂੰ ਸਕੋਰ ਅਤੇ ਜ਼ਿੰਦਗੀਆਂ ਦੇ ਨਾਲ ਸਕ੍ਰੀਨ 'ਤੇ ਦਿਖਾਓ।

## 🚀 ਚੈਲੈਂਜ

ਆਵਾਜ਼ ਸ਼ਾਮਲ ਕਰੋ! ਕੀ ਤੁਸੀਂ ਆਪਣੀ ਖੇਡ ਦੇ ਖੇਡਣ ਦੇ ਤਜਰਬੇ ਨੂੰ ਵਧਾਉਣ ਲਈ ਇੱਕ ਆਵਾਜ਼ ਸ਼ਾਮਲ ਕਰ ਸਕਦੇ ਹੋ, ਸ਼ਾਇਦ ਜਦੋਂ ਲੇਜ਼ਰ ਹਿੱਟ ਹੁੰਦਾ ਹੈ, ਜਾਂ ਹੀਰੋ ਮਰ ਜਾਂਦਾ ਹੈ ਜਾਂ ਜਿੱਤਦਾ ਹੈ? ਇਸ [sandbox](https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_audio_play) ਨੂੰ ਦੇਖੋ ਕਿ ਜਾਵਾਸਕ੍ਰਿਪਟ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਆਵਾਜ਼ ਨੂੰ ਕਿਵੇਂ ਚਲਾਇਆ ਜਾ ਸਕਦਾ ਹੈ।

## ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵੀਜ਼

[ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵੀਜ਼](https://ff-quizzes.netlify.app/web/quiz/40)

## ਸਮੀਖਿਆ ਅਤੇ ਸਵੈ ਅਧਿਐਨ

ਤੁਹਾਡਾ ਕੰਮ ਇੱਕ ਨਵੀਂ ਨਮੂਨਾ ਖੇਡ ਬਣਾਉਣਾ ਹੈ, ਇਸ ਲਈ ਬਾਹਰ ਕੁਝ ਦਿਲਚਸਪ ਖੇਡਾਂ ਦੀ ਖੋਜ ਕਰੋ ਤਾਂ ਜੋ ਦੇਖਿਆ ਜਾ ਸਕੇ ਕਿ ਤੁਸੀਂ ਕਿਸ ਤਰ੍ਹਾਂ ਦੀ ਖੇਡ ਬਣਾਉਣਾ ਚਾਹੁੰਦੇ ਹੋ।

## ਅਸਾਈਨਮੈਂਟ

[ਨਮੂਨਾ ਖੇਡ ਬਣਾਓ](assignment.md)

---

**ਅਸਵੀਕਰਤਾ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁੱਤੀਆਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਇਸ ਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤ ਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।