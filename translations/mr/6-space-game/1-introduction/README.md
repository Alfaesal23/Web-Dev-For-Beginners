<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T16:33:11+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "mr"
}
-->
# स्पेस गेम तयार करा भाग 1: परिचय

![स्पेस गेम अ‍ॅनिमेशन गेमप्ले दाखवत आहे](../../../../6-space-game/images/pewpew.gif)

जसे NASA चे मिशन कंट्रोल स्पेस लॉन्च दरम्यान अनेक प्रणालींचे समन्वय साधते, तसेच आपण एक स्पेस गेम तयार करणार आहोत जो दाखवेल की प्रोग्रामचे विविध भाग एकत्र कसे कार्य करू शकतात. काहीतरी खेळण्यायोग्य तयार करताना, तुम्ही महत्त्वाचे प्रोग्रामिंग संकल्पना शिकाल ज्या कोणत्याही सॉफ्टवेअर प्रकल्पासाठी लागू होतात.

आपण कोड आयोजित करण्यासाठी दोन मूलभूत दृष्टिकोनांचा अभ्यास करू: इनहेरिटन्स आणि कंपोझिशन. हे केवळ शैक्षणिक संकल्पना नाहीत – हेच पद्धती आहेत ज्या व्हिडिओ गेम्सपासून बँकिंग सिस्टमपर्यंत सर्वकाही चालवतात. आपण एक कम्युनिकेशन सिस्टम देखील अंमलात आणू ज्याला pub/sub म्हणतात, जे स्पेसक्राफ्टमध्ये वापरल्या जाणाऱ्या कम्युनिकेशन नेटवर्क्ससारखे कार्य करते, विविध घटकांना परस्पर अवलंबित्व निर्माण न करता माहिती सामायिक करण्यास अनुमती देते.

या मालिकेच्या शेवटी, तुम्हाला गेम्स, वेब अ‍ॅप्लिकेशन्स किंवा कोणत्याही सॉफ्टवेअर सिस्टम विकसित करताना स्केल आणि विकसित होणाऱ्या अ‍ॅप्लिकेशन्स कसे तयार करायचे हे समजेल.

## प्री-लेक्चर क्विझ

[प्री-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/29)

## गेम डेव्हलपमेंटमध्ये इनहेरिटन्स आणि कंपोझिशन

प्रकल्प जसे जसे जटिल होतात, कोडचे आयोजन महत्त्वाचे बनते. जे एक साधे स्क्रिप्ट म्हणून सुरू होते ते योग्य संरचनेशिवाय देखभाल करणे कठीण होऊ शकते – जसे अपोलो मिशन्समध्ये हजारो घटकांमध्ये काळजीपूर्वक समन्वय आवश्यक होता.

आपण कोड आयोजित करण्यासाठी दोन मूलभूत दृष्टिकोनांचा अभ्यास करू: इनहेरिटन्स आणि कंपोझिशन. प्रत्येकाचे वेगळे फायदे आहेत आणि दोन्ही समजून घेणे तुम्हाला वेगवेगळ्या परिस्थितीत योग्य दृष्टिकोन निवडण्यास मदत करते. आपण आमच्या स्पेस गेमद्वारे या संकल्पनांचे प्रदर्शन करू, जिथे हिरो, शत्रू, पॉवर-अप्स आणि इतर वस्तूंना कार्यक्षमतेने संवाद साधावा लागतो.

✅ सर्वात प्रसिद्ध प्रोग्रामिंग पुस्तकांपैकी एक [डिझाइन पॅटर्न्स](https://en.wikipedia.org/wiki/Design_Patterns) बद्दल आहे.

कोणत्याही गेममध्ये, तुम्हाला `गेम ऑब्जेक्ट्स` असतात – परस्परसंवादी घटक जे तुमच्या गेमच्या जगात भर घालतात. हिरो, शत्रू, पॉवर-अप्स आणि व्हिज्युअल इफेक्ट्स हे सर्व गेम ऑब्जेक्ट्स आहेत. प्रत्येक विशिष्ट स्क्रीन कोऑर्डिनेट्सवर `x` आणि `y` मूल्यांचा वापर करून अस्तित्वात असतो, ज्यामुळे बिंदू प्लॉटिंगसारखे कार्य होते.

त्यांच्या व्हिज्युअल फरक असूनही, या वस्तूंमध्ये सामान्यतः मूलभूत वर्तन सामायिक असते:

- **ते कुठेतरी अस्तित्वात असतात** – प्रत्येक वस्तूला x आणि y कोऑर्डिनेट्स असतात जेणेकरून गेमला ते कुठे काढायचे ते माहित असते
- **अनेक फिरू शकतात** – हिरो धावतात, शत्रू पाठलाग करतात, बुलेट्स स्क्रीनवर उडतात
- **त्यांना आयुष्यकाल असतो** – काही कायम राहतात, तर काही (उदाहरणार्थ, स्फोट) थोड्या वेळासाठी दिसतात आणि गायब होतात
- **ते गोष्टींवर प्रतिक्रिया देतात** – जेव्हा वस्तू एकमेकांवर आदळतात, पॉवर-अप्स गोळा होतात, हेल्थ बार अपडेट होतो

✅ पॅक-मॅन सारख्या गेमबद्दल विचार करा. तुम्ही या गेममध्ये वरील चार ऑब्जेक्ट प्रकार ओळखू शकता का?

### कोडद्वारे वर्तन व्यक्त करणे

आता तुम्हाला गेम ऑब्जेक्ट्स सामायिक करतात अशा सामान्य वर्तनाची समज आहे, चला जावास्क्रिप्टमध्ये या वर्तनाची अंमलबजावणी कशी करायची ते शोधूया. तुम्ही वर्ग किंवा वैयक्तिक वस्तूंशी संलग्न पद्धतींद्वारे ऑब्जेक्ट वर्तन व्यक्त करू शकता आणि निवडण्यासाठी अनेक दृष्टिकोन आहेत.

**क्लास-आधारित दृष्टिकोन**

क्लासेस आणि इनहेरिटन्स गेम ऑब्जेक्ट्स आयोजित करण्यासाठी संरचित दृष्टिकोन प्रदान करतात. कार्ल लिनिअसने विकसित केलेल्या वर्गीकरण प्रणालीसारखे, तुम्ही सामान्य गुणधर्म असलेल्या बेस क्लाससह प्रारंभ करता, नंतर विशिष्ट क्षमता जोडत असलेल्या विशेष वर्ग तयार करता.

✅ इनहेरिटन्स समजून घेणे महत्त्वाचे आहे. [MDN च्या इनहेरिटन्सवरील लेख](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) वर अधिक जाणून घ्या.

गेम ऑब्जेक्ट्स क्लासेस आणि इनहेरिटन्स वापरून कसे अंमलात आणता येतील ते येथे आहे:

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

**चला हे टप्प्याटप्प्याने समजून घेऊया:**
- आपण प्रत्येक गेम ऑब्जेक्ट वापरू शकणारे एक मूलभूत टेम्पलेट तयार करत आहोत
- कन्स्ट्रक्टर ऑब्जेक्ट कुठे आहे (`x`, `y`) आणि ते कोणत्या प्रकारचे आहे हे जतन करते
- हे तुमच्या सर्व गेम ऑब्जेक्ट्ससाठी पाया बनते

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

**वरीलमध्ये, आपण:**
- गेमऑब्जेक्ट क्लास **वाढवला** जेणेकरून मूव्हमेंट फंक्शनॅलिटी जोडता येईल
- `super()` वापरून पॅरेंट कन्स्ट्रक्टर **कॉल केला** जेणेकरून वारसाहक्क गुणधर्म प्रारंभ होऊ शकतील
- ऑब्जेक्टची स्थिती अपडेट करणारी `moveTo()` पद्धत **जोडली**

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

**या संकल्पना समजून घेणे:**
- योग्य वर्तन वारसाहक्क घेणारे विशेष ऑब्जेक्ट प्रकार **तयार करते**
- इनहेरिटन्स कसे निवडक वैशिष्ट्य समाविष्ट करण्यास अनुमती देते हे **दाखवते**
- हिरो हलू शकतात तर झाडे स्थिर राहतात हे **दाखवते**
- क्लास हायरार्की अयोग्य क्रिया टाळते हे **दर्शवते**

✅ काही मिनिटे घ्या आणि पॅक-मॅन हिरो (उदाहरणार्थ, इन्की, पिंकी किंवा ब्लिंकी) पुन्हा कसे लिहिले जाईल याचा विचार करा.

**कंपोझिशन दृष्टिकोन**

कंपोझिशन मॉड्युलर डिझाइन तत्त्वज्ञानाचे अनुसरण करते, जसे अभियंते इंटरचेंज करण्यायोग्य घटकांसह स्पेसक्राफ्ट डिझाइन करतात. पॅरेंट क्लासकडून वारसाहक्क घेण्याऐवजी, तुम्ही विशिष्ट वर्तन एकत्र करून ऑब्जेक्ट्स तयार करता ज्यांना त्यांना आवश्यक असलेली अचूक कार्यक्षमता मिळते. हा दृष्टिकोन कठोर श्रेणीबद्ध मर्यादा न ठेवता लवचिकता प्रदान करतो.

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

**या कोडमध्ये काय होते:**
- स्थिती आणि प्रकार गुणधर्मांसह बेस `gameObject` **परिभाषित करते**
- मूव्हमेंट फंक्शनॅलिटीसह स्वतंत्र `movable` वर्तन ऑब्जेक्ट **तयार करते**
- स्थिती डेटा आणि मूव्हमेंट लॉजिक स्वतंत्र ठेवून चिंता **वेगळ्या करते**

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

**वरीलमध्ये, आपण:**
- स्प्रेड सिंटॅक्स वापरून मूव्हमेंट वर्तनासह बेस ऑब्जेक्ट गुणधर्म **एकत्र केले**
- सानुकूलित ऑब्जेक्ट्स परत करणारे फॅक्टरी फंक्शन्स **तयार केले**
- कठोर क्लास हायरार्कीजशिवाय लवचिक ऑब्जेक्ट निर्मिती **सक्षम केली**
- ऑब्जेक्ट्सना त्यांना आवश्यक असलेले अचूक वर्तन असण्याची **परवानगी दिली**

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**महत्त्वाचे मुद्दे लक्षात ठेवा:**
- वर्तन मिसळून ऑब्जेक्ट्स **कंपोज करते** त्याऐवजी त्यांना वारसाहक्क देते
- कठोर इनहेरिटन्स हायरार्कीजपेक्षा अधिक लवचिकता **प्रदान करते**
- ऑब्जेक्ट्सना त्यांना आवश्यक असलेली अचूक वैशिष्ट्ये असण्याची **परवानगी देते**
- स्वच्छ ऑब्जेक्ट संयोजनासाठी आधुनिक जावास्क्रिप्ट स्प्रेड सिंटॅक्स **वापरते**

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

**येथे काय होते ते समजून घेणे:**
- एक साधा क्लास वापरून केंद्रीय इव्हेंट मॅनेजमेंट सिस्टम **तयार करते**
- संदेश प्रकारानुसार आयोजित केलेल्या ऑब्जेक्टमध्ये लिसनर्स **साठवते**
- `on()` पद्धत वापरून नवीन लिसनर्स **नोंदवते**
- `emit()` वापरून सर्व इच्छुक लिसनर्सना संदेश **प्रसारित करते**
- संबंधित माहिती पास करण्यासाठी वैकल्पिक डेटा पेलोड्स **समर्थित करते**

### सर्वकाही एकत्र ठेवणे: एक व्यावहारिक उदाहरण

ठीक आहे, चला हे कृतीत पाहूया! आपण एक साधी मूव्हमेंट सिस्टम तयार करू जी pub/sub किती स्वच्छ आणि लवचिक असू शकते हे दर्शवते:

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

**या कोडमध्ये काय होते:**
- संदेश नावांमध्ये टायपो टाळण्यासाठी एक constants ऑब्जेक्ट **परिभाषित करते**
- सर्व कम्युनिकेशन हाताळण्यासाठी एक इव्हेंट एमिटर उदाहरण **तयार करते**
- सुरुवातीच्या स्थितीत हिरो ऑब्जेक्ट **प्रारंभ करते**

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

**वरीलमध्ये, आपण:**
- मूव्हमेंट संदेशांना प्रतिसाद देणारे इव्हेंट लिसनर्स **नोंदवले**
- मूव्हमेंट दिशेच्या आधारे हिरोची स्थिती **अपडेट केली**
- हिरोच्या स्थिती बदलांचा मागोवा घेण्यासाठी कन्सोल लॉगिंग **जोडले**
- मूव्हमेंट लॉजिक इनपुट हँडलिंगपासून **वेगळे केले**

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

**या संकल्पना समजून घेणे:**
- कीबोर्ड इनपुटला गेम इव्हेंट्सशी घट्ट जोडणी न करता **कनेक्ट करते**
- इनपुट सिस्टमला अप्रत्यक्षपणे गेम ऑब्जेक्ट्सशी संवाद साधण्यास **सक्षम करते**
- समान कीबोर्ड इव्हेंट्सला प्रतिसाद देण्यासाठी एकाधिक सिस्टम्सला **परवानगी देते**
- की बाइंडिंग बदलणे किंवा नवीन इनपुट पद्धती जोडणे **सुलभ करते**

> 💡 **प्रो टिप**: या पॅटर्नचे सौंदर्य म्हणजे लवचिकता! तुम्ही फक्त अधिक इव्हेंट लिसनर्स जोडून ध्वनी प्रभाव, स्क्रीन शेक किंवा पार्टिकल इफेक्ट्स सहजपणे जोडू शकता – विद्यमान कीबोर्ड किंवा मूव्हमेंट कोड बदलण्याची गरज नाही.
> 
**तुम्हाला हा दृष्टिकोन का आवडेल:**
- नवीन वैशिष्ट्ये जोडणे खूप सोपे होते – फक्त तुम्हाला हवे असलेल्या इव्हेंट्ससाठी ऐका
- एकाच इव्हेंटला प्रतिसाद देण्यासाठी अनेक गोष्टी एकमेकांवर परिणाम न करता कार्य करू शकतात
- चाचणी खूप सोपी होते कारण प्रत्येक भाग स्वतंत्रपणे कार्य करतो
- काहीतरी बिघडल्यास, तुम्हाला अचूकपणे कुठे पाहायचे आहे हे माहित असते

### Pub/Sub स्केलिंग प्रभावीपणे का करते

Pub/Sub पॅटर्न अ‍ॅप्लिकेशन्स जटिलतेत वाढत असताना साधेपणा टिकवून ठेवतो. शत्रूंच्या डझनभर व्यवस्थापन, डायनॅमिक UI अपडेट्स किंवा साउंड सिस्टम्स असो, पॅटर्न आर्किटेक्चरल बदलांशिवाय वाढीव स्केल हाताळतो. नवीन वैशिष्ट्ये विद्यमान इव्हेंट सिस्टममध्ये समाकलित होतात ज्यामुळे स्थापन केलेल्या कार्यक्षमतेवर परिणाम होत नाही.

> ⚠️ **सामान्य चूक**: सुरुवातीला खूप विशिष्ट संदेश प्रकार तयार करू नका. विस्तृत श्रेणींनी प्रारंभ करा आणि तुमच्या गेमच्या गरजा स्पष्ट झाल्यामुळे त्यांना परिष्कृत करा.
> 
**पालन करण्यासाठी सर्वोत्तम पद्धती:**
- संबंधित संदेशांना तार्किक श्रेणींमध्ये **गटबद्ध करते**
- काय घडले आहे हे स्पष्टपणे सूचित करणारी वर्णनात्मक नावे **वापरते**
- संदेश पेलोड्स साधे आणि लक्ष केंद्रित **ठेवते**
- तुमच्या टीमसाठी संदेश प्रकार **दस्तऐवजीकरण करते**

---

## GitHub Copilot Agent Challenge 🚀

Agent मोड वापरून खालील आव्हान पूर्ण करा:

**वर्णन:** इनहेरिटन्स आणि Pub/Sub पॅटर्न दोन्ही वापरून एक साधी गेम ऑब्जेक्ट सिस्टम तयार करा. तुम्ही एक मूलभूत गेम अंमलात आणाल जिथे विविध ऑब्जेक्ट्स इव्हेंट्सद्वारे एकमेकांबद्दल थेट माहिती न घेता संवाद साधू शकतात.

**प्रॉम्प्ट:** खालील आवश्यकता असलेली जावास्क्रिप्ट गेम सिस्टम तयार करा: 1) x, y कोऑर्डिनेट्स आणि प्रकार गुणधर्मांसह बेस GameObject क्लास तयार करा. 2) GameObject क्लासचा विस्तार करणारा आणि हलू शकणारा Hero क्लास तयार करा. 3) GameObject क्लासचा विस्तार करणारा आणि हिरोचा पाठलाग करणारा Enemy क्लास तयार करा. 4) Pub/Sub पॅटर्नसाठी EventEmitter क्लास अंमलात आणा. 5) इव्हेंट लिसनर्स सेट करा जेणेकरून हिरो हलल्यावर, जवळच्या शत्रूंना 'HERO_MOVED' इव्हेंट प्राप्त होईल आणि हिरोकडे हलण्यासाठी त्यांची स्थिती अपडेट होईल. ऑब्जेक्ट्समधील संवाद दर्शवण्यासाठी console.log स्टेटमेंट्स समाविष्ट करा.

Agent मोडबद्दल अधिक जाणून घ्या [येथे](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode).

## 🚀 आव्हान

Pub/Sub पॅटर्न गेम आर्किटेक्चर कसे सुधारू शकतो याचा विचार करा. कोणते घटक इव्हेंट्स प्रसारित करावेत आणि सिस्टम कसे प्रतिसाद द्यावे याची ओळख करा. गेम संकल्पना डिझाइन करा आणि त्याच्या घटकांमधील कम्युनिकेशन पॅटर्न मॅप करा.

## पोस्ट-लेक्चर क्विझ

[पोस्ट-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/30)

## पुनरावलोकन आणि स्व-अभ्यास

Pub/Sub बद्दल अधिक जाणून घ्या [याबद्दल वाचून](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## असाइनमेंट

[गेमचे मॉकअप तयार करा](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात ठेवा की स्वयंचलित भाषांतरे त्रुटी किंवा अचूकतेच्या अभावाने युक्त असू शकतात. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून उद्भवलेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार राहणार नाही.