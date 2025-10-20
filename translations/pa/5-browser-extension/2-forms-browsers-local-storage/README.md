<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "7e164d318e19925330cfcaeea954e7b5",
  "translation_date": "2025-10-20T22:10:21+00:00",
  "source_file": "5-browser-extension/2-forms-browsers-local-storage/README.md",
  "language_code": "pa"
}
-->
# ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਪ੍ਰੋਜੈਕਟ ਭਾਗ 2: API ਕਾਲ ਕਰੋ, ਲੋਕਲ ਸਟੋਰੇਜ ਵਰਤੋ

## ਪੂਰਵ-ਵਿਦਿਆਰਥੀ ਕਵਿਜ਼

[ਪੂਰਵ-ਵਿਦਿਆਰਥੀ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/25)

### ਪਰਿਚਯ

ਇਸ ਪਾਠ ਵਿੱਚ, ਤੁਸੀਂ ਆਪਣੇ ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਦੇ ਫਾਰਮ ਨੂੰ ਸਬਮਿਟ ਕਰਕੇ API ਕਾਲ ਕਰੋਗੇ ਅਤੇ ਨਤੀਜੇ ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਵਿੱਚ ਦਿਖਾਓਗੇ। ਇਸ ਤੋਂ ਇਲਾਵਾ, ਤੁਸੀਂ ਸਿੱਖੋਗੇ ਕਿ ਆਪਣੇ ਬ੍ਰਾਊਜ਼ਰ ਦੇ ਲੋਕਲ ਸਟੋਰੇਜ ਵਿੱਚ ਡਾਟਾ ਨੂੰ ਭਵਿੱਖ ਵਿੱਚ ਹਵਾਲੇ ਅਤੇ ਵਰਤੋਂ ਲਈ ਕਿਵੇਂ ਸਟੋਰ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ।

✅ ਸਹੀ ਫਾਈਲਾਂ ਵਿੱਚ ਨੰਬਰਵਾਰ ਸੈਗਮੈਂਟਾਂ ਦੀ ਪਾਲਣਾ ਕਰੋ ਤਾਂ ਜੋ ਪਤਾ ਲੱਗੇ ਕਿ ਕੋਡ ਕਿੱਥੇ ਰੱਖਣਾ ਹੈ।

### ਐਕਸਟੈਂਸ਼ਨ ਵਿੱਚ ਮੈਨਿਪੁਲੇਟ ਕਰਨ ਲਈ ਤੱਤ ਸੈਟ ਕਰੋ:

ਇਸ ਸਮੇਂ ਤੱਕ ਤੁਸੀਂ ਆਪਣੇ ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਲਈ ਫਾਰਮ ਅਤੇ ਨਤੀਜਿਆਂ `<div>` ਲਈ HTML ਬਣਾਈ ਹੈ। ਹੁਣ ਤੋਂ, ਤੁਹਾਨੂੰ `/src/index.js` ਫਾਈਲ ਵਿੱਚ ਕੰਮ ਕਰਨ ਦੀ ਲੋੜ ਹੈ ਅਤੇ ਆਪਣਾ ਐਕਸਟੈਂਸ਼ਨ ਹੌਲੀ-ਹੌਲੀ ਬਣਾਉਣਾ ਹੈ। ਆਪਣੇ ਪ੍ਰੋਜੈਕਟ ਨੂੰ ਸੈਟ ਕਰਨ ਅਤੇ ਬਣਾਉਣ ਦੀ ਪ੍ਰਕਿਰਿਆ ਬਾਰੇ [ਪਿਛਲੇ ਪਾਠ](../1-about-browsers/README.md) ਨੂੰ ਵੇਖੋ।

ਆਪਣੀ `index.js` ਫਾਈਲ ਵਿੱਚ ਕੰਮ ਕਰਦੇ ਹੋਏ, ਕੁਝ `const` ਵੈਰੀਏਬਲ ਬਣਾਉਣ ਨਾਲ ਸ਼ੁਰੂ ਕਰੋ ਜੋ ਵੱਖ-ਵੱਖ ਫੀਲਡਾਂ ਨਾਲ ਸੰਬੰਧਿਤ ਮੁੱਲਾਂ ਨੂੰ ਰੱਖਦੇ ਹਨ:

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

ਇਹ ਸਾਰੇ ਫੀਲਡ HTML ਵਿੱਚ ਸੈਟ ਕੀਤੇ CSS ਕਲਾਸ ਦੁਆਰਾ ਦਰਸਾਏ ਗਏ ਹਨ।

### ਲਿਸਨਰ ਸ਼ਾਮਲ ਕਰੋ

ਅਗਲੇ ਕਦਮ ਵਿੱਚ, ਫਾਰਮ ਅਤੇ ਕਲੀਅਰ ਬਟਨ ਲਈ ਇਵੈਂਟ ਲਿਸਨਰ ਸ਼ਾਮਲ ਕਰੋ ਜੋ ਫਾਰਮ ਨੂੰ ਰੀਸੈਟ ਕਰਦਾ ਹੈ, ਤਾਂ ਜੋ ਜੇਕਰ ਕੋਈ ਯੂਜ਼ਰ ਫਾਰਮ ਸਬਮਿਟ ਕਰਦਾ ਹੈ ਜਾਂ ਰੀਸੈਟ ਬਟਨ 'ਤੇ ਕਲਿਕ ਕਰਦਾ ਹੈ, ਕੁਝ ਹੋਵੇ। ਫਾਈਲ ਦੇ ਤਲ 'ਤੇ ਐਪ ਨੂੰ ਸ਼ੁਰੂ ਕਰਨ ਲਈ ਕਾਲ ਸ਼ਾਮਲ ਕਰੋ:

```JavaScript
form.addEventListener('submit', (e) => handleSubmit(e));
clearBtn.addEventListener('click', (e) => reset(e));
init();
```

✅ ਧਿਆਨ ਦਿਓ ਕਿ ਸਬਮਿਟ ਜਾਂ ਕਲਿਕ ਇਵੈਂਟ ਨੂੰ ਸੁਣਨ ਲਈ ਵਰਤੀ ਗਈ ਸ਼ਾਰਟਹੈਂਡ ਅਤੇ ਇਹ ਕਿਵੇਂ ਇਵੈਂਟ ਨੂੰ handleSubmit ਜਾਂ reset ਫੰਕਸ਼ਨ ਵਿੱਚ ਪਾਸ ਕੀਤਾ ਜਾਂਦਾ ਹੈ। ਕੀ ਤੁਸੀਂ ਇਸ ਸ਼ਾਰਟਹੈਂਡ ਦਾ ਲੰਬਾ ਫਾਰਮੈਟ ਲਿਖ ਸਕਦੇ ਹੋ? ਤੁਹਾਨੂੰ ਕਿਹੜਾ ਪਸੰਦ ਹੈ?

### init() ਫੰਕਸ਼ਨ ਅਤੇ reset() ਫੰਕਸ਼ਨ ਬਣਾਓ:

ਹੁਣ ਤੁਸੀਂ ਐਕਸਟੈਂਸ਼ਨ ਨੂੰ ਸ਼ੁਰੂ ਕਰਨ ਵਾਲਾ ਫੰਕਸ਼ਨ ਬਣਾਉਣ ਜਾ ਰਹੇ ਹੋ, ਜਿਸਨੂੰ init() ਕਿਹਾ ਜਾਂਦਾ ਹੈ:

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

ਇਸ ਫੰਕਸ਼ਨ ਵਿੱਚ ਕੁਝ ਦਿਲਚਸਪ ਲਾਜਿਕ ਹੈ। ਇਸਨੂੰ ਪੜ੍ਹਦੇ ਹੋਏ, ਕੀ ਤੁਸੀਂ ਦੇਖ ਸਕਦੇ ਹੋ ਕਿ ਕੀ ਹੁੰਦਾ ਹੈ?

- ਦੋ `const` ਸੈਟ ਕੀਤੇ ਜਾਂਦੇ ਹਨ ਤਾਂ ਜੋ ਜਾਂਚਿਆ ਜਾ ਸਕੇ ਕਿ ਯੂਜ਼ਰ ਨੇ APIKey ਅਤੇ ਰੀਜਨ ਕੋਡ ਨੂੰ ਲੋਕਲ ਸਟੋਰੇਜ ਵਿੱਚ ਸਟੋਰ ਕੀਤਾ ਹੈ।
- ਜੇਕਰ ਇਹਨਾਂ ਵਿੱਚੋਂ ਕੋਈ ਵੀ null ਹੈ, ਤਾਂ ਫਾਰਮ ਨੂੰ 'block' ਵਜੋਂ ਦਿਖਾਉਣ ਲਈ ਇਸਦੀ ਸ਼ੈਲੀ ਨੂੰ ਬਦਲੋ।
- ਨਤੀਜੇ, ਲੋਡਿੰਗ, ਅਤੇ clearBtn ਨੂੰ ਛੁਪਾਓ ਅਤੇ ਕਿਸੇ ਵੀ error ਟੈਕਸਟ ਨੂੰ ਖਾਲੀ ਸਟ੍ਰਿੰਗ ਵਿੱਚ ਸੈਟ ਕਰੋ।
- ਜੇਕਰ ਇੱਕ key ਅਤੇ region ਮੌਜੂਦ ਹੈ, ਤਾਂ ਇੱਕ ਰੂਟੀਨ ਸ਼ੁਰੂ ਕਰੋ:
  - API ਨੂੰ ਕਾਲ ਕਰੋ ਤਾਂ ਜੋ ਕਾਰਬਨ ਵਰਤੋਂ ਡਾਟਾ ਪ੍ਰਾਪਤ ਕੀਤਾ ਜਾ ਸਕੇ।
  - ਨਤੀਜਿਆਂ ਦੇ ਖੇਤਰ ਨੂੰ ਛੁਪਾਓ।
  - ਫਾਰਮ ਨੂੰ ਛੁਪਾਓ।
  - ਰੀਸੈਟ ਬਟਨ ਦਿਖਾਓ।

ਅੱਗੇ ਵਧਣ ਤੋਂ ਪਹਿਲਾਂ, ਬ੍ਰਾਊਜ਼ਰ ਵਿੱਚ ਉਪਲਬਧ ਇੱਕ ਬਹੁਤ ਹੀ ਮਹੱਤਵਪੂਰਨ ਧਾਰਨਾ ਬਾਰੇ ਸਿੱਖਣਾ ਲਾਭਦਾਇਕ ਹੈ: [LocalStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)। LocalStorage ਬ੍ਰਾਊਜ਼ਰ ਵਿੱਚ ਸਟ੍ਰਿੰਗਜ਼ ਨੂੰ `key-value` ਜੋੜੇ ਵਜੋਂ ਸਟੋਰ ਕਰਨ ਦਾ ਇੱਕ ਲਾਭਦਾਇਕ ਤਰੀਕਾ ਹੈ। ਇਸ ਤਰ੍ਹਾਂ ਦੇ ਵੈੱਬ ਸਟੋਰੇਜ ਨੂੰ ਜਾਵਾਸਕ੍ਰਿਪਟ ਦੁਆਰਾ ਮੈਨੇਜ ਕੀਤਾ ਜਾ ਸਕਦਾ ਹੈ। LocalStorage ਖਤਮ ਨਹੀਂ ਹੁੰਦਾ, ਜਦਕਿ SessionStorage, ਇੱਕ ਹੋਰ ਕਿਸਮ ਦਾ ਵੈੱਬ ਸਟੋਰੇਜ, ਬ੍ਰਾਊਜ਼ਰ ਬੰਦ ਹੋਣ 'ਤੇ ਸਾਫ਼ ਹੋ ਜਾਂਦਾ ਹੈ। ਸਟੋਰੇਜ ਦੀਆਂ ਵੱਖ-ਵੱਖ ਕਿਸਮਾਂ ਦੇ ਉਪਯੋਗਤਾ ਲਈ ਫਾਇਦੇ ਅਤੇ ਨੁਕਸਾਨ ਹਨ।

> ਨੋਟ - ਤੁਹਾਡੇ ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਦਾ ਆਪਣਾ ਲੋਕਲ ਸਟੋਰੇਜ ਹੈ; ਮੁੱਖ ਬ੍ਰਾਊਜ਼ਰ ਵਿੰਡੋ ਇੱਕ ਵੱਖਰਾ instance ਹੈ ਅਤੇ ਵੱਖਰੇ ਤਰੀਕੇ ਨਾਲ ਕੰਮ ਕਰਦਾ ਹੈ।

ਤੁਹਾਨੂੰ ਆਪਣਾ APIKey ਇੱਕ ਸਟ੍ਰਿੰਗ ਮੁੱਲ ਦੇਣ ਲਈ ਸੈਟ ਕਰਨਾ ਹੈ, ਉਦਾਹਰਨ ਵਜੋਂ, ਅਤੇ ਤੁਸੀਂ ਦੇਖ ਸਕਦੇ ਹੋ ਕਿ ਇਹ Edge 'ਤੇ "ਇੰਸਪੈਕਟ" ਕਰਕੇ ਸੈਟ ਕੀਤਾ ਗਿਆ ਹੈ (ਤੁਸੀਂ ਬ੍ਰਾਊਜ਼ਰ 'ਤੇ ਰਾਈਟ-ਕਲਿਕ ਕਰਕੇ ਇੰਸਪੈਕਟ ਕਰ ਸਕਦੇ ਹੋ) ਅਤੇ ਸਟੋਰੇਜ ਦੇਖਣ ਲਈ Applications ਟੈਬ 'ਤੇ ਜਾ ਸਕਦੇ ਹੋ।

![Local storage pane](../../../../translated_images/localstorage.472f8147b6a3f8d141d9551c95a2da610ac9a3c6a73d4a1c224081c98bae09d9.pa.png)

✅ ਉਹ ਸਥਿਤੀਆਂ ਬਾਰੇ ਸੋਚੋ ਜਿੱਥੇ ਤੁਸੀਂ ਕੁਝ ਡਾਟਾ LocalStorage ਵਿੱਚ ਸਟੋਰ ਨਹੀਂ ਕਰਨਾ ਚਾਹੁੰਦੇ। ਆਮ ਤੌਰ 'ਤੇ, LocalStorage ਵਿੱਚ API Keys ਰੱਖਣਾ ਇੱਕ ਖਰਾਬ ਵਿਚਾਰ ਹੈ! ਕੀ ਤੁਸੀਂ ਦੇਖ ਸਕਦੇ ਹੋ ਕਿ ਕਿਉਂ? ਸਾਡੇ ਕੇਸ ਵਿੱਚ, ਕਿਉਂਕਿ ਸਾਡਾ ਐਪ ਸਿਰਫ ਸਿੱਖਣ ਲਈ ਹੈ ਅਤੇ ਇਸਨੂੰ ਐਪ ਸਟੋਰ ਵਿੱਚ ਡਿਪਲੌਇ ਨਹੀਂ ਕੀਤਾ ਜਾਵੇਗਾ, ਅਸੀਂ ਇਸ ਤਰੀਕੇ ਨੂੰ ਵਰਤਾਂਗੇ।

ਧਿਆਨ ਦਿਓ ਕਿ ਤੁਸੀਂ LocalStorage ਨੂੰ ਮੈਨਿਪੁਲੇਟ ਕਰਨ ਲਈ Web API ਵਰਤਦੇ ਹੋ, ਜਾਂ `getItem()`, `setItem()`, ਜਾਂ `removeItem()` ਵਰਤਦੇ ਹੋ। ਇਹ ਬ੍ਰਾਊਜ਼ਰਾਂ ਵਿੱਚ ਵਿਆਪਕ ਤੌਰ 'ਤੇ ਸਹਾਇਕ ਹੈ।

`displayCarbonUsage()` ਫੰਕਸ਼ਨ ਬਣਾਉਣ ਤੋਂ ਪਹਿਲਾਂ ਜੋ `init()` ਵਿੱਚ ਕਾਲ ਕੀਤਾ ਜਾਂਦਾ ਹੈ, ਆਓ ਸ਼ੁਰੂਆਤੀ ਫਾਰਮ ਸਬਮਿਟ ਕਰਨ ਦੀ ਕਾਰਗੁਜ਼ਾਰੀ ਬਣਾਈਏ।

### ਫਾਰਮ ਸਬਮਿਟ ਕਰਨ ਦੀ ਕਾਰਗੁਜ਼ਾਰੀ

ਇੱਕ ਫੰਕਸ਼ਨ `handleSubmit` ਬਣਾਓ ਜੋ ਇੱਕ ਇਵੈਂਟ ਆਰਗੂਮੈਂਟ `(e)` ਨੂੰ ਸਵੀਕਾਰ ਕਰਦਾ ਹੈ। ਇਵੈਂਟ ਨੂੰ ਫੈਲਣ ਤੋਂ ਰੋਕੋ (ਇਸ ਮਾਮਲੇ ਵਿੱਚ, ਅਸੀਂ ਬ੍ਰਾਊਜ਼ਰ ਨੂੰ ਰੀਫ੍ਰੈਸ਼ ਕਰਨ ਤੋਂ ਰੋਕਣਾ ਚਾਹੁੰਦੇ ਹਾਂ) ਅਤੇ ਇੱਕ ਨਵੇਂ ਫੰਕਸ਼ਨ `setUpUser` ਨੂੰ ਕਾਲ ਕਰੋ, ਜਿਸ ਵਿੱਚ `apiKey.value` ਅਤੇ `region.value` ਆਰਗੂਮੈਂਟ ਪਾਸ ਕੀਤੇ ਗਏ ਹਨ। ਇਸ ਤਰੀਕੇ ਨਾਲ, ਤੁਸੀਂ ਦੋ ਮੁੱਲਾਂ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋ ਜੋ ਸ਼ੁਰੂਆਤੀ ਫਾਰਮ ਦੁਆਰਾ ਲਿਆਂਦੇ ਜਾਂਦੇ ਹਨ ਜਦੋਂ ਸਬੰਧਤ ਫੀਲਡਾਂ ਨੂੰ ਪੂਰਾ ਕੀਤਾ ਜਾਂਦਾ ਹੈ।

```JavaScript
function handleSubmit(e) {
	e.preventDefault();
	setUpUser(apiKey.value, region.value);
}
```

✅ ਆਪਣੀ ਯਾਦ ਤਾਜ਼ਾ ਕਰੋ - ਪਿਛਲੇ ਪਾਠ ਵਿੱਚ ਸੈਟ ਕੀਤਾ HTML ਵਿੱਚ ਦੋ ਇਨਪੁਟ ਫੀਲਡ ਹਨ ਜਿਨ੍ਹਾਂ ਦੇ `values` ਨੂੰ ਫਾਈਲ ਦੇ ਸਿਖਰ 'ਤੇ ਸੈਟ ਕੀਤੇ `const` ਦੁਆਰਾ ਕੈਪਚਰ ਕੀਤਾ ਜਾਂਦਾ ਹੈ, ਅਤੇ ਇਹ ਦੋਵੇਂ `required` ਹਨ ਤਾਂ ਜੋ ਬ੍ਰਾਊਜ਼ਰ ਯੂਜ਼ਰ ਨੂੰ null ਮੁੱਲਾਂ ਦਾਖਲ ਕਰਨ ਤੋਂ ਰੋਕ ਸਕੇ।

### ਯੂਜ਼ਰ ਸੈਟ ਕਰੋ

`setUpUser` ਫੰਕਸ਼ਨ ਵੱਲ ਵਧਦੇ ਹੋਏ, ਇੱਥੇ ਤੁਸੀਂ apiKey ਅਤੇ regionName ਲਈ ਲੋਕਲ ਸਟੋਰੇਜ ਮੁੱਲ ਸੈਟ ਕਰਦੇ ਹੋ। ਇੱਕ ਨਵਾਂ ਫੰਕਸ਼ਨ ਸ਼ਾਮਲ ਕਰੋ:

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

ਇਹ ਫੰਕਸ਼ਨ API ਕਾਲ ਕਰਨ ਦੌਰਾਨ ਦਿਖਾਉਣ ਲਈ ਇੱਕ ਲੋਡਿੰਗ ਸੁਨੇਹਾ ਸੈਟ ਕਰਦਾ ਹੈ। ਇਸ ਪੜਾਅ 'ਤੇ, ਤੁਸੀਂ ਇਸ ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਦੇ ਸਭ ਤੋਂ ਮਹੱਤਵਪੂਰਨ ਫੰਕਸ਼ਨ ਨੂੰ ਬਣਾਉਣ 'ਤੇ ਪਹੁੰਚ ਗਏ ਹੋ!

### ਕਾਰਬਨ ਵਰਤੋਂ ਦਿਖਾਓ

ਅੰਤ ਵਿੱਚ, API ਨੂੰ ਕਵੈਰੀ ਕਰਨ ਦਾ ਸਮਾਂ ਹੈ!

ਅੱਗੇ ਵਧਣ ਤੋਂ ਪਹਿਲਾਂ, ਸਾਨੂੰ APIs ਬਾਰੇ ਚਰਚਾ ਕਰਨੀ ਚਾਹੀਦੀ ਹੈ। APIs, ਜਾਂ [Application Programming Interfaces](https://www.webopedia.com/TERM/A/API.html), ਵੈੱਬ ਡਿਵੈਲਪਰ ਦੇ ਟੂਲਬਾਕਸ ਦਾ ਇੱਕ ਮਹੱਤਵਪੂਰਨ ਤੱਤ ਹੈ। ਇਹ ਪ੍ਰੋਗਰਾਮਾਂ ਨੂੰ ਇੱਕ-ਦੂਜੇ ਨਾਲ ਇੰਟਰਫੇਸ ਕਰਨ ਲਈ ਮਿਆਰੀ ਤਰੀਕੇ ਪ੍ਰਦਾਨ ਕਰਦੇ ਹਨ। ਉਦਾਹਰਨ ਵਜੋਂ, ਜੇਕਰ ਤੁਸੀਂ ਇੱਕ ਵੈੱਬਸਾਈਟ ਬਣਾਉਣ ਜਾ ਰਹੇ ਹੋ ਜਿਸਨੂੰ ਡਾਟਾਬੇਸ ਨੂੰ ਕਵੈਰੀ ਕਰਨ ਦੀ ਲੋੜ ਹੈ, ਤਾਂ ਕੋਈ ਤੁਹਾਡੇ ਲਈ ਵਰਤਣ ਲਈ API ਬਣਾਇਆ ਹੋ ਸਕਦਾ ਹੈ। ਜਦਕਿ APIs ਦੀਆਂ ਕਈ ਕਿਸਮਾਂ ਹਨ, ਸਭ ਤੋਂ ਪ੍ਰਸਿੱਧ ਵਿੱਚੋਂ ਇੱਕ ਹੈ [REST API](https://www.smashingmagazine.com/2018/01/understanding-using-rest-api/)।

✅ 'REST' ਦਾ ਅਰਥ 'Representational State Transfer' ਹੈ ਅਤੇ ਡਾਟਾ ਪ੍ਰਾਪਤ ਕਰਨ ਲਈ ਵੱਖ-ਵੱਖ ਤਰੀਕੇ ਨਾਲ ਸੰਰਚਿਤ URLs ਦੀ ਵਰਤੋਂ ਕਰਦਾ ਹੈ। ਡਿਵੈਲਪਰਾਂ ਲਈ ਉਪਲਬਧ APIs ਦੀਆਂ ਵੱਖ-ਵੱਖ ਕਿਸਮਾਂ 'ਤੇ ਕੁਝ ਖੋਜ ਕਰੋ। ਤੁਹਾਨੂੰ ਕਿਹੜਾ ਫਾਰਮੈਟ ਪਸੰਦ ਹੈ?

ਇਸ ਫੰਕਸ਼ਨ ਬਾਰੇ ਕੁਝ ਮਹੱਤਵਪੂਰਨ ਗੱਲਾਂ ਨੋਟ ਕਰਨ ਵਾਲੀਆਂ ਹਨ। ਪਹਿਲਾਂ, [`async` keyword](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/async_function) ਨੂੰ ਧਿਆਨ ਦਿਓ। ਆਪਣੇ ਫੰਕਸ਼ਨ ਨੂੰ ਇਸ ਤਰੀਕੇ ਨਾਲ ਲਿਖਣਾ ਕਿ ਇਹ ਅਸਿੰਕਰੋਨਸ ਤਰੀਕੇ ਨਾਲ ਚੱਲਦੇ ਹਨ, ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਇਹ ਕਿਸੇ ਕਾਰਵਾਈ, ਜਿਵੇਂ ਕਿ ਡਾਟਾ ਵਾਪਸ ਆਉਣਾ, ਪੂਰਾ ਹੋਣ ਦੀ ਉਡੀਕ ਕਰਦੇ ਹਨ।

ਇੱਥੇ `async` ਬਾਰੇ ਇੱਕ ਛੋਟੀ ਵੀਡੀਓ ਹੈ:

[![Async ਅਤੇ Await ਪ੍ਰੋਮਿਸਜ਼ ਨੂੰ ਮੈਨੇਜ ਕਰਨ ਲਈ](https://img.youtube.com/vi/YwmlRkrxvkk/0.jpg)](https://youtube.com/watch?v=YwmlRkrxvkk "Async ਅਤੇ Await ਪ੍ਰੋਮਿਸਜ਼ ਨੂੰ ਮੈਨੇਜ ਕਰਨ ਲਈ")

> 🎥 ਉੱਪਰ ਦਿੱਤੀ ਤਸਵੀਰ 'ਤੇ ਕਲਿਕ ਕਰੋ async/await ਬਾਰੇ ਵੀਡੀਓ ਦੇਖਣ ਲਈ।

C02Signal API ਨੂੰ ਕਵੈਰੀ ਕਰਨ ਲਈ ਇੱਕ ਨਵਾਂ ਫੰਕਸ਼ਨ ਬਣਾਓ:

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

ਇਹ ਇੱਕ ਵੱਡਾ ਫੰਕਸ਼ਨ ਹੈ। ਇੱਥੇ ਕੀ ਹੋ ਰਿਹਾ ਹੈ?

- ਬਿਹਤਰ ਤਰੀਕੇ ਅਨੁਸਾਰ, ਤੁਸੀਂ ਇਸ ਫੰਕਸ਼ਨ ਨੂੰ ਅਸਿੰਕਰੋਨਸ ਬਣਾਉਣ ਲਈ `async` keyword ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋ। ਫੰਕਸ਼ਨ ਵਿੱਚ ਇੱਕ `try/catch` ਬਲਾਕ ਹੈ ਕਿਉਂਕਿ ਇਹ API ਤੋਂ ਡਾਟਾ ਵਾਪਸ ਆਉਣ 'ਤੇ ਇੱਕ ਪ੍ਰੋਮਿਸ਼ ਵਾਪਸ ਕਰੇਗਾ। ਕਿਉਂਕਿ ਤੁਹਾਨੂੰ API ਦੇ ਜਵਾਬ ਦੇਣ ਦੀ ਗਤੀ 'ਤੇ ਕੰਟਰੋਲ ਨਹੀਂ ਹੈ (ਇਹ ਜਵਾਬ ਨਹੀਂ ਦੇ ਸਕਦਾ!), ਤੁਹਾਨੂੰ ਇਸ ਅਨਿਸ਼ਚਿਤਤਾ ਨੂੰ ਅਸਿੰਕਰੋਨਸ ਤਰੀਕੇ ਨਾਲ ਕਾਲ ਕਰਕੇ ਮੈਨੇਜ ਕਰਨ ਦੀ ਲੋੜ ਹੈ।
- ਤੁਸੀਂ co2signal API ਨੂੰ ਆਪਣੇ region ਦਾ ਡਾਟਾ ਪ੍ਰਾਪਤ ਕਰਨ ਲਈ ਕਵੈਰੀ ਕਰ ਰਹੇ ਹੋ, ਆਪਣੇ API Key ਦੀ ਵਰਤੋਂ ਕਰਕੇ। ਉਸ key ਨੂੰ ਵਰਤਣ ਲਈ, ਤੁਹਾਨੂੰ ਆਪਣੇ header parameters ਵਿੱਚ ਇੱਕ authentication ਦੀ ਕਿਸਮ ਦੀ ਲੋੜ ਹੈ।
- ਜਦੋਂ API ਜਵਾਬ ਦਿੰਦਾ ਹੈ, ਤੁਸੀਂ ਇਸਦੇ ਜਵਾਬ ਡਾਟਾ ਦੇ ਵੱਖ-ਵੱਖ ਤੱਤਾਂ ਨੂੰ ਆਪਣੇ ਸਕ੍ਰੀਨ ਦੇ ਹਿੱਸਿਆਂ ਵਿੱਚ ਸੈਟ ਕਰਦੇ ਹੋ ਜੋ ਇਹ ਡਾਟਾ ਦਿਖਾਉਣ ਲਈ ਸੈਟ ਕੀਤੇ ਗਏ ਹਨ।
- ਜੇਕਰ ਕੋਈ ਗਲਤੀ ਹੁੰਦੀ ਹੈ, ਜਾਂ ਜੇਕਰ ਕੋਈ ਨਤੀਜਾ ਨਹੀਂ ਹੈ, ਤਾਂ ਤੁਸੀਂ ਇੱਕ error ਸੁਨੇਹਾ ਦਿਖਾਉਂਦੇ ਹੋ।

✅ ਅਸਿੰਕਰੋਨਸ ਪ੍ਰੋਗਰਾਮਿੰਗ ਪੈਟਰਨ ਦੀ ਵਰਤੋਂ ਕਰਨਾ ਤੁਹਾਡੇ ਟੂਲਬਾਕਸ ਵਿੱਚ ਇੱਕ ਹੋਰ ਬਹੁਤ ਹੀ ਲਾਭਦਾਇਕ ਟੂਲ ਹੈ। [ਵੱਖ-ਵੱਖ ਤਰੀਕਿਆਂ](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/async_function) ਬਾਰੇ ਪੜ੍ਹੋ ਜਿਨ੍ਹਾਂ ਨਾਲ ਤੁਸੀਂ ਇਸ ਕਿਸਮ ਦਾ ਕੋਡ ਸੰਰਚਿਤ ਕਰ ਸਕਦੇ ਹੋ।

ਵਧਾਈ ਹੋਵੇ! ਜੇਕਰ ਤੁਸੀਂ ਆਪਣਾ ਐਕਸਟੈਂਸ਼ਨ ਬਣਾਉਂਦੇ ਹੋ (`npm run build`) ਅਤੇ ਇਸਨੂੰ ਆਪਣੇ ਐਕਸਟੈਂਸ਼ਨ ਪੈਨ ਵਿੱਚ ਰੀਫ੍ਰੈਸ਼ ਕਰਦੇ ਹੋ, ਤਾਂ ਤੁਹਾਡੇ ਕੋਲ ਇੱਕ ਕੰਮ ਕਰਨ ਵਾਲਾ ਐਕਸਟੈਂਸ਼ਨ ਹੈ! ਸਿਰਫ ਇੱਕ ਚੀਜ਼ ਜੋ ਕੰਮ ਨਹੀਂ ਕਰ ਰਹੀ ਹੈ ਉਹ ਹੈ ਆਈਕਨ, ਅਤੇ ਤੁਸੀਂ ਇਸਨੂੰ ਅਗਲੇ ਪਾਠ ਵਿੱਚ ਠੀਕ ਕਰੋਗੇ।

---

## GitHub Copilot Agent ਚੈਲੈਂਜ 🚀

Agent ਮੋਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਚੈਲੈਂਜ ਨੂੰ ਪੂਰਾ ਕਰੋ:

**ਵੇਰਵਾ:** ਬ੍ਰਾਊਜ਼ਰ ਐਕਸਟੈਂਸ਼ਨ ਨੂੰ error ਹੈਂਡਲਿੰਗ ਵਿੱਚ ਸੁਧਾਰ ਅਤੇ ਯੂਜ਼ਰ ਐਕਸਪੀਰੀਅੰਸ ਫੀਚਰਾਂ ਸ਼ਾਮਲ ਕਰਕੇ ਵਧਾਓ। ਇਹ ਚੈਲੈਂਜ ਤੁਹਾਨੂੰ APIs, local storage, ਅਤੇ DOM ਮੈਨਿਪੁਲੇਸ਼ਨ 'ਤੇ ਕੰਮ ਕਰਨ ਦੀ ਅਭਿਆਸ ਕਰਨ ਵਿੱਚ ਮਦਦ ਕਰੇਗਾ।

**ਪ੍ਰੋਮਪਟ:** displayCarbonUsage ਫੰਕਸ਼ਨ ਦਾ ਇੱਕ ਵਧੀਆ ਸੰਸਕਰਣ ਬਣਾਓ ਜਿਸ ਵਿੱਚ ਸ਼ਾਮਲ ਹੋਵੇ: 1) ਫੇਲ੍ਹ ਹੋਈ API ਕਾਲਾਂ ਲਈ exponential backoff ਨਾਲ retry ਮਕੈਨਿਜ਼ਮ, 2) API ਕਾਲ ਕਰਨ ਤੋਂ ਪਹਿਲਾਂ region code ਲਈ input validation, 3) ਲੋਡਿੰਗ ਐਨੀਮੇਸ਼ਨ ਨਾਲ progress indicators, 4) localStorage ਵਿੱਚ expiration timestamps ਨਾਲ API ਜਵਾਬਾਂ ਦੀ caching (30 ਮਿੰਟ ਲਈ cache), ਅਤੇ 5) ਪਿਛਲੇ API ਕਾਲਾਂ ਤੋਂ ਇਤਿਹਾਸਕ ਡਾਟਾ ਦਿਖਾਉਣ ਦੀ ਵਿਸ਼ੇਸ਼ਤਾ। ਸਾਰੇ ਫੰਕਸ਼ਨ parameters ਅਤੇ return types ਨੂੰ ਦਸਤਾਵੇਜ਼ ਕਰਨ ਲਈ TypeScript-style JSDoc comments ਸ਼ਾਮਲ ਕਰੋ।

## 🚀 ਚੈਲੈਂਜ

ਅਸੀਂ ਇਨ੍ਹਾਂ ਪਾਠਾਂ ਵਿੱਚ ਹੁਣ ਤੱਕ ਕਈ ਕਿਸਮ ਦੇ API ਬਾਰੇ ਚਰਚਾ ਕੀਤੀ ਹੈ। ਇੱਕ ਵੈੱਬ API ਚੁਣੋ ਅਤੇ ਗਹਿਰਾਈ ਵਿੱਚ ਖੋਜ ਕਰੋ ਕਿ ਇਹ ਕੀ ਪੇਸ਼ ਕਰਦਾ ਹੈ। ਉਦਾਹਰਨ ਵਜੋਂ, ਬ੍ਰਾਊਜ਼ਰਾਂ ਵਿੱਚ ਉਪਲਬਧ APIs ਨੂੰ ਵੇਖੋ ਜਿਵੇਂ ਕਿ [HTML Drag and Drop API](https://developer.mozilla.org/docs/Web/API/HTML_Drag_and_Drop_API)। ਤੁਹਾਡੇ ਵਿਚਾਰ ਵਿੱਚ ਇੱਕ ਵਧੀਆ API ਕਿਹੜਾ ਹੈ?

## ਪਾਠ-ਪ੍ਰਸ਼ਨ ਕਵਿਜ਼

[ਪਾਠ-ਪ੍ਰਸ਼ਨ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/26)

## ਸਮੀਖਿਆ ਅਤੇ ਸਵੈ ਅਧਿਐਨ

ਤੁਸੀਂ ਇਸ ਪਾਠ ਵਿੱਚ LocalStorage ਅਤੇ APIs ਬਾਰੇ ਸਿੱਖਿਆ, ਜੋ ਕਿ ਪੇਸ਼ੇਵਰ ਵੈੱਬ ਡਿਵੈਲਪਰ ਲਈ ਬਹੁਤ ਹੀ ਲਾਭਦਾਇਕ ਹਨ। ਕੀ ਤੁਸੀਂ ਸੋਚ

---

**ਅਸਵੀਕਰਤਾ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁਚੀਤਤਾਵਾਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਇਸਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।