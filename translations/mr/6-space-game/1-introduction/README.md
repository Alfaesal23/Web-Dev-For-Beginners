<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "38777f8c81874368d3b4b9b8a54aa242",
  "translation_date": "2025-10-20T21:28:17+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "mr"
}
-->
# स्पेस गेम तयार करा भाग 1: परिचय

![व्हिडिओ](../../../../6-space-game/images/pewpew.gif)

## व्याख्यानपूर्व प्रश्नमंजुषा

[व्याख्यानपूर्व प्रश्नमंजुषा](https://ff-quizzes.netlify.app/web/quiz/29)

### गेम डेव्हलपमेंटमध्ये इनहेरिटन्स आणि कंपोझिशन

पूर्वीच्या धड्यांमध्ये, तुम्ही तयार केलेल्या अ‍ॅप्सच्या डिझाइन आर्किटेक्चरबद्दल फारसा विचार करण्याची गरज नव्हती, कारण प्रकल्पांचा आवाका खूप लहान होता. परंतु, जेव्हा तुमचे अ‍ॅप्लिकेशन्स आकाराने आणि आवाक्याने वाढतात, तेव्हा आर्किटेक्चरल निर्णय अधिक महत्त्वाचे होतात. जावास्क्रिप्टमध्ये मोठ्या अ‍ॅप्लिकेशन्स तयार करण्यासाठी दोन प्रमुख पद्धती आहेत: *कंपोझिशन* किंवा *इनहेरिटन्स*. दोन्हींचे फायदे आणि तोटे आहेत, परंतु गेमच्या संदर्भात त्याचे स्पष्टीकरण देऊया.

✅ सर्वात प्रसिद्ध प्रोग्रामिंग पुस्तकांपैकी एक [डिझाइन पॅटर्न्स](https://en.wikipedia.org/wiki/Design_Patterns) याबद्दल आहे.

गेममध्ये तुम्हाला `गेम ऑब्जेक्ट्स` असतात, जे स्क्रीनवर असणारे ऑब्जेक्ट्स असतात. याचा अर्थ असा की त्यांना कार्टेशियन कोऑर्डिनेट सिस्टमवर स्थान असते, ज्यामध्ये `x` आणि `y` कोऑर्डिनेट असते. तुम्ही गेम विकसित करत असताना तुम्हाला लक्षात येईल की तुमच्या सर्व गेम ऑब्जेक्ट्समध्ये एक मानक गुणधर्म असतो, जो तुम्ही तयार केलेल्या प्रत्येक गेमसाठी सामान्य असतो, म्हणजेच घटक जे:

- **स्थान-आधारित** बहुतेक, किंवा सर्व गेम घटक स्थान-आधारित असतात. याचा अर्थ असा की त्यांना एक स्थान असते, `x` आणि `y`.
- **चालणारे** हे ऑब्जेक्ट्स आहेत जे नवीन ठिकाणी जाऊ शकतात. हे सामान्यतः एक हिरो, एक मॉन्स्टर किंवा एक NPC (नॉन प्लेअर कॅरेक्टर) असते, परंतु उदाहरणार्थ, झाडासारख्या स्थिर ऑब्जेक्टसाठी नाही.
- **स्वत: नष्ट करणारे** हे ऑब्जेक्ट्स फक्त काही कालावधीसाठी अस्तित्वात असतात आणि नंतर स्वत: ला हटवण्यासाठी सेट करतात. सामान्यतः हे `मृत` किंवा `नष्ट झालेले` बूलियनद्वारे दर्शविले जाते जे गेम इंजिनला सूचित करते की हे ऑब्जेक्ट आता रेंडर केले जाऊ नये.
- **कूल-डाउन** 'कूल-डाउन' हा अल्पकालीन ऑब्जेक्ट्समध्ये एक सामान्य गुणधर्म आहे. एक सामान्य उदाहरण म्हणजे एक टेक्स्ट किंवा ग्राफिकल इफेक्ट जसे की स्फोट जो फक्त काही मिलीसेकंदांसाठी दिसला पाहिजे.

✅ पॅक-मॅन सारख्या गेमचा विचार करा. तुम्ही या गेममध्ये वरील चार ऑब्जेक्ट प्रकार ओळखू शकता का?

### वर्तन व्यक्त करणे

आम्ही वर वर्णन केलेले सर्व वर्तन आहे जे गेम ऑब्जेक्ट्समध्ये असू शकते. तर आपण ते कसे कोड करतो? आम्ही हे वर्तन `क्लासेस` किंवा ऑब्जेक्ट्सशी संबंधित पद्धती म्हणून व्यक्त करू शकतो.

**क्लासेस**

`क्लासेस`चा वापर करून आणि `इनहेरिटन्स`सह विशिष्ट वर्तन क्लासमध्ये जोडण्यासाठी ही कल्पना आहे.

✅ इनहेरिटन्स समजून घेणे महत्त्वाचे आहे. [MDN च्या इनहेरिटन्स आणि प्रोटोटाइप चेनबद्दलच्या लेखात](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain) अधिक जाणून घ्या.

कोडद्वारे व्यक्त केले गेले, एक गेम ऑब्जेक्ट सामान्यतः असे दिसते:

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

✅ पॅक-मॅन हिरो (उदाहरणार्थ, इन्की, पिंकी किंवा ब्लिंकी) पुन्हा कसा लिहिला जाऊ शकतो आणि तो जावास्क्रिप्टमध्ये कसा दिसेल याचा विचार करण्यासाठी काही मिनिटे घ्या.

**कंपोझिशन**

ऑब्जेक्ट इनहेरिटन्स हाताळण्याचा एक वेगळा मार्ग म्हणजे *कंपोझिशन* वापरणे. मग, ऑब्जेक्ट्स त्यांचे वर्तन अशा प्रकारे व्यक्त करतात:

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

**मला कोणता पॅटर्न वापरावा?**

तुम्ही कोणता पॅटर्न निवडता हे तुमच्यावर अवलंबून आहे. जावास्क्रिप्ट या दोन्ही पद्धतींना समर्थन देते.

--

गेम डेव्हलपमेंटमध्ये एक सामान्य पॅटर्न गेमचा युजर अनुभव आणि कार्यक्षमता हाताळण्याच्या समस्येचे निराकरण करते.

## पब/सब पॅटर्न

✅ पब/सब म्हणजे 'पब्लिश-सबस्क्राइब'

हा पॅटर्न तुमच्या अ‍ॅप्लिकेशनच्या विविध भागांनी एकमेकांबद्दल माहिती नसावी या कल्पनेला संबोधित करतो. का? कारण जर विविध भाग वेगळे असतील तर एकूण काय चालले आहे हे पाहणे खूप सोपे होते. जर तुम्हाला गरज असेल तर वर्तन अचानक बदलणे देखील सोपे होते. आपण हे कसे साध्य करतो? आम्ही काही संकल्पना स्थापित करून हे करतो:

- **संदेश**: संदेश हा सामान्यतः एक टेक्स्ट स्ट्रिंग असतो ज्यासह एक पर्यायी पेलोड (डेटाचा तुकडा जो संदेशाबद्दल स्पष्ट करतो) असतो. गेममधील एक सामान्य संदेश `KEY_PRESSED_ENTER` असू शकतो.
- **पब्लिशर**: हा घटक एक संदेश *पब्लिश* करतो आणि तो सर्व सबस्क्राइबर्सकडे पाठवतो.
- **सबस्क्राइबर**: हा घटक विशिष्ट संदेश *ऐकतो* आणि हा संदेश प्राप्त झाल्यामुळे काही कार्य करतो, जसे की लेसर फायर करणे.

अंमलबजावणी आकाराने खूप लहान आहे परंतु हा एक अतिशय शक्तिशाली पॅटर्न आहे. हे कसे अंमलात आणले जाऊ शकते ते येथे आहे:

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

वरील कोड वापरण्यासाठी आम्ही एक अतिशय लहान अंमलबजावणी तयार करू शकतो:

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

वरील उदाहरणात, आम्ही कीबोर्ड इव्हेंट `ArrowLeft` कनेक्ट करतो आणि `HERO_MOVE_LEFT` संदेश पाठवतो. आम्ही तो संदेश ऐकतो आणि त्याचा परिणाम म्हणून `हिरो` हलवतो. या पॅटर्नची ताकद अशी आहे की इव्हेंट लिसनर आणि हिरो एकमेकांना ओळखत नाहीत. तुम्ही `ArrowLeft` ला `A` कीवर पुन्हा मॅप करू शकता. याशिवाय, इव्हेंटएमिटरच्या `on` फंक्शनमध्ये काही संपादने करून `ArrowLeft` वर काहीतरी पूर्णपणे वेगळे करणे शक्य होईल:

```javascript
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.move(5,0);
});
```

तुमचा गेम वाढत असताना गोष्टी अधिक क्लिष्ट होत असताना, हा पॅटर्न जटिलतेत समान राहतो आणि तुमचा कोड स्वच्छ राहतो. हा पॅटर्न स्वीकारणे खरोखरच शिफारस केले जाते.

---

## GitHub Copilot Agent चॅलेंज 🚀

Agent मोड वापरून खालील चॅलेंज पूर्ण करा:

**वर्णन:** इनहेरिटन्स आणि पब/सब पॅटर्न दोन्ही वापरून एक साधी गेम ऑब्जेक्ट प्रणाली तयार करा. तुम्ही एक मूलभूत गेम अंमलात आणाल जिथे विविध ऑब्जेक्ट्स एकमेकांबद्दल थेट माहिती न घेता इव्हेंट्सद्वारे संवाद साधू शकतात.

**प्रॉम्प्ट:** खालील आवश्यकता असलेली जावास्क्रिप्ट गेम प्रणाली तयार करा: 1) x, y कोऑर्डिनेट्स आणि एक प्रकार गुणधर्म असलेला बेस GameObject क्लास तयार करा. 2) GameObject विस्तारणारा Hero क्लास तयार करा जो हलू शकतो. 3) GameObject विस्तारणारा Enemy क्लास तयार करा जो हिरोचा पाठलाग करू शकतो. 4) पब/सब पॅटर्नसाठी EventEmitter क्लास अंमलात आणा. 5) इव्हेंट लिसनर्स सेट करा जेव्हा हिरो हलतो, तेव्हा जवळच्या शत्रूंना 'HERO_MOVED' इव्हेंट प्राप्त होतो आणि हिरोकडे हलण्यासाठी त्यांची स्थिती अपडेट करतो. ऑब्जेक्ट्समधील संवाद दाखवण्यासाठी console.log स्टेटमेंट्स समाविष्ट करा.

## 🚀 चॅलेंज

पब-सब पॅटर्न गेम कसा सुधारू शकतो याचा विचार करा. कोणते भाग इव्हेंट्स पाठवायला हवेत, आणि गेमने त्यावर कसा प्रतिसाद द्यायला हवा? आता नवीन गेमचा विचार करण्याची आणि त्याचे भाग कसे वागतील याबद्दल सर्जनशील होण्याची संधी आहे.

## व्याख्यानोत्तर प्रश्नमंजुषा

[व्याख्यानोत्तर प्रश्नमंजुषा](https://ff-quizzes.netlify.app/web/quiz/30)

## पुनरावलोकन आणि स्व-अभ्यास

पब/सब बद्दल अधिक जाणून घ्या [याबद्दल वाचा](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## असाइनमेंट

[गेमची रूपरेषा तयार करा](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपया लक्षात ठेवा की स्वयंचलित भाषांतरांमध्ये त्रुटी किंवा अचूकतेचा अभाव असू शकतो. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून निर्माण झालेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार राहणार नाही.