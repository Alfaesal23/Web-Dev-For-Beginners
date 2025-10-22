<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T17:15:48+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ne"
}
-->
# स्पेस गेम बनाउनुहोस् भाग १: परिचय

![स्पेस गेमको एनिमेशन जसले गेमप्ले देखाउँछ](../../../../6-space-game/images/pewpew.gif)

जसरी नासा मिशन कन्ट्रोलले स्पेस लन्चको समयमा विभिन्न प्रणालीहरू समन्वय गर्छ, हामी एक स्पेस गेम बनाउनेछौं जसले देखाउँछ कि कसरी प्रोग्रामका विभिन्न भागहरू एकसाथ काम गर्न सक्छन्। तपाईंले खेल्न सक्ने केही बनाउँदै, तपाईंले कुनै पनि सफ्टवेयर प्रोजेक्टमा लागू गर्न सकिने आवश्यक प्रोग्रामिङ अवधारणाहरू सिक्नुहुनेछ।

हामी कोडलाई व्यवस्थित गर्ने दुई आधारभूत दृष्टिकोणहरू अन्वेषण गर्नेछौं: इनहेरिटेन्स र कम्पोजिसन। यी केवल शैक्षिक अवधारणाहरू मात्र होइनन् – यी नै ढाँचाहरू हुन् जसले भिडियो गेमदेखि बैंकिङ प्रणालीसम्म सबैलाई शक्ति प्रदान गर्छ। हामी एक कम्युनिकेशन प्रणाली पनि कार्यान्वयन गर्नेछौं जसलाई पब/सब भनिन्छ, जसले स्पेसक्राफ्टमा प्रयोग गरिने कम्युनिकेशन नेटवर्कहरू जस्तै विभिन्न कम्पोनेन्टहरूलाई निर्भरता सिर्जना नगरी जानकारी साझा गर्न अनुमति दिन्छ।

यस श्रृंखलाको अन्त्यसम्ममा, तपाईंले स्केल र विकास गर्न सक्ने एप्लिकेसनहरू निर्माण गर्ने तरिका बुझ्नुहुनेछ – चाहे तपाईं गेमहरू, वेब एप्लिकेसनहरू, वा कुनै अन्य सफ्टवेयर प्रणाली विकास गर्दै हुनुहुन्छ।

## प्रि-लेक्चर क्विज

[प्रि-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/29)

## गेम विकासमा इनहेरिटेन्स र कम्पोजिसन

जसरी प्रोजेक्टहरू जटिलतामा बढ्छन्, कोडको संगठन महत्वपूर्ण हुन्छ। साधारण स्क्रिप्टको रूपमा सुरु भएको कुरा उचित संरचना बिना मर्मत गर्न गाह्रो हुन सक्छ – ठीक त्यस्तै जस्तो अपोलो मिशनहरूले हजारौं कम्पोनेन्टहरू बीच सावधानीपूर्वक समन्वयको आवश्यकता थियो।

हामी कोडलाई व्यवस्थित गर्नका लागि दुई आधारभूत दृष्टिकोणहरू अन्वेषण गर्नेछौं: इनहेरिटेन्स र कम्पोजिसन। प्रत्येकको अलग-अलग फाइदाहरू छन्, र दुवैलाई बुझ्नाले विभिन्न परिस्थितिहरूका लागि सही दृष्टिकोण चयन गर्न मद्दत गर्दछ। हामी यी अवधारणाहरू हाम्रो स्पेस गेम मार्फत प्रदर्शन गर्नेछौं, जहाँ नायकहरू, शत्रुहरू, पावर-अपहरू, र अन्य वस्तुहरूले कुशलतापूर्वक अन्तरक्रिया गर्नुपर्छ।

✅ सबैभन्दा प्रसिद्ध प्रोग्रामिङ पुस्तकहरू मध्ये एक [डिजाइन प्याटर्नहरू](https://en.wikipedia.org/wiki/Design_Patterns)सँग सम्बन्धित छ।

कुनै पनि गेममा, तपाईंसँग `गेम वस्तुहरू` हुन्छन् – तपाईंको गेम संसारलाई भरपर्दा अन्तरक्रियात्मक तत्वहरू। नायकहरू, शत्रुहरू, पावर-अपहरू, र दृश्य प्रभावहरू सबै गेम वस्तुहरू हुन्। प्रत्येकले `x` र `y` मानहरू प्रयोग गरेर विशिष्ट स्क्रिन समन्वयमा अवस्थित हुन्छ, ठीक जस्तै समन्वय प्लेनमा बिन्दुहरू प्लट गर्दै।

तिनीहरूको दृश्य भिन्नताहरूको बाबजुद, यी वस्तुहरूले प्रायः आधारभूत व्यवहारहरू साझा गर्छन्:

- **तिनीहरू कतै अवस्थित छन्** – प्रत्येक वस्तुमा x र y समन्वय हुन्छ ताकि गेमले यसलाई कहाँ ड्र गर्नुपर्छ थाहा पाओस्
- **धेरैले वरिपरि सर्न सक्छन्** – नायकहरू दौडन्छन्, शत्रुहरू पछ्याउँछन्, गोलीहरू स्क्रिनभरि उड्छन्
- **तिनीहरूको जीवनकाल हुन्छ** – केही सधैं रहन्छन्, अरू (जस्तै विस्फोटहरू) छोटो समयको लागि देखा पर्छन् र हराउँछन्
- **तिनीहरू कुराहरूमा प्रतिक्रिया दिन्छन्** – जब चीजहरू ठोक्किन्छन्, पावर-अपहरू सङ्कलन गरिन्छ, स्वास्थ्य बारहरू अपडेट हुन्छन्

✅ प्याक-म्यान जस्तो गेमको बारेमा सोच्नुहोस्। के तपाईं यस गेममा माथि सूचीबद्ध चार वस्तु प्रकारहरू पहिचान गर्न सक्नुहुन्छ?

### कोड मार्फत व्यवहार व्यक्त गर्दै

अब तपाईंले बुझ्नुभयो कि गेम वस्तुहरूले साझा गर्ने सामान्य व्यवहारहरू के हुन्, आउनुहोस् यी व्यवहारहरूलाई JavaScript मा कार्यान्वयन गर्ने तरिका अन्वेषण गरौं। तपाईंले वस्तुको व्यवहारलाई कक्षाहरू वा व्यक्तिगत वस्तुहरूमा संलग्न विधिहरू मार्फत व्यक्त गर्न सक्नुहुन्छ, र छनौट गर्नका लागि धेरै दृष्टिकोणहरू छन्।

**क्लास-आधारित दृष्टिकोण**

कक्षाहरू र इनहेरिटेन्सले गेम वस्तुहरूलाई व्यवस्थित गर्न संरचित दृष्टिकोण प्रदान गर्दछ। कार्ल लिनियसद्वारा विकसित कर प्रणाली जस्तै, तपाईं सामान्य गुणहरू समावेश गर्ने आधार कक्षा संग सुरु गर्नुहुन्छ, त्यसपछि विशेष क्षमताहरू थप्दै यी आधारभूतहरूलाई इनहेरिट गर्ने विशेष कक्षाहरू सिर्जना गर्नुहुन्छ।

✅ इनहेरिटेन्स बुझ्न महत्त्वपूर्ण अवधारणा हो। [MDN को इनहेरिटेन्सको बारेमा लेख](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) मा थप जान्नुहोस्।

यहाँ कसरी तपाईं कक्षाहरू र इनहेरिटेन्स प्रयोग गरेर गेम वस्तुहरू कार्यान्वयन गर्न सक्नुहुन्छ:

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

**यसलाई चरणबद्ध रूपमा तोडौं:**
- हामी प्रत्येक गेम वस्तुले प्रयोग गर्न सक्ने आधारभूत टेम्प्लेट सिर्जना गर्दैछौं
- कन्स्ट्रक्टरले वस्तु कहाँ छ (`x`, `y`) र कस्तो प्रकारको वस्तु हो भनेर बचत गर्दछ
- यो आधार बनिन्छ जसमा तपाईंका सबै गेम वस्तुहरू निर्माण हुनेछ

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

**माथिको कोडमा, हामीले:**
- गेमओब्जेक्ट कक्षालाई विस्तार गरेर मूभमेन्ट कार्यक्षमता थपेका छौं
- `super()` प्रयोग गरेर अभिभावक कन्स्ट्रक्टरलाई कल गरेका छौं ताकि इनहेरिटेड गुणहरू आरम्भ गर्न सकियोस्
- `moveTo()` विधि थपेका छौं जसले वस्तुको स्थिति अपडेट गर्दछ

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

**यी अवधारणाहरू बुझ्दै:**
- उपयुक्त व्यवहारहरू इनहेरिट गर्ने विशेष वस्तु प्रकारहरू सिर्जना गर्दछ
- इनहेरिटेन्सले चयनात्मक सुविधा समावेश गर्न कसरी अनुमति दिन्छ देखाउँछ
- नायकहरू सर्न सक्छन् जबकि रूखहरू स्थिर रहन्छन्
- कक्षा पदानुक्रमले अनुपयुक्त कार्यहरू रोक्छ भनेर चित्रण गर्दछ

✅ प्याक-म्यान नायक (जस्तै इन्की, पिन्की वा ब्लिन्की) लाई पुनः कल्पना गर्न केही मिनेट लिनुहोस् र यसलाई JavaScript मा कसरी लेख्न सकिन्छ भनेर सोच्नुहोस्।

**कम्पोजिसन दृष्टिकोण**

कम्पोजिसनले मोड्युलर डिजाइन दर्शन अनुसरण गर्दछ, जस्तै इन्जिनियरहरूले अन्तरिक्ष यानलाई विनिमेय कम्पोनेन्टहरूसँग डिजाइन गर्छन्। अभिभावक कक्षाबाट इनहेरिट गर्ने सट्टा, तपाईंले विशिष्ट व्यवहारहरू संयोजन गरेर वस्तुहरू सिर्जना गर्नुहुन्छ जसमा तिनीहरूलाई चाहिने कार्यक्षमता मात्र हुन्छ। यस दृष्टिकोणले कठोर पदानुक्रमीय बाधाहरू बिना लचिलोपन प्रदान गर्दछ।

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

**यस कोडले के गर्छ:**
- स्थिति र प्रकार गुणहरूसँग आधार `gameObject` परिभाषित गर्दछ
- मूभमेन्ट कार्यक्षमतासहित अलग `movable` व्यवहार वस्तु सिर्जना गर्दछ
- स्थिति डेटा र मूभमेन्ट तर्कलाई स्वतन्त्र राखेर चिन्ता अलग गर्दछ

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

**माथिको कोडमा, हामीले:**
- आधार वस्तु गुणहरू मूभमेन्ट व्यवहारसँग संयोजन गरेका छौं स्प्रेड सिन्ट्याक्स प्रयोग गरेर
- कस्टमाइज्ड वस्तुहरू फर्काउने फ्याक्टरी कार्यहरू सिर्जना गरेका छौं
- कठोर कक्षा पदानुक्रम बिना लचिलो वस्तु सिर्जना सक्षम गरेका छौं
- वस्तुहरूलाई तिनीहरूलाई चाहिने व्यवहारहरू मात्र दिन अनुमति दिएका छौं

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**महत्त्वपूर्ण बुँदाहरू सम्झनुहोस्:**
- वस्तुहरूलाई इनहेरिट गर्ने सट्टा व्यवहारहरू मिलाएर कम्पोज गर्छ
- कठोर इनहेरिटेन्स पदानुक्रमभन्दा बढी लचिलोपन प्रदान गर्छ
- वस्तुहरूलाई तिनीहरूलाई चाहिने सुविधाहरू मात्र दिन अनुमति दिन्छ
- सफा वस्तु संयोजनको लागि आधुनिक JavaScript स्प्रेड सिन्ट्याक्स प्रयोग गर्छ 
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

**यहाँ के हुन्छ भनेर तोड्दै:**
- साधारण कक्षाको प्रयोग गरेर केन्द्रीय इभेन्ट व्यवस्थापन प्रणाली सिर्जना गर्दछ
- सन्देश प्रकारद्वारा व्यवस्थित वस्तुमा श्रोताहरू भण्डारण गर्दछ
- `on()` विधि प्रयोग गरेर नयाँ श्रोताहरू दर्ता गर्दछ
- सबै इच्छुक श्रोताहरूलाई सन्देशहरू प्रसारण गर्दछ `emit()` प्रयोग गरेर
- सान्दर्भिक जानकारी पास गर्न वैकल्पिक डेटा पेलोडहरू समर्थन गर्दछ

### सबैलाई एकसाथ राख्दै: व्यावहारिक उदाहरण

ठीक छ, यसलाई कार्यमा देखौं! हामी एक साधारण मूभमेन्ट प्रणाली निर्माण गर्नेछौं जसले पब/सब कति सफा र लचिलो हुन सक्छ देखाउँछ:

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

**यस कोडले के गर्छ:**
- सन्देश नामहरूमा टाइपो रोक्न स्थिर वस्तु परिभाषित गर्दछ
- सबै कम्युनिकेसन ह्यान्डल गर्न इभेन्ट इमिटर उदाहरण सिर्जना गर्दछ
- सुरुवात स्थितिमा नायक वस्तु आरम्भ गर्दछ

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

**माथिको कोडमा, हामीले:**
- मूभमेन्ट सन्देशहरूमा प्रतिक्रिया दिने इभेन्ट श्रोताहरू दर्ता गरेका छौं
- मूभमेन्ट दिशाको आधारमा नायकको स्थिति अपडेट गरेका छौं
- नायकको स्थिति परिवर्तनहरू ट्र्याक गर्न कन्सोल लगिङ थपेका छौं
- इनपुट ह्यान्डलिङबाट मूभमेन्ट तर्क अलग गरेका छौं

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

**यी अवधारणाहरू बुझ्दै:**
- टाइट कपलिङ बिना गेम इभेन्टहरूसँग किबोर्ड इनपुट जडान गर्दछ
- इनपुट प्रणालीलाई अप्रत्यक्ष रूपमा गेम वस्तुहरूसँग कम्युनिकेसन गर्न सक्षम बनाउँछ
- एउटै किबोर्ड इभेन्टहरूमा धेरै प्रणालीहरू प्रतिक्रिया दिन अनुमति दिन्छ
- की बाइन्डिङ परिवर्तन गर्न वा नयाँ इनपुट विधिहरू थप्न सजिलो बनाउँछ

> 💡 **प्रो टिप**: यस ढाँचाको सुन्दरता लचिलोपनमा छ! तपाईंले ध्वनि प्रभावहरू, स्क्रिन शेक, वा पार्टिकल प्रभावहरू सजिलै थप्न सक्नुहुन्छ – केवल थप इभेन्ट श्रोताहरू थप्नुहोस् – विद्यमान किबोर्ड वा मूभमेन्ट कोडलाई परिवर्तन गर्न आवश्यक छैन।
> 
**तपाईंलाई यो दृष्टिकोण किन मनपर्छ:**
- नयाँ सुविधाहरू थप्न धेरै सजिलो हुन्छ – केवल तपाईंलाई चासो लाग्ने इभेन्टहरूको लागि सुन्नुहोस्
- एउटै इभेन्टमा धेरै चीजहरूले एकअर्कामा बाधा नपुगिकन प्रतिक्रिया दिन सक्छन्
- परीक्षण धेरै सरल हुन्छ किनकि प्रत्येक टुक्रा स्वतन्त्र रूपमा काम गर्छ
- जब केही बिग्रन्छ, तपाईंलाई ठीक कहाँ हेर्नुपर्छ थाहा हुन्छ

### किन पब/सब प्रभावकारी रूपमा स्केल हुन्छ

पब/सब ढाँचाले एप्लिकेसनहरू जटिलतामा बढ्दै जाँदा सरलता कायम राख्छ। दर्जनौं शत्रुहरू, गतिशील UI अपडेटहरू, वा ध्वनि प्रणालीहरू व्यवस्थापन गर्दा, ढाँचाले वास्तुकलामा परिवर्तन नगरी बढ्दो स्केललाई ह्यान्डल गर्छ। नयाँ सुविधाहरू स्थापित कार्यक्षमतालाई असर नगरी विद्यमान इभेन्ट प्रणालीमा एकीकृत हुन्छन्।

> ⚠️ **सामान्य गल्ती**: धेरै विशिष्ट सन्देश प्रकारहरू प्रारम्भमा सिर्जना नगर्नुहोस्। व्यापक श्रेणीहरूसँग सुरु गर्नुहोस् र तपाईंको गेमको आवश्यकताहरू स्पष्ट हुँदै जाँदा तिनीहरूलाई परिष्कृत गर्नुहोस्।
> 
**पालना गर्नुपर्ने उत्कृष्ट अभ्यासहरू:**
- सम्बन्धित सन्देशहरूलाई तार्किक श्रेणीहरूमा समूह बनाउँछ
- के भयो भनेर स्पष्ट रूपमा संकेत गर्ने वर्णनात्मक नामहरू प्रयोग गर्छ
- सन्देश पेलोडहरूलाई सरल र केन्द्रित राख्छ
- टोली सहयोगका लागि तपाईंको सन्देश प्रकारहरूलाई कागजात बनाउँछ

---

## GitHub Copilot एजेन्ट चुनौती 🚀

एजेन्ट मोड प्रयोग गरेर निम्न चुनौती पूरा गर्नुहोस्:

**विवरण:** इनहेरिटेन्स र पब/सब ढाँचाको प्रयोग गरेर एक साधारण गेम वस्तु प्रणाली सिर्जना गर्नुहोस्। तपाईंले एक आधारभूत गेम कार्यान्वयन गर्नुहुनेछ जहाँ विभिन्न वस्तुहरूले एकअर्काको बारेमा प्रत्यक्ष रूपमा थाहा नपाई इभेन्टहरू मार्फत कम्युनिकेसन गर्न सक्छन्।

**प्रेरणा:** निम्न आवश्यकताहरू सहित एक JavaScript गेम प्रणाली सिर्जना गर्नुहोस्: १) x, y समन्वय र प्रकार गुणहरूसहित आधार GameObject कक्षा सिर्जना गर्नुहोस्। २) GameObject विस्तार गर्ने र सर्न सक्ने Hero कक्षा सिर्जना गर्नुहोस्। ३) GameObject विस्तार गर्ने र नायकलाई पछ्याउन सक्ने Enemy कक्षा सिर्जना गर्नुहोस्। ४) पब/सब ढाँचाको लागि EventEmitter कक्षा कार्यान्वयन गर्नुहोस्। ५) इभेन्ट श्रोताहरू सेटअप गर्नुहोस् ताकि जब नायक सर्छ, नजिकका शत्रुहरूले 'HERO_MOVED' इभेन्ट प्राप्त गर्छन् र नायकतर्फ सर्ने आफ्नो स्थिति अपडेट गर्छन्। वस्तुहरू बीचको कम्युनिकेसन देखाउन कन्सोल लग स्टेटमेन्टहरू समावेश गर्नुहोस्।

[एजेन्ट मोडको बारेमा थप जान्नुहोस्](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) यहाँ।

## 🚀 चुनौती

पब-सब ढाँचाले गेम आर्किटेक्चरलाई कसरी सुधार गर्न सक्छ भनेर विचार गर्नुहोस्। कुन कम्पोनेन्टहरूले इभेन्टहरू प्रसारण गर्नुपर्छ र प्रणालीले कसरी प्रतिक्रिया दिनुपर्छ भनेर पहिचान गर्नुहोस्। गेम अवधारणा डिजाइन गर्नुहोस् र यसको कम्पोनेन्टहरू बीचको कम्युनिकेसन ढाँचाहरूको नक्सा बनाउनुहोस्।

## पोस्ट-लेक्चर क्विज

[पोस्ट-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/30)

## समीक्षा र आत्म अध्ययन

पब/सबको बारेमा [यसको बारेमा पढेर](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon) थप जान्नुहोस्।

## असाइनमेन्ट

[एक गेमको मोडेल बनाउनुहोस्](assignment.md)

---

**अस्वीकरण**:  
यो दस्तावेज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको छ। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादमा त्रुटिहरू वा अशुद्धताहरू हुन सक्छ। यसको मूल भाषा मा रहेको दस्तावेजलाई आधिकारिक स्रोत मानिनुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न हुने कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुने छैनौं।