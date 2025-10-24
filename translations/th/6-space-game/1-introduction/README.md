<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-23T21:20:54+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "th"
}
-->
# สร้างเกมอวกาศ ตอนที่ 1: บทนำ

![ภาพเคลื่อนไหวเกมอวกาศแสดงการเล่นเกม](../../../../6-space-game/images/pewpew.gif)

เหมือนกับที่ศูนย์ควบคุมภารกิจของ NASA ประสานงานระบบต่างๆ ในการปล่อยยานอวกาศ เราจะสร้างเกมอวกาศที่แสดงให้เห็นว่าชิ้นส่วนต่างๆ ของโปรแกรมสามารถทำงานร่วมกันได้อย่างราบรื่น ในขณะที่สร้างสิ่งที่คุณสามารถเล่นได้จริง คุณจะได้เรียนรู้แนวคิดการเขียนโปรแกรมที่สำคัญซึ่งสามารถนำไปใช้กับโครงการซอฟต์แวร์ใดๆ ก็ได้

เราจะสำรวจสองวิธีพื้นฐานในการจัดระเบียบโค้ด: การสืบทอด (inheritance) และการประกอบ (composition) ซึ่งไม่ได้เป็นเพียงแนวคิดเชิงวิชาการเท่านั้น แต่ยังเป็นรูปแบบที่ใช้ในทุกสิ่งตั้งแต่เกมวิดีโอไปจนถึงระบบธนาคาร นอกจากนี้เรายังจะนำระบบการสื่อสารที่เรียกว่า pub/sub มาใช้ ซึ่งทำงานเหมือนเครือข่ายการสื่อสารที่ใช้ในยานอวกาศ ช่วยให้ส่วนประกอบต่างๆ สามารถแบ่งปันข้อมูลโดยไม่สร้างการพึ่งพากัน

เมื่อจบซีรีส์นี้ คุณจะเข้าใจวิธีสร้างแอปพลิเคชันที่สามารถขยายและพัฒนาได้ ไม่ว่าคุณจะพัฒนาเกม แอปพลิเคชันเว็บ หรือระบบซอฟต์แวร์อื่นๆ

## แบบทดสอบก่อนเรียน

[แบบทดสอบก่อนเรียน](https://ff-quizzes.netlify.app/web/quiz/29)

## การสืบทอดและการประกอบในพัฒนาเกม

เมื่อโครงการมีความซับซ้อนมากขึ้น การจัดระเบียบโค้ดจะกลายเป็นสิ่งสำคัญ สิ่งที่เริ่มต้นจากสคริปต์ง่ายๆ อาจกลายเป็นเรื่องยากที่จะดูแลรักษา หากไม่มีโครงสร้างที่เหมาะสม เช่นเดียวกับที่ภารกิจ Apollo ต้องการการประสานงานอย่างรอบคอบระหว่างส่วนประกอบนับพัน

เราจะสำรวจสองวิธีพื้นฐานในการจัดระเบียบโค้ด: การสืบทอดและการประกอบ แต่ละวิธีมีข้อดีที่แตกต่างกัน และการเข้าใจทั้งสองวิธีจะช่วยให้คุณเลือกวิธีที่เหมาะสมสำหรับสถานการณ์ต่างๆ เราจะสาธิตแนวคิดเหล่านี้ผ่านเกมอวกาศของเรา ซึ่งฮีโร่ ศัตรู พาวเวอร์อัพ และวัตถุอื่นๆ ต้องทำงานร่วมกันอย่างมีประสิทธิภาพ

✅ หนึ่งในหนังสือการเขียนโปรแกรมที่มีชื่อเสียงที่สุดเกี่ยวกับ [รูปแบบการออกแบบ](https://en.wikipedia.org/wiki/Design_Patterns)

ในเกมใดๆ คุณจะมี `game objects` – องค์ประกอบที่สามารถโต้ตอบได้ซึ่งอยู่ในโลกของเกม ฮีโร่ ศัตรู พาวเวอร์อัพ และเอฟเฟกต์ภาพทั้งหมดเป็น game objects แต่ละตัวมีตำแหน่งบนหน้าจอที่เฉพาะเจาะจงโดยใช้ค่าพิกัด `x` และ `y` คล้ายกับการวางจุดบนระนาบพิกัด

แม้ว่าจะมีความแตกต่างทางภาพ แต่ game objects เหล่านี้มักมีพฤติกรรมพื้นฐานที่เหมือนกัน:

- **พวกมันมีตำแหน่งที่อยู่** – ทุก object มีพิกัด x และ y เพื่อให้เกมรู้ว่าจะวาดมันที่ไหน
- **หลายตัวสามารถเคลื่อนที่ได้** – ฮีโร่วิ่ง ศัตรูไล่ตาม กระสุนบินผ่านหน้าจอ
- **พวกมันมีอายุการใช้งาน** – บางตัวอยู่ตลอดไป บางตัว (เช่น การระเบิด) ปรากฏขึ้นชั่วคราวแล้วหายไป
- **พวกมันตอบสนองต่อสิ่งต่างๆ** – เมื่อมีการชนกัน พาวเวอร์อัพจะถูกเก็บรวบรวม แถบพลังชีวิตจะอัปเดต

✅ ลองคิดถึงเกมอย่าง Pac-Man คุณสามารถระบุประเภท object ทั้งสี่ที่กล่าวถึงข้างต้นในเกมนี้ได้หรือไม่?

### การแสดงพฤติกรรมผ่านโค้ด

ตอนนี้คุณเข้าใจพฤติกรรมทั่วไปที่ game objects มีร่วมกันแล้ว ลองมาสำรวจวิธีการนำพฤติกรรมเหล่านี้ไปใช้ใน JavaScript คุณสามารถแสดงพฤติกรรมของ object ผ่าน methods ที่แนบมากับคลาสหรือ object แต่ละตัว และมีหลายวิธีให้เลือก

**วิธีการแบบคลาส**

คลาสและการสืบทอดให้วิธีการที่มีโครงสร้างในการจัดระเบียบ game objects เช่นเดียวกับระบบการจำแนกทางชีววิทยาที่พัฒนาโดย Carl Linnaeus คุณเริ่มต้นด้วยคลาสพื้นฐานที่มีคุณสมบัติทั่วไป จากนั้นสร้างคลาสเฉพาะที่สืบทอดพื้นฐานเหล่านี้พร้อมเพิ่มความสามารถเฉพาะตัว

✅ การสืบทอดเป็นแนวคิดสำคัญที่ควรเข้าใจ เรียนรู้เพิ่มเติมได้ที่ [บทความของ MDN เกี่ยวกับการสืบทอด](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

นี่คือวิธีที่คุณสามารถนำ game objects ไปใช้โดยใช้คลาสและการสืบทอด:

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

**มาดูทีละขั้นตอน:**
- เรากำลังสร้างแม่แบบพื้นฐานที่ทุก game object สามารถใช้ได้
- ตัวสร้าง (constructor) จะบันทึกตำแหน่งของ object (`x`, `y`) และประเภทของมัน
- สิ่งนี้กลายเป็นพื้นฐานที่ game objects ทั้งหมดจะสร้างขึ้น

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

**ในโค้ดด้านบน เราได้:**
- **ขยาย** คลาส GameObject เพื่อเพิ่มฟังก์ชันการเคลื่อนไหว
- **เรียกใช้** ตัวสร้างของคลาสแม่โดยใช้ `super()` เพื่อเริ่มต้นคุณสมบัติที่สืบทอดมา
- **เพิ่ม** method `moveTo()` ที่อัปเดตตำแหน่งของ object

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

**การทำความเข้าใจแนวคิดเหล่านี้:**
- **สร้าง** object ประเภทเฉพาะที่สืบทอดพฤติกรรมที่เหมาะสม
- **แสดงให้เห็น**ว่าการสืบทอดช่วยให้สามารถเลือกฟีเจอร์ที่เหมาะสมได้
- **แสดงให้เห็น**ว่าฮีโร่สามารถเคลื่อนที่ได้ในขณะที่ต้นไม้ยังคงอยู่กับที่
- **แสดงให้เห็น**ว่าลำดับชั้นของคลาสช่วยป้องกันการกระทำที่ไม่เหมาะสม

✅ ใช้เวลาสักครู่เพื่อจินตนาการถึงฮีโร่ใน Pac-Man (เช่น Inky, Pinky หรือ Blinky) และวิธีการเขียนโค้ดใน JavaScript

**วิธีการแบบการประกอบ**

การประกอบเป็นไปตามปรัชญาการออกแบบแบบโมดูลาร์ คล้ายกับวิศวกรที่ออกแบบยานอวกาศด้วยส่วนประกอบที่สามารถเปลี่ยนได้ แทนที่จะสืบทอดจากคลาสแม่ คุณรวมพฤติกรรมเฉพาะเพื่อสร้าง object ที่มีฟังก์ชันการทำงานที่ต้องการ วิธีนี้ให้ความยืดหยุ่นโดยไม่มีข้อจำกัดของลำดับชั้นที่เข้มงวด

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

**โค้ดนี้ทำอะไร:**
- **กำหนด** base `gameObject` พร้อมคุณสมบัติตำแหน่งและประเภท
- **สร้าง** object พฤติกรรม `movable` แยกต่างหากพร้อมฟังก์ชันการเคลื่อนไหว
- **แยก**ความกังวลโดยการเก็บข้อมูลตำแหน่งและตรรกะการเคลื่อนไหวแยกกัน

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

**ในโค้ดด้านบน เราได้:**
- **รวม** คุณสมบัติ object พื้นฐานกับพฤติกรรมการเคลื่อนไหวโดยใช้ spread syntax
- **สร้าง** factory functions ที่ส่งคืน object ที่ปรับแต่งได้
- **เปิดใช้งาน**การสร้าง object ที่ยืดหยุ่นโดยไม่มีลำดับชั้นของคลาสที่เข้มงวด
- **อนุญาต**ให้ object มีพฤติกรรมที่ต้องการได้อย่างแม่นยำ

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**จุดสำคัญที่ควรจำ:**
- **ประกอบ** object โดยการผสมพฤติกรรมแทนที่จะสืบทอด
- **ให้**ความยืดหยุ่นมากกว่าลำดับชั้นการสืบทอดที่เข้มงวด
- **อนุญาต**ให้ object มีฟีเจอร์ที่ต้องการได้อย่างแม่นยำ
- **ใช้** modern JavaScript spread syntax เพื่อการรวม object ที่สะอาด

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

**การวิเคราะห์สิ่งที่เกิดขึ้นในที่นี้:**
- **สร้าง**ระบบการจัดการเหตุการณ์ส่วนกลางโดยใช้คลาสง่ายๆ
- **จัดเก็บ** listeners ใน object ที่จัดระเบียบตามประเภทข้อความ
- **ลงทะเบียน** listeners ใหม่โดยใช้ method `on()`
- **ส่งข้อความ**ไปยัง listeners ที่สนใจทั้งหมดโดยใช้ `emit()`
- **รองรับ** payload ข้อมูลเสริมสำหรับการส่งข้อมูลที่เกี่ยวข้อง

### รวมทุกอย่างเข้าด้วยกัน: ตัวอย่างการใช้งานจริง

เอาล่ะ มาดูสิ่งนี้ในทางปฏิบัติ! เราจะสร้างระบบการเคลื่อนไหวง่ายๆ ที่แสดงให้เห็นว่า pub/sub สามารถสะอาดและยืดหยุ่นได้อย่างไร:

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

**โค้ดนี้ทำอะไร:**
- **กำหนด** object ค่าคงที่เพื่อป้องกันการพิมพ์ผิดในชื่อข้อความ
- **สร้าง** instance ของ event emitter เพื่อจัดการการสื่อสารทั้งหมด
- **เริ่มต้น** object ฮีโร่ที่ตำแหน่งเริ่มต้น

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

**ในโค้ดด้านบน เราได้:**
- **ลงทะเบียน** event listeners ที่ตอบสนองต่อข้อความการเคลื่อนไหว
- **อัปเดต**ตำแหน่งของฮีโร่ตามทิศทางการเคลื่อนไหว
- **เพิ่ม**การบันทึกใน console เพื่อติดตามการเปลี่ยนแปลงตำแหน่งของฮีโร่
- **แยก**ตรรกะการเคลื่อนไหวออกจากการจัดการอินพุต

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

**การทำความเข้าใจแนวคิดเหล่านี้:**
- **เชื่อมโยง**การป้อนข้อมูลจากแป้นพิมพ์กับเหตุการณ์ในเกมโดยไม่ต้องเชื่อมโยงกันอย่างแน่นหนา
- **เปิดใช้งาน**ระบบอินพุตเพื่อสื่อสารกับ object ในเกมโดยอ้อม
- **อนุญาต**ให้หลายระบบตอบสนองต่อเหตุการณ์แป้นพิมพ์เดียวกัน
- **ทำให้**การเปลี่ยนแปลงการผูกปุ่มหรือเพิ่มวิธีการป้อนข้อมูลใหม่ง่ายขึ้น

> 💡 **เคล็ดลับ**: ความสวยงามของรูปแบบนี้คือความยืดหยุ่น! คุณสามารถเพิ่มเอฟเฟกต์เสียง การสั่นหน้าจอ หรือเอฟเฟกต์อนุภาคได้ง่ายๆ เพียงแค่เพิ่ม event listeners – ไม่จำเป็นต้องแก้ไขโค้ดแป้นพิมพ์หรือการเคลื่อนไหวที่มีอยู่
> 
**เหตุผลที่คุณจะชอบวิธีนี้:**
- การเพิ่มฟีเจอร์ใหม่กลายเป็นเรื่องง่ายมาก – เพียงแค่ฟังเหตุการณ์ที่คุณสนใจ
- หลายสิ่งสามารถตอบสนองต่อเหตุการณ์เดียวกันโดยไม่รบกวนกัน
- การทดสอบง่ายขึ้นมากเพราะแต่ละส่วนทำงานอย่างอิสระ
- เมื่อมีสิ่งผิดพลาด คุณจะรู้ได้ทันทีว่าต้องดูที่ไหน

### ทำไม Pub/Sub ถึงรองรับการขยายได้อย่างมีประสิทธิภาพ

รูปแบบ pub/sub รักษาความเรียบง่ายเมื่อแอปพลิเคชันมีความซับซ้อนมากขึ้น ไม่ว่าจะเป็นการจัดการศัตรูหลายตัว การอัปเดต UI แบบไดนามิก หรือระบบเสียง รูปแบบนี้สามารถจัดการกับการขยายขนาดโดยไม่ต้องเปลี่ยนแปลงสถาปัตยกรรม ฟีเจอร์ใหม่สามารถรวมเข้ากับระบบเหตุการณ์ที่มีอยู่ได้โดยไม่กระทบต่อฟังก์ชันที่มีอยู่

> ⚠️ **ข้อผิดพลาดทั่วไป**: อย่าสร้างประเภทข้อความเฉพาะมากเกินไปในช่วงแรก เริ่มต้นด้วยหมวดหมู่กว้างๆ และปรับปรุงเมื่อความต้องการของเกมชัดเจนขึ้น
> 
**แนวปฏิบัติที่ดีที่สุดที่ควรปฏิบัติตาม:**
- **จัดกลุ่ม**ข้อความที่เกี่ยวข้องในหมวดหมู่ที่มีเหตุผล
- **ใช้**ชื่อที่อธิบายได้ชัดเจนว่าเกิดอะไรขึ้น
- **รักษา** payload ข้อมูลข้อความให้เรียบง่ายและมุ่งเน้น
- **เอกสาร**ประเภทข้อความของคุณเพื่อการทำงานร่วมกันในทีม

---

## ความท้าทาย GitHub Copilot Agent 🚀

ใช้โหมด Agent เพื่อทำความท้าทายต่อไปนี้:

**คำอธิบาย:** สร้างระบบ object เกมง่ายๆ โดยใช้ทั้งการสืบทอดและรูปแบบ pub/sub คุณจะสร้างเกมพื้นฐานที่ object ต่างๆ สามารถสื่อสารผ่านเหตุการณ์โดยไม่รู้จักกันโดยตรง

**คำสั่ง:** สร้างระบบเกม JavaScript ที่มีข้อกำหนดดังนี้: 1) สร้างคลาส GameObject พื้นฐานที่มีพิกัด x, y และคุณสมบัติประเภท 2) สร้างคลาส Hero ที่ขยาย GameObject และสามารถเคลื่อนที่ได้ 3) สร้างคลาส Enemy ที่ขยาย GameObject และสามารถไล่ตามฮีโร่ได้ 4) นำคลาส EventEmitter มาใช้สำหรับรูปแบบ pub/sub 5) ตั้งค่า event listeners เพื่อให้เมื่อฮีโร่เคลื่อนที่ ศัตรูที่อยู่ใกล้จะได้รับเหตุการณ์ 'HERO_MOVED' และอัปเดตตำแหน่งของพวกเขาเพื่อไล่ตามฮีโร่ รวมถึง console.log เพื่อแสดงการสื่อสารระหว่าง object

เรียนรู้เพิ่มเติมเกี่ยวกับ [โหมด Agent](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) ที่นี่

## 🚀 ความท้าทาย

พิจารณาว่ารูปแบบ pub-sub สามารถปรับปรุงสถาปัตยกรรมเกมได้อย่างไร ระบุว่าคอมโพเนนต์ใดควรส่งเหตุการณ์และระบบควรตอบสนองอย่างไร ออกแบบแนวคิดเกมและวางแผนรูปแบบการสื่อสารระหว่างคอมโพเนนต์

## แบบทดสอบหลังเรียน

[แบบทดสอบหลังเรียน](https://ff-quizzes.netlify.app/web/quiz/30)

## ทบทวนและศึกษาด้วยตนเอง

เรียนรู้เพิ่มเติมเกี่ยวกับ Pub/Sub โดย [อ่านเกี่ยวกับมัน](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon)

## งานที่ได้รับมอบหมาย

[สร้างเกมจำลอง](assignment.md)

---

**ข้อจำกัดความรับผิดชอบ**:  
เอกสารนี้ได้รับการแปลโดยใช้บริการแปลภาษา AI [Co-op Translator](https://github.com/Azure/co-op-translator) แม้ว่าเราจะพยายามให้การแปลมีความถูกต้อง แต่โปรดทราบว่าการแปลอัตโนมัติอาจมีข้อผิดพลาดหรือความไม่ถูกต้อง เอกสารต้นฉบับในภาษาดั้งเดิมควรถือเป็นแหล่งข้อมูลที่เชื่อถือได้ สำหรับข้อมูลที่สำคัญ ขอแนะนำให้ใช้บริการแปลภาษามืออาชีพ เราไม่รับผิดชอบต่อความเข้าใจผิดหรือการตีความผิดที่เกิดจากการใช้การแปลนี้