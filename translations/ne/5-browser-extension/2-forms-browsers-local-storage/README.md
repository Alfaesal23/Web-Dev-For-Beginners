<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7e164d318e19925330cfcaeea954e7b5",
  "translation_date": "2025-10-20T21:46:23+00:00",
  "source_file": "5-browser-extension/2-forms-browsers-local-storage/README.md",
  "language_code": "ne"
}
-->
# ब्राउजर एक्सटेन्सन प्रोजेक्ट भाग २: API कल गर्नुहोस्, लोकल स्टोरेज प्रयोग गर्नुहोस्

## प्रि-लेक्चर क्विज

[प्रि-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/25)

### परिचय

यस पाठमा, तपाईं आफ्नो ब्राउजर एक्सटेन्सनको फारम सबमिट गरेर API कल गर्नुहुनेछ र परिणामहरू ब्राउजर एक्सटेन्सनमा देखाउनुहुनेछ। साथै, तपाईं आफ्नो ब्राउजरको लोकल स्टोरेजमा डाटा भविष्यमा प्रयोगको लागि कसरी भण्डारण गर्न सकिन्छ भन्ने कुरा सिक्नुहुनेछ।

✅ कोड कहाँ राख्ने भनेर जान्नको लागि उपयुक्त फाइलहरूमा क्रमांकित खण्डहरू पालना गर्नुहोस्।

### एक्सटेन्सनमा परिवर्तन गर्नका लागि तत्वहरू सेट गर्नुहोस्:

यस समयसम्म तपाईंले आफ्नो ब्राउजर एक्सटेन्सनको फारम र परिणामहरूको `<div>` को लागि HTML बनाइसक्नुभएको छ। अबदेखि, तपाईंले `/src/index.js` फाइलमा काम गर्नुपर्नेछ र आफ्नो एक्सटेन्सनलाई क्रमशः निर्माण गर्नुपर्नेछ। आफ्नो प्रोजेक्ट सेट अप गर्ने र निर्माण प्रक्रियाको बारेमा जान्न [अघिल्लो पाठ](../1-about-browsers/README.md) हेर्नुहोस्।

`index.js` फाइलमा काम गर्दै, विभिन्न फिल्डहरूसँग सम्बन्धित मानहरू राख्नका लागि केही `const` भेरिएबलहरू सिर्जना गरेर सुरु गर्नुहोस्:

```JavaScript
// form fields
const form = document.querySelector('.form-data');
const region = document.querySelector('.region-name');
const apiKey = document.querySelector('.api-key');

// results
const errors = document.querySelector('.errors');
const loading = document.querySelector('.loading');
const results = document.querySelector('.result-container');
const usage = document.querySelector('.carbon-usage');
const fossilfuel = document.querySelector('.fossil-fuel');
const myregion = document.querySelector('.my-region');
const clearBtn = document.querySelector('.clear-btn');
```

यी सबै फिल्डहरू CSS क्लासद्वारा सन्दर्भित छन्, जुन तपाईंले अघिल्लो पाठमा HTML मा सेट गर्नुभएको थियो।

### लिसनरहरू थप्नुहोस्

अब, फारम र रिसेट बटनमा इभेन्ट लिसनरहरू थप्नुहोस् जसले फारम सबमिट गर्दा वा रिसेट बटन क्लिक गर्दा केही हुनेछ। साथै, फाइलको तल एपलाई इनिसियलाइज गर्ने कल थप्नुहोस्:

```JavaScript
form.addEventListener('submit', (e) => handleSubmit(e));
clearBtn.addEventListener('click', (e) => reset(e));
init();
```

✅ फारम सबमिट वा क्लिक इभेन्ट सुन्नको लागि प्रयोग गरिएको छोटो तरिका र इभेन्टलाई कसरी handleSubmit वा reset फङ्सनमा पास गरिएको छ भन्ने कुरा नोट गर्नुहोस्। के तपाईं यस छोटो तरिकाको लामो संस्करण लेख्न सक्नुहुन्छ? कुन तरिका तपाईंलाई मनपर्छ?

### init() फङ्सन र reset() फङ्सन निर्माण गर्नुहोस्:

अब तपाईं एक्सटेन्सनलाई इनिसियलाइज गर्ने फङ्सन निर्माण गर्न जाँदै हुनुहुन्छ, जसलाई init() भनिन्छ:

```JavaScript
function init() {
	//if anything is in localStorage, pick it up
	const storedApiKey = localStorage.getItem('apiKey');
	const storedRegion = localStorage.getItem('regionName');

	//set icon to be generic green
	//todo

	if (storedApiKey === null || storedRegion === null) {
		//if we don't have the keys, show the form
		form.style.display = 'block';
		results.style.display = 'none';
		loading.style.display = 'none';
		clearBtn.style.display = 'none';
		errors.textContent = '';
	} else {
        //if we have saved keys/regions in localStorage, show results when they load
        displayCarbonUsage(storedApiKey, storedRegion);
		results.style.display = 'none';
		form.style.display = 'none';
		clearBtn.style.display = 'block';
	}
};

function reset(e) {
	e.preventDefault();
	//clear local storage for region only
	localStorage.removeItem('regionName');
	init();
}

```

यस फङ्सनमा केही रोचक तर्कहरू छन्। यसलाई पढ्दा, के हुन्छ भन्ने देख्न सक्नुहुन्छ?

- दुई `const` सेट गरिन्छ ताकि प्रयोगकर्ताले लोकल स्टोरेजमा APIKey र क्षेत्र कोड भण्डारण गरेको छ कि छैन भनेर जाँच्न सकियोस्।
- यदि ती मध्ये कुनै पनि null छ भने, फारमलाई 'ब्लक' को रूपमा देखाउन यसको शैली परिवर्तन गर्नुहोस्।
- परिणामहरू, लोडिङ, र clearBtn लुकाउनुहोस् र कुनै पनि त्रुटि पाठलाई खाली स्ट्रिङमा सेट गर्नुहोस्।
- यदि कुनै key र क्षेत्र छ भने, एक प्रक्रिया सुरु गर्नुहोस्:
  - कार्बन प्रयोग डाटा प्राप्त गर्न API कल गर्नुहोस्।
  - परिणाम क्षेत्र लुकाउनुहोस्।
  - फारम लुकाउनुहोस्।
  - रिसेट बटन देखाउनुहोस्।

अगाडि बढ्नु अघि, ब्राउजरहरूमा उपलब्ध एक धेरै महत्त्वपूर्ण अवधारणाको बारेमा जान्न उपयोगी छ: [LocalStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)। LocalStorage ब्राउजरमा `key-value` जोडीको रूपमा स्ट्रिङहरू भण्डारण गर्न उपयोगी तरिका हो। यस प्रकारको वेब स्टोरेजलाई ब्राउजरमा डाटा व्यवस्थापन गर्नका लागि JavaScript द्वारा हेरफेर गर्न सकिन्छ। LocalStorage कहिल्यै समाप्त हुँदैन, जबकि SessionStorage, अर्को प्रकारको वेब स्टोरेज, ब्राउजर बन्द हुँदा सफा हुन्छ। स्टोरेजका विभिन्न प्रकारहरूको प्रयोगका लागि फाइदा र बेफाइदा छन्।

> नोट - तपाईंको ब्राउजर एक्सटेन्सनको आफ्नै लोकल स्टोरेज छ; मुख्य ब्राउजर विन्डो एक अलग उदाहरण हो र अलग व्यवहार गर्दछ।

तपाईं आफ्नो APIKey लाई स्ट्रिङ मान दिनुहुन्छ, उदाहरणका लागि, र तपाईंले Edge मा यो सेट गरिएको देख्न सक्नुहुन्छ जब तपाईं वेब पेजलाई "इन्स्पेक्ट" गर्नुहुन्छ (तपाईं ब्राउजरमा राइट-क्लिक गरेर इन्स्पेक्ट गर्न सक्नुहुन्छ) र स्टोरेज हेर्नको लागि Applications ट्याबमा जानुहोस्।

![लोकल स्टोरेज प्यान](../../../../translated_images/localstorage.472f8147b6a3f8d141d9551c95a2da610ac9a3c6a73d4a1c224081c98bae09d9.ne.png)

✅ ती परिस्थितिहरूको बारेमा सोच्नुहोस् जहाँ तपाईं लोकल स्टोरेजमा केही डाटा भण्डारण गर्न चाहनुहुन्न। सामान्यतया, लोकल स्टोरेजमा API Keys राख्नु खराब विचार हो! किन हो, तपाईं देख्न सक्नुहुन्छ? हाम्रो मामलामा, किनकि हाम्रो एप केवल सिकाइको लागि हो र एप स्टोरमा तैनात गरिने छैन, हामी यो विधि प्रयोग गर्नेछौं।

नोट गर्नुहोस् कि तपाईं लोकल स्टोरेजलाई Web API प्रयोग गरेर हेरफेर गर्नुहुन्छ, `getItem()`, `setItem()`, वा `removeItem()` प्रयोग गरेर। यो ब्राउजरहरूमा व्यापक रूपमा समर्थित छ।

`init()` मा कल गरिएको `displayCarbonUsage()` फङ्सन निर्माण गर्नु अघि, प्रारम्भिक फारम सबमिशनलाई ह्यान्डल गर्ने कार्यक्षमता निर्माण गरौं।

### फारम सबमिशन ह्यान्डल गर्नुहोस्

`handleSubmit` नामको फङ्सन सिर्जना गर्नुहोस् जसले इभेन्ट आर्गुमेन्ट `(e)` स्वीकार्छ। इभेन्टलाई फैलिनबाट रोक्नुहोस् (यस अवस्थामा, हामी ब्राउजरलाई रिफ्रेस गर्न रोक्न चाहन्छौं) र नयाँ फङ्सन `setUpUser` कल गर्नुहोस्, जसमा `apiKey.value` र `region.value` आर्गुमेन्टहरू पास गर्नुहोस्। यस तरिकाले, तपाईंले प्रारम्भिक फारमबाट ल्याइएका दुई मानहरू प्रयोग गर्नुहुन्छ जब उपयुक्त फिल्डहरू भरिएका छन्।

```JavaScript
function handleSubmit(e) {
	e.preventDefault();
	setUpUser(apiKey.value, region.value);
}
```

✅ आफ्नो स्मृति ताजा गर्नुहोस् - अघिल्लो पाठमा तपाईंले सेट अप गरेको HTML मा दुई इनपुट फिल्डहरू छन् जसको `values` तपाईंले फाइलको माथि सेट गरेको `const` मार्फत समात्न सकिन्छ, र ती दुवै `required` छन् ताकि ब्राउजरले प्रयोगकर्ताहरूलाई null मानहरू इनपुट गर्नबाट रोक्न सकियोस्।

### प्रयोगकर्ता सेट अप गर्नुहोस्

`setUpUser` फङ्सनमा अगाडि बढ्दै, यहाँ तपाईंले apiKey र regionName को लागि लोकल स्टोरेज मानहरू सेट गर्नुहुन्छ। नयाँ फङ्सन थप्नुहोस्:

```JavaScript
function setUpUser(apiKey, regionName) {
	localStorage.setItem('apiKey', apiKey);
	localStorage.setItem('regionName', regionName);
	loading.style.display = 'block';
	errors.textContent = '';
	clearBtn.style.display = 'block';
	//make initial call
	displayCarbonUsage(apiKey, regionName);
}
```

यो फङ्सनले API कल गर्दा देखाउनको लागि लोडिङ सन्देश सेट गर्दछ। यस बिन्दुमा, तपाईं यस ब्राउजर एक्सटेन्सनको सबैभन्दा महत्त्वपूर्ण फङ्सन सिर्जना गर्न आइपुग्नुभएको छ!

### कार्बन प्रयोग देखाउनुहोस्

अन्ततः, API क्वेरी गर्ने समय आएको छ!

अगाडि बढ्नु अघि, हामीले API को बारेमा छलफल गर्नुपर्छ। API, वा [Application Programming Interfaces](https://www.webopedia.com/TERM/A/API.html), वेब डेभलपरको टूलबक्सको एक महत्त्वपूर्ण तत्व हो। तिनीहरूले प्रोग्रामहरू एकअर्कासँग अन्तरक्रिया गर्न र इन्टरफेस गर्नका लागि मानक तरिकाहरू प्रदान गर्छन्। उदाहरणका लागि, यदि तपाईं डेटाबेस क्वेरी गर्न आवश्यक पर्ने वेब साइट निर्माण गर्दै हुनुहुन्छ भने, कसैले तपाईंलाई प्रयोग गर्नको लागि API सिर्जना गरेको हुन सक्छ। धेरै प्रकारका API हरू छन्, तर सबैभन्दा लोकप्रिय मध्ये एक हो [REST API](https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/)।

✅ 'REST' को अर्थ 'Representational State Transfer' हो र विभिन्न प्रकारका URL हरू प्रयोग गरेर डाटा फेच गर्न विशेषता हो। डेभलपरहरूलाई उपलब्ध विभिन्न प्रकारका API हरूको बारेमा थोरै अनुसन्धान गर्नुहोस्। कुन प्रकारको API तपाईंलाई मनपर्छ?

यस फङ्सनको बारेमा महत्त्वपूर्ण कुराहरू नोट गर्नुहोस्। पहिलो, [`async` कीवर्ड](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/async_function) लाई नोट गर्नुहोस्। तपाईंको फङ्सनहरूलाई असिंक्रोनस रूपमा चल्ने गरी लेख्दा, तिनीहरूले कुनै कार्य, जस्तै डाटा फर्काउने, पूरा नभएसम्म पर्खन्छन्।

यहाँ `async` को बारेमा छिटो भिडियो छ:

[![प्रोमिसहरू व्यवस्थापन गर्न Async र Await](https://img.youtube.com/vi/YwmlRkrxvkk/0.jpg)](https://youtube.com/watch?v=YwmlRkrxvkk "प्रोमिसहरू व्यवस्थापन गर्न Async र Await")

> 🎥 माथिको छवि क्लिक गरेर async/await को बारेमा भिडियो हेर्नुहोस्।

C02Signal API क्वेरी गर्न नयाँ फङ्सन सिर्जना गर्नुहोस्:

```JavaScript
import axios from '../node_modules/axios';

async function displayCarbonUsage(apiKey, region) {
	try {
		await axios
			.get('https://api.co2signal.com/v1/latest', {
				params: {
					countryCode: region,
				},
				headers: {
					'auth-token': apiKey,
				},
			})
			.then((response) => {
				let CO2 = Math.floor(response.data.data.carbonIntensity);

				//calculateColor(CO2);

				loading.style.display = 'none';
				form.style.display = 'none';
				myregion.textContent = region;
				usage.textContent =
					Math.round(response.data.data.carbonIntensity) + ' grams (grams C02 emitted per kilowatt hour)';
				fossilfuel.textContent =
					response.data.data.fossilFuelPercentage.toFixed(2) +
					'% (percentage of fossil fuels used to generate electricity)';
				results.style.display = 'block';
			});
	} catch (error) {
		console.log(error);
		loading.style.display = 'none';
		results.style.display = 'none';
		errors.textContent = 'Sorry, we have no data for the region you have requested.';
	}
}
```

यो ठूलो फङ्सन हो। यहाँ के भइरहेको छ?

- राम्रो अभ्यासको पालना गर्दै, तपाईंले यस फङ्सनलाई असिंक्रोनस रूपमा व्यवहार गर्न `async` कीवर्ड प्रयोग गर्नुभएको छ। फङ्सनमा `try/catch` ब्लक समावेश छ किनभने यो API ले डाटा फर्काउँदा प्रोमिस फर्काउनेछ। किनभने तपाईंलाई API ले प्रतिक्रिया दिने गति नियन्त्रण गर्न सक्दैन (यो बिल्कुल प्रतिक्रिया नदिन पनि सक्छ!), तपाईंले यस अनिश्चिततालाई असिंक्रोनस रूपमा कल गरेर ह्यान्डल गर्न आवश्यक छ।
- तपाईं आफ्नो क्षेत्रको डाटा प्राप्त गर्न co2signal API क्वेरी गर्दै हुनुहुन्छ, आफ्नो API Key प्रयोग गरेर। उक्त key प्रयोग गर्न, तपाईंले आफ्नो हेडर प्यारामिटरहरूमा एक प्रकारको प्रमाणीकरण प्रयोग गर्नुपर्छ।
- एकपटक API ले प्रतिक्रिया दिएपछि, तपाईंले यसको प्रतिक्रिया डाटाका विभिन्न तत्वहरूलाई आफ्नो स्क्रिनका भागहरूमा असाइन गर्नुहुन्छ।
- यदि कुनै त्रुटि छ वा कुनै परिणाम छैन भने, तपाईंले त्रुटि सन्देश देखाउनुहुन्छ।

✅ असिंक्रोनस प्रोग्रामिङ ढाँचाहरू प्रयोग गर्नु तपाईंको टूलबक्समा अर्को धेरै उपयोगी उपकरण हो। [विभिन्न तरिकाहरूको बारेमा](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/async_function) पढ्नुहोस् जसले तपाईंलाई यस प्रकारको कोड कन्फिगर गर्न अनुमति दिन्छ।

बधाई छ! यदि तपाईं आफ्नो एक्सटेन्सन निर्माण गर्नुहुन्छ (`npm run build`) र यसलाई आफ्नो एक्सटेन्सन प्यानमा रिफ्रेस गर्नुहुन्छ भने, तपाईंको एक्सटेन्सन काम गरिरहेको छ! एकमात्र कुरा जुन काम गरिरहेको छैन त्यो आइकन हो, र तपाईंले यसलाई अर्को पाठमा सुधार गर्नुहुनेछ।

---

## GitHub Copilot Agent चुनौती 🚀

Agent मोड प्रयोग गरेर निम्न चुनौती पूरा गर्नुहोस्:

**विवरण:** ब्राउजर एक्सटेन्सनलाई त्रुटि ह्यान्डलिङ सुधार र प्रयोगकर्ता अनुभव सुविधाहरू थपेर सुधार गर्नुहोस्। यो चुनौतीले तपाईंलाई आधुनिक JavaScript ढाँचाहरू प्रयोग गरेर API, लोकल स्टोरेज, र DOM ह्यान्डलिङमा अभ्यास गर्न मद्दत गर्नेछ।

**प्रेरणा:** displayCarbonUsage फङ्सनको सुधारिएको संस्करण सिर्जना गर्नुहोस् जसमा समावेश हो: १) असफल API कलहरूको लागि एक्सपोनेंशियल ब्याकअफसहितको पुन: प्रयास मेकानिज्म, २) API कल गर्नु अघि क्षेत्र कोडको लागि इनपुट मान्यता, ३) प्रगति सूचकहरू सहितको लोडिङ एनिमेसन, ४) लोकल स्टोरेजमा API प्रतिक्रियाहरूको क्यासिङ ३० मिनेटको समाप्ति समयसहित, र ५) अघिल्लो API कलहरूको ऐतिहासिक डाटा देखाउने सुविधा। साथै, सबै फङ्सन प्यारामिटरहरू र रिटर्न प्रकारहरूलाई डकुमेन्ट गर्न उचित TypeScript-शैलीको JSDoc टिप्पणीहरू थप्नुहोस्।

## 🚀 चुनौती

हामीले यी पाठहरूमा विभिन्न प्रकारका API हरूको बारेमा छलफल गर्यौं। वेब API छान्नुहोस् र यसले के प्रस्ताव गर्दछ भन्ने बारेमा गहिरो अनुसन्धान गर्नुहोस्। उदाहरणका लागि, ब्राउजरहरूमा उपलब्ध API हरू जस्तै [HTML Drag and Drop API](https://developer.mozilla.org/docs/Web/API/HTML_Drag_and_Drop_API) हेर्नुहोस्। तपाईंको विचारमा उत्कृष्ट API के बनाउँछ?

## पोस्ट-लेक्चर क्विज

[पोस्ट-लेक्चर क्विज](https://ff-quizzes.netlify.app/web/quiz/26)

## समीक्षा र आत्म अध्ययन

यस पाठमा तपाईंले लोकल स्टोरेज र API को बारेमा सिक्नुभयो, जुन व्यावसायिक वेब डेभलपरको लागि धेरै उपयोगी छ। यी दुई चीजहरू कसरी सँगसँगै काम गर्छन् भन्ने बारे सोच्न सक्नुहुन्छ? तपाईं कसरी वेब साइट आर्किटेक्ट गर्नुहुन्छ भन्ने बारे सोच्नुहोस् जसले API द्वारा प्रयोग गरिने वस्तुहरू भण्डारण गर्दछ।

## असाइनमेन्ट

[एक API अपनाउनुहोस्](assignment.md)

---

**अस्वीकरण**:  
यो दस्तावेज़ AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको छ। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादहरूमा त्रुटिहरू वा अशुद्धताहरू हुन सक्छ। यसको मूल भाषा मा रहेको दस्तावेज़लाई आधिकारिक स्रोत मानिनुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न हुने कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुने छैनौं।