<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "c125271e53e7d12e6eb73f772de74b8a",
  "translation_date": "2025-10-20T21:13:56+00:00",
  "source_file": "2-js-basics/4-arrays-loops/README.md",
  "language_code": "mr"
}
-->
# JavaScript मूलभूत गोष्टी: Arrays आणि Loops

![JavaScript Basics - Arrays](../../../../translated_images/webdev101-js-arrays.439d7528b8a294558d0e4302e448d193f8ad7495cc407539cc81f1afe904b470.mr.png)
> स्केच नोट [Tomomi Imura](https://twitter.com/girlie_mac) यांच्याकडून

## पूर्व-व्याख्यान प्रश्नमंजुषा
[पूर्व-व्याख्यान प्रश्नमंजुषा](https://ff-quizzes.netlify.app/web/quiz/13)

ही धडा JavaScript च्या मूलभूत गोष्टींचा आढावा घेते, जी वेबवर परस्परसंवाद प्रदान करणारी भाषा आहे. या धड्यात तुम्ही arrays आणि loops बद्दल शिकाल, जे डेटा हाताळण्यासाठी वापरले जातात.

[![Arrays](https://img.youtube.com/vi/1U4qTyq02Xw/0.jpg)](https://youtube.com/watch?v=1U4qTyq02Xw "Arrays")

[![Loops](https://img.youtube.com/vi/Eeh7pxtTZ3k/0.jpg)](https://www.youtube.com/watch?v=Eeh7pxtTZ3k "Loops")

> 🎥 वरील प्रतिमांवर क्लिक करा arrays आणि loops बद्दल व्हिडिओ पाहण्यासाठी.

> तुम्ही हा धडा [Microsoft Learn](https://docs.microsoft.com/learn/modules/web-development-101-arrays/?WT.mc_id=academic-77807-sagibbon) वर घेऊ शकता!

## Arrays

डेटा हाताळणे ही कोणत्याही भाषेसाठी सामान्य गोष्ट आहे, आणि डेटा संरचनात्मक स्वरूपात, जसे की arrays मध्ये आयोजित केल्यास हे कार्य खूप सोपे होते. Arrays मध्ये, डेटा यादीसारख्या संरचनेत संग्रहित केला जातो. Arrays चा एक मोठा फायदा म्हणजे तुम्ही एका array मध्ये वेगवेगळ्या प्रकारचा डेटा संग्रहित करू शकता.

✅ Arrays सर्वत्र आहेत! तुम्ही arrays चा वास्तविक जीवनातील उदाहरण विचार करू शकता का, जसे की सौर पॅनेल array?

Array साठी सिंटॅक्स म्हणजे चौकोनी कंसांची जोडी.

```javascript
let myArray = [];
```

हे रिक्त array आहे, परंतु arrays आधीच डेटा भरून घोषित केले जाऊ शकतात. Array मध्ये अनेक मूल्ये अल्पविरामाने वेगळी केली जातात.

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
```

Array मूल्यांना **index** नावाचे एक अद्वितीय मूल्य दिले जाते, जे array च्या सुरुवातीपासूनच्या अंतरावर आधारित असते. वरील उदाहरणात, "Chocolate" या स्ट्रिंग मूल्याचा index 0 आहे, आणि "Rocky Road" चा index 4 आहे. Index चा वापर करून चौकोनी कंसांसह array मूल्ये मिळवणे, बदलणे किंवा घालणे शक्य आहे.

✅ तुम्हाला आश्चर्य वाटते का की arrays 0 index पासून सुरू होतात? काही प्रोग्रामिंग भाषांमध्ये indexes 1 पासून सुरू होतात. यामागे एक मनोरंजक इतिहास आहे, जो तुम्ही [Wikipedia वर वाचू शकता](https://en.wikipedia.org/wiki/Zero-based_numbering).

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
iceCreamFlavors[2]; //"Vanilla"
```

तुम्ही index चा उपयोग करून मूल्य बदलू शकता, असे:

```javascript
iceCreamFlavors[4] = "Butter Pecan"; //Changed "Rocky Road" to "Butter Pecan"
```

आणि तुम्ही दिलेल्या index वर नवीन मूल्य घालू शकता असे:

```javascript
iceCreamFlavors[5] = "Cookie Dough"; //Added "Cookie Dough"
```

✅ Array मध्ये मूल्ये जोडण्यासाठी अधिक सामान्य पद्धत म्हणजे array.push() सारखे array ऑपरेटर वापरणे.

Array मध्ये किती आयटम आहेत हे शोधण्यासाठी `length` प्रॉपर्टी वापरा.

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];
iceCreamFlavors.length; //5
```

✅ स्वतः प्रयत्न करा! तुमच्या ब्राउझरच्या कन्सोलमध्ये स्वतः तयार केलेल्या array वर प्रक्रिया करा आणि त्यात बदल करा.

## Loops

Loops आपल्याला पुनरावृत्ती किंवा **iterative** कार्ये करण्यास अनुमती देतात, आणि बरेच वेळ आणि कोड वाचवतात. प्रत्येक पुनरावृत्तीमध्ये त्यांचे व्हेरिएबल्स, मूल्ये आणि अटी वेगळ्या असू शकतात. JavaScript मध्ये loops चे वेगवेगळे प्रकार आहेत, आणि त्यामध्ये लहान फरक असले तरी ते मूलतः एकच काम करतात: डेटा वर loop करणे.

### For Loop

`for` loop ला पुनरावृत्ती करण्यासाठी 3 भागांची आवश्यकता असते:
- `counter` एक व्हेरिएबल जो सामान्यतः पुनरावृत्तीची संख्या मोजण्यासाठी एका संख्येसह प्रारंभ केला जातो
- `condition` तुलना ऑपरेटर वापरून अभिव्यक्ती जी `false` झाल्यावर loop थांबवते
- `iteration-expression` प्रत्येक पुनरावृत्तीच्या शेवटी चालते, सामान्यतः counter मूल्य बदलण्यासाठी वापरले जाते
  
```javascript
// Counting up to 10
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

✅ हे कोड ब्राउझर कन्सोलमध्ये चालवा. तुम्ही counter, condition, किंवा iteration expression मध्ये छोटे बदल केल्यास काय होते? तुम्ही ते उलट चालवू शकता का, countdown तयार करत?

### While loop

`for` loop च्या सिंटॅक्सच्या विपरीत, `while` loops फक्त एक condition आवश्यक असते जी condition `false` झाल्यावर loop थांबवते. Loops मधील conditions सामान्यतः counters सारख्या इतर मूल्यांवर अवलंबून असतात, आणि loop दरम्यान व्यवस्थापित करणे आवश्यक असते. Counters साठी प्रारंभिक मूल्ये loop च्या बाहेर तयार करावी लागतात, आणि condition पूर्ण करण्यासाठी कोणत्याही अभिव्यक्ती, counter बदलणे यासह loop च्या आत व्यवस्थापित करावी लागते.

```javascript
//Counting up to 10
let i = 0;
while (i < 10) {
 console.log(i);
 i++;
}
```

✅ तुम्ही for loop ऐवजी while loop का निवडाल? StackOverflow वर 17K दर्शकांना याच प्रश्नाचे उत्तर हवे होते, आणि काही मते [तुमच्यासाठी मनोरंजक असू शकतात](https://stackoverflow.com/questions/39969145/while-loops-vs-for-loops-in-javascript).

## Loops आणि Arrays

Arrays सहसा loops सह वापरले जातात कारण बहुतेक conditions ला loop थांबवण्यासाठी array ची लांबी आवश्यक असते, आणि index देखील counter मूल्य असू शकतो.

```javascript
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Rocky Road"];

for (let i = 0; i < iceCreamFlavors.length; i++) {
  console.log(iceCreamFlavors[i]);
} //Ends when all flavors are printed
```

✅ तुमच्या ब्राउझरच्या कन्सोलमध्ये स्वतः तयार केलेल्या array वर loop करण्याचा प्रयोग करा.

---

## GitHub Copilot Agent Challenge 🚀

Agent mode वापरून खालील आव्हान पूर्ण करा:

**वर्णन:** डेटा प्रक्रिया करणारे फंक्शन तयार करा जे arrays आणि loops एकत्र करून dataset चे विश्लेषण करते.

**प्रॉम्प्ट:** `analyzeGrades` नावाचे फंक्शन तयार करा जे student grade objects च्या array (प्रत्येकात name आणि score प्रॉपर्टीज असतात) घेते आणि उच्चतम score, न्यूनतम score, सरासरी score, आणि पास झालेल्या विद्यार्थ्यांची संख्या (score >= 70) यासह आकडेवारी परत करते. डेटा प्रक्रिया करण्यासाठी loops वापरा.

## 🚀 Challenge

Arrays वर loop करण्याचे for आणि while loops व्यतिरिक्त इतर मार्ग आहेत. [forEach](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach), [for-of](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/for...of), आणि [map](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array/map) यांचा समावेश आहे. तुमचा array loop या तंत्रांपैकी एक वापरून पुन्हा लिहा.

## व्याख्यानानंतरची प्रश्नमंजुषा
[व्याख्यानानंतरची प्रश्नमंजुषा](https://ff-quizzes.netlify.app/web/quiz/14)

## पुनरावलोकन आणि स्व-अभ्यास

JavaScript मधील arrays मध्ये अनेक पद्धती असतात, ज्या डेटा हाताळण्यासाठी अत्यंत उपयुक्त असतात. [या पद्धतींबद्दल वाचा](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array) आणि तुमच्या स्वतःच्या array वर काही पद्धती वापरून पहा (जसे की push, pop, slice आणि splice).

## असाइनमेंट

[Loop an Array](assignment.md)

---

**अस्वीकरण**:  
हा दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित करण्यात आला आहे. आम्ही अचूकतेसाठी प्रयत्नशील असलो तरी, कृपयास लक्षात ठेवा की स्वयंचलित भाषांतरे त्रुटी किंवा अचूकतेच्या अभावाने युक्त असू शकतात. मूळ भाषेतील दस्तऐवज हा अधिकृत स्रोत मानला जावा. महत्त्वाच्या माहितीसाठी, व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराचा वापर करून उद्भवलेल्या कोणत्याही गैरसमज किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार राहणार नाही.