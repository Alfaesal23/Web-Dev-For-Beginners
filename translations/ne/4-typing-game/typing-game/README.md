<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "6b04a23d9d5e9edb252c909af4fb5f31",
  "translation_date": "2025-10-20T21:43:14+00:00",
  "source_file": "4-typing-game/typing-game/README.md",
  "language_code": "ne"
}
-->
# इभेन्ट प्रयोग गरेर खेल बनाउने

## प्रि-लेक्चर क्विज

[प्रि-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/21)

## इभेन्ट ड्राइभन प्रोग्रामिङ

जब ब्राउजरमा आधारित एप्लिकेसन बनाइन्छ, हामीले प्रयोगकर्तालाई ग्राफिकल यूजर इन्टरफेस (GUI) प्रदान गर्छौं जसको माध्यमबाट उनीहरूले हाम्रो बनाएको कुरासँग अन्तरक्रिया गर्न सक्छन्। ब्राउजरसँग अन्तरक्रिया गर्ने सबैभन्दा सामान्य तरिका विभिन्न तत्वहरूमा क्लिक गर्ने र टाइप गर्ने हो। तर, चुनौती यो छ कि हामीलाई थाहा छैन उनीहरूले यी कार्यहरू कहिले गर्नेछन्!

[इभेन्ट ड्राइभन प्रोग्रामिङ](https://en.wikipedia.org/wiki/Event-driven_programming) भनेको GUI बनाउन आवश्यक पर्ने प्रोग्रामिङको प्रकार हो। यदि हामी यस वाक्यांशलाई अलिकति तोड्छौं भने, हामी देख्छौं कि यहाँको मुख्य शब्द **इभेन्ट** हो। [इभेन्ट](https://www.merriam-webster.com/dictionary/event), Merriam-Webster अनुसार, "केही कुरा जो हुन्छ" भनेर परिभाषित गरिएको छ। यो हाम्रो स्थितिलाई पूर्ण रूपमा वर्णन गर्दछ। हामीलाई थाहा छ कि केही हुनेवाला छ जसको लागि हामीले प्रतिक्रिया स्वरूप केही कोड कार्यान्वयन गर्न चाहन्छौं, तर हामीलाई थाहा छैन यो कहिले हुनेछ।

हामीले कार्यान्वयन गर्न चाहेको कोडको खण्डलाई चिन्हित गर्ने तरिका भनेको फङ्सन बनाउनु हो। जब हामी [प्रोसीड्युरल प्रोग्रामिङ](https://en.wikipedia.org/wiki/Procedural_programming) को बारेमा सोच्छौं, फङ्सनहरू निश्चित क्रममा बोलाइन्छ। इभेन्ट ड्राइभन प्रोग्रामिङमा पनि यही कुरा सत्य हुनेछ। फरक भनेको फङ्सनहरू **कसरी** बोलाइन्छ भन्ने हो।

इभेन्टहरू (बटन क्लिक गर्ने, टाइप गर्ने, आदि) ह्यान्डल गर्नका लागि हामी **इभेन्ट लिस्नरहरू** दर्ता गर्छौं। इभेन्ट लिस्नर भनेको एउटा फङ्सन हो जसले इभेन्ट हुने प्रतीक्षा गर्छ र प्रतिक्रिया स्वरूप कार्यान्वयन गर्छ। इभेन्ट लिस्नरहरूले UI अपडेट गर्न, सर्भरमा कल गर्न, वा प्रयोगकर्ताको कार्यको प्रतिक्रिया स्वरूप गर्नुपर्ने अन्य कार्यहरू गर्न सक्छ। हामी [addEventListener](https://developer.mozilla.org/docs/Web/API/EventTarget/addEventListener) प्रयोग गरेर इभेन्ट लिस्नर थप्छौं र कार्यान्वयन गर्न फङ्सन प्रदान गर्छौं।

> **NOTE:** इभेन्ट लिस्नरहरू बनाउने धेरै तरिकाहरू छन्। तपाईंले अनाम फङ्सनहरू प्रयोग गर्न सक्नुहुन्छ, वा नामित फङ्सनहरू बनाउनुहोस्। तपाईंले `click` प्रोपर्टी सेट गर्ने वा `addEventListener` प्रयोग गर्ने जस्ता विभिन्न सर्टकटहरू प्रयोग गर्न सक्नुहुन्छ। हाम्रो अभ्यासमा हामी `addEventListener` र अनाम फङ्सनहरूमा ध्यान केन्द्रित गर्नेछौं, किनकि यो वेब डेभलपरहरूले सबैभन्दा सामान्य रूपमा प्रयोग गर्ने प्रविधि हो। यो सबैभन्दा लचिलो पनि हो, किनकि `addEventListener` सबै इभेन्टहरूको लागि काम गर्छ, र इभेन्टको नामलाई एक प्यारामिटरको रूपमा प्रदान गर्न सकिन्छ।

### सामान्य इभेन्टहरू

एप्लिकेसन बनाउँदा तपाईंले सुन्न सक्ने [दर्जनौं इभेन्टहरू](https://developer.mozilla.org/docs/Web/Events) उपलब्ध छन्। आधारभूत रूपमा प्रयोगकर्ताले पृष्ठमा गर्ने कुनै पनि कार्यले इभेन्ट उठाउँछ, जसले तपाईंलाई उनीहरूले चाहेको अनुभव सुनिश्चित गर्न धेरै शक्ति दिन्छ। भाग्यवश, तपाईंलाई सामान्यतया केही इभेन्टहरू मात्र आवश्यक पर्छ। यहाँ केही सामान्य इभेन्टहरू छन् (जसमा दुई हामीले खेल बनाउँदा प्रयोग गर्नेछौं):

- [click](https://developer.mozilla.org/docs/Web/API/Element/click_event): प्रयोगकर्ताले केही क्लिक गरे, सामान्यतया बटन वा हाइपरलिंक
- [contextmenu](https://developer.mozilla.org/docs/Web/API/Element/contextmenu_event): प्रयोगकर्ताले दायाँ माउस बटन क्लिक गरे
- [select](https://developer.mozilla.org/docs/Web/API/Element/select_event): प्रयोगकर्ताले केही पाठलाई हाइलाइट गरे
- [input](https://developer.mozilla.org/docs/Web/API/Element/input_event): प्रयोगकर्ताले केही पाठ इनपुट गरे

## खेल बनाउने

हामी JavaScript मा इभेन्टहरू कसरी काम गर्छन् भनेर अन्वेषण गर्न खेल बनाउनेछौं। हाम्रो खेलले खेलाडीको टाइपिङ कौशल परीक्षण गर्नेछ, जुन सबै डेभलपरहरूले अभ्यास गर्नुपर्ने सबैभन्दा कम मूल्याङ्कन गरिएको कौशल हो। खेलको सामान्य प्रवाह यस प्रकार हुनेछ:

- खेलाडीले स्टार्ट बटन क्लिक गर्छ र टाइप गर्नको लागि एउटा उद्धरण प्रस्तुत गरिन्छ
- खेलाडीले उद्धरणलाई सकेसम्म छिटो टाइप गर्छ
  - प्रत्येक शब्द पूरा भएपछि अर्को शब्द हाइलाइट हुन्छ
  - यदि खेलाडीले टाइपो गर्छ भने टेक्स्टबक्स रातो हुन्छ
  - जब खेलाडीले उद्धरण पूरा गर्छ, सफलताको सन्देश देखाइन्छ र समयको गणना गरिन्छ

आउनुहोस्, खेल बनाऔं र इभेन्टहरूको बारेमा सिकौं!

### फाइल संरचना

हामीलाई तीनवटा फाइलहरू चाहिन्छ: **index.html**, **script.js** र **style.css**। आउनुहोस्, ती सेटअप गरौं ताकि हाम्रो काम सजिलो होस्।

- कन्सोल वा टर्मिनल विन्डो खोल्नुहोस् र तलको कमाण्ड प्रयोग गरेर आफ्नो कामको लागि नयाँ फोल्डर बनाउनुहोस्:

```bash
# Linux or macOS
mkdir typing-game && cd typing-game

# Windows
md typing-game && cd typing-game
```

- Visual Studio Code खोल्नुहोस्

```bash
code .
```

- Visual Studio Code मा फोल्डरमा तीनवटा फाइलहरू थप्नुहोस्:
  - index.html
  - script.js
  - style.css

## यूजर इन्टरफेस बनाउनुहोस्

यदि हामी आवश्यकताहरू अन्वेषण गर्छौं भने, हामीलाई HTML पृष्ठमा केही तत्वहरू चाहिन्छ। यो एक प्रकारको रेसिपी जस्तै हो, जहाँ हामीलाई केही सामग्रीहरू चाहिन्छ:

- प्रयोगकर्ताले टाइप गर्न उद्धरण देखाउने ठाउँ
- सन्देशहरू देखाउने ठाउँ, जस्तै सफलताको सन्देश
- टाइप गर्न टेक्स्टबक्स
- स्टार्ट बटन

यी प्रत्येकलाई ID चाहिन्छ ताकि हामीले JavaScript मा तिनीहरूसँग काम गर्न सकौं। हामीले सिर्जना गर्न लागेको CSS र JavaScript फाइलहरूको सन्दर्भ पनि थप्नेछौं।

**index.html** नामको नयाँ फाइल बनाउनुहोस्। तलको HTML थप्नुहोस्:

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

### एप्लिकेसन सुरु गर्नुहोस्

सधैं राम्रो हुन्छ कि विकासलाई क्रमिक रूपमा अगाडि बढाएर हेर्नुहोस्। आउनुहोस्, हाम्रो एप्लिकेसन सुरु गरौं। Visual Studio Code को लागि [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer&WT.mc_id=academic-77807-sagibbon) नामक एक उत्कृष्ट एक्सटेन्सन छ जसले तपाईंको एप्लिकेसनलाई स्थानीय रूपमा होस्ट गर्नेछ र प्रत्येक पटक तपाईंले बचत गर्दा ब्राउजरलाई रिफ्रेस गर्नेछ।

- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer&WT.mc_id=academic-77807-sagibbon) इन्स्टल गर्नुहोस्। लिंकमा क्लिक गरेर **Install** क्लिक गर्नुहोस्।
  - ब्राउजरले Visual Studio Code खोल्न अनुरोध गर्नेछ, त्यसपछि Visual Studio Code ले इन्स्टलेसन गर्न अनुरोध गर्नेछ।
  - यदि अनुरोध गरियो भने Visual Studio Code पुनः सुरु गर्नुहोस्।
- इन्स्टलेसन पछि, Visual Studio Code मा Ctrl-Shift-P (वा Cmd-Shift-P) क्लिक गरेर कमाण्ड प्यालेट खोल्नुहोस्।
- **Live Server: Open with Live Server** टाइप गर्नुहोस्।
  - Live Server ले तपाईंको एप्लिकेसन होस्ट गर्न सुरु गर्नेछ।
- ब्राउजर खोल्नुहोस् र **https://localhost:5500** मा जानुहोस्।
- अब तपाईंले बनाएको पृष्ठ देख्न सक्नुहुन्छ!

आउनुहोस्, केही कार्यक्षमता थपौं।

## CSS थप्नुहोस्

हाम्रो HTML बनाइसकेपछि, अब हामी कोर स्टाइलिङको लागि CSS थप्नेछौं। हामीले खेलाडीले टाइप गर्नुपर्ने शब्दलाई हाइलाइट गर्न र उनीहरूले गलत टाइप गरेमा टेक्स्टबक्सलाई रंगीन बनाउन आवश्यक छ। हामी यो दुईवटा क्लासहरूको प्रयोग गरेर गर्नेछौं।

**style.css** नामको नयाँ फाइल बनाउनुहोस् र तलको सिन्ट्याक्स थप्नुहोस्।

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

✅ CSS को कुरा गर्दा तपाईं आफ्नो पृष्ठलाई जस्तो चाहनुहुन्छ त्यस्तै लेआउट गर्न सक्नुहुन्छ। पृष्ठलाई अझ आकर्षक बनाउन केही समय लिनुहोस्:

- फरक फन्ट छान्नुहोस्
- हेडरहरू रंगीन बनाउनुहोस्
- वस्तुहरूलाई पुनः आकार दिनुहोस्

## JavaScript

हाम्रो UI बनाइसकेपछि, अब हामी JavaScript मा ध्यान केन्द्रित गर्नेछौं जसले तर्क प्रदान गर्नेछ। हामी यसलाई केही चरणहरूमा तोड्नेछौं:

- [कन्स्ट्यान्टहरू बनाउनुहोस्](../../../../4-typing-game/typing-game)
- [खेल सुरु गर्न इभेन्ट लिस्नर थप्नुहोस्](../../../../4-typing-game/typing-game)
- [टाइपिङको लागि इभेन्ट लिस्नर थप्नुहोस्](../../../../4-typing-game/typing-game)

तर पहिले, **script.js** नामको नयाँ फाइल बनाउनुहोस्।

### कन्स्ट्यान्टहरू थप्नुहोस्

हामीलाई प्रोग्रामिङलाई सजिलो बनाउन केही वस्तुहरू चाहिन्छ। फेरि, रेसिपी जस्तै, यहाँ हामीलाई चाहिने वस्तुहरू छन्:

- उद्धरणहरूको सूची भएको एरे
- हालको उद्धरणका सबै शब्दहरू भण्डारण गर्न खाली एरे
- खेलाडीले हाल टाइप गरिरहेको शब्दको इन्डेक्स भण्डारण गर्ने ठाउँ
- खेलाडीले स्टार्ट क्लिक गरेको समय

हामीलाई UI तत्वहरूको सन्दर्भ पनि चाहिन्छ:

- टेक्स्टबक्स (**typed-value**)
- उद्धरण प्रदर्शन (**quote**)
- सन्देश (**message**)

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

✅ आफ्नो खेलमा थप उद्धरणहरू थप्नुहोस्

> **NOTE:** हामी `document.getElementById` प्रयोग गरेर कोडमा तत्वहरू जबसुकै प्राप्त गर्न सक्छौं। किनकि हामीले यी तत्वहरूलाई नियमित रूपमा सन्दर्भ गर्नेछौं, हामी स्ट्रिङ लिटरलहरूमा टाइपोबाट बच्न कन्स्ट्यान्टहरू प्रयोग गर्नेछौं। [Vue.js](https://vuejs.org/) वा [React](https://reactjs.org/) जस्ता फ्रेमवर्कहरूले तपाईंलाई आफ्नो कोडलाई केन्द्रित गर्न मद्दत गर्न सक्छ।

`const`, `let` र `var` प्रयोग गर्ने बारेमा भिडियो हेर्न एक मिनेट लिनुहोस्।

[![भेरिएबलहरूको प्रकार](https://img.youtube.com/vi/JNIXfGiDWM8/0.jpg)](https://youtube.com/watch?v=JNIXfGiDWM8 "भेरिएबलहरूको प्रकार")

> 🎥 माथिको छवि क्लिक गरेर भेरिएबलहरूको बारेमा भिडियो हेर्नुहोस्।

### सुरु गर्ने तर्क थप्नुहोस्

खेल सुरु गर्न, खेलाडीले स्टार्ट क्लिक गर्नेछ। अवश्य पनि, हामीलाई थाहा छैन उनीहरूले कहिले स्टार्ट क्लिक गर्नेछन्। यही ठाउँमा [इभेन्ट लिस्नर](https://developer.mozilla.org/docs/Web/API/EventTarget/addEventListener) काममा आउँछ। इभेन्ट लिस्नरले हामीलाई केही हुने प्रतीक्षा गर्न र प्रतिक्रिया स्वरूप कोड कार्यान्वयन गर्न अनुमति दिन्छ। हाम्रो केसमा, हामीले स्टार्ट क्लिक गर्दा कोड कार्यान्वयन गर्न चाहन्छौं।

जब प्रयोगकर्ताले **स्टार्ट** क्लिक गर्छ, हामीले उद्धरण चयन गर्न, यूजर इन्टरफेस सेटअप गर्न, र हालको शब्द र समयको ट्र्याकिङ सेटअप गर्न आवश्यक छ। तलको JavaScript तपाईंले थप्नुपर्नेछ; हामी स्क्रिप्ट ब्लक पछि यसलाई छलफल गर्छौं।

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

आउनुहोस्, कोडलाई तोडेर बुझौं!

- शब्द ट्र्याकिङ सेटअप गर्नुहोस्
  - [Math.floor](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) र [Math.random](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Math/random) प्रयोग गरेर हामीले `quotes` एरेबाट र्यान्डम उद्धरण चयन गर्छौं
  - हामी `quote` लाई `words` को एरेमा रूपान्तरण गर्छौं ताकि खेलाडीले हाल टाइप गरिरहेको शब्दलाई ट्र्याक गर्न सकियोस्
  - `wordIndex` लाई 0 मा सेट गरिन्छ, किनकि खेलाडी पहिलो शब्दबाट सुरु गर्नेछ
- UI सेटअप गर्नुहोस्
  - `spanWords` को एरे बनाउनुहोस्, जसमा प्रत्येक शब्द `span` तत्वभित्र हुन्छ
    - यसले प्रदर्शनमा शब्दलाई हाइलाइट गर्न अनुमति दिनेछ
  - `join` एरेलाई `quoteElement` को `innerHTML` अपडेट गर्न प्रयोग गरिन्छ
    - यसले खेलाडीलाई उद्धरण देखाउनेछ
  - पहिलो `span` तत्वको `className` लाई `highlight` मा सेट गरेर यसलाई पहेँलो हाइलाइट गरिन्छ
  - `messageElement` लाई सफा गर्न `innerText` लाई `''` मा सेट गर्नुहोस्
- टेक्स्टबक्स सेटअप गर्नुहोस्
  - हालको `value` लाई `typedValueElement` मा सफा गर्नुहोस्
  - `typedValueElement` मा `focus` सेट गर्नुहोस्
- टाइमर सुरु गर्न `getTime` कल गर्नुहोस्

### टाइपिङ तर्क थप्नुहोस्

जब खेलाडीले टाइप गर्छ, `input` इभेन्ट उठ्छ। यो इभेन्ट लिस्नरले खेलाडीले शब्द सही टाइप गरिरहेको छ कि छैन भनेर जाँच गर्नेछ, र खेलको हालको स्थिति ह्यान्डल गर्नेछ। **script.js** मा फर्केर, तलको कोड अन्त्यमा थप्नुहोस्। हामी यसलाई पछि तोडेर बुझ्नेछौं।

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

आउनुहोस्, कोडलाई तोडेर बुझौं! हामीले हालको शब्द र खेलाडीले अहिलेसम्म टाइप गरेको मान प्राप्त गर्छौं। त्यसपछि हामीले वॉटरफॉल तर्क प्रयोग गर्छौं, जहाँ हामी उद्धरण पूरा भएको छ कि छैन, शब्द पूरा भएको छ कि छैन, शब्द सही छ कि छैन, वा (अन्ततः), कुनै त्रुटि छ कि छैन भनेर जाँच गर्छौं।

- उद्धरण पूरा भएको छ, `typedValue` `currentWord` बराबर छ, र `wordIndex` `words` को `length` भन्दा एक कम बराबर छ
  - `startTime` बाट हालको समय घटाएर `elapsedTime` गणना गर्नुहोस्
  - `elapsedTime` लाई 1,000 बाट भाग गरेर मिलिसेकेन्डलाई सेकेन्डमा रूपान्तरण गर्नुहोस्
  - सफलताको सन्देश देखाउनुहोस्
- शब्द पूरा भएको छ, `typedValue` स्पेसमा समाप्त भएको छ (शब्दको अन्त्य) र `typedValue` `currentWord` बराबर छ
  - `typedElement` मा `value` लाई `''` मा सेट गर्नुहोस् ताकि अर्को शब्द टाइप गर्न सकियोस्
  - `wordIndex` बढाएर अर्को शब्दमा जानुहोस्
  - `quoteElement` का सबै `childNodes` मा लूप गरेर `className` लाई `''` मा सेट गर्नुहोस् ताकि डिफल्ट प्रदर्शनमा फर्कियोस्
  - हालको शब्दको `className` लाई `highlight` मा सेट गर्नुहोस् ताकि यो टाइप गर्नुपर्ने अर्को शब्दको रूपमा चिन्हित होस्
- शब्द हाल सही टाइप गरिएको छ (तर पूरा भएको छैन), `currentWord` `typedValue` बाट सुरु भएको छ
  - `typedValueElement` लाई डिफल्टमा प्रदर्शन गर्न सुनिश्चित गर्नुहोस् र `className` सफा गर्नुहोस्
- यदि हामी यहाँसम्म आइपुग्यौं भने, त्रुटि छ
  - `typedValueElement` मा `className` लाई `error` मा सेट गर्नुहोस्

## आफ्नो एप्लिकेसन परीक्षण गर्नुहोस्

तपाईं अन्त्यमा आइपुग्नुभएको छ! अन्तिम चरण भनेको हाम्रो एप्लिकेसन काम गर्छ कि छैन सुनिश्चित गर्नु हो। यसलाई प्रयास गर्नुहोस्! यदि त्रुटिहरू छन् भने चिन्ता नगर्नुहोस्; **सबै डेभलपरहरू**सँग त्रुटिहरू हुन्छ। सन्देशहरू जाँच गर्नुहोस् र आवश्यक परे डिबग गर्नुहोस्।

**स्टार्ट** क्लिक गर्नुहोस्, र टाइप गर्न सुरु गर्नुहोस्! यो पहिले देखिएको एनिमेसन जस्तै देखिनु पर्छ।

![खेलको कार्यमा एनिमेसन](../../../../4-typing-game/images/demo.gif)

---

## GitHub Copilot Agent Challenge 🎮

Agent मोड प्रयोग गरेर तलको चुनौती पूरा गर्नुहोस्:
**वर्णन:** खेलाडीको प्रदर्शनको आधारमा खेल समायोजन गर्ने कठिनाई प्रणाली कार्यान्वयन गरेर टाइपिङ खेललाई विस्तार गर्नुहोस्। यो चुनौतीले तपाईंलाई उन्नत इभेन्ट ह्यान्डलिङ, डाटा विश्लेषण, र गतिशील UI अपडेट अभ्यास गर्न मद्दत गर्नेछ।

**प्रेरणा:** टाइपिङ खेलको लागि कठिनाई समायोजन प्रणाली बनाउनुहोस् जसले:
1. खेलाडीको टाइपिङ गति (शब्द प्रति मिनेट) र शुद्धता प्रतिशत ट्र्याक गर्छ।
2. तीन कठिनाई स्तरमा स्वतः समायोजन गर्छ: सजिलो (साधारण उद्धरणहरू), मध्यम (वर्तमान उद्धरणहरू), कठिन (जटिल उद्धरणहरू, विराम चिह्नसहित)
3. UI मा हालको कठिनाई स्तर र खेलाडीको तथ्यांक देखाउँछ।
4. लगातार ३ राम्रो प्रदर्शनपछि कठिनाई बढाउने स्ट्रीक काउन्टर कार्यान्वयन गर्छ।
5. कठिनाई परिवर्तन संकेत गर्न दृश्य प्रतिक्रिया (रंगहरू, एनिमेसनहरू) थप्छ।

यो सुविधा कार्यान्वयन गर्न आवश्यक HTML तत्वहरू, CSS शैलीहरू, र JavaScript कार्यहरू थप्नुहोस्। उचित त्रुटि ह्यान्डलिङ समावेश गर्नुहोस् र खेललाई उपयुक्त ARIA लेबलहरूसहित पहुँचयोग्य बनाउनुहोस्।

## 🚀 चुनौती

थप कार्यक्षमता थप्नुहोस्

- `input` इभेन्ट लिस्नर पूरा भएपछि निष्क्रिय गर्नुहोस्, र बटन क्लिक गर्दा पुन: सक्रिय गर्नुहोस्।
- खेलाडीले उद्धरण पूरा गरेपछि टेक्स्टबक्स निष्क्रिय गर्नुहोस्।
- सफलताको सन्देशसहितको मोडल संवाद बक्स देखाउनुहोस्।
- [localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) प्रयोग गरेर उच्च स्कोरहरू भण्डारण गर्नुहोस्।

## पोस्ट-व्याख्यान क्विज

[पोस्ट-व्याख्यान क्विज](https://ff-quizzes.netlify.app/web/quiz/22)

## समीक्षा र आत्म अध्ययन

[वेब ब्राउजर मार्फत उपलब्ध सबै इभेन्टहरू](https://developer.mozilla.org/docs/Web/Events) को बारेमा पढ्नुहोस्, र तपाईंले प्रत्येकलाई कुन परिस्थितिमा प्रयोग गर्नुहुन्छ भनेर विचार गर्नुहोस्।

## असाइनमेन्ट

[नयाँ किबोर्ड खेल बनाउनुहोस्](assignment.md)

---

**अस्वीकरण**:  
यो दस्तावेज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको छ। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादमा त्रुटिहरू वा अशुद्धताहरू हुन सक्छ। यसको मूल भाषामा रहेको मूल दस्तावेजलाई आधिकारिक स्रोत मानिनुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न हुने कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुने छैनौं।