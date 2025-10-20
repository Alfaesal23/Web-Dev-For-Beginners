<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "6b04a23d9d5e9edb252c909af4fb5f31",
  "translation_date": "2025-10-20T21:26:20+00:00",
  "source_file": "4-typing-game/typing-game/README.md",
  "language_code": "mr"
}
-->
# इव्हेंट्स वापरून गेम तयार करणे

## प्री-लेक्चर क्विझ

[प्री-लेक्चर क्विझ](https://ff-quizzes.netlify.app/web/quiz/21)

## इव्हेंट-ड्रिव्हन प्रोग्रामिंग

ब्राउझर आधारित अॅप्लिकेशन तयार करताना, आपण वापरकर्त्याला आपल्याने तयार केलेल्या गोष्टींशी संवाद साधण्यासाठी ग्राफिकल यूजर इंटरफेस (GUI) प्रदान करतो. ब्राउझरशी संवाद साधण्याचा सर्वात सामान्य मार्ग म्हणजे विविध घटकांवर क्लिक करणे आणि टाइप करणे. एक विकसक म्हणून आपल्याला आव्हान आहे की ते हे ऑपरेशन्स कधी करणार आहेत हे आपल्याला माहित नाही!

[इव्हेंट-ड्रिव्हन प्रोग्रामिंग](https://en.wikipedia.org/wiki/Event-driven_programming) ही आपल्याला GUI तयार करण्यासाठी करावी लागणारी प्रोग्रामिंगची पद्धत आहे. जर आपण या वाक्यांशाचे थोडेसे विश्लेषण केले तर आपल्याला दिसेल की मुख्य शब्द आहे **इव्हेंट**. [इव्हेंट](https://www.merriam-webster.com/dictionary/event), मेरियम-वेबस्टरनुसार, "काहीतरी जे घडते" असे परिभाषित केले जाते. हे आपली परिस्थिती उत्तम प्रकारे वर्णन करते. आपल्याला माहित आहे की काहीतरी घडणार आहे ज्यासाठी आपण काही कोड अंमलात आणू इच्छितो, परंतु ते कधी होईल हे आपल्याला माहित नाही.

आपण अंमलात आणू इच्छित असलेल्या कोडचा विभाग चिन्हांकित करण्याचा मार्ग म्हणजे फंक्शन तयार करणे. [प्रोसीजरल प्रोग्रामिंग](https://en.wikipedia.org/wiki/Procedural_programming) विचार करताना, फंक्शन्स विशिष्ट क्रमाने कॉल केले जातात. इव्हेंट-ड्रिव्हन प्रोग्रामिंगसाठीही हेच खरे आहे. फरक फक्त **कसा** फंक्शन्स कॉल केले जातात यामध्ये आहे.

इव्हेंट्स (बटण क्लिक करणे, टाइप करणे, इ.) हाताळण्यासाठी, आपण **इव्हेंट लिसनर्स** नोंदवतो. इव्हेंट लिसनर म्हणजे एक फंक्शन जे इव्हेंट घडण्याची वाट पाहते आणि प्रतिसाद म्हणून अंमलात आणते. इव्हेंट लिसनर्स UI अपडेट करू शकतात, सर्व्हरला कॉल करू शकतात किंवा वापरकर्त्याच्या क्रियेस प्रतिसाद म्हणून करणे आवश्यक असलेले इतर काहीही करू शकतात. आपण [addEventListener](https://developer.mozilla.org/docs/Web/API/EventTarget/addEventListener) वापरून आणि अंमलात आणण्यासाठी फंक्शन प्रदान करून इव्हेंट लिसनर जोडतो.

> **NOTE:** इव्हेंट लिसनर्स तयार करण्याचे अनेक मार्ग आहेत हे अधोरेखित करणे योग्य आहे. आपण अज्ञात फंक्शन्स वापरू शकता किंवा नामांकित फंक्शन्स तयार करू शकता. आपण `click` प्रॉपर्टी सेट करणे किंवा `addEventListener` वापरणे यासारख्या विविध शॉर्टकट्स वापरू शकता. आपल्या व्यायामामध्ये आपण `addEventListener` आणि अज्ञात फंक्शन्सवर लक्ष केंद्रित करणार आहोत, कारण वेब विकसक सर्वात सामान्य तंत्र वापरतात. हे सर्वात लवचिक आहे, कारण `addEventListener` सर्व इव्हेंट्ससाठी कार्य करते आणि इव्हेंटचे नाव पॅरामीटर म्हणून प्रदान केले जाऊ शकते.

### सामान्य इव्हेंट्स

[डझनभर इव्हेंट्स](https://developer.mozilla.org/docs/Web/Events) उपलब्ध आहेत जेव्हा आपण अॅप्लिकेशन तयार करत असतो. पृष्ठावर वापरकर्ता जे काही करतो ते इव्हेंट निर्माण करते, जे आपल्याला त्यांना हवे असलेले अनुभव मिळविण्यासाठी खूप शक्ती देते. सुदैवाने, आपल्याला सामान्यतः फक्त काही इव्हेंट्सची आवश्यकता असते. येथे काही सामान्य इव्हेंट्स आहेत (ज्यामध्ये आपण गेम तयार करताना वापरणार आहोत):

- [click](https://developer.mozilla.org/docs/Web/API/Element/click_event): वापरकर्त्याने काहीतरी क्लिक केले, सामान्यतः बटण किंवा हायपरलिंक
- [contextmenu](https://developer.mozilla.org/docs/Web/API/Element/contextmenu_event): वापरकर्त्याने उजव्या माऊस बटणावर क्लिक केले
- [select](https://developer.mozilla.org/docs/Web/API/Element/select_event): वापरकर्त्याने काही मजकूर हायलाइट केला
- [input](https://developer.mozilla.org/docs/Web/API/Element/input_event): वापरकर्त्याने काही मजकूर टाइप केला

## गेम तयार करणे

आम्ही जावास्क्रिप्टमध्ये इव्हेंट्स कसे कार्य करतात हे एक्सप्लोर करण्यासाठी एक गेम तयार करणार आहोत. आमचा गेम खेळाडूच्या टाइपिंग कौशल्याची चाचणी घेणार आहे, जे सर्व विकसकांनी असले पाहिजे असे एक कौशल्य आहे. आपल्याला सर्वांनी आपले टाइपिंग सराव करणे आवश्यक आहे! गेमचा सामान्य प्रवाह असा दिसेल:

- खेळाडू स्टार्ट बटणावर क्लिक करतो आणि टाइप करण्यासाठी एक कोट दिला जातो
- खेळाडू कोट जितक्या लवकर टाइप करू शकतो तितक्या लवकर टाइप करतो
  - प्रत्येक शब्द पूर्ण झाल्यावर पुढील शब्द हायलाइट केला जातो
  - जर खेळाडूने टायपो केला तर टेक्स्टबॉक्स लाल रंगात अपडेट केला जातो
  - जेव्हा खेळाडू कोट पूर्ण करतो, तेव्हा यशाचा संदेश प्रदर्शित होतो आणि लागलेला वेळ दाखवला जातो

चला आपला गेम तयार करूया आणि इव्हेंट्सबद्दल शिकूया!

### फाइल स्ट्रक्चर

आम्हाला एकूण तीन फाइल्सची आवश्यकता असेल: **index.html**, **script.js** आणि **style.css**. चला ते सेट करूया जेणेकरून आपले काम सोपे होईल.

- कन्सोल किंवा टर्मिनल विंडो उघडून खालील कमांड जारी करून आपल्या कामासाठी एक नवीन फोल्डर तयार करा:

```bash
# Linux or macOS
mkdir typing-game && cd typing-game

# Windows
md typing-game && cd typing-game
```

- व्हिज्युअल स्टुडिओ कोड उघडा

```bash
code .
```

- व्हिज्युअल स्टुडिओ कोडमध्ये फोल्डरमध्ये खालील नावांच्या तीन फाइल्स जोडा:
  - index.html
  - script.js
  - style.css

## यूजर इंटरफेस तयार करा

जर आपण आवश्यकता एक्सप्लोर केल्या तर आपल्याला माहित आहे की आपल्याला आपल्या HTML पृष्ठावर काही घटकांची आवश्यकता आहे. हे काहीसे रेसिपीसारखे आहे, जिथे आपल्याला काही घटकांची आवश्यकता आहे:

- वापरकर्त्याला टाइप करण्यासाठी कोट प्रदर्शित करण्यासाठी जागा
- कोणतेही संदेश प्रदर्शित करण्यासाठी जागा, जसे की यशाचा संदेश
- टाइप करण्यासाठी टेक्स्टबॉक्स
- स्टार्ट बटण

यापैकी प्रत्येकाला आयडी आवश्यक असेल जेणेकरून आपण आपल्या जावास्क्रिप्टमध्ये त्यांच्याशी काम करू शकू. आम्ही तयार करणार असलेल्या CSS आणि जावास्क्रिप्ट फाइल्ससाठी संदर्भ देखील जोडू.

**index.html** नावाची नवीन फाइल तयार करा. खालील HTML जोडा:

```html
<!-- inside index.html -->
<html>
<head>
  <title>Typing game</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Typing game!</h1>
  <p>Practice your typing skills with a quote from Sherlock Holmes. Click **start** to begin!</p>
  <p id="quote"></p> <!-- This will display our quote -->
  <p id="message"></p> <!-- This will display any status messages -->
  <div>
    <input type="text" aria-label="current word" id="typed-value" /> <!-- The textbox for typing -->
    <button type="button" id="start">Start</button> <!-- To start the game -->
  </div>
  <script src="script.js"></script>
</body>
</html>
```

### अॅप्लिकेशन लॉन्च करा

सर्वकाही कसे दिसते हे पाहण्यासाठी नेहमीच पुनरावृत्तीने विकसित करणे चांगले असते. चला आपले अॅप्लिकेशन लॉन्च करूया. व्हिज्युअल स्टुडिओ कोडसाठी [लाइव्ह सर्व्हर](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer&WT.mc_id=academic-77807-sagibbon) नावाचा एक उत्कृष्ट एक्सटेंशन आहे जो आपले अॅप्लिकेशन स्थानिक पातळीवर होस्ट करेल आणि आपण प्रत्येक वेळी सेव्ह केल्यावर ब्राउझर रीफ्रेश करेल.

- [लाइव्ह सर्व्हर](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer&WT.mc_id=academic-77807-sagibbon) इंस्टॉल करा, लिंकवर क्लिक करून **Install** वर क्लिक करा
  - ब्राउझर आपल्याला व्हिज्युअल स्टुडिओ कोड उघडण्यासाठी प्रॉम्प्ट करेल आणि नंतर व्हिज्युअल स्टुडिओ कोड इंस्टॉलेशन करण्यासाठी प्रॉम्प्ट करेल
  - जर प्रॉम्प्ट केले गेले तर व्हिज्युअल स्टुडिओ कोड रीस्टार्ट करा
- इंस्टॉल झाल्यानंतर, व्हिज्युअल स्टुडिओ कोडमध्ये, Ctrl-Shift-P (किंवा Cmd-Shift-P) क्लिक करा आणि कमांड पॅलेट उघडा
- **Live Server: Open with Live Server** टाइप करा
  - लाइव्ह सर्व्हर आपले अॅप्लिकेशन होस्ट करणे सुरू करेल
- ब्राउझर उघडा आणि **https://localhost:5500** वर जा
- आता आपण तयार केलेले पृष्ठ पाहू शकता!

चला काही फंक्शनॅलिटी जोडूया.

## CSS जोडा

आपले HTML तयार झाल्यावर, कोर स्टाइलिंगसाठी CSS जोडा. आपल्याला खेळाडूने टाइप करावयाचा शब्द हायलाइट करायचा आहे आणि त्यांनी चुकीचे टाइप केल्यास टेक्स्टबॉक्स रंगवायचा आहे. आम्ही हे दोन क्लासेससह करू.

**style.css** नावाची नवीन फाइल तयार करा आणि खालील सिंटॅक्स जोडा.

```css
/* inside style.css */
.highlight {
  background-color: yellow;
}

.error {
  background-color: lightcoral;
  border: red;
}
```

✅ CSS बद्दल बोलायचे झाले तर आपण आपले पृष्ठ कसे मांडायचे ते ठरवू शकता. थोडा वेळ घ्या आणि पृष्ठ अधिक आकर्षक बनवा:

- वेगळा फॉन्ट निवडा
- हेडर्स रंगवा
- आयटम्सचे आकार बदला

## जावास्क्रिप्ट

आपले UI तयार झाल्यानंतर, आता आपण जावास्क्रिप्टवर लक्ष केंद्रित करूया जे लॉजिक प्रदान करेल. आम्ही याला काही चरणांमध्ये विभागणार आहोत:

- [कॉन्स्टंट्स तयार करा](../../../../4-typing-game/typing-game)
- [गेम सुरू करण्यासाठी इव्हेंट लिसनर](../../../../4-typing-game/typing-game)
- [टाइपिंगसाठी इव्हेंट लिसनर](../../../../4-typing-game/typing-game)

परंतु प्रथम, **script.js** नावाची नवीन फाइल तयार करा.

### कॉन्स्टंट्स जोडा

प्रोग्रामिंग आपल्यासाठी सोपे करण्यासाठी आम्हाला काही आयटम्सची आवश्यकता आहे. पुन्हा, रेसिपीसारखे, आपल्याला याची आवश्यकता आहे:

- सर्व कोट्सच्या यादीसह अ‍ॅरे
- सध्याच्या कोटसाठी सर्व शब्द साठवण्यासाठी रिक्त अ‍ॅरे
- खेळाडू सध्या टाइप करत असलेल्या शब्दाचा निर्देशांक साठवण्यासाठी जागा
- खेळाडूने स्टार्ट क्लिक केलेला वेळ

आपल्याला UI घटकांसाठी संदर्भ देखील हवे आहेत:

- टेक्स्टबॉक्स (**typed-value**)
- कोट डिस्प्ले (**quote**)
- संदेश (**message**)

```javascript
// inside script.js
// all of our quotes
const quotes = [
    'When you have eliminated the impossible, whatever remains, however improbable, must be the truth.',
    'There is nothing more deceptive than an obvious fact.',
    'I ought to know by this time that when a fact appears to be opposed to a long train of deductions it invariably proves to be capable of bearing some other interpretation.',
    'I never make exceptions. An exception disproves the rule.',
    'What one man can invent another can discover.',
    'Nothing clears up a case so much as stating it to another person.',
    'Education never ends, Watson. It is a series of lessons, with the greatest for the last.',
];
// store the list of words and the index of the word the player is currently typing
let words = [];
let wordIndex = 0;
// the starting time
let startTime = Date.now();
// page elements
const quoteElement = document.getElementById('quote');
const messageElement = document.getElementById('message');
const typedValueElement = document.getElementById('typed-value');
```

✅ आपल्या गेममध्ये अधिक कोट्स जोडा

> **NOTE:** आपण `document.getElementById` वापरून कोडमध्ये कधीही घटक पुनर्प्राप्त करू शकतो. कारण आपण नियमितपणे या घटकांचा संदर्भ घेणार आहोत, आम्ही स्ट्रिंग लिटरल्ससह टायपो टाळण्यासाठी कॉन्स्टंट्स वापरणार आहोत. [Vue.js](https://vuejs.org/) किंवा [React](https://reactjs.org/) सारख्या फ्रेमवर्क्स आपल्याला आपला कोड केंद्रीकृत व्यवस्थापित करण्यात मदत करू शकतात.

`const`, `let` आणि `var` वापरण्याबद्दल व्हिडिओ पाहण्यासाठी एक मिनिट घ्या

[![व्हेरिएबल्सचे प्रकार](https://img.youtube.com/vi/JNIXfGiDWM8/0.jpg)](https://youtube.com/watch?v=JNIXfGiDWM8 "व्हेरिएबल्सचे प्रकार")

> 🎥 वरील प्रतिमेवर क्लिक करा आणि व्हेरिएबल्सबद्दल व्हिडिओ पहा.

### स्टार्ट लॉजिक जोडा

गेम सुरू करण्यासाठी, खेळाडू स्टार्ट क्लिक करेल. अर्थात, ते स्टार्ट कधी क्लिक करणार आहेत हे आपल्याला माहित नाही. येथे [इव्हेंट लिसनर](https://developer.mozilla.org/docs/Web/API/EventTarget/addEventListener) कामी येतो. इव्हेंट लिसनर आपल्याला काहीतरी घडण्याची वाट पाहण्याची (इव्हेंट) आणि प्रतिसाद म्हणून कोड अंमलात आणण्याची परवानगी देतो. आपल्या बाबतीत, वापरकर्त्याने स्टार्ट क्लिक केल्यावर कोड अंमलात आणायचा आहे.

जेव्हा वापरकर्त्याने **स्टार्ट** क्लिक केले, तेव्हा आपल्याला कोट निवडणे, यूजर इंटरफेस सेट करणे आणि सध्याच्या शब्दासाठी आणि टाइमिंगसाठी ट्रॅकिंग सेट करणे आवश्यक आहे. खाली आपल्याला आवश्यक असलेला जावास्क्रिप्ट आहे; आम्ही स्क्रिप्ट ब्लॉकनंतर त्यावर चर्चा करतो.

```javascript
// at the end of script.js
document.getElementById('start').addEventListener('click', () => {
  // get a quote
  const quoteIndex = Math.floor(Math.random() * quotes.length);
  const quote = quotes[quoteIndex];
  // Put the quote into an array of words
  words = quote.split(' ');
  // reset the word index for tracking
  wordIndex = 0;

  // UI updates
  // Create an array of span elements so we can set a class
  const spanWords = words.map(function(word) { return `<span>${word} </span>`});
  // Convert into string and set as innerHTML on quote display
  quoteElement.innerHTML = spanWords.join('');
  // Highlight the first word
  quoteElement.childNodes[0].className = 'highlight';
  // Clear any prior messages
  messageElement.innerText = '';

  // Setup the textbox
  // Clear the textbox
  typedValueElement.value = '';
  // set focus
  typedValueElement.focus();
  // set the event handler

  // Start the timer
  startTime = new Date().getTime();
});
```

चला कोडचे विश्लेषण करूया!

- शब्द ट्रॅकिंग सेट करा
  - [Math.floor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) आणि [Math.random](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/random) वापरून आम्ही `quotes` अ‍ॅरेमधून एक कोट निवडतो
  - आम्ही `quote` ला `words` च्या अ‍ॅरेमध्ये रूपांतरित करतो जेणेकरून आम्ही खेळाडू सध्या टाइप करत असलेल्या शब्दाचा ट्रॅक ठेवू शकू
  - `wordIndex` 0 वर सेट केले जाते, कारण खेळाडू पहिल्या शब्दावर सुरू करेल
- UI सेट करा
  - `spanWords` च्या अ‍ॅरे तयार करा, ज्यामध्ये प्रत्येक शब्द `span` घटकात समाविष्ट आहे
    - यामुळे आम्हाला डिस्प्लेमध्ये शब्द हायलाइट करता येईल
  - अ‍ॅरेला `join` करून एक स्ट्रिंग तयार करा जी आम्ही `quoteElement` वर `innerHTML` अपडेट करण्यासाठी वापरू शकतो
    - हे खेळाडूला कोट प्रदर्शित करेल
  - पहिल्या `span` घटकाचा `className` `highlight` वर सेट करा जेणेकरून तो पिवळा हायलाइट होईल
  - `messageElement` साफ करा आणि `innerText` `''` वर सेट करा
- टेक्स्टबॉक्स सेट करा
  - सध्याचा `value` `typedValueElement` वरून साफ करा
  - `typedValueElement` वर `focus` सेट करा
- टाइमर सुरू करा, `getTime` कॉल करून

### टाइपिंग लॉजिक जोडा

खेळाडू टाइप करत असताना, एक `input` इव्हेंट उभा राहील. हा इव्हेंट लिसनर खेळाडू योग्य शब्द टाइप करत आहे याची खात्री करेल आणि गेमची सध्याची स्थिती हाताळेल. **script.js** मध्ये परत जा आणि खालील कोड शेवटी जोडा. आम्ही नंतर त्याचे विश्लेषण करू.

```javascript
// at the end of script.js
typedValueElement.addEventListener('input', () => {
  // Get the current word
  const currentWord = words[wordIndex];
  // get the current value
  const typedValue = typedValueElement.value;

  if (typedValue === currentWord && wordIndex === words.length - 1) {
    // end of sentence
    // Display success
    const elapsedTime = new Date().getTime() - startTime;
    const message = `CONGRATULATIONS! You finished in ${elapsedTime / 1000} seconds.`;
    messageElement.innerText = message;
  } else if (typedValue.endsWith(' ') && typedValue.trim() === currentWord) {
    // end of word
    // clear the typedValueElement for the new word
    typedValueElement.value = '';
    // move to the next word
    wordIndex++;
    // reset the class name for all elements in quote
    for (const wordElement of quoteElement.childNodes) {
      wordElement.className = '';
    }
    // highlight the new word
    quoteElement.childNodes[wordIndex].className = 'highlight';
  } else if (currentWord.startsWith(typedValue)) {
    // currently correct
    // highlight the next word
    typedValueElement.className = '';
  } else {
    // error state
    typedValueElement.className = 'error';
  }
});
```

चला कोडचे विश्लेषण करूया! आम्ही सध्याचा शब्द आणि खेळाडूने आतापर्यंत टाइप केलेले मूल्य पकडून सुरुवात करतो. नंतर आमच्याकडे वॉटरफॉल लॉजिक आहे, जिथे आम्ही तपासतो की कोट पूर्ण आहे, शब्द पूर्ण आहे, शब्द योग्य आहे किंवा (शेवटी), काही त्रुटी आहे.

- कोट पूर्ण आहे, `typedValue` `currentWord` च्या समान आहे आणि `wordIndex` `words` च्या `length` पेक्षा एक कमी आहे
  - `startTime` मधून सध्याचा वेळ वजा करून `elapsedTime` काढा
  - मिलिसेकंदांपासून सेकंदांमध्ये रूपांतर करण्यासाठी `elapsedTime` ला 1,000 ने भागा
  - यशाचा संदेश प्रदर्शित करा
- शब्द पूर्ण आहे, `typedValue` स्पेसने संपतो (शब्दाचा शेवट) आणि `typedValue` `currentWord` च्या समान आहे
  - पुढील शब्द टाइप करण्यासाठी `typedElement` वर `value` `''` सेट करा
  - पुढील शब्दावर जाण्यासाठी `wordIndex` वाढवा
  - `quoteElement` च्या सर्व `childNodes` वर लूप करा आणि `className` `''` वर सेट करा जेणेकरून ते डिफॉल्ट डिस्प्लेमध्ये परत जाईल
  - सध्याच्या शब्दाचा `className` `highlight` वर सेट करा जेणेकरून तो टाइप करण्यासाठी पुढील शब्द म्हणून फ्लॅग केला जाईल
- शब्द सध्या योग्य प्रकारे टाइप केला आहे (पण पूर्ण नाही), `currentWord` `typedValue` ने सुरू होतो
  - `typedValueElement` डिफॉल्ट म्हणून प्रदर्शित केला आहे याची खात्री करा, `className` साफ करून
- जर आपण येथे पोहोचलो, तर आपल्याला त्रुटी आहे
  - `typedValueElement` वर `className` `error` वर सेट करा

## आपले अॅप्लिकेशन तपासा

आपण शेवटपर्यंत पोहो
**वर्णन:** टायपिंग गेममध्ये सुधारणा करून एक अशा पातळी प्रणालीची अंमलबजावणी करा जी खेळाडूच्या कामगिरीनुसार गेम समायोजित करते. ही आव्हाने तुम्हाला प्रगत इव्हेंट हाताळणी, डेटा विश्लेषण आणि डायनॅमिक UI अद्यतनांचा सराव करण्यास मदत करेल.

**सूचना:** टायपिंग गेमसाठी एक पातळी समायोजन प्रणाली तयार करा जी:
1. खेळाडूचा टायपिंग वेग (शब्द प्रति मिनिट) आणि अचूकता टक्केवारी ट्रॅक करते
2. आपोआप तीन पातळींमध्ये समायोजित होते: सोपी (साधे कोट्स), मध्यम (सध्याचे कोट्स), कठीण (अधिक क्लिष्ट कोट्स, विरामचिन्हांसह)
3. सध्याची पातळी आणि खेळाडूची आकडेवारी UI वर दर्शवते
4. एक स्ट्रीक काउंटर अंमलात आणते जो सलग 3 चांगल्या कामगिरीनंतर पातळी वाढवतो
5. पातळी बदल सूचित करण्यासाठी व्हिज्युअल फीडबॅक (रंग, अ‍ॅनिमेशन) जोडते

या वैशिष्ट्याची अंमलबजावणी करण्यासाठी आवश्यक HTML घटक, CSS शैली आणि JavaScript फंक्शन्स जोडा. योग्य एरर हाताळणी समाविष्ट करा आणि गेम सुलभ राहील याची खात्री करा, योग्य ARIA लेबल्ससह.

## 🚀 आव्हान

अधिक कार्यक्षमता जोडा

- पूर्ण झाल्यावर `input` इव्हेंट लिसनर अक्षम करा आणि बटण क्लिक केल्यावर पुन्हा सक्षम करा
- खेळाडू कोट पूर्ण केल्यावर टेक्स्टबॉक्स अक्षम करा
- यशाचा संदेश असलेला एक मोडल डायलॉग बॉक्स दर्शवा
- [localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) वापरून उच्च स्कोअर संग्रहित करा

## व्याख्यानानंतरचा क्विझ

[व्याख्यानानंतरचा क्विझ](https://ff-quizzes.netlify.app/web/quiz/22)

## पुनरावलोकन आणि स्व-अभ्यास

[वेब ब्राउझरद्वारे उपलब्ध असलेल्या सर्व इव्हेंट्स](https://developer.mozilla.org/docs/Web/Events) बद्दल वाचा आणि तुम्ही प्रत्येक इव्हेंट कोणत्या परिस्थितीत वापराल याचा विचार करा.

## असाइनमेंट

[नवीन कीबोर्ड गेम तयार करा](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपयास लक्षात ठेवा की स्वयंचलित भाषांतरे त्रुटी किंवा अचूकतेच्या अभावाने युक्त असू शकतात. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून उद्भवलेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार राहणार नाही.