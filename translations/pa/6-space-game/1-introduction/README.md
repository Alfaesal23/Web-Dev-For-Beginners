<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "38777f8c81874368d3b4b9b8a54aa242",
  "translation_date": "2025-10-20T22:09:08+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "pa"
}
-->
# ਸਪੇਸ ਗੇਮ ਬਣਾਓ ਭਾਗ 1: ਜਾਣ ਪਛਾਣ

![video](../../../../6-space-game/images/pewpew.gif)

## ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵਿਜ਼

[ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/29)

### ਗੇਮ ਡਿਵੈਲਪਮੈਂਟ ਵਿੱਚ ਵਾਰਸਿਕਤਾ ਅਤੇ ਰਚਨਾ

ਪਿਛਲੇ ਪਾਠਾਂ ਵਿੱਚ, ਤੁਸੀਂ ਜੋ ਐਪਸ ਬਣਾਈਆਂ, ਉਹ ਬਹੁਤ ਛੋਟੇ ਪੱਧਰ ਦੇ ਪ੍ਰਾਜੈਕਟ ਸਨ, ਇਸ ਲਈ ਡਿਜ਼ਾਈਨ ਆਰਕੀਟੈਕਚਰ ਬਾਰੇ ਜ਼ਿਆਦਾ ਸੋਚਣ ਦੀ ਲੋੜ ਨਹੀਂ ਸੀ। ਪਰ ਜਦੋਂ ਤੁਹਾਡੇ ਐਪਲੀਕੇਸ਼ਨ ਦਾ ਆਕਾਰ ਅਤੇ ਦਾਇਰਾ ਵਧਦਾ ਹੈ, ਤਾਂ ਆਰਕੀਟੈਕਚਰਲ ਫੈਸਲੇ ਮਹੱਤਵਪੂਰਨ ਹੋ ਜਾਂਦੇ ਹਨ। ਜਾਵਾਸਕ੍ਰਿਪਟ ਵਿੱਚ ਵੱਡੇ ਐਪਲੀਕੇਸ਼ਨ ਬਣਾਉਣ ਦੇ ਦੋ ਮੁੱਖ ਤਰੀਕੇ ਹਨ: *ਰਚਨਾ* ਜਾਂ *ਵਾਰਸਿਕਤਾ*। ਦੋਹਾਂ ਦੇ ਫਾਇਦੇ ਅਤੇ ਨੁਕਸਾਨ ਹਨ, ਪਰ ਆਓ ਇਸਨੂੰ ਗੇਮ ਦੇ ਸੰਦਰਭ ਵਿੱਚ ਸਮਝੀਏ।

✅ ਸਭ ਤੋਂ ਪ੍ਰਸਿੱਧ ਪ੍ਰੋਗਰਾਮਿੰਗ ਕਿਤਾਬਾਂ ਵਿੱਚੋਂ ਇੱਕ [ਡਿਜ਼ਾਈਨ ਪੈਟਰਨ](https://en.wikipedia.org/wiki/Design_Patterns) ਬਾਰੇ ਹੈ।

ਇੱਕ ਗੇਮ ਵਿੱਚ ਤੁਹਾਡੇ ਕੋਲ `game objects` ਹੁੰਦੇ ਹਨ ਜੋ ਸਕ੍ਰੀਨ 'ਤੇ ਮੌਜੂਦ ਹੁੰਦੇ ਹਨ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਇਹਨਾਂ ਦੀ ਕਾਰਟੀਸ਼ੀਅਨ ਕੋਆਰਡੀਨੇਟ ਸਿਸਟਮ 'ਤੇ ਸਥਿਤੀ ਹੁੰਦੀ ਹੈ, ਜਿਸਨੂੰ `x` ਅਤੇ `y` ਕੋਆਰਡੀਨੇਟ ਦੁਆਰਾ ਦਰਸਾਇਆ ਜਾਂਦਾ ਹੈ। ਜਦੋਂ ਤੁਸੀਂ ਗੇਮ ਵਿਕਸਿਤ ਕਰਦੇ ਹੋ, ਤਾਂ ਤੁਹਾਨੂੰ ਪਤਾ ਲੱਗੇਗਾ ਕਿ ਤੁਹਾਡੇ ਸਾਰੇ ਗੇਮ ਆਬਜੈਕਟਸ ਵਿੱਚ ਇੱਕ ਸਧਾਰਨ ਗੁਣ ਹੁੰਦਾ ਹੈ, ਜੋ ਹਰ ਗੇਮ ਵਿੱਚ ਆਮ ਹੁੰਦਾ ਹੈ, ਜਿਵੇਂ ਕਿ:

- **ਸਥਿਤੀ-ਅਧਾਰਿਤ** ਜ਼ਿਆਦਾਤਰ, ਜੇਕਰ ਸਾਰੇ ਨਹੀਂ, ਗੇਮ ਆਬਜੈਕਟਸ ਸਥਿਤੀ-ਅਧਾਰਿਤ ਹੁੰਦੇ ਹਨ। ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਇਹਨਾਂ ਦੀ ਇੱਕ ਸਥਿਤੀ ਹੁੰਦੀ ਹੈ, `x` ਅਤੇ `y`।
- **ਚਲਣਯੋਗ** ਇਹ ਉਹ ਆਬਜੈਕਟਸ ਹਨ ਜੋ ਨਵੀਂ ਸਥਿਤੀ ਵੱਲ ਚੱਲ ਸਕਦੇ ਹਨ। ਇਹ ਆਮ ਤੌਰ 'ਤੇ ਇੱਕ ਹੀਰੋ, ਇੱਕ ਮਾਨਸਟਰ ਜਾਂ ਇੱਕ NPC (ਨਾਨ ਪਲੇਅਰ ਕਿਰਦਾਰ) ਹੁੰਦਾ ਹੈ, ਪਰ ਉਦਾਹਰਣ ਲਈ, ਇੱਕ ਸਥਿਰ ਆਬਜੈਕਟ ਜਿਵੇਂ ਕਿ ਇੱਕ ਦਰੱਖਤ ਨਹੀਂ।
- **ਸਵੈ-ਵਿਨਾਸ਼ਕ** ਇਹ ਆਬਜੈਕਟਸ ਸਿਰਫ਼ ਇੱਕ ਨਿਰਧਾਰਿਤ ਸਮੇਂ ਲਈ ਮੌਜੂਦ ਹੁੰਦੇ ਹਨ, ਇਸ ਤੋਂ ਪਹਿਲਾਂ ਕਿ ਇਹ ਆਪਣੇ ਆਪ ਨੂੰ ਮਿਟਾਉਣ ਲਈ ਸੈਟ ਕਰ ਲੈਂਦੇ ਹਨ। ਆਮ ਤੌਰ 'ਤੇ ਇਹ `dead` ਜਾਂ `destroyed` ਬੂਲੀਅਨ ਦੁਆਰਾ ਦਰਸਾਇਆ ਜਾਂਦਾ ਹੈ ਜੋ ਗੇਮ ਇੰਜਨ ਨੂੰ ਸੰਕੇਤ ਦਿੰਦਾ ਹੈ ਕਿ ਇਹ ਆਬਜੈਕਟ ਹੁਣ ਰੈਂਡਰ ਨਹੀਂ ਕੀਤਾ ਜਾਣਾ ਚਾਹੀਦਾ।
- **ਕੂਲ-ਡਾਊਨ** 'ਕੂਲ-ਡਾਊਨ' ਛੋਟੇ ਸਮੇਂ ਲਈ ਮੌਜੂਦ ਆਬਜੈਕਟਸ ਵਿੱਚ ਇੱਕ ਆਮ ਗੁਣ ਹੈ। ਇੱਕ ਆਮ ਉਦਾਹਰਣ ਇੱਕ ਟੈਕਸਟ ਜਾਂ ਗ੍ਰਾਫਿਕਲ ਪ੍ਰਭਾਵ ਜਿਵੇਂ ਕਿ ਧਮਾਕਾ ਹੈ ਜੋ ਸਿਰਫ਼ ਕੁਝ ਮਿਲੀਸੈਕੰਡ ਲਈ ਦਿਖਾਈ ਦੇਣਾ ਚਾਹੀਦਾ ਹੈ।

✅ ਪੈਕ-ਮੈਨ ਵਰਗੇ ਗੇਮ ਬਾਰੇ ਸੋਚੋ। ਕੀ ਤੁਸੀਂ ਇਸ ਗੇਮ ਵਿੱਚ ਉਪਰੋਕਤ ਚਾਰ ਆਬਜੈਕਟ ਕਿਸਮਾਂ ਦੀ ਪਹਿਚਾਣ ਕਰ ਸਕਦੇ ਹੋ?

### ਵਿਹਾਰ ਨੂੰ ਦਰਸਾਉਣਾ

ਜੋ ਕੁਝ ਅਸੀਂ ਉਪਰ ਦਰਸਾਇਆ ਹੈ, ਉਹ ਸਾਰੇ ਵਿਹਾਰ ਹਨ ਜੋ ਗੇਮ ਆਬਜੈਕਟਸ ਵਿੱਚ ਹੋ ਸਕਦੇ ਹਨ। ਤਾਂ ਅਸੀਂ ਇਹਨਾਂ ਨੂੰ ਕਿਵੇਂ ਕੋਡ ਕਰਦੇ ਹਾਂ? ਅਸੀਂ ਇਹ ਵਿਹਾਰ ਕਲਾਸਾਂ ਜਾਂ ਆਬਜੈਕਟਸ ਨਾਲ ਸੰਬੰਧਿਤ ਵਿਧੀਆਂ ਵਜੋਂ ਦਰਸਾ ਸਕਦੇ ਹਾਂ।

**ਕਲਾਸਾਂ**

ਵਿਚਾਰ ਇਹ ਹੈ ਕਿ `classes` ਨੂੰ `inheritance` ਦੇ ਨਾਲ ਵਰਤ ਕੇ ਇੱਕ ਕਲਾਸ ਵਿੱਚ ਇੱਕ ਨਿਰਧਾਰਿਤ ਵਿਹਾਰ ਸ਼ਾਮਲ ਕੀਤਾ ਜਾਵੇ।

✅ ਵਾਰਸਿਕਤਾ ਨੂੰ ਸਮਝਣਾ ਇੱਕ ਮਹੱਤਵਪੂਰਨ ਸੰਕਲਪ ਹੈ। [MDN ਦੇ ਲੇਖ ਵਾਰਸਿਕਤਾ ਬਾਰੇ](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) ਵਿੱਚ ਹੋਰ ਜਾਣੋ।

ਕੋਡ ਦੁਆਰਾ ਦਰਸਾਇਆ ਗਿਆ, ਇੱਕ ਗੇਮ ਆਬਜੈਕਟ ਆਮ ਤੌਰ 'ਤੇ ਇਸ ਤਰ੍ਹਾਂ ਲੱਗ ਸਕਦਾ ਹੈ:

```javascript

//set up the class GameObject
class GameObject {
  constructor(x, y, type) {
    this.x = x;
    this.y = y;
    this.type = type;
  }
}

//this class will extend the GameObject's inherent class properties
class Movable extends GameObject {
  constructor(x,y, type) {
    super(x,y, type)
  }

//this movable object can be moved on the screen
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}

//this is a specific class that extends the Movable class, so it can take advantage of all the properties that it inherits
class Hero extends Movable {
  constructor(x,y) {
    super(x,y, 'Hero')
  }
}

//this class, on the other hand, only inherits the GameObject properties
class Tree extends GameObject {
  constructor(x,y) {
    super(x,y, 'Tree')
  }
}

//a hero can move...
const hero = new Hero();
hero.moveTo(5,5);

//but a tree cannot
const tree = new Tree();
```

✅ ਕੁਝ ਮਿੰਟ ਲਓ ਅਤੇ ਪੈਕ-ਮੈਨ ਹੀਰੋ (ਜਿਵੇਂ ਕਿ ਇੰਕੀ, ਪਿੰਕੀ ਜਾਂ ਬਲਿੰਕੀ) ਨੂੰ ਦੁਬਾਰਾ ਸੋਚੋ ਅਤੇ ਇਹ ਜਾਵਾਸਕ੍ਰਿਪਟ ਵਿੱਚ ਕਿਵੇਂ ਲਿਖਿਆ ਜਾਵੇਗਾ।

**ਰਚਨਾ**

ਆਬਜੈਕਟ ਵਾਰਸਿਕਤਾ ਨੂੰ ਸੰਭਾਲਣ ਦਾ ਇੱਕ ਵੱਖਰਾ ਤਰੀਕਾ *ਰਚਨਾ* ਦੁਆਰਾ ਹੈ। ਫਿਰ, ਆਬਜੈਕਟਸ ਆਪਣਾ ਵਿਹਾਰ ਇਸ ਤਰ੍ਹਾਂ ਦਰਸਾਉਂਦੇ ਹਨ:

```javascript
//create a constant gameObject
const gameObject = {
  x: 0,
  y: 0,
  type: ''
};

//...and a constant movable
const movable = {
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}
//then the constant movableObject is composed of the gameObject and movable constants
const movableObject = {...gameObject, ...movable};

//then create a function to create a new Hero who inherits the movableObject properties
function createHero(x, y) {
  return {
    ...movableObject,
    x,
    y,
    type: 'Hero'
  }
}
//...and a static object that inherits only the gameObject properties
function createStatic(x, y, type) {
  return {
    ...gameObject
    x,
    y,
    type
  }
}
//create the hero and move it
const hero = createHero(10,10);
hero.moveTo(5,5);
//and create a static tree which only stands around
const tree = createStatic(0,0, 'Tree'); 
```

**ਮੈਨੂੰ ਕਿਹੜਾ ਪੈਟਰਨ ਵਰਤਣਾ ਚਾਹੀਦਾ ਹੈ?**

ਤੁਹਾਡੇ ਉੱਤੇ ਹੈ ਕਿ ਤੁਸੀਂ ਕਿਹੜਾ ਪੈਟਰਨ ਚੁਣਦੇ ਹੋ। ਜਾਵਾਸਕ੍ਰਿਪਟ ਦੋਹਾਂ ਪੈਰਾਡਾਈਮਜ਼ ਦਾ ਸਮਰਥਨ ਕਰਦਾ ਹੈ।

--

ਗੇਮ ਡਿਵੈਲਪਮੈਂਟ ਵਿੱਚ ਇੱਕ ਹੋਰ ਆਮ ਪੈਟਰਨ ਗੇਮ ਦੇ ਯੂਜ਼ਰ ਅਨੁਭਵ ਅਤੇ ਪ੍ਰਦਰਸ਼ਨ ਨੂੰ ਸੰਭਾਲਣ ਦੀ ਸਮੱਸਿਆ ਨੂੰ ਹੱਲ ਕਰਦਾ ਹੈ।

## ਪਬ/ਸਬ ਪੈਟਰਨ

✅ ਪਬ/ਸਬ ਦਾ ਮਤਲਬ ਹੈ 'ਪਬਲਿਸ਼-ਸਬਸਕ੍ਰਾਈਬ'

ਇਹ ਪੈਟਰਨ ਇਸ ਵਿਚਾਰ ਨੂੰ ਦਰਸਾਉਂਦਾ ਹੈ ਕਿ ਤੁਹਾਡੇ ਐਪਲੀਕੇਸ਼ਨ ਦੇ ਵੱਖ-ਵੱਖ ਹਿੱਸੇ ਇੱਕ-ਦੂਜੇ ਬਾਰੇ ਨਹੀਂ ਜਾਣਦੇ। ਇਹ ਕਿਉਂ ਹੈ? ਜੇਕਰ ਵੱਖ-ਵੱਖ ਹਿੱਸੇ ਵੱਖਰੇ ਹਨ ਤਾਂ ਆਮ ਤੌਰ 'ਤੇ ਕੀ ਹੋ ਰਿਹਾ ਹੈ ਇਹ ਦੇਖਣਾ ਬਹੁਤ ਆਸਾਨ ਹੋ ਜਾਂਦਾ ਹੈ। ਇਹ ਇਸਨੂੰ ਅਚਾਨਕ ਵਿਹਾਰ ਬਦਲਣ ਲਈ ਵੀ ਆਸਾਨ ਬਣਾਉਂਦਾ ਹੈ ਜੇਕਰ ਤੁਹਾਨੂੰ ਲੋੜ ਹੋਵੇ। ਅਸੀਂ ਇਹ ਕਿਵੇਂ ਹਾਸਲ ਕਰਦੇ ਹਾਂ? ਅਸੀਂ ਕੁਝ ਸੰਕਲਪ ਸਥਾਪਿਤ ਕਰਕੇ ਇਹ ਕਰਦੇ ਹਾਂ:

- **ਸੁਨੇਹਾ**: ਇੱਕ ਸੁਨੇਹਾ ਆਮ ਤੌਰ 'ਤੇ ਇੱਕ ਟੈਕਸਟ ਸਟ੍ਰਿੰਗ ਹੁੰਦਾ ਹੈ ਜਿਸਦੇ ਨਾਲ ਇੱਕ ਵਿਕਲਪਿਕ ਪੇਲੋਡ (ਡਾਟਾ ਦਾ ਇੱਕ ਟੁਕੜਾ ਜੋ ਦਰਸਾਉਂਦਾ ਹੈ ਕਿ ਸੁਨੇਹਾ ਕਿਸ ਬਾਰੇ ਹੈ) ਹੁੰਦਾ ਹੈ। ਗੇਮ ਵਿੱਚ ਇੱਕ ਆਮ ਸੁਨੇਹਾ `KEY_PRESSED_ENTER` ਹੋ ਸਕਦਾ ਹੈ।
- **ਪਬਲਿਸ਼ਰ**: ਇਹ ਤੱਤ ਇੱਕ ਸੁਨੇਹਾ *ਪਬਲਿਸ਼* ਕਰਦਾ ਹੈ ਅਤੇ ਇਸਨੂੰ ਸਾਰੇ ਸਬਸਕ੍ਰਾਈਬਰਾਂ ਨੂੰ ਭੇਜਦਾ ਹੈ।
- **ਸਬਸਕ੍ਰਾਈਬਰ**: ਇਹ ਤੱਤ ਨਿਰਧਾਰਿਤ ਸੁਨੇਹਿਆਂ ਨੂੰ *ਸੁਣਦਾ* ਹੈ ਅਤੇ ਇਸ ਸੁਨੇਹੇ ਨੂੰ ਪ੍ਰਾਪਤ ਕਰਨ ਦੇ ਨਤੀਜੇ ਵਜੋਂ ਕੁਝ ਕੰਮ ਕਰਦਾ ਹੈ, ਜਿਵੇਂ ਕਿ ਲੇਜ਼ਰ ਚਲਾਉਣਾ।

ਇਸਦੀ ਕਾਰਗੁਜ਼ਾਰੀ ਆਕਾਰ ਵਿੱਚ ਬਹੁਤ ਛੋਟੀ ਹੈ ਪਰ ਇਹ ਇੱਕ ਬਹੁਤ ਹੀ ਸ਼ਕਤੀਸ਼ਾਲੀ ਪੈਟਰਨ ਹੈ। ਇਹ ਇਸ ਤਰ੍ਹਾਂ ਲਾਗੂ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ:

```javascript
//set up an EventEmitter class that contains listeners
class EventEmitter {
  constructor() {
    this.listeners = {};
  }
//when a message is received, let the listener to handle its payload
  on(message, listener) {
    if (!this.listeners[message]) {
      this.listeners[message] = [];
    }
    this.listeners[message].push(listener);
  }
//when a message is sent, send it to a listener with some payload
  emit(message, payload = null) {
    if (this.listeners[message]) {
      this.listeners[message].forEach(l => l(message, payload))
    }
  }
}

```

ਉਪਰੋਕਤ ਕੋਡ ਨੂੰ ਵਰਤਣ ਲਈ ਅਸੀਂ ਇੱਕ ਬਹੁਤ ਛੋਟੀ ਕਾਰਗੁਜ਼ਾਰੀ ਬਣਾਉਣ ਲਈ ਇਹ ਕਰ ਸਕਦੇ ਹਾਂ:

```javascript
//set up a message structure
const Messages = {
  HERO_MOVE_LEFT: 'HERO_MOVE_LEFT'
};
//invoke the eventEmitter you set up above
const eventEmitter = new EventEmitter();
//set up a hero
const hero = createHero(0,0);
//let the eventEmitter know to watch for messages pertaining to the hero moving left, and act on it
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});

//set up the window to listen for the keyup event, specifically if the left arrow is hit, emit a message to move the hero left
window.addEventListener('keyup', (evt) => {
  if (evt.key === 'ArrowLeft') {
    eventEmitter.emit(Messages.HERO_MOVE_LEFT)
  }
});
```

ਉਪਰ ਅਸੀਂ ਇੱਕ ਕੀਬੋਰਡ ਇਵੈਂਟ, `ArrowLeft` ਨੂੰ ਜੋੜਿਆ ਅਤੇ `HERO_MOVE_LEFT` ਸੁਨੇਹਾ ਭੇਜਿਆ। ਅਸੀਂ ਉਸ ਸੁਨੇਹੇ ਨੂੰ ਸੁਣਦੇ ਹਾਂ ਅਤੇ ਨਤੀਜੇ ਵਜੋਂ `hero` ਨੂੰ ਚਲਾਉਂਦੇ ਹਾਂ। ਇਸ ਪੈਟਰਨ ਦੀ ਤਾਕਤ ਇਹ ਹੈ ਕਿ ਇਵੈਂਟ ਲਿਸਨਰ ਅਤੇ ਹੀਰੋ ਇੱਕ-ਦੂਜੇ ਬਾਰੇ ਨਹੀਂ ਜਾਣਦੇ। ਤੁਸੀਂ `ArrowLeft` ਨੂੰ `A` ਕੀ ਨਾਲ ਰੀਮੈਪ ਕਰ ਸਕਦੇ ਹੋ। ਇਸ ਤੋਂ ਇਲਾਵਾ, ਇਹ ਸੰਭਵ ਹੋਵੇਗਾ ਕਿ `ArrowLeft` 'ਤੇ ਕੁਝ ਬਿਲਕੁਲ ਵੱਖਰਾ ਕੀਤਾ ਜਾਵੇ, ਸਿਰਫ਼ eventEmitter ਦੇ `on` ਫੰਕਸ਼ਨ ਵਿੱਚ ਕੁਝ ਸੋਧਾਂ ਕਰਕੇ:

```javascript
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});
```

ਜਦੋਂ ਤੁਹਾਡਾ ਗੇਮ ਵਧਦਾ ਹੈ ਅਤੇ ਚੀਜ਼ਾਂ ਜਟਿਲ ਹੋ ਜਾਂਦੀਆਂ ਹਨ, ਇਹ ਪੈਟਰਨ ਜਟਿਲਤਾ ਵਿੱਚ ਇੱਕੋ ਜਿਹਾ ਰਹਿੰਦਾ ਹੈ ਅਤੇ ਤੁਹਾਡਾ ਕੋਡ ਸਾਫ਼ ਰਹਿੰਦਾ ਹੈ। ਇਹ ਪੈਟਰਨ ਅਪਨਾਉਣ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ।

---

## GitHub Copilot Agent ਚੈਲੈਂਜ 🚀

Agent ਮੋਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਚੈਲੈਂਜ ਨੂੰ ਪੂਰਾ ਕਰੋ:

**ਵੇਰਵਾ:** ਵਾਰਸਿਕਤਾ ਅਤੇ ਪਬ/ਸਬ ਪੈਟਰਨ ਦੋਹਾਂ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਇੱਕ ਸਧਾਰਨ ਗੇਮ ਆਬਜੈਕਟ ਸਿਸਟਮ ਬਣਾਓ। ਤੁਸੀਂ ਇੱਕ ਬੁਨਿਆਦੀ ਗੇਮ ਲਾਗੂ ਕਰੋਗੇ ਜਿੱਥੇ ਵੱਖ-ਵੱਖ ਆਬਜੈਕਟਸ ਇੱਕ-ਦੂਜੇ ਬਾਰੇ ਸਿੱਧੇ ਜਾਣਕਾਰੀ ਰੱਖਣ ਤੋਂ ਬਿਨਾਂ ਇਵੈਂਟਸ ਰਾਹੀਂ ਸੰਚਾਰ ਕਰ ਸਕਦੇ ਹਨ।

**ਪ੍ਰੋੰਪਟ:** ਹੇਠਾਂ ਦਿੱਤੇ ਲੋੜਾਂ ਦੇ ਨਾਲ ਇੱਕ ਜਾਵਾਸਕ੍ਰਿਪਟ ਗੇਮ ਸਿਸਟਮ ਬਣਾਓ: 1) x, y ਕੋਆਰਡੀਨੇਟਸ ਅਤੇ ਇੱਕ type ਗੁਣ ਵਾਲੀ ਬੇਸ GameObject ਕਲਾਸ ਬਣਾਓ। 2) Hero ਕਲਾਸ ਬਣਾਓ ਜੋ GameObject ਤੋਂ ਵਾਰਸਿਕ ਹੋਵੇ ਅਤੇ ਚੱਲ ਸਕੇ। 3) Enemy ਕਲਾਸ ਬਣਾਓ ਜੋ GameObject ਤੋਂ ਵਾਰਸਿਕ ਹੋਵੇ ਅਤੇ ਹੀਰੋ ਦਾ ਪਿੱਛਾ ਕਰ ਸਕੇ। 4) ਪਬ/ਸਬ ਪੈਟਰਨ ਲਈ ਇੱਕ EventEmitter ਕਲਾਸ ਲਾਗੂ ਕਰੋ। 5) ਇਵੈਂਟ ਲਿਸਨਰ ਸੈਟ ਕਰੋ ਤਾਂ ਜੋ ਜਦੋਂ ਹੀਰੋ ਚੱਲਦਾ ਹੈ, ਨੇੜੇ ਦੇ ਦੁਸ਼ਮਨ `HERO_MOVED` ਇਵੈਂਟ ਪ੍ਰਾਪਤ ਕਰਦੇ ਹਨ ਅਤੇ ਹੀਰੋ ਵੱਲ ਚੱਲਣ ਲਈ ਆਪਣੀ ਸਥਿਤੀ ਅਪਡੇਟ ਕਰਦੇ ਹਨ। ਆਬਜੈਕਟਸ ਦੇ ਵਿਚਕਾਰ ਸੰਚਾਰ ਦਿਖਾਉਣ ਲਈ console.log ਬਿਆਨ ਸ਼ਾਮਲ ਕਰੋ।

## 🚀 ਚੈਲੈਂਜ

ਸੋਚੋ ਕਿ ਪਬ-ਸਬ ਪੈਟਰਨ ਇੱਕ ਗੇਮ ਨੂੰ ਕਿਵੇਂ ਵਧੀਆ ਬਣਾ ਸਕਦਾ ਹੈ। ਕਿਹੜੇ ਹਿੱਸੇ ਇਵੈਂਟਸ ਨੂੰ ਜਾਰੀ ਕਰਨ ਚਾਹੀਦੇ ਹਨ, ਅਤੇ ਗੇਮ ਨੂੰ ਇਹਨਾਂ 'ਤੇ ਕਿਵੇਂ ਪ੍ਰਤੀਕਿਰਿਆ ਕਰਨੀ ਚਾਹੀਦੀ ਹੈ? ਹੁਣ ਤੁਹਾਡੇ ਕੋਲ ਇੱਕ ਨਵਾਂ ਗੇਮ ਸੋਚਣ ਦਾ ਮੌਕਾ ਹੈ ਅਤੇ ਇਸਦੇ ਹਿੱਸੇ ਕਿਵੇਂ ਵਿਹਾਰ ਕਰ ਸਕਦੇ ਹਨ।

## ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵਿਜ਼

[ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/30)

## ਸਮੀਖਿਆ ਅਤੇ ਖੁਦ ਅਧਿਐਨ

ਪਬ/ਸਬ ਬਾਰੇ ਹੋਰ ਜਾਣਕਾਰੀ ਪ੍ਰਾਪਤ ਕਰੋ [ਇਸ ਬਾਰੇ ਪੜ੍ਹ ਕੇ](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon)।

## ਅਸਾਈਨਮੈਂਟ

[ਗੇਮ ਬਣਾਓ](assignment.md)

---

**ਅਸਵੀਕਰਤਾ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁਚੀਤਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਇਸਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।