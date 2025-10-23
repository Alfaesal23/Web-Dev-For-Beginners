<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T22:03:27+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "bn"
}
-->
# মহাকাশ গেম তৈরি করুন পর্ব ১: পরিচিতি

![মহাকাশ গেমের অ্যানিমেশন যা গেমপ্লে দেখাচ্ছে](../../../../6-space-game/images/pewpew.gif)

যেভাবে NASA এর মিশন কন্ট্রোল মহাকাশ উৎক্ষেপণের সময় বিভিন্ন সিস্টেম সমন্বয় করে, আমরা একটি মহাকাশ গেম তৈরি করতে যাচ্ছি যা দেখাবে কীভাবে একটি প্রোগ্রামের বিভিন্ন অংশ একসাথে নির্বিঘ্নে কাজ করতে পারে। এমন কিছু তৈরি করার সময় যা আপনি আসলে খেলতে পারবেন, আপনি গুরুত্বপূর্ণ প্রোগ্রামিং ধারণাগুলি শিখবেন যা যেকোনো সফটওয়্যার প্রকল্পে প্রযোজ্য।

আমরা কোড সংগঠিত করার দুটি মৌলিক পদ্ধতি অন্বেষণ করব: ইনহেরিটেন্স এবং কম্পোজিশন। এগুলি শুধুমাত্র একাডেমিক ধারণা নয় – এগুলি সেই প্যাটার্ন যা ভিডিও গেম থেকে ব্যাংকিং সিস্টেম পর্যন্ত সবকিছু চালিত করে। আমরা একটি যোগাযোগ ব্যবস্থা বাস্তবায়ন করব যাকে pub/sub বলা হয় যা মহাকাশযানে ব্যবহৃত যোগাযোগ নেটওয়ার্কের মতো কাজ করে, বিভিন্ন উপাদানকে নির্ভরতা তৈরি না করেই তথ্য ভাগ করতে দেয়।

এই সিরিজের শেষে, আপনি এমন অ্যাপ্লিকেশন তৈরি করতে শিখবেন যা স্কেল এবং বিকশিত হতে পারে – আপনি গেম, ওয়েব অ্যাপ্লিকেশন বা অন্য কোনো সফটওয়্যার সিস্টেম তৈরি করছেন কিনা।

## প্রাক-লেকচার কুইজ

[প্রাক-লেকচার কুইজ](https://ff-quizzes.netlify.app/web/quiz/29)

## গেম ডেভেলপমেন্টে ইনহেরিটেন্স এবং কম্পোজিশন

যখন প্রকল্পগুলি জটিলতায় বৃদ্ধি পায়, তখন কোড সংগঠন গুরুত্বপূর্ণ হয়ে ওঠে। একটি সাধারণ স্ক্রিপ্ট হিসাবে যা শুরু হয় তা সঠিক কাঠামো ছাড়া বজায় রাখা কঠিন হয়ে যেতে পারে – যেমন অ্যাপোলো মিশনগুলিকে হাজার হাজার উপাদানের মধ্যে সাবধানে সমন্বয় করতে হয়েছিল।

আমরা কোড সংগঠিত করার দুটি মৌলিক পদ্ধতি অন্বেষণ করব: ইনহেরিটেন্স এবং কম্পোজিশন। প্রতিটির স্বতন্ত্র সুবিধা রয়েছে এবং উভয়ই বোঝা আপনাকে বিভিন্ন পরিস্থিতির জন্য সঠিক পদ্ধতি বেছে নিতে সাহায্য করে। আমরা আমাদের মহাকাশ গেমের মাধ্যমে এই ধারণাগুলি প্রদর্শন করব, যেখানে নায়ক, শত্রু, পাওয়ার-আপ এবং অন্যান্য বস্তুগুলি দক্ষতার সাথে যোগাযোগ করতে হবে।

✅ প্রোগ্রামিং সম্পর্কিত সবচেয়ে বিখ্যাত বইগুলির মধ্যে একটি হল [ডিজাইন প্যাটার্নস](https://en.wikipedia.org/wiki/Design_Patterns)।

যেকোনো গেমে, আপনার কাছে থাকে `গেম অবজেক্ট` – ইন্টারঅ্যাকটিভ উপাদানগুলি যা আপনার গেমের জগৎকে পূর্ণ করে। নায়ক, শত্রু, পাওয়ার-আপ এবং ভিজ্যুয়াল ইফেক্ট সবই গেম অবজেক্ট। প্রতিটি নির্দিষ্ট স্ক্রিন কোঅর্ডিনেটে বিদ্যমান থাকে `x` এবং `y` মান ব্যবহার করে, পয়েন্ট প্লট করার মতো।

তাদের ভিজ্যুয়াল পার্থক্য থাকা সত্ত্বেও, এই বস্তুগুলি প্রায়শই মৌলিক আচরণ ভাগ করে:

- **তারা কোথাও থাকে** – প্রতিটি বস্তুর x এবং y কোঅর্ডিনেট থাকে যাতে গেমটি জানে কোথায় এটি আঁকতে হবে
- **অনেকেই চারপাশে চলতে পারে** – নায়করা দৌড়ায়, শত্রুরা তাড়া করে, বুলেট স্ক্রিন জুড়ে উড়ে যায়
- **তাদের একটি জীবনকাল থাকে** – কিছু চিরকাল থাকে, অন্যরা (যেমন বিস্ফোরণ) অল্প সময়ের জন্য উপস্থিত হয় এবং অদৃশ্য হয়ে যায়
- **তারা প্রতিক্রিয়া দেখায়** – যখন জিনিসগুলি সংঘর্ষ হয়, পাওয়ার-আপ সংগ্রহ করা হয়, স্বাস্থ্য বার আপডেট হয়

✅ একটি গেমের কথা ভাবুন যেমন Pac-Man। আপনি কি এই গেমে উপরের চারটি অবজেক্ট টাইপ চিহ্নিত করতে পারেন?

### কোডের মাধ্যমে আচরণ প্রকাশ করা

এখন আপনি বুঝতে পেরেছেন যে গেম অবজেক্টগুলি সাধারণ আচরণ ভাগ করে, আসুন আমরা জাভাস্ক্রিপ্টে এই আচরণগুলি কীভাবে বাস্তবায়ন করতে পারি তা অন্বেষণ করি। আপনি ক্লাস বা পৃথক অবজেক্টের সাথে সংযুক্ত পদ্ধতির মাধ্যমে অবজেক্টের আচরণ প্রকাশ করতে পারেন এবং বেছে নেওয়ার জন্য বেশ কয়েকটি পদ্ধতি রয়েছে।

**ক্লাস-ভিত্তিক পদ্ধতি**

ক্লাস এবং ইনহেরিটেন্স গেম অবজেক্ট সংগঠিত করার জন্য একটি কাঠামোগত পদ্ধতি প্রদান করে। কার্ল লিনিয়াস দ্বারা বিকশিত ট্যাক্সোনমিক শ্রেণীবিন্যাস ব্যবস্থার মতো, আপনি সাধারণ বৈশিষ্ট্যগুলি ধারণকারী একটি বেস ক্লাস দিয়ে শুরু করেন, তারপর বিশেষ ক্ষমতা যোগ করার সময় এই মৌলিক বিষয়গুলি উত্তরাধিকারসূত্রে প্রাপ্ত বিশেষায়িত ক্লাস তৈরি করেন।

✅ ইনহেরিটেন্স একটি গুরুত্বপূর্ণ ধারণা বুঝতে হবে। [MDN এর ইনহেরিটেন্স সম্পর্কিত নিবন্ধ](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) সম্পর্কে আরও জানুন।

এখানে দেখানো হয়েছে কীভাবে আপনি ক্লাস এবং ইনহেরিটেন্স ব্যবহার করে গেম অবজেক্টগুলি বাস্তবায়ন করতে পারেন:

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

**এটি ধাপে ধাপে বিশ্লেষণ করা যাক:**
- আমরা একটি মৌলিক টেমপ্লেট তৈরি করছি যা প্রতিটি গেম অবজেক্ট ব্যবহার করতে পারে
- কনস্ট্রাক্টর সংরক্ষণ করে বস্তুর অবস্থান (`x`, `y`) এবং এটি কী ধরনের জিনিস
- এটি এমন একটি ভিত্তি হয়ে ওঠে যার উপর আপনার সমস্ত গেম অবজেক্ট তৈরি হবে

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

**উপরের কোডে আমরা:**
- GameObject ক্লাসটি **এক্সটেন্ড** করেছি যাতে মুভমেন্ট ফাংশনালিটি যোগ করা যায়
- `super()` ব্যবহার করে প্যারেন্ট কনস্ট্রাক্টর **কল** করেছি উত্তরাধিকারসূত্রে প্রাপ্ত বৈশিষ্ট্যগুলি ইনিশিয়ালাইজ করতে
- একটি `moveTo()` মেথড **যোগ করেছি** যা বস্তুর অবস্থান আপডেট করে

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

**এই ধারণাগুলি বোঝা:**
- **বিশেষায়িত** অবজেক্ট টাইপ তৈরি করে যা উপযুক্ত আচরণ উত্তরাধিকারসূত্রে পায়
- **প্রদর্শন করে** কীভাবে ইনহেরিটেন্স নির্বাচনী বৈশিষ্ট্য অন্তর্ভুক্তি সক্ষম করে
- **দেখায়** যে নায়করা চলতে পারে যখন গাছগুলি স্থির থাকে
- **চিত্রিত করে** কীভাবে ক্লাস হায়ারার্কি অনুপযুক্ত ক্রিয়াগুলি প্রতিরোধ করে

✅ কয়েক মিনিট সময় নিন একটি Pac-Man নায়ক (উদাহরণস্বরূপ, Inky, Pinky বা Blinky) পুনরায় কল্পনা করতে এবং এটি কীভাবে জাভাস্ক্রিপ্টে লেখা হবে তা ভাবুন।

**কম্পোজিশন পদ্ধতি**

কম্পোজিশন একটি মডুলার ডিজাইন দর্শন অনুসরণ করে, যেমন ইঞ্জিনিয়াররা বিনিময়যোগ্য উপাদান সহ মহাকাশযান ডিজাইন করে। একটি প্যারেন্ট ক্লাস থেকে উত্তরাধিকারসূত্রে প্রাপ্ত হওয়ার পরিবর্তে, আপনি নির্দিষ্ট আচরণগুলি একত্রিত করেন যাতে ঠিক সেই কার্যকারিতা সহ অবজেক্ট তৈরি করা যায় যা তাদের প্রয়োজন। এই পদ্ধতি কঠোর শ্রেণীবিন্যাসমূলক সীমাবদ্ধতা ছাড়াই নমনীয়তা প্রদান করে।

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

**এই কোডটি যা করে:**
- একটি বেস `gameObject` সংজ্ঞায়িত করে যার অবস্থান এবং টাইপ বৈশিষ্ট্য রয়েছে
- একটি পৃথক `movable` আচরণ অবজেক্ট তৈরি করে যার মুভমেন্ট ফাংশনালিটি রয়েছে
- অবস্থান ডেটা এবং মুভমেন্ট লজিককে স্বাধীন রেখে **কনসার্ন** আলাদা করে

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

**উপরের কোডে আমরা:**
- **কম্বাইন** করেছি বেস অবজেক্ট বৈশিষ্ট্যগুলি এবং মুভমেন্ট আচরণ স্প্রেড সিনট্যাক্স ব্যবহার করে
- **ফ্যাক্টরি ফাংশন** তৈরি করেছি যা কাস্টমাইজড অবজেক্ট রিটার্ন করে
- **নমনীয়** অবজেক্ট তৈরি সক্ষম করেছি কঠোর ক্লাস হায়ারার্কি ছাড়াই
- **ব্যবহার করেছি** আধুনিক জাভাস্ক্রিপ্ট স্প্রেড সিনট্যাক্স পরিষ্কার অবজেক্ট কম্বিনেশনের জন্য

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**মনে রাখার মূল পয়েন্ট:**
- **কম্পোজ** করে অবজেক্টগুলি আচরণ মিশ্রিত করে, উত্তরাধিকারসূত্রে নয়
- **নমনীয়তা প্রদান করে** কঠোর ইনহেরিটেন্স হায়ারার্কির চেয়ে বেশি
- **সক্ষম করে** অবজেক্টগুলিকে ঠিক সেই বৈশিষ্ট্যগুলি পেতে যা তাদের প্রয়োজন
- **ব্যবহার করে** আধুনিক জাভাস্ক্রিপ্ট স্প্রেড সিনট্যাক্স পরিষ্কার অবজেক্ট কম্বিনেশনের জন্য

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

**এখানে যা ঘটছে তা বিশ্লেষণ করা:**
- একটি সাধারণ ক্লাস ব্যবহার করে একটি কেন্দ্রীয় ইভেন্ট ম্যানেজমেন্ট সিস্টেম তৈরি করে
- বার্তার ধরন অনুযায়ী সংগঠিত একটি অবজেক্টে লিসনার সংরক্ষণ করে
- নতুন লিসনার নিবন্ধন করে `on()` মেথড ব্যবহার করে
- সমস্ত আগ্রহী লিসনারদের বার্তা **ব্রডকাস্ট** করে `emit()` ব্যবহার করে
- প্রাসঙ্গিক তথ্য পাস করার জন্য **অপশনাল ডেটা পে-লোড** সমর্থন করে

### সবকিছু একত্রিত করা: একটি ব্যবহারিক উদাহরণ

ঠিক আছে, আসুন এটি কার্যকরভাবে দেখি! আমরা একটি সাধারণ মুভমেন্ট সিস্টেম তৈরি করব যা দেখাবে pub/sub কতটা পরিষ্কার এবং নমনীয় হতে পারে:

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

**এই কোডটি যা করে:**
- বার্তার নামগুলিতে টাইপো প্রতিরোধ করতে একটি কনস্ট্যান্টস অবজেক্ট **সংজ্ঞায়িত করে**
- সমস্ত যোগাযোগ পরিচালনা করতে একটি ইভেন্ট এমিটার ইনস্ট্যান্স **তৈরি করে**
- নায়ক অবজেক্টকে প্রাথমিক অবস্থানে **ইনিশিয়ালাইজ করে**

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

**উপরের কোডে আমরা:**
- মুভমেন্ট বার্তাগুলিতে প্রতিক্রিয়া জানাতে ইভেন্ট লিসনার **নিবন্ধন করেছি**
- মুভমেন্ট ডিরেকশন অনুযায়ী নায়কের অবস্থান **আপডেট করেছি**
- নায়কের অবস্থান পরিবর্তন **ট্র্যাক করতে** কনসোল লগিং যোগ করেছি
- ইনপুট হ্যান্ডলিং থেকে মুভমেন্ট লজিক **আলাদা করেছি**

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

**এই ধারণাগুলি বোঝা:**
- **কীবোর্ড ইনপুটকে** গেম ইভেন্টের সাথে সংযুক্ত করে টাইট কাপলিং ছাড়াই
- **সক্ষম করে** ইনপুট সিস্টেমকে গেম অবজেক্টের সাথে পরোক্ষভাবে যোগাযোগ করতে
- **অনুমতি দেয়** একাধিক সিস্টেম একই কীবোর্ড ইভেন্টের প্রতিক্রিয়া জানাতে
- **সহজ করে** কী বাইন্ডিং পরিবর্তন করা বা নতুন ইনপুট পদ্ধতি যোগ করা

> 💡 **প্রো টিপ**: এই প্যাটার্নের সৌন্দর্য হল নমনীয়তা! আপনি সহজেই নতুন বৈশিষ্ট্য যোগ করতে পারেন – শুধু সেই ইভেন্টগুলির জন্য লিসেন করুন যা আপনার প্রয়োজন।
> 
**আপনি এই পদ্ধতিটি কেন পছন্দ করবেন:**
- নতুন বৈশিষ্ট্য যোগ করা খুব সহজ হয়ে যায় – শুধু সেই ইভেন্টগুলির জন্য লিসেন করুন যা আপনার প্রয়োজন
- একাধিক জিনিস একই ইভেন্টে প্রতিক্রিয়া জানাতে পারে একে অপরের উপর প্রভাব না ফেলেই
- টেস্টিং অনেক সহজ হয়ে যায় কারণ প্রতিটি অংশ স্বাধীনভাবে কাজ করে
- যখন কিছু ভেঙে যায়, আপনি ঠিক কোথায় দেখতে হবে তা জানেন

### কেন Pub/Sub কার্যকরভাবে স্কেল করে

Pub/Sub প্যাটার্ন অ্যাপ্লিকেশনগুলি জটিলতায় বৃদ্ধি পাওয়ার সাথে সাথে সরলতা বজায় রাখে। ডজন ডজন শত্রু, ডায়নামিক UI আপডেট বা সাউন্ড সিস্টেম পরিচালনা করা হোক না কেন, প্যাটার্নটি স্থাপত্যগত পরিবর্তন ছাড়াই বৃদ্ধি পায়। নতুন বৈশিষ্ট্যগুলি বিদ্যমান ইভেন্ট সিস্টেমে একীভূত হয় প্রতিষ্ঠিত কার্যকারিতাকে প্রভাবিত না করে।

> ⚠️ **সাধারণ ভুল**: খুব বেশি নির্দিষ্ট বার্তার ধরন প্রাথমিকভাবে তৈরি করবেন না। প্রশস্ত বিভাগ দিয়ে শুরু করুন এবং আপনার গেমের প্রয়োজন অনুসারে সেগুলি পরিমার্জন করুন।
> 
**অনুসরণ করার সেরা অনুশীলন:**
- **সম্পর্কিত বার্তাগুলিকে** যৌক্তিক বিভাগে গ্রুপ করে
- **বর্ণনামূলক নাম ব্যবহার করে** যা স্পষ্টভাবে নির্দেশ করে কী ঘটেছে
- **বার্তার পে-লোডকে** সহজ এবং কেন্দ্রীভূত রাখে
- **আপনার বার্তার ধরনগুলি ডকুমেন্ট করে** দলগত সহযোগিতার জন্য

---

## GitHub Copilot Agent চ্যালেঞ্জ 🚀

Agent মোড ব্যবহার করে নিম্নলিখিত চ্যালেঞ্জটি সম্পূর্ণ করুন:

**বর্ণনা:** ইনহেরিটেন্স এবং pub/sub প্যাটার্ন উভয় ব্যবহার করে একটি সাধারণ গেম অবজেক্ট সিস্টেম তৈরি করুন। আপনি একটি মৌলিক গেম বাস্তবায়ন করবেন যেখানে বিভিন্ন অবজেক্ট ইভেন্টের মাধ্যমে একে অপরের সম্পর্কে সরাসরি না জেনে যোগাযোগ করতে পারে।

**প্রম্পট:** নিম্নলিখিত প্রয়োজনীয়তাগুলি সহ একটি জাভাস্ক্রিপ্ট গেম সিস্টেম তৈরি করুন: ১) x, y কোঅর্ডিনেট এবং একটি টাইপ প্রপার্টি সহ একটি বেস GameObject ক্লাস তৈরি করুন। ২) GameObject এক্সটেন্ড করে একটি Hero ক্লাস তৈরি করুন যা চলতে পারে। ৩) GameObject এক্সটেন্ড করে একটি Enemy ক্লাস তৈরি করুন যা নায়ককে তাড়া করতে পারে। ৪) pub/sub প্যাটার্নের জন্য একটি EventEmitter ক্লাস বাস্তবায়ন করুন। ৫) ইভেন্ট লিসনার সেট আপ করুন যাতে নায়ক চললে, কাছাকাছি শত্রুরা 'HERO_MOVED' ইভেন্ট পায় এবং নায়কের দিকে এগিয়ে যাওয়ার জন্য তাদের অবস্থান আপডেট করে। অবজেক্টগুলির মধ্যে যোগাযোগ দেখানোর জন্য console.log স্টেটমেন্ট অন্তর্ভুক্ত করুন।

Agent মোড সম্পর্কে আরও জানুন [এখানে](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode)।

## 🚀 চ্যালেঞ্জ

Pub-sub প্যাটার্ন কীভাবে গেম আর্কিটেকচারকে উন্নত করতে পারে তা বিবেচনা করুন। কোন উপাদানগুলি ইভেন্ট ইমিট করা উচিত এবং সিস্টেম কীভাবে প্রতিক্রিয়া জানাবে তা চিহ্নিত করুন। একটি গেম ধারণা ডিজাইন করুন এবং এর উপাদানগুলির মধ্যে যোগাযোগের প্যাটার্নগুলি ম্যাপ করুন।

## পোস্ট-লেকচার কুইজ

[পোস্ট-লেকচার কুইজ](https://ff-quizzes.netlify.app/web/quiz/30)

## পর্যালোচনা এবং স্ব-অধ্যয়ন

Pub/Sub সম্পর্কে আরও জানুন [এখানে পড়ুন](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon)।

## অ্যাসাইনমেন্ট

[একটি গেমের মক আপ তৈরি করুন](assignment.md)

---

**অস্বীকৃতি**:  
এই নথিটি AI অনুবাদ পরিষেবা [Co-op Translator](https://github.com/Azure/co-op-translator) ব্যবহার করে অনুবাদ করা হয়েছে। আমরা যথাসাধ্য সঠিকতার জন্য চেষ্টা করি, তবে অনুগ্রহ করে মনে রাখবেন যে স্বয়ংক্রিয় অনুবাদে ত্রুটি বা অসঙ্গতি থাকতে পারে। নথিটির মূল ভাষায় থাকা আসল সংস্করণকে প্রামাণিক উৎস হিসেবে বিবেচনা করা উচিত। গুরুত্বপূর্ণ তথ্যের জন্য, পেশাদার মানব অনুবাদ সুপারিশ করা হয়। এই অনুবাদ ব্যবহারের ফলে কোনো ভুল বোঝাবুঝি বা ভুল ব্যাখ্যার জন্য আমরা দায়ী থাকব না।