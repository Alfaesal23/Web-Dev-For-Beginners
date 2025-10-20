<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "03f5022615bbc23417d5af42943d12f5",
  "translation_date": "2025-10-20T22:07:32+00:00",
  "source_file": "6-space-game/3-moving-elements-around/README.md",
  "language_code": "pa"
}
-->
# ਸਪੇਸ ਗੇਮ ਬਣਾਓ ਭਾਗ 3: ਮੋਸ਼ਨ ਸ਼ਾਮਲ ਕਰਨਾ

## ਪੂਰਵ-ਲੈਕਚਰ ਕਵਿਜ਼

[ਪੂਰਵ-ਲੈਕਚਰ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/33)

ਗੇਮਾਂ ਤਦ ਤੱਕ ਮਜ਼ੇਦਾਰ ਨਹੀਂ ਹੁੰਦੀਆਂ ਜਦ ਤੱਕ ਸਕ੍ਰੀਨ 'ਤੇ ਐਲੀਅਨ ਦੌੜਦੇ ਨਹੀਂ ਹਨ! ਇਸ ਗੇਮ ਵਿੱਚ, ਅਸੀਂ ਦੋ ਕਿਸਮ ਦੇ ਮੋਸ਼ਨ ਦੀ ਵਰਤੋਂ ਕਰਾਂਗੇ:

- **ਕੀਬੋਰਡ/ਮਾਊਸ ਮੋਸ਼ਨ**: ਜਦੋਂ ਯੂਜ਼ਰ ਸਕ੍ਰੀਨ 'ਤੇ ਕਿਸੇ ਆਬਜੈਕਟ ਨੂੰ ਹਿਲਾਉਣ ਲਈ ਕੀਬੋਰਡ ਜਾਂ ਮਾਊਸ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦਾ ਹੈ।
- **ਗੇਮ ਦੁਆਰਾ ਪ੍ਰੇਰਿਤ ਮੋਸ਼ਨ**: ਜਦੋਂ ਗੇਮ ਇੱਕ ਨਿਰਧਾਰਤ ਸਮੇਂ ਦੇ ਅੰਤਰਾਲ ਨਾਲ ਕਿਸੇ ਆਬਜੈਕਟ ਨੂੰ ਹਿਲਾਉਂਦਾ ਹੈ।

ਤਾਂ ਅਸੀਂ ਸਕ੍ਰੀਨ 'ਤੇ ਚੀਜ਼ਾਂ ਨੂੰ ਕਿਵੇਂ ਹਿਲਾਉਂਦੇ ਹਾਂ? ਇਹ ਸਾਰਾ ਕਾਰਟੀਸੀਅਨ ਕੋਆਰਡੀਨੇਟਸ ਬਾਰੇ ਹੈ: ਅਸੀਂ ਆਬਜੈਕਟ ਦੇ ਸਥਾਨ (x, y) ਨੂੰ ਬਦਲਦੇ ਹਾਂ ਅਤੇ ਫਿਰ ਸਕ੍ਰੀਨ ਨੂੰ ਦੁਬਾਰਾ ਡਰਾਅ ਕਰਦੇ ਹਾਂ।

ਆਮ ਤੌਰ 'ਤੇ ਤੁਹਾਨੂੰ ਸਕ੍ਰੀਨ 'ਤੇ *ਮੋਸ਼ਨ* ਹਾਸਲ ਕਰਨ ਲਈ ਹੇਠਾਂ ਦਿੱਤੇ ਕਦਮਾਂ ਦੀ ਲੋੜ ਹੁੰਦੀ ਹੈ:

1. **ਨਵਾਂ ਸਥਾਨ ਸੈਟ ਕਰੋ** ਕਿਸੇ ਆਬਜੈਕਟ ਲਈ; ਇਹ ਆਬਜੈਕਟ ਨੂੰ ਹਿਲਿਆ ਹੋਇਆ ਮਹਿਸੂਸ ਕਰਨ ਲਈ ਜ਼ਰੂਰੀ ਹੈ।
2. **ਸਕ੍ਰੀਨ ਸਾਫ਼ ਕਰੋ**, ਡਰਾਅ ਦੇ ਵਿਚਕਾਰ ਸਕ੍ਰੀਨ ਨੂੰ ਸਾਫ਼ ਕਰਨ ਦੀ ਲੋੜ ਹੁੰਦੀ ਹੈ। ਅਸੀਂ ਇਸਨੂੰ ਪਿਛੋਕੜ ਦੇ ਰੰਗ ਨਾਲ ਭਰਕੇ ਇੱਕ ਆਯਤ ਬਣਾਕੇ ਸਾਫ਼ ਕਰ ਸਕਦੇ ਹਾਂ।
3. **ਨਵੇਂ ਸਥਾਨ 'ਤੇ ਆਬਜੈਕਟ ਨੂੰ ਦੁਬਾਰਾ ਡਰਾਅ ਕਰੋ**। ਇਸਨੂੰ ਕਰਨ ਨਾਲ ਅਸੀਂ ਆਖਿਰਕਾਰ ਆਬਜੈਕਟ ਨੂੰ ਇੱਕ ਸਥਾਨ ਤੋਂ ਦੂਜੇ ਸਥਾਨ ਤੱਕ ਹਿਲਾਉਣ ਵਿੱਚ ਸਫਲ ਹੁੰਦੇ ਹਾਂ।

ਇਹ ਕੋਡ ਵਿੱਚ ਇਸ ਤਰ੍ਹਾਂ ਲੱਗ ਸਕਦਾ ਹੈ:

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

✅ ਕੀ ਤੁਸੀਂ ਸੋਚ ਸਕਦੇ ਹੋ ਕਿ ਕਿਉਂ ਤੁਹਾਡੇ ਹੀਰੋ ਨੂੰ ਹਰ ਸੈਕਿੰਡ ਕਈ ਫਰੇਮਾਂ ਵਿੱਚ ਦੁਬਾਰਾ ਡਰਾਅ ਕਰਨ ਨਾਲ ਪ੍ਰਦਰਸ਼ਨ ਦੀ ਲਾਗਤ ਵਧ ਸਕਦੀ ਹੈ? [ਇਸ ਪੈਟਰਨ ਦੇ ਵਿਕਲਪਾਂ](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Optimizing_canvas) ਬਾਰੇ ਪੜ੍ਹੋ।

## ਕੀਬੋਰਡ ਇਵੈਂਟਸ ਨੂੰ ਹੈਂਡਲ ਕਰੋ

ਤੁਸੀਂ ਇਵੈਂਟਸ ਨੂੰ ਕੋਡ ਨਾਲ ਜੁੜ ਕੇ ਹੈਂਡਲ ਕਰਦੇ ਹੋ। ਕੀਬੋਰਡ ਇਵੈਂਟਸ ਪੂਰੇ ਵਿੰਡੋ 'ਤੇ ਟ੍ਰਿਗਰ ਹੁੰਦੇ ਹਨ ਜਦਕਿ ਮਾਊਸ ਇਵੈਂਟਸ ਜਿਵੇਂ ਕਿ `click` ਨੂੰ ਕਿਸੇ ਖਾਸ ਐਲੀਮੈਂਟ 'ਤੇ ਕਲਿਕ ਕਰਨ ਨਾਲ ਜੁੜਿਆ ਜਾ ਸਕਦਾ ਹੈ। ਅਸੀਂ ਇਸ ਪ੍ਰੋਜੈਕਟ ਵਿੱਚ ਕੀਬੋਰਡ ਇਵੈਂਟਸ ਦੀ ਵਰਤੋਂ ਕਰਾਂਗੇ।

ਇੱਕ ਇਵੈਂਟ ਨੂੰ ਹੈਂਡਲ ਕਰਨ ਲਈ ਤੁਹਾਨੂੰ ਵਿੰਡੋ ਦੇ `addEventListener()` ਮੈਥਡ ਦੀ ਵਰਤੋਂ ਕਰਨੀ ਪਵੇਗੀ ਅਤੇ ਇਸਨੂੰ ਦੋ ਇਨਪੁਟ ਪੈਰਾਮੀਟਰ ਦੇਣੇ ਪੈਣਗੇ। ਪਹਿਲਾ ਪੈਰਾਮੀਟਰ ਇਵੈਂਟ ਦਾ ਨਾਮ ਹੈ, ਉਦਾਹਰਨ ਲਈ `keyup`। ਦੂਜਾ ਪੈਰਾਮੀਟਰ ਉਹ ਫੰਕਸ਼ਨ ਹੈ ਜੋ ਇਵੈਂਟ ਹੋਣ ਦੇ ਨਤੀਜੇ ਵਜੋਂ ਚਲਾਇਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ।

ਇਹ ਇੱਕ ਉਦਾਹਰਨ ਹੈ:

```javascript
window.addEventListener('keyup', (evt) => {
  // `evt.key` = string representation of the key
  if (evt.key === 'ArrowUp') {
    // do something
  }
})
```

ਕੀ ਇਵੈਂਟਸ ਲਈ ਇਵੈਂਟ 'ਤੇ ਦੋ ਪ੍ਰਾਪਰਟੀਜ਼ ਹੁੰਦੀਆਂ ਹਨ ਜੋ ਤੁਸੀਂ ਵੇਖ ਸਕਦੇ ਹੋ ਕਿ ਕਿਹੜੀ ਕੁੰਜੀ ਦਬਾਈ ਗਈ ਸੀ:

- `key`, ਇਹ ਦਬਾਈ ਗਈ ਕੁੰਜੀ ਦਾ ਸਟ੍ਰਿੰਗ ਪ੍ਰਤੀਨਿਧੀ ਹੈ, ਉਦਾਹਰਨ ਲਈ `ArrowUp`
- `keyCode`, ਇਹ ਇੱਕ ਨੰਬਰ ਪ੍ਰਤੀਨਿਧੀ ਹੈ, ਉਦਾਹਰਨ ਲਈ `37`, ਜੋ `ArrowLeft` ਦੇ ਅਨੁਕੂਲ ਹੈ।

✅ ਕੀ ਇਵੈਂਟ ਮੈਨਿਪੂਲੇਸ਼ਨ ਗੇਮ ਡਿਵੈਲਪਮੈਂਟ ਤੋਂ ਬਾਹਰ ਵੀ ਲਾਭਦਾਇਕ ਹੈ। ਇਸ ਤਕਨੀਕ ਲਈ ਹੋਰ ਕੀ ਵਰਤੋਂ ਤੁਸੀਂ ਸੋਚ ਸਕਦੇ ਹੋ?

### ਖਾਸ ਕੁੰਜੀਆਂ: ਇੱਕ ਚੇਤਾਵਨੀ

ਕੁਝ *ਖਾਸ* ਕੁੰਜੀਆਂ ਹਨ ਜੋ ਵਿੰਡੋ ਨੂੰ ਪ੍ਰਭਾਵਿਤ ਕਰਦੀਆਂ ਹਨ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਜੇ ਤੁਸੀਂ `keyup` ਇਵੈਂਟ ਨੂੰ ਸੁਣ ਰਹੇ ਹੋ ਅਤੇ ਤੁਸੀਂ ਆਪਣੇ ਹੀਰੋ ਨੂੰ ਹਿਲਾਉਣ ਲਈ ਇਹ ਖਾਸ ਕੁੰਜੀਆਂ ਵਰਤਦੇ ਹੋ ਤਾਂ ਇਹ ਹੋਰਿਜ਼ਾਂਟਲ ਸਕ੍ਰੋਲਿੰਗ ਵੀ ਕਰੇਗਾ। ਇਸ ਕਾਰਨ ਤੁਸੀਂ ਆਪਣੇ ਗੇਮ ਨੂੰ ਬਣਾਉਂਦੇ ਸਮੇਂ ਇਸ ਬਿਲਟ-ਇਨ ਬ੍ਰਾਊਜ਼ਰ ਵਿਹਾਰ ਨੂੰ *ਬੰਦ* ਕਰਨਾ ਚਾਹੁੰਦੇ ਹੋ। ਤੁਹਾਨੂੰ ਇਸ ਤਰ੍ਹਾਂ ਦਾ ਕੋਡ ਚਾਹੀਦਾ ਹੈ:

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

ਉਪਰੋਕਤ ਕੋਡ ਇਹ ਯਕੀਨੀ ਬਣਾਏਗਾ ਕਿ ਐਰੋ-ਕੀਜ਼ ਅਤੇ ਸਪੇਸ ਕੀ ਦੀਆਂ *ਡਿਫਾਲਟ* ਵਿਹਾਰ ਬੰਦ ਹੋ ਗਈਆਂ ਹਨ। *ਬੰਦ* ਮਕੈਨਿਜ਼ਮ ਤਦ ਹੁੰਦਾ ਹੈ ਜਦੋਂ ਅਸੀਂ `e.preventDefault()` ਨੂੰ ਕਾਲ ਕਰਦੇ ਹਾਂ।

## ਗੇਮ ਦੁਆਰਾ ਪ੍ਰੇਰਿਤ ਮੋਸ਼ਨ

ਅਸੀਂ ਚੀਜ਼ਾਂ ਨੂੰ ਆਪਣੇ ਆਪ ਹਿਲਾ ਸਕਦੇ ਹਾਂ ਜਦੋਂ ਅਸੀਂ ਟਾਈਮਰ ਜਿਵੇਂ ਕਿ `setTimeout()` ਜਾਂ `setInterval()` ਫੰਕਸ਼ਨ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹਾਂ ਜੋ ਹਰ ਟਿਕ ਜਾਂ ਸਮੇਂ ਦੇ ਅੰਤਰਾਲ 'ਤੇ ਆਬਜੈਕਟ ਦੇ ਸਥਾਨ ਨੂੰ ਅਪਡੇਟ ਕਰਦੇ ਹਨ। ਇਹ ਇਸ ਤਰ੍ਹਾਂ ਲੱਗ ਸਕਦਾ ਹੈ:

```javascript
let id = setInterval(() => {
  //move the enemy on the y axis
  enemy.y += 10;
})
```

## ਗੇਮ ਲੂਪ

ਗੇਮ ਲੂਪ ਇੱਕ ਧਾਰਨਾ ਹੈ ਜੋ ਅਸਲ ਵਿੱਚ ਇੱਕ ਫੰਕਸ਼ਨ ਹੈ ਜੋ ਨਿਯਮਿਤ ਅੰਤਰਾਲ 'ਤੇ ਚਲਾਇਆ ਜਾਂਦਾ ਹੈ। ਇਸਨੂੰ ਗੇਮ ਲੂਪ ਕਿਹਾ ਜਾਂਦਾ ਹੈ ਕਿਉਂਕਿ ਜੋ ਕੁਝ ਵੀ ਯੂਜ਼ਰ ਨੂੰ ਦਿਖਾਈ ਦੇਣਾ ਚਾਹੀਦਾ ਹੈ ਉਹ ਲੂਪ ਵਿੱਚ ਖਿੱਚਿਆ ਜਾਂਦਾ ਹੈ। ਗੇਮ ਲੂਪ ਗੇਮ ਦੇ ਸਾਰੇ ਆਬਜੈਕਟਸ ਦੀ ਵਰਤੋਂ ਕਰਦਾ ਹੈ ਜੋ ਗੇਮ ਦਾ ਹਿੱਸਾ ਹੁੰਦੇ ਹਨ, ਸਾਰੇ ਨੂੰ ਖਿੱਚਦਾ ਹੈ ਜਦ ਤੱਕ ਕਿ ਕਿਸੇ ਕਾਰਨ ਕਰਕੇ ਉਹ ਹੁਣ ਗੇਮ ਦਾ ਹਿੱਸਾ ਨਹੀਂ ਹੁੰਦੇ। ਉਦਾਹਰਨ ਲਈ ਜੇਕਰ ਕੋਈ ਆਬਜੈਕਟ ਇੱਕ ਦੁਸ਼ਮਨ ਹੈ ਜਿਸਨੂੰ ਲੇਜ਼ਰ ਨਾਲ ਮਾਰਿਆ ਗਿਆ ਸੀ ਅਤੇ ਉਹ ਫਟ ਜਾਂਦਾ ਹੈ, ਤਾਂ ਇਹ ਹੁਣ ਮੌਜੂਦਾ ਗੇਮ ਲੂਪ ਦਾ ਹਿੱਸਾ ਨਹੀਂ ਹੁੰਦਾ (ਤੁਸੀਂ ਇਸ ਬਾਰੇ ਹੋਰ ਜਾਣੋਗੇ ਅਗਲੇ ਪਾਠਾਂ ਵਿੱਚ)।

ਇਹ ਗੇਮ ਲੂਪ ਆਮ ਤੌਰ 'ਤੇ ਇਸ ਤਰ੍ਹਾਂ ਲੱਗ ਸਕਦਾ ਹੈ, ਕੋਡ ਵਿੱਚ ਪ੍ਰਗਟ ਕੀਤਾ:

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

ਉਪਰੋਕਤ ਲੂਪ ਹਰ `200` ਮਿਲੀਸੈਕਿੰਡ ਵਿੱਚ ਕੈਨਵਾਸ ਨੂੰ ਦੁਬਾਰਾ ਡਰਾਅ ਕਰਨ ਲਈ ਚਲਾਇਆ ਜਾਂਦਾ ਹੈ। ਤੁਹਾਡੇ ਕੋਲ ਇਹ ਚੋਣ ਕਰਨ ਦੀ ਯੋਗਤਾ ਹੈ ਕਿ ਤੁਹਾਡੇ ਗੇਮ ਲਈ ਸਭ ਤੋਂ ਵਧੀਆ ਅੰਤਰਾਲ ਕਿਹੜਾ ਹੈ।

## ਸਪੇਸ ਗੇਮ ਜਾਰੀ ਰੱਖਣਾ

ਤੁਸੀਂ ਮੌਜੂਦਾ ਕੋਡ ਲੈ ਕੇ ਇਸਨੂੰ ਵਧਾਓਗੇ। ਜਾਂ ਤਾਂ ਉਸ ਕੋਡ ਨਾਲ ਸ਼ੁਰੂ ਕਰੋ ਜੋ ਤੁਸੀਂ ਭਾਗ I ਦੌਰਾਨ ਪੂਰਾ ਕੀਤਾ ਸੀ ਜਾਂ [ਭਾਗ II- ਸ਼ੁਰੂਆਤੀ](../../../../6-space-game/3-moving-elements-around/your-work) ਵਿੱਚ ਕੋਡ ਦੀ ਵਰਤੋਂ ਕਰੋ।

- **ਹੀਰੋ ਨੂੰ ਹਿਲਾਉਣਾ**: ਤੁਸੀਂ ਇਹ ਯਕੀਨੀ ਬਣਾਉਣ ਲਈ ਕੋਡ ਸ਼ਾਮਲ ਕਰੋਗੇ ਕਿ ਤੁਸੀਂ ਐਰੋ ਕੀਜ਼ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੀਰੋ ਨੂੰ ਹਿਲਾ ਸਕਦੇ ਹੋ।
- **ਦੁਸ਼ਮਨਾਂ ਨੂੰ ਹਿਲਾਉਣਾ**: ਤੁਹਾਨੂੰ ਇਹ ਵੀ ਯਕੀਨੀ ਬਣਾਉਣ ਲਈ ਕੋਡ ਸ਼ਾਮਲ ਕਰਨ ਦੀ ਲੋੜ ਹੋਵੇਗੀ ਕਿ ਦੁਸ਼ਮਨ ਇੱਕ ਨਿਰਧਾਰਤ ਗਤੀ 'ਤੇ ਉੱਪਰ ਤੋਂ ਹੇਠਾਂ ਹਿਲਦੇ ਹਨ।

## ਸਿਫਾਰਸ਼ੀ ਕਦਮ

ਉਹ ਫਾਈਲਾਂ ਲੱਭੋ ਜੋ ਤੁਹਾਡੇ ਲਈ `your-work` ਸਬ ਫੋਲਡਰ ਵਿੱਚ ਬਣਾਈ ਗਈਆਂ ਹਨ। ਇਸ ਵਿੱਚ ਹੇਠਾਂ ਦਿੱਤੇ ਹੋਣ ਚਾਹੀਦੇ ਹਨ:

```bash
-| assets
  -| enemyShip.png
  -| player.png
-| index.html
-| app.js
-| package.json
```

ਤੁਸੀਂ ਆਪਣੇ ਪ੍ਰੋਜੈਕਟ ਨੂੰ `your_work` ਫੋਲਡਰ ਵਿੱਚ ਸ਼ੁਰੂ ਕਰਦੇ ਹੋ ਇਸ ਨੂੰ ਟਾਈਪ ਕਰਕੇ:

```bash
cd your-work
npm start
```

ਉਪਰੋਕਤ HTTP ਸਰਵਰ ਪਤਾ `http://localhost:5000` 'ਤੇ ਸ਼ੁਰੂ ਕਰੇਗਾ। ਇੱਕ ਬ੍ਰਾਊਜ਼ਰ ਖੋਲ੍ਹੋ ਅਤੇ ਉਹ ਪਤਾ ਦਰਜ ਕਰੋ, ਇਸ ਸਮੇਂ ਇਹ ਹੀਰੋ ਅਤੇ ਸਾਰੇ ਦੁਸ਼ਮਨਾਂ ਨੂੰ ਰੈਂਡਰ ਕਰੇਗਾ; ਕੁਝ ਵੀ ਹਿਲ ਨਹੀਂ ਰਿਹਾ - ਅਜੇ ਤੱਕ!

### ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ

1. **ਹੀਰੋ**, **ਦੁਸ਼ਮਨ**, ਅਤੇ **ਗੇਮ ਆਬਜੈਕਟ** ਲਈ ਵੱਖਰੇ ਆਬਜੈਕਟਸ ਸ਼ਾਮਲ ਕਰੋ, ਇਹਨਾਂ ਵਿੱਚ `x` ਅਤੇ `y` ਪ੍ਰਾਪਰਟੀਜ਼ ਹੋਣੀਆਂ ਚਾਹੀਦੀਆਂ ਹਨ। (ਯਾਦ ਰੱਖੋ [ਵਿਰਾਸਤ ਜਾਂ ਰਚਨਾ](../README.md) ਬਾਰੇ ਹਿੱਸਾ)।

   *ਸੁਝਾਅ*: ਇੱਕ ਨਵਾਂ GameObject ਕਲਾਸ ਸ਼ੁਰੂ ਕਰੋ ਜਿਸਦਾ ਕੰਸਟ੍ਰਕਟਰ ਹੇਠਾਂ ਦਿੱਤੇ ਤਰੀਕੇ ਨਾਲ ਬਣਾਇਆ ਗਿਆ ਹੈ, ਅਤੇ ਫਿਰ ਇਸਨੂੰ ਕੈਨਵਾਸ 'ਤੇ ਡਰਾਅ ਕਰੋ:
  
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

    ਹੁਣ, ਇਸ GameObject ਨੂੰ ਵਧਾਓ ਤਾਂ ਜੋ ਹੀਰੋ ਅਤੇ ਦੁਸ਼ਮਨ ਬਣ ਸਕਣ।
    
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

2. **ਕੀ-ਇਵੈਂਟ ਹੈਂਡਲਰਸ ਸ਼ਾਮਲ ਕਰੋ** ਤਾਂ ਜੋ ਕੀ ਨੈਵੀਗੇਸ਼ਨ (ਹੀਰੋ ਨੂੰ ਉੱਪਰ/ਹੇਠਾਂ, ਖੱਬੇ/ਸੱਜੇ ਹਿਲਾਉਣਾ) ਹੈਂਡਲ ਕੀਤਾ ਜਾ ਸਕੇ।

   *ਯਾਦ ਰੱਖੋ*: ਇਹ ਇੱਕ ਕਾਰਟੀਸੀਅਨ ਸਿਸਟਮ ਹੈ, ਟੌਪ-ਲੈਫਟ `0,0` ਹੈ। ਇਹ ਵੀ ਯਾਦ ਰੱਖੋ ਕਿ *ਡਿਫਾਲਟ ਵਿਹਾਰ* ਨੂੰ ਰੋਕਣ ਲਈ ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ।

   >ਸੁਝਾਅ: ਆਪਣਾ onKeyDown ਫੰਕਸ਼ਨ ਬਣਾਓ ਅਤੇ ਇਸਨੂੰ ਵਿੰਡੋ ਨਾਲ ਜੁੜੋ:

   ```javascript
    let onKeyDown = function (e) {
	      console.log(e.keyCode);
	        ...add the code from the lesson above to stop default behavior
	      }
    };

    window.addEventListener("keydown", onKeyDown);
   ```
    
   ਇਸ ਸਮੇਂ ਆਪਣੇ ਬ੍ਰਾਊਜ਼ਰ ਕਨਸੋਲ ਨੂੰ ਚੈੱਕ ਕਰੋ, ਅਤੇ ਕੁੰਜੀਆਂ ਦੇ ਦਬਾਏ ਜਾਣ ਨੂੰ ਦੇਖੋ।

3. **ਪਬ-ਸਬ ਪੈਟਰਨ** ਨੂੰ ਲਾਗੂ ਕਰੋ, ਇਹ ਤੁਹਾਡੇ ਕੋਡ ਨੂੰ ਸਾਫ਼ ਰੱਖੇਗਾ ਜਦੋਂ ਤੁਸੀਂ ਬਾਕੀ ਭਾਗਾਂ ਦੀ ਪਾਲਣਾ ਕਰੋਗੇ।

   ਇਹ ਆਖਰੀ ਹਿੱਸਾ ਕਰਨ ਲਈ, ਤੁਸੀਂ:

   1. **ਇਵੈਂਟ ਲਿਸਨਰ ਸ਼ਾਮਲ ਕਰੋ** ਵਿੰਡੋ 'ਤੇ:

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

    1. **ਇਵੈਂਟ ਇਮੀਟਰ ਕਲਾਸ ਬਣਾਓ** ਤਾਂ ਜੋ ਸੁਨੇਹੇ ਪਬਲਿਸ਼ ਅਤੇ ਸਬਸਕ੍ਰਾਈਬ ਕੀਤੇ ਜਾ ਸਕਣ:

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

    1. **ਕਾਂਸਟੈਂਟਸ ਸ਼ਾਮਲ ਕਰੋ** ਅਤੇ ਇਵੈਂਟ ਇਮੀਟਰ ਸੈਟ ਕਰੋ:

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

    1. **ਗੇਮ ਨੂੰ ਸ਼ੁਰੂ ਕਰੋ**

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

1. **ਗੇਮ ਲੂਪ ਸੈਟ ਕਰੋ**

   ਵਿੰਡੋ.onload ਫੰਕਸ਼ਨ ਨੂੰ ਰੀਫੈਕਟਰ ਕਰੋ ਤਾਂ ਜੋ ਗੇਮ ਸ਼ੁਰੂ ਹੋਵੇ ਅਤੇ ਇੱਕ ਵਧੀਆ ਅੰਤਰਾਲ 'ਤੇ ਗੇਮ ਲੂਪ ਸੈਟ ਕੀਤਾ ਜਾਵੇ। ਤੁਸੀਂ ਇੱਕ ਲੇਜ਼ਰ ਬੀਮ ਵੀ ਸ਼ਾਮਲ ਕਰੋਗੇ:

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

5. **ਕੋਡ ਸ਼ਾਮਲ ਕਰੋ** ਤਾਂ ਜੋ ਦੁਸ਼ਮਨ ਇੱਕ ਨਿਰਧਾਰਤ ਅੰਤਰਾਲ 'ਤੇ ਹਿਲ ਸਕਣ

    `createEnemies()` ਫੰਕਸ਼ਨ ਨੂੰ ਰੀਫੈਕਟਰ ਕਰੋ ਤਾਂ ਜੋ ਦੁਸ਼ਮਨ ਬਣਾਏ ਜਾ ਸਕਣ ਅਤੇ ਉਹਨਾਂ ਨੂੰ ਨਵੇਂ gameObjects ਕਲਾਸ ਵਿੱਚ ਪੁਸ਼ ਕੀਤਾ ਜਾ ਸਕੇ:

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
    
    ਅਤੇ ਇੱਕ `createHero()` ਫੰਕਸ਼ਨ ਸ਼ਾਮਲ ਕਰੋ ਜੋ ਹੀਰੋ ਲਈ ਇੱਕ ਸਮਾਨ ਪ੍ਰਕਿਰਿਆ ਕਰੇ।

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

    ਅਤੇ ਆਖਿਰਕਾਰ, ਇੱਕ `drawGameObjects()` ਫੰਕਸ਼ਨ ਸ਼ਾਮਲ ਕਰੋ ਤਾਂ ਜੋ ਡਰਾਅ ਸ਼ੁਰੂ ਕੀਤਾ ਜਾ ਸਕੇ:

    ```javascript
    function drawGameObjects(ctx) {
      gameObjects.forEach(go => go.draw(ctx));
    }
    ```

    ਤੁਹਾਡੇ ਦੁਸ਼ਮਨ ਤੁਹਾਡੇ ਹੀਰੋ ਸਪੇਸਸ਼ਿਪ ਵੱਲ ਅੱਗੇ ਵਧਣੇ ਸ਼ੁਰੂ ਹੋ ਜਾਣੇ ਚਾਹੀਦੇ ਹਨ!

---

## GitHub Copilot Agent ਚੈਲੈਂਜ 🚀

Agent ਮੋਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਚੈਲੈਂਜ ਨੂੰ ਪੂਰਾ ਕਰੋ:

**ਵੇਰਵਾ:** ਸਪੇਸ ਗੇਮ ਨੂੰ ਵਧਾਓ ਅਤੇ ਬਾਊਂਡਰੀ ਡਿਟੈਕਸ਼ਨ ਅਤੇ ਸਮਰਥ ਮੋਸ਼ਨ ਕੰਟਰੋਲਸ ਲਾਗੂ ਕਰੋ। ਇਹ ਚੈਲੈਂਜ ਤੁਹਾਨੂੰ ਗੇਮ ਆਬਜੈਕਟ ਮੈਨਿਪੂਲੇਸ਼ਨ, ਇਵੈਂਟ ਹੈਂਡਲਿੰਗ, ਅਤੇ ਕੈਨਵਾਸ ਰੈਂਡਰਿੰਗ ਤਕਨੀਕਾਂ ਦਾ ਅਭਿਆਸ ਕਰਨ ਵਿੱਚ ਮਦਦ ਕਰੇਗਾ।

**ਪ੍ਰੋੰਪਟ:** ਇੱਕ ਬਾਊਂਡਰੀ ਡਿਟੈਕਸ਼ਨ ਸਿਸਟਮ ਬਣਾਓ ਜੋ ਹੀਰੋ ਸਪੇਸਸ਼ਿਪ ਨੂੰ ਕੈਨਵਾਸ ਬਾਊਂਡਰੀਜ਼ ਤੋਂ ਬਾਹਰ ਹਿਲਣ ਤੋਂ ਰੋਕਦਾ ਹੈ। ਇਸਦੇ ਨਾਲ-ਨਾਲ, ਇੱਕ ਸਮਰਥ ਮੋਸ਼ਨ ਸਿਸਟਮ ਲਾਗੂ ਕਰੋ ਜਿੱਥੇ ਐਰੋ ਕੀਜ਼ ਨੂੰ ਦਬਾ ਕੇ ਰੱਖਣ ਨਾਲ ਲਗਾਤਾਰ ਮੋਸ਼ਨ ਹੁੰਦਾ ਹੈ ਨਾ ਕਿ ਸਿੰਗਲ-ਸਟੈਪ ਮੋਸ਼ਨ। ਯਕੀਨੀ ਬਣਾਓ ਕਿ ਜਦੋਂ ਕੁੰਜੀਆਂ ਛੱਡੀਆਂ ਜਾਂਦੀਆਂ ਹਨ ਤਾਂ ਹੀਰੋ ਤੁਰੰਤ ਰੁਕ ਜਾਂਦਾ ਹੈ ਅਤੇ ਜਦੋਂ ਹੀਰੋ ਬਾਊਂਡਰੀ ਨੂੰ ਹਿੱਟ ਕਰਦਾ ਹੈ ਤਾਂ ਵਿਜ਼ੂਅਲ ਫੀਡਬੈਕ ਸ਼ਾਮਲ ਕਰੋ (ਜਿਵੇਂ ਕਿ ਇੱਕ ਛੋਟਾ ਰੰਗ ਬਦਲਣਾ ਜਾਂ ਗਲੋ ਪ੍ਰਭਾਵ)।

## 🚀 ਚੈਲੈਂਜ

ਜਿਵੇਂ ਤੁਸੀਂ ਦੇਖ ਸਕਦੇ ਹੋ, ਜਦੋਂ ਤੁਸੀਂ ਫੰਕਸ਼ਨ, ਵੈਰੀਏਬਲ ਅਤੇ ਕਲਾਸਾਂ ਸ਼ਾਮਲ ਕਰਨਾ ਸ਼ੁਰੂ ਕਰਦੇ ਹੋ ਤਾਂ ਤੁਹਾਡਾ ਕੋਡ 'ਸਪੈਗੇਟੀ ਕੋਡ' ਵਿੱਚ ਬਦਲ ਸਕਦਾ ਹੈ। ਤੁਹਾਡੇ ਕੋਡ ਨੂੰ ਵਧੇਰੇ ਪੜ੍ਹਨਯੋਗ ਬਣਾਉਣ ਲਈ ਇੱਕ ਸਿਸਟਮ ਨੂੰ ਆਰਗਨਾਈਜ਼ ਕਰਨ ਲਈ ਇੱਕ ਸਕੈਚ ਬਣਾਓ, ਭਾਵੇਂ ਇਹ ਅਜੇ ਵੀ ਇੱਕ ਫਾਈਲ ਵਿੱਚ ਰਹੇ।

## ਪੋਸਟ-ਲੈਕਚਰ ਕਵਿਜ਼

[ਪੋਸਟ-ਲੈਕਚਰ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/34)

## ਸਮੀਖਿਆ ਅਤੇ ਸਵੈ ਅਧਿਐਨ

ਜਦੋਂ ਅਸੀਂ ਆਪਣੇ ਗੇਮ ਨੂੰ ਫਰੇਮਵਰਕ ਦੀ ਵਰਤੋਂ ਕੀਤੇ ਬਿਨਾਂ ਲਿਖ ਰਹੇ ਹਾਂ, ਤਾਂ ਗੇਮ ਡਿਵੈਲਪਮੈਂਟ ਲਈ ਕਈ ਜਾਵਾਸਕ੍ਰਿਪਟ-ਅਧਾਰਤ ਕੈਨਵਾਸ ਫਰੇਮਵਰਕ ਹਨ। [ਇਨ੍ਹਾਂ ਬਾਰੇ ਪੜ੍ਹਨ](https://github.com/collections/javascript-game-engines) ਲਈ ਕੁਝ ਸਮਾਂ ਲਓ।

## ਅਸਾਈਨਮੈਂਟ

[ਆਪਣੇ ਕੋਡ 'ਤੇ ਟਿੱਪਣੀ ਕਰੋ](assignment.md)

---

**ਅਸਵੀਕਰਤਾ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦਾ ਯਤਨ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁੱਤੀਆਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਇਸਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।