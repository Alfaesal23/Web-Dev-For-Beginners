<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T18:11:48+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "pa"
}
-->
# ਸਪੇਸ ਗੇਮ ਬਣਾਓ ਭਾਗ 1: ਜਾਣ ਪਛਾਣ

![ਸਪੇਸ ਗੇਮ ਐਨੀਮੇਸ਼ਨ ਜੋ ਗੇਮਪਲੇ ਦਿਖਾਉਂਦੀ ਹੈ](../../../../6-space-game/images/pewpew.gif)

ਜਿਵੇਂ NASA ਦਾ ਮਿਸ਼ਨ ਕੰਟਰੋਲ ਸਪੇਸ ਲਾਂਚ ਦੌਰਾਨ ਕਈ ਸਿਸਟਮਾਂ ਨੂੰ ਸਹੀ ਤਰੀਕੇ ਨਾਲ ਸਾਂਝਾ ਕਰਦਾ ਹੈ, ਅਸੀਂ ਇੱਕ ਸਪੇਸ ਗੇਮ ਬਣਾਉਣ ਜਾ ਰਹੇ ਹਾਂ ਜੋ ਦਿਖਾਏਗਾ ਕਿ ਕਿਸ ਤਰ੍ਹਾਂ ਇੱਕ ਪ੍ਰੋਗਰਾਮ ਦੇ ਵੱਖ-ਵੱਖ ਹਿੱਸੇ ਬਿਨਾਂ ਰੁਕਾਵਟ ਦੇ ਇਕੱਠੇ ਕੰਮ ਕਰ ਸਕਦੇ ਹਨ। ਕੁਝ ਐਸਾ ਬਣਾਉਂਦੇ ਹੋਏ ਜੋ ਤੁਸੀਂ ਖੇਡ ਸਕਦੇ ਹੋ, ਤੁਸੀਂ ਅਹਿਮ ਪ੍ਰੋਗਰਾਮਿੰਗ ਸੰਕਲਪ ਸਿੱਖੋਗੇ ਜੋ ਕਿਸੇ ਵੀ ਸਾਫਟਵੇਅਰ ਪ੍ਰੋਜੈਕਟ ਲਈ ਲਾਗੂ ਹੁੰਦੇ ਹਨ।

ਅਸੀਂ ਕੋਡ ਨੂੰ ਸੰਗਠਿਤ ਕਰਨ ਦੇ ਦੋ ਮੁੱਖ ਤਰੀਕੇ: ਵਾਰਸ ਅਤੇ ਰਚਨਾ ਦੀ ਪੜਚੋਲ ਕਰਾਂਗੇ। ਇਹ ਸਿਰਫ਼ ਅਕਾਦਮਿਕ ਸੰਕਲਪ ਨਹੀਂ ਹਨ - ਇਹ ਉਹੀ ਪੈਟਰਨ ਹਨ ਜੋ ਵੀਡੀਓ ਗੇਮਾਂ ਤੋਂ ਬੈਂਕਿੰਗ ਸਿਸਟਮਾਂ ਤੱਕ ਸਭ ਕੁਝ ਚਲਾਉਂਦੇ ਹਨ। ਅਸੀਂ ਇੱਕ ਸੰਚਾਰ ਪ੍ਰਣਾਲੀ ਨੂੰ ਵੀ ਲਾਗੂ ਕਰਾਂਗੇ ਜਿਸਨੂੰ pub/sub ਕਿਹਾ ਜਾਂਦਾ ਹੈ ਜੋ ਸਪੇਸਕ੍ਰਾਫਟ ਵਿੱਚ ਵਰਤੀਆਂ ਜਾਣ ਵਾਲੀਆਂ ਸੰਚਾਰ ਜਾਲਾਂ ਵਾਂਗ ਕੰਮ ਕਰਦੀ ਹੈ, ਵੱਖ-ਵੱਖ ਹਿੱਸਿਆਂ ਨੂੰ ਜਾਣਕਾਰੀ ਸਾਂਝਾ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦੀ ਹੈ ਬਿਨਾਂ ਨਿਰਭਰਤਾ ਬਣਾਉਣ ਦੇ।

ਇਸ ਸਿਰੀਜ਼ ਦੇ ਅੰਤ ਤੱਕ, ਤੁਸੀਂ ਸਮਝ ਜਾਵੋਗੇ ਕਿ ਐਪਲੀਕੇਸ਼ਨ ਕਿਵੇਂ ਬਣਾਉਣੀਆਂ ਹਨ ਜੋ ਵਧ ਸਕਦੀਆਂ ਹਨ ਅਤੇ ਵਿਕਸਿਤ ਹੋ ਸਕਦੀਆਂ ਹਨ - ਚਾਹੇ ਤੁਸੀਂ ਗੇਮਾਂ, ਵੈੱਬ ਐਪਲੀਕੇਸ਼ਨ ਜਾਂ ਕੋਈ ਹੋਰ ਸਾਫਟਵੇਅਰ ਸਿਸਟਮ ਵਿਕਸਿਤ ਕਰ ਰਹੇ ਹੋਵੋ।

## ਪ੍ਰੀ-ਲੈਕਚਰ ਕਵਿਜ਼

[ਪ੍ਰੀ-ਲੈਕਚਰ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/29)

## ਗੇਮ ਡਿਵੈਲਪਮੈਂਟ ਵਿੱਚ ਵਾਰਸ ਅਤੇ ਰਚਨਾ

ਜਿਵੇਂ ਪ੍ਰੋਜੈਕਟ ਜਟਿਲਤਾ ਵਿੱਚ ਵਧਦੇ ਹਨ, ਕੋਡ ਦਾ ਸੰਗਠਨ ਮਹੱਤਵਪੂਰਨ ਬਣ ਜਾਂਦਾ ਹੈ। ਜੋ ਇੱਕ ਸਧਾਰਨ ਸਕ੍ਰਿਪਟ ਵਜੋਂ ਸ਼ੁਰੂ ਹੁੰਦਾ ਹੈ ਉਹ ਬਿਨਾਂ ਸਹੀ ਬਣਤਰ ਦੇ ਸੰਭਾਲਣਾ ਮੁਸ਼ਕਲ ਹੋ ਸਕਦਾ ਹੈ - ਬਿਲਕੁਲ ਜਿਵੇਂ Apollo ਮਿਸ਼ਨ ਨੂੰ ਹਜ਼ਾਰਾਂ ਹਿੱਸਿਆਂ ਦੇ ਵਿਚਕਾਰ ਧਿਆਨਪੂਰਵਕ ਸਹਿ-ਸੰਚਾਲਨ ਦੀ ਲੋੜ ਸੀ।

ਅਸੀਂ ਕੋਡ ਨੂੰ ਸੰਗਠਿਤ ਕਰਨ ਦੇ ਦੋ ਮੁੱਖ ਤਰੀਕੇ ਦੀ ਪੜਚੋਲ ਕਰਾਂਗੇ: ਵਾਰਸ ਅਤੇ ਰਚਨਾ। ਹਰ ਇੱਕ ਦੇ ਵੱਖ-ਵੱਖ ਫਾਇਦੇ ਹਨ, ਅਤੇ ਦੋਵਾਂ ਨੂੰ ਸਮਝਣ ਨਾਲ ਤੁਹਾਨੂੰ ਵੱਖ-ਵੱਖ ਸਥਿਤੀਆਂ ਲਈ ਸਹੀ ਤਰੀਕਾ ਚੁਣਨ ਵਿੱਚ ਮਦਦ ਮਿਲਦੀ ਹੈ। ਅਸੀਂ ਆਪਣੇ ਸਪੇਸ ਗੇਮ ਦੇ ਜ਼ਰੀਏ ਇਹ ਸੰਕਲਪ ਦਿਖਾਵਾਂਗੇ, ਜਿੱਥੇ ਹੀਰੋ, ਦੁਸ਼ਮਨ, ਪਾਵਰ-ਅੱਪਸ ਅਤੇ ਹੋਰ ਵਸਤੂਆਂ ਨੂੰ ਕੁਸ਼ਲਤਾਪੂਰਵਕ ਪਰਸਪਰ ਕਰਨਾ ਪਵੇਗਾ।

✅ ਸਭ ਤੋਂ ਪ੍ਰਸਿੱਧ ਪ੍ਰੋਗਰਾਮਿੰਗ ਕਿਤਾਬਾਂ ਵਿੱਚੋਂ ਇੱਕ [ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ](https://en.wikipedia.org/wiki/Design_Patterns) ਬਾਰੇ ਹੈ।

ਕਿਸੇ ਵੀ ਗੇਮ ਵਿੱਚ, ਤੁਹਾਡੇ ਕੋਲ `game objects` ਹੁੰਦੇ ਹਨ - ਇੰਟਰੈਕਟਿਵ ਤੱਤ ਜੋ ਤੁਹਾਡੇ ਗੇਮ ਵਰਲਡ ਨੂੰ ਭਰਦੇ ਹਨ। ਹੀਰੋ, ਦੁਸ਼ਮਨ, ਪਾਵਰ-ਅੱਪਸ ਅਤੇ ਵਿਜ਼ੁਅਲ ਪ੍ਰਭਾਵ ਸਾਰੇ ਗੇਮ ਆਬਜੈਕਟ ਹਨ। ਹਰ ਇੱਕ `x` ਅਤੇ `y` ਮੁੱਲਾਂ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋਏ ਨਿਰਧਾਰਤ ਸਕ੍ਰੀਨ ਕੋਆਰਡੀਨੇਟਸ 'ਤੇ ਮੌਜੂਦ ਹੁੰਦਾ ਹੈ, ਬਿਲਕੁਲ ਜਿਵੇਂ ਕੋਆਰਡੀਨੇਟ ਪਲੇਨ 'ਤੇ ਬਿੰਦੂ ਪਲਾਟ ਕਰਦੇ ਹਨ।

ਇਹਨਾਂ ਦੇ ਵਿਜ਼ੁਅਲ ਅੰਤਰ ਦੇ ਬਾਵਜੂਦ, ਇਹ ਵਸਤੂਆਂ ਅਕਸਰ ਮੁੱਢਲੇ ਵਿਹਾਰਾਂ ਨੂੰ ਸਾਂਝਾ ਕਰਦੀਆਂ ਹਨ:

- **ਇਹ ਕਿਤੇ ਮੌਜੂਦ ਹੁੰਦੀਆਂ ਹਨ** - ਹਰ ਵਸਤੂ ਦੇ x ਅਤੇ y ਕੋਆਰਡੀਨੇਟ ਹੁੰਦੇ ਹਨ ਤਾਂ ਜੋ ਗੇਮ ਨੂੰ ਪਤਾ ਹੋਵੇ ਕਿ ਇਸਨੂੰ ਕਿੱਥੇ ਡਰਾਅ ਕਰਨਾ ਹੈ
- **ਕਈ ਚਲ ਸਕਦੇ ਹਨ** - ਹੀਰੋ ਦੌੜਦੇ ਹਨ, ਦੁਸ਼ਮਨ ਪਿੱਛਾ ਕਰਦੇ ਹਨ, ਗੋਲੀਆਂ ਸਕ੍ਰੀਨ 'ਤੇ ਦੌੜਦੀਆਂ ਹਨ
- **ਇਹਨਾਂ ਦੀ ਉਮਰ ਹੁੰਦੀ ਹੈ** - ਕੁਝ ਹਮੇਸ਼ਾ ਰਹਿੰਦੇ ਹਨ, ਹੋਰ (ਜਿਵੇਂ ਧਮਾਕੇ) ਕੁਝ ਸਮੇਂ ਲਈ ਦਿਖਾਈ ਦਿੰਦੇ ਹਨ ਅਤੇ ਗਾਇਬ ਹੋ ਜਾਂਦੇ ਹਨ
- **ਇਹਨਾਂ ਦਾ ਪ੍ਰਤੀਕਰਮ ਹੁੰਦਾ ਹੈ** - ਜਦੋਂ ਚੀਜ਼ਾਂ ਟਕਰਾਉਂਦੀਆਂ ਹਨ, ਪਾਵਰ-ਅੱਪਸ ਇਕੱਠੇ ਕੀਤੇ ਜਾਂਦੇ ਹਨ, ਹੈਲਥ ਬਾਰ ਅੱਪਡੇਟ ਹੁੰਦੇ ਹਨ

✅ Pac-Man ਵਰਗੇ ਗੇਮ ਬਾਰੇ ਸੋਚੋ। ਕੀ ਤੁਸੀਂ ਇਸ ਗੇਮ ਵਿੱਚ ਉਪਰੋਕਤ ਚਾਰ ਆਬਜੈਕਟ ਕਿਸਮਾਂ ਦੀ ਪਹਿਚਾਣ ਕਰ ਸਕਦੇ ਹੋ?

### ਕੋਡ ਰਾਹੀਂ ਵਿਹਾਰ ਨੂੰ ਪ੍ਰਗਟ ਕਰਨਾ

ਹੁਣ ਜਦੋਂ ਤੁਹਾਨੂੰ ਸਮਝ ਆ ਗਈ ਹੈ ਕਿ ਗੇਮ ਆਬਜੈਕਟਾਂ ਸਾਂਝੇ ਵਿਹਾਰਾਂ ਨੂੰ ਕਿਵੇਂ ਸਾਂਝਾ ਕਰਦੇ ਹਨ, ਆਓ ਜਾਵਾਸਕ੍ਰਿਪਟ ਵਿੱਚ ਇਹ ਵਿਹਾਰ ਲਾਗੂ ਕਰਨ ਦੇ ਤਰੀਕੇ ਦੀ ਪੜਚੋਲ ਕਰੀਏ। ਤੁਸੀਂ ਕਲਾਸਾਂ ਜਾਂ ਵਿਅਕਤੀਗਤ ਆਬਜੈਕਟਾਂ ਨਾਲ ਜੁੜੇ ਤਰੀਕਿਆਂ ਰਾਹੀਂ ਆਬਜੈਕਟ ਵਿਹਾਰ ਨੂੰ ਪ੍ਰਗਟ ਕਰ ਸਕਦੇ ਹੋ, ਅਤੇ ਚੋਣ ਕਰਨ ਲਈ ਕਈ ਤਰੀਕੇ ਹਨ।

**ਕਲਾਸ-ਅਧਾਰਿਤ ਤਰੀਕਾ**

ਕਲਾਸਾਂ ਅਤੇ ਵਾਰਸ ਗੇਮ ਆਬਜੈਕਟਾਂ ਨੂੰ ਸੰਗਠਿਤ ਕਰਨ ਲਈ ਇੱਕ ਸੰਗਠਿਤ ਤਰੀਕਾ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ। ਜਿਵੇਂ ਕਿ Carl Linnaeus ਦੁਆਰਾ ਵਿਕਸਿਤ ਟੈਕਸੋਨੋਮਿਕ ਵਰਗੀਕਰਨ ਪ੍ਰਣਾਲੀ, ਤੁਸੀਂ ਆਮ ਗੁਣਾਂ ਵਾਲੀ ਬੇਸ ਕਲਾਸ ਨਾਲ ਸ਼ੁਰੂ ਕਰਦੇ ਹੋ, ਫਿਰ ਵਿਸ਼ੇਸ਼ ਯੋਗਤਾਵਾਂ ਸ਼ਾਮਲ ਕਰਦੇ ਹੋਏ ਇਹਨਾਂ ਮੁੱਢਲੇ ਗੁਣਾਂ ਨੂੰ ਵਾਰਸ ਕਰਨ ਵਾਲੀਆਂ ਵਿਸ਼ੇਸ਼ ਕਲਾਸਾਂ ਬਣਾਉਂਦੇ ਹੋ।

✅ ਵਾਰਸ ਨੂੰ ਸਮਝਣਾ ਇੱਕ ਮਹੱਤਵਪੂਰਨ ਸੰਕਲਪ ਹੈ। [MDN ਦੇ ਵਾਰਸ ਬਾਰੇ ਲੇਖ](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) 'ਤੇ ਹੋਰ ਜਾਣਕਾਰੀ ਪ੍ਰਾਪਤ ਕਰੋ।

ਇਹ ਹੈ ਕਿ ਤੁਸੀਂ ਕਲਾਸਾਂ ਅਤੇ ਵਾਰਸ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋਏ ਗੇਮ ਆਬਜੈਕਟਾਂ ਨੂੰ ਕਿਵੇਂ ਲਾਗੂ ਕਰ ਸਕਦੇ ਹੋ:

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

**ਆਓ ਇਸਨੂੰ ਕਦਮ-ਦਰ-ਕਦਮ ਵੰਡ ਕੇ ਸਮਝੀਏ:**
- ਅਸੀਂ ਇੱਕ ਬੁਨਿਆਦੀ ਟੈਂਪਲੇਟ ਬਣਾਉਂਦੇ ਹਾਂ ਜੋ ਹਰ ਗੇਮ ਆਬਜੈਕਟ ਵਰਤ ਸਕਦਾ ਹੈ
- ਕਨਸਟ੍ਰਕਟਰ ਸੇਵ ਕਰਦਾ ਹੈ ਕਿ ਆਬਜੈਕਟ ਕਿੱਥੇ ਹੈ (`x`, `y`) ਅਤੇ ਇਹ ਕਿਸ ਤਰ੍ਹਾਂ ਦੀ ਚੀਜ਼ ਹੈ
- ਇਹ ਉਹ ਅਧਾਰ ਬਣ ਜਾਂਦਾ ਹੈ ਜਿਸ 'ਤੇ ਤੁਹਾਡੇ ਸਾਰੇ ਗੇਮ ਆਬਜੈਕਟ ਬਣਾਏ ਜਾਣਗੇ

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

**ਉਪਰੋਕਤ ਵਿੱਚ, ਅਸੀਂ:**
- GameObject ਕਲਾਸ ਨੂੰ ਵਧਾਇਆ ਹੈ ਤਾਂ ਜੋ ਮੂਵਮੈਂਟ ਫੰਕਸ਼ਨਲਿਟੀ ਸ਼ਾਮਲ ਕੀਤੀ ਜਾ ਸਕੇ
- `super()` ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਪੇਰੈਂਟ ਕਨਸਟ੍ਰਕਟਰ ਨੂੰ ਕਾਲ ਕੀਤਾ ਹੈ ਤਾਂ ਜੋ ਵਾਰਸ ਕੀਤੇ ਗੁਣਾਂ ਨੂੰ ਸ਼ੁਰੂ ਕੀਤਾ ਜਾ ਸਕੇ
- ਇੱਕ `moveTo()` ਮੈਥਡ ਸ਼ਾਮਲ ਕੀਤਾ ਹੈ ਜੋ ਆਬਜੈਕਟ ਦੀ ਸਥਿਤੀ ਨੂੰ ਅੱਪਡੇਟ ਕਰਦਾ ਹੈ

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

**ਇਹ ਸੰਕਲਪਾਂ ਨੂੰ ਸਮਝਣਾ:**
- **ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ** ਵਾਲੇ ਆਬਜੈਕਟ ਕਿਸਮਾਂ ਬਣਾਉਂਦਾ ਹੈ ਜੋ ਉਚਿਤ ਵਿਹਾਰਾਂ ਨੂੰ ਵਾਰਸ ਕਰਦੇ ਹਨ
- **ਦਿਖਾਉਂਦਾ ਹੈ** ਕਿ ਵਾਰਸ ਕਿਵੇਂ ਚੁਣਵਾਂ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਨੂੰ ਸ਼ਾਮਲ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ
- **ਦਿਖਾਉਂਦਾ ਹੈ** ਕਿ ਹੀਰੋ ਚਲ ਸਕਦੇ ਹਨ ਜਦਕਿ ਦਰੱਖਤ ਅਸਥਿਰ ਰਹਿੰਦੇ ਹਨ
- **ਦਿਖਾਉਂਦਾ ਹੈ** ਕਿ ਕਲਾਸ ਹਾਇਰਾਰਕੀ ਅਣਚਾਹੇ ਕਾਰਵਾਈਆਂ ਨੂੰ ਰੋਕਦੀ ਹੈ

✅ ਕੁਝ ਮਿੰਟ ਲਓ ਅਤੇ Pac-Man ਹੀਰੋ (ਜਿਵੇਂ Inky, Pinky ਜਾਂ Blinky) ਨੂੰ ਦੁਬਾਰਾ ਸੋਚੋ ਅਤੇ ਇਹ ਕਿਵੇਂ ਜਾਵਾਸਕ੍ਰਿਪਟ ਵਿੱਚ ਲਿਖਿਆ ਜਾ ਸਕਦਾ ਹੈ।

**ਰਚਨਾ ਦਾ ਤਰੀਕਾ**

ਰਚਨਾ ਇੱਕ ਮਾਡਿਊਲਰ ਡਿਜ਼ਾਈਨ ਫਿਲਾਸਫੀ ਦੀ ਪਾਲਣਾ ਕਰਦੀ ਹੈ, ਬਿਲਕੁਲ ਜਿਵੇਂ ਇੰਜੀਨੀਅਰ ਸਪੇਸਕ੍ਰਾਫਟ ਨੂੰ ਅਦਲ-ਬਦਲ ਕਰਨ ਵਾਲੇ ਹਿੱਸਿਆਂ ਨਾਲ ਡਿਜ਼ਾਈਨ ਕਰਦੇ ਹਨ। ਪੇਰੈਂਟ ਕਲਾਸ ਤੋਂ ਵਾਰਸ ਕਰਨ ਦੀ ਬਜਾਏ, ਤੁਸੀਂ ਵਿਸ਼ੇਸ਼ ਵਿਹਾਰਾਂ ਨੂੰ ਜੋੜਦੇ ਹੋ ਤਾਂ ਜੋ ਆਬਜੈਕਟਾਂ ਨੂੰ ਉਹ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਮਿਲਣ ਜੋ ਉਹਨਾਂ ਨੂੰ ਲੋੜੀਂਦੀਆਂ ਹਨ। ਇਹ ਤਰੀਕਾ ਸਖਤ ਹਾਇਰਾਰਕੀਕਲ ਪਾਬੰਦੀਆਂ ਤੋਂ ਬਿਨਾਂ ਲਚਕਦਾਰਤਾ ਪ੍ਰਦਾਨ ਕਰਦਾ ਹੈ।

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

**ਇਹ ਕੋਡ ਕੀ ਕਰਦਾ ਹੈ:**
- **ਬੇਸ** `gameObject` ਨੂੰ ਸਥਿਤੀ ਅਤੇ ਕਿਸਮ ਗੁਣਾਂ ਨਾਲ ਪਰਿਭਾਸ਼ਿਤ ਕਰਦਾ ਹੈ
- **ਵੱਖਰੇ** `movable` ਵਿਹਾਰ ਆਬਜੈਕਟ ਨੂੰ ਮੂਵਮੈਂਟ ਫੰਕਸ਼ਨਲਿਟੀ ਨਾਲ ਬਣਾਉਂਦਾ ਹੈ
- **ਚਿੰਤਾਵਾਂ ਨੂੰ ਵੱਖ ਕਰਦਾ ਹੈ** ਸਥਿਤੀ ਡੇਟਾ ਅਤੇ ਮੂਵਮੈਂਟ ਲਾਜਿਕ ਨੂੰ ਅਜ਼ਾਦ ਰੱਖ ਕੇ

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

**ਉਪਰੋਕਤ ਵਿੱਚ, ਅਸੀਂ:**
- **ਬੇਸ** ਆਬਜੈਕਟ ਗੁਣਾਂ ਨੂੰ ਮੂਵਮੈਂਟ ਵਿਹਾਰ ਨਾਲ ਜੋੜਿਆ ਹੈ ਸਪ੍ਰੈਡ ਸਿੰਟੈਕਸ ਦੀ ਵਰਤੋਂ ਕਰਕੇ
- **ਫੈਕਟਰੀ ਫੰਕਸ਼ਨ** ਬਣਾਏ ਹਨ ਜੋ ਕਸਟਮਾਈਜ਼ਡ ਆਬਜੈਕਟ ਵਾਪਸ ਕਰਦੇ ਹਨ
- **ਲਚਕਦਾਰ** ਆਬਜੈਕਟ ਬਣਾਉਣ ਦੀ ਆਗਿਆ ਦਿੱਤੀ ਹੈ ਬਿਨਾਂ ਸਖਤ ਕਲਾਸ ਹਾਇਰਾਰਕੀਜ਼ ਦੇ
- **ਆਬਜੈਕਟਾਂ ਨੂੰ** ਉਹ ਵਿਹਾਰਾਂ ਦੇਣ ਦੀ ਆਗਿਆ ਦਿੱਤੀ ਹੈ ਜੋ ਉਹਨਾਂ ਨੂੰ ਲੋੜੀਂਦੇ ਹਨ

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**ਮੁੱਖ ਬਿੰਦੂ ਯਾਦ ਰੱਖੋ:**
- **ਆਬਜੈਕਟਾਂ ਨੂੰ** ਵਿਹਾਰਾਂ ਨੂੰ ਮਿਲਾ ਕੇ ਬਣਾਉਂਦਾ ਹੈ ਨਾ ਕਿ ਉਹਨਾਂ ਨੂੰ ਵਾਰਸ ਕਰਕੇ
- **ਸਖਤ ਵਾਰਸ ਹਾਇਰਾਰਕੀਜ਼ ਤੋਂ** ਵਧੇਰੇ ਲਚਕਦਾਰਤਾ ਪ੍ਰਦਾਨ ਕਰਦਾ ਹੈ
- **ਆਬਜੈਕਟਾਂ ਨੂੰ** ਉਹ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਦੇਣ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ ਜੋ ਉਹਨਾਂ ਨੂੰ ਲੋੜੀਂਦੀਆਂ ਹਨ
- **ਸਾਫਟਵੇਅਰ ਜਾਵਾਸਕ੍ਰਿਪਟ ਸਪ੍ਰੈਡ ਸਿੰਟੈਕਸ ਦੀ ਵਰਤੋਂ ਕਰਦਾ ਹੈ** ਸਾਫ ਸੰਗਠਨ ਲਈ

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

**ਇੱਥੇ ਕੀ ਹੁੰਦਾ ਹੈ:**
- **ਇੱਕ ਕੇਂਦਰੀ** ਇਵੈਂਟ ਮੈਨੇਜਮੈਂਟ ਸਿਸਟਮ ਬਣਾਉਂਦਾ ਹੈ ਇੱਕ ਸਧਾਰਨ ਕਲਾਸ ਦੀ ਵਰਤੋਂ ਕਰਕੇ
- **ਸੁਣਨ ਵਾਲਿਆਂ ਨੂੰ** ਇੱਕ ਆਬਜੈਕਟ ਵਿੱਚ ਸੰਗਠਿਤ ਕਰਦਾ ਹੈ ਜੋ ਸੁਨੇਹਾ ਕਿਸਮ ਦੁਆਰਾ ਸੰਗਠਿਤ ਹੁੰਦਾ ਹੈ
- **ਨਵੇਂ ਸੁਣਨ ਵਾਲਿਆਂ ਨੂੰ** `on()` ਮੈਥਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਰਜਿਸਟਰ ਕਰਦਾ ਹੈ
- **ਸਾਰੇ ਰੁਚੀ ਰੱਖਣ ਵਾਲੇ ਸੁਣਨ ਵਾਲਿਆਂ ਨੂੰ** ਸੁਨੇਹੇ ਪ੍ਰਸਾਰਿਤ ਕਰਦਾ ਹੈ `emit()` ਦੀ ਵਰਤੋਂ ਕਰਕੇ
- **ਵਿਕਲਪਿਕ ਡੇਟਾ ਪੇਲੋਡਾਂ** ਦਾ ਸਮਰਥਨ ਕਰਦਾ ਹੈ ਸਬੰਧਤ ਜਾਣਕਾਰੀ ਪਾਸ ਕਰਨ ਲਈ

### ਸਾਰਾ ਕੁਝ ਇਕੱਠੇ ਕਰਨਾ: ਇੱਕ ਵਿਹਾਰਕ ਉਦਾਹਰਨ

ਚਲੋ, ਇਸਨੂੰ ਕਾਰਵਾਈ ਵਿੱਚ ਵੇਖੀਏ! ਅਸੀਂ ਇੱਕ ਸਧਾਰਨ ਮੂਵਮੈਂਟ ਸਿਸਟਮ ਬਣਾਵਾਂਗੇ ਜੋ ਦਿਖਾਵੇਗਾ ਕਿ pub/sub ਕਿੰਨਾ ਸਾਫ ਅਤੇ ਲਚਕਦਾਰ ਹੋ ਸਕਦਾ ਹੈ:

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

**ਇਹ ਕੋਡ ਕੀ ਕਰਦਾ ਹੈ:**
- **ਸੁਨੇਹਾ ਨਾਮਾਂ ਵਿੱਚ ਟਾਈਪੋਜ਼ ਨੂੰ ਰੋਕਣ ਲਈ** ਇੱਕ constants ਆਬਜੈਕਟ ਪਰਿਭਾਸ਼ਿਤ ਕਰਦਾ ਹੈ
- **ਸਾਰੇ ਸੰਚਾਰ ਨੂੰ ਸੰਭਾਲਣ ਲਈ** ਇੱਕ ਇਵੈਂਟ ਐਮੀਟਰ ਇੰਸਟੈਂਸ ਬਣਾਉਂਦਾ ਹੈ
- **ਸ਼ੁਰੂਆਤੀ ਸਥਿਤੀ 'ਤੇ** ਇੱਕ ਹੀਰੋ ਆਬਜੈਕਟ ਸ਼ੁਰੂ ਕਰਦਾ ਹੈ

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

**ਉਪਰੋਕਤ ਵਿੱਚ, ਅਸੀਂ:**
- **ਇਵੈਂਟ ਸੁਣਨ ਵਾਲਿਆਂ ਨੂੰ ਰਜਿਸਟਰ ਕੀਤਾ** ਜੋ ਮੂਵਮੈਂਟ ਸੁਨੇਹਿਆਂ ਦਾ ਜਵਾਬ ਦਿੰਦੇ ਹਨ
- **ਹੀਰੋ ਦੀ ਸਥਿਤੀ ਨੂੰ ਅੱਪਡੇਟ ਕੀਤਾ** ਮੂਵਮੈਂਟ ਦਿਸ਼ਾ ਦੇ ਅਧਾਰ 'ਤੇ
- **ਹੀਰੋ ਦੀ ਸਥਿਤੀ ਬਦਲਾਅ ਨੂੰ ਟ੍ਰੈਕ ਕਰਨ ਲਈ** ਕਨਸੋਲ ਲੌਗਿੰਗ ਸ਼ਾਮਲ ਕੀਤੀ
- **ਮੂਵਮੈਂਟ ਲਾਜਿਕ ਨੂੰ ਇਨਪੁਟ ਹੈਂਡਲਿੰਗ ਤੋਂ ਵੱਖ ਕੀਤਾ**

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

**ਇਹ ਸੰਕਲਪਾਂ ਨੂੰ ਸਮਝਣਾ:**
- **ਕੀਬੋਰਡ ਇਨਪੁਟ ਨੂੰ** ਗੇਮ ਇਵੈਂਟਾਂ ਨਾਲ ਬਿਨਾਂ ਸਖਤ ਜੁੜਨ ਦੇ ਜੋੜਦਾ ਹੈ
- **ਇਨਪੁਟ ਸਿਸਟਮ ਨੂੰ** ਗੇਮ ਆਬਜੈਕਟਾਂ ਨਾਲ ਅਪਰੋਕਸ਼ ਸੰਚਾਰ ਕਰਨ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ
- **ਇੱਕੋ ਹੀ ਕੀਬੋਰਡ ਇਵੈਂਟਾਂ ਲਈ** ਕਈ ਸਿਸਟਮਾਂ ਨੂੰ ਜਵਾਬ ਦੇਣ ਦੀ ਆਗਿਆ ਦਿੰਦਾ ਹੈ
- **ਕੀਬਾਈਂਡਿੰਗ ਨੂੰ ਬਦਲਣ ਜਾਂ ਨਵੇਂ ਇਨਪੁਟ ਤਰੀਕੇ ਸ਼ਾਮਲ ਕਰਨ ਨੂੰ** ਆਸਾਨ ਬਣਾਉਂਦਾ ਹੈ

> 💡 **ਪ੍ਰੋ ਟਿਪ**: ਇਸ ਪੈਟਰਨ ਦੀ ਖੂਬਸੂਰਤੀ ਲਚਕਦਾਰਤਾ ਹੈ! ਤੁਸੀਂ ਆਸਾਨੀ ਨਾਲ ਸਾਊਂਡ ਇਫੈਕਟ, ਸਕ੍ਰੀਨ ਸ਼ੇਕ ਜਾਂ ਪਾਰਟੀਕਲ ਇਫੈਕਟ ਸ਼ਾਮਲ ਕਰ ਸਕਦੇ ਹੋ ਸਿਰਫ਼ ਹੋਰ ਇਵੈਂਟ ਸੁਣਨ ਵਾਲੇ ਸ਼ਾਮਲ ਕਰਕੇ - ਮੌਜੂਦਾ ਕੀਬੋਰਡ ਜਾਂ ਮੂਵਮੈਂਟ ਕੋਡ ਨੂੰ ਬਦਲਣ ਦੀ ਲੋੜ ਨਹੀਂ।

**ਇਸ ਤਰੀਕੇ ਨੂੰ ਪਸੰਦ ਕਰਨ ਦੇ ਕਾਰਨ:**
- ਨਵੀਆਂ ਵਿਸ਼ੇਸ਼ਤਾਵਾਂ ਸ਼ਾਮਲ ਕਰਨਾ ਬਹੁਤ ਆਸਾਨ ਬਣ ਜਾਂਦਾ ਹੈ - ਸਿਰਫ਼ ਉਹਨਾਂ ਇਵੈਂਟਾਂ ਨੂੰ ਸੁਣੋ ਜੋ ਤੁਹਾਨੂੰ ਲੋੜੀਂਦੇ ਹਨ
- ਕਈ ਚੀਜ਼ਾਂ ਇੱਕੋ ਹੀ ਇਵੈਂਟ 'ਤੇ ਪ੍ਰਤੀਕਰਮ ਕਰ ਸਕਦੀਆਂ ਹਨ ਬਿਨਾਂ ਇੱਕ-ਦੂਜੇ ਨੂੰ ਰੋਕਣ ਦੇ
- ਟੈਸਟਿੰਗ ਬਹੁਤ ਆਸਾਨ ਹੋ ਜਾਂਦੀ ਹੈ ਕਿਉਂਕਿ ਹਰ ਹਿੱਸਾ ਅਜ਼ਾਦ ਤੌਰ 'ਤੇ ਕੰਮ ਕਰਦਾ ਹੈ
- ਜਦੋਂ ਕੁਝ ਟੁੱਟਦਾ ਹੈ, ਤੁਹਾਨੂੰ ਪਤਾ ਹੁੰਦਾ ਹੈ ਕਿ ਕਿੱਥੇ ਵੇਖਣਾ ਹੈ

### ਕਿਉਂ pub/sub ਪ੍ਰਭਾਵਸ਼ਾਲੀ ਤਰੀਕੇ ਨਾਲ ਸਕੇਲ ਕਰਦਾ

---

**ਅਸਵੀਕਰਤੀ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁੱਤੀਆਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਇਸਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।