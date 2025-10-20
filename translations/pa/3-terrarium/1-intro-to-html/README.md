<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "f6235d42b9e6862267e92c53f1be2655",
  "translation_date": "2025-10-20T22:00:54+00:00",
  "source_file": "3-terrarium/1-intro-to-html/README.md",
  "language_code": "pa"
}
-->
# ਟੈਰੀਰੀਅਮ ਪ੍ਰੋਜੈਕਟ ਭਾਗ 1: HTML ਦਾ ਪਰਚੇ

![HTML ਦਾ ਪਰਚੇ](../../../../translated_images/webdev101-html.4389c2067af68e98280c1bde52b6c6269f399eaae3659b7c846018d8a7b0bbd9.pa.png)
> ਸਕੈਚਨੋਟ [ਟੋਮੋਮੀ ਇਮੁਰਾ](https://twitter.com/girlie_mac) ਦੁਆਰਾ

## ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵਿਜ਼

[ਲੈਕਚਰ ਤੋਂ ਪਹਿਲਾਂ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/15)

> ਵੀਡੀਓ ਦੇਖੋ

> 
> [![Git ਅਤੇ GitHub ਬੇਸਿਕਸ ਵੀਡੀਓ](https://img.youtube.com/vi/1TvxJKBzhyQ/0.jpg)](https://www.youtube.com/watch?v=1TvxJKBzhyQ)

### ਪਰਚੇ

HTML, ਜਾਂ HyperText Markup Language, ਵੈੱਬ ਦਾ 'ਡھانਚਾ' ਹੈ। ਜੇ CSS ਤੁਹਾਡੇ HTML ਨੂੰ 'ਸਜਾਉਂਦਾ' ਹੈ ਅਤੇ JavaScript ਇਸਨੂੰ ਜ਼ਿੰਦਗੀ ਦਿੰਦਾ ਹੈ, ਤਾਂ HTML ਤੁਹਾਡੇ ਵੈੱਬ ਐਪਲੀਕੇਸ਼ਨ ਦਾ ਸਰੀਰ ਹੈ। HTML ਦੀ syntax ਇਸ ਵਿਚਾਰ ਨੂੰ ਦਰਸਾਉਂਦੀ ਹੈ, ਕਿਉਂਕਿ ਇਸ ਵਿੱਚ "head", "body", ਅਤੇ "footer" ਟੈਗ ਸ਼ਾਮਲ ਹਨ।

ਇਸ ਪਾਠ ਵਿੱਚ, ਅਸੀਂ ਆਪਣੇ ਵਰਚੁਅਲ ਟੈਰੀਰੀਅਮ ਦੇ ਇੰਟਰਫੇਸ ਦਾ 'ਡھانਚਾ' ਬਣਾਉਣ ਲਈ HTML ਦੀ ਵਰਤੋਂ ਕਰਨ ਜਾ ਰਹੇ ਹਾਂ। ਇਸ ਵਿੱਚ ਇੱਕ ਸਿਰਲੇਖ ਅਤੇ ਤਿੰਨ ਕਾਲਮ ਹੋਣਗੇ: ਇੱਕ ਸੱਜੇ ਅਤੇ ਇੱਕ ਖੱਬੇ ਕਾਲਮ ਜਿੱਥੇ ਖਿੱਚਣ ਵਾਲੇ ਪੌਦੇ ਹੋਣਗੇ, ਅਤੇ ਇੱਕ ਕੇਂਦਰੀ ਖੇਤਰ ਜੋ ਅਸਲ ਵਿੱਚ ਕੱਚ-ਵਾਲਾ ਟੈਰੀਰੀਅਮ ਹੋਵੇਗਾ। ਇਸ ਪਾਠ ਦੇ ਅੰਤ ਤੱਕ, ਤੁਸੀਂ ਕਾਲਮਾਂ ਵਿੱਚ ਪੌਦੇ ਦੇਖ ਸਕੋਗੇ, ਪਰ ਇੰਟਰਫੇਸ ਕੁਝ ਅਜੀਬ ਲੱਗੇਗਾ; ਚਿੰਤਾ ਨਾ ਕਰੋ, ਅਗਲੇ ਭਾਗ ਵਿੱਚ ਤੁਸੀਂ CSS ਸ਼ੈਲੀਆਂ ਨੂੰ ਇੰਟਰਫੇਸ ਵਿੱਚ ਸ਼ਾਮਲ ਕਰਕੇ ਇਸਨੂੰ ਵਧੀਆ ਬਣਾਉਣਗੇ।

### ਕੰਮ

ਆਪਣੇ ਕੰਪਿਊਟਰ 'ਤੇ, 'terrarium' ਨਾਮਕ ਫੋਲਡਰ ਬਣਾਓ ਅਤੇ ਇਸਦੇ ਅੰਦਰ 'index.html' ਨਾਮਕ ਫਾਈਲ ਬਣਾਓ। ਤੁਸੀਂ ਇਹ Visual Studio Code ਵਿੱਚ ਕਰ ਸਕਦੇ ਹੋ ਜਦੋਂ ਤੁਸੀਂ ਆਪਣਾ terrarium ਫੋਲਡਰ ਬਣਾਉਂਦੇ ਹੋ, ਨਵਾਂ VS Code ਵਿੰਡੋ ਖੋਲ੍ਹ ਕੇ, 'open folder' 'ਤੇ ਕਲਿੱਕ ਕਰਕੇ ਆਪਣੇ ਨਵੇਂ ਫੋਲਡਰ 'ਤੇ ਜਾਓ। Explorer ਪੈਨ ਵਿੱਚ ਛੋਟੇ 'file' ਬਟਨ 'ਤੇ ਕਲਿੱਕ ਕਰੋ ਅਤੇ ਨਵੀਂ ਫਾਈਲ ਬਣਾਓ:

![VS Code ਵਿੱਚ Explorer](../../../../translated_images/vs-code-index.e2986cf919471eb984a0afef231380c8b132b000635105f2397bd2754d1b689c.pa.png)

ਜਾਂ

ਆਪਣੇ git bash 'ਤੇ ਇਹ ਕਮਾਂਡਾਂ ਵਰਤੋ:
* `mkdir terrarium`
* `cd terrarium`
* `touch index.html`
* `code index.html` ਜਾਂ `nano index.html`

> index.html ਫਾਈਲਾਂ ਬ੍ਰਾਊਜ਼ਰ ਨੂੰ ਦਰਸਾਉਂਦੀਆਂ ਹਨ ਕਿ ਇਹ ਫੋਲਡਰ ਵਿੱਚ ਡਿਫਾਲਟ ਫਾਈਲ ਹੈ; URLs ਜਿਵੇਂ `https://anysite.com/test` ਇੱਕ ਫੋਲਡਰ ਸਟ੍ਰਕਚਰ ਵਰਤ ਕੇ ਬਣਾਈ ਜਾ ਸਕਦੀ ਹੈ ਜਿਸ ਵਿੱਚ `test` ਨਾਮਕ ਫੋਲਡਰ ਅਤੇ ਇਸਦੇ ਅੰਦਰ `index.html` ਸ਼ਾਮਲ ਹੈ; URL ਵਿੱਚ `index.html` ਦਿਖਾਈ ਦੇਣ ਦੀ ਲੋੜ ਨਹੀਂ ਹੁੰਦੀ।

---

## DocType ਅਤੇ html ਟੈਗ

HTML ਫਾਈਲ ਦੀ ਪਹਿਲੀ ਲਾਈਨ ਇਸਦਾ doctype ਹੁੰਦੀ ਹੈ। ਇਹ ਕੁਝ ਹੈਰਾਨੀਜਨਕ ਹੈ ਕਿ ਤੁਹਾਨੂੰ ਇਹ ਲਾਈਨ ਫਾਈਲ ਦੇ ਬਿਲਕੁਲ ਉੱਪਰ ਹੋਣੀ ਚਾਹੀਦੀ ਹੈ, ਪਰ ਇਹ ਪੁਰਾਣੇ ਬ੍ਰਾਊਜ਼ਰਾਂ ਨੂੰ ਦੱਸਦੀ ਹੈ ਕਿ ਬ੍ਰਾਊਜ਼ਰ ਨੂੰ ਪੇਜ ਨੂੰ ਮੌਜੂਦਾ html ਵਿਸ਼ੇਸ਼ਤਾ ਦੇ ਅਨੁਸਾਰ ਸਟੈਂਡਰਡ ਮੋਡ ਵਿੱਚ ਰੈਂਡਰ ਕਰਨ ਦੀ ਲੋੜ ਹੈ।

> ਟਿਪ: VS Code ਵਿੱਚ, ਤੁਸੀਂ ਕਿਸੇ ਟੈਗ 'ਤੇ ਹਵਰ ਕਰ ਸਕਦੇ ਹੋ ਅਤੇ ਇਸਦੇ ਵਰਤੋਂ ਬਾਰੇ ਜਾਣਕਾਰੀ MDN Reference ਗਾਈਡ ਤੋਂ ਪ੍ਰਾਪਤ ਕਰ ਸਕਦੇ ਹੋ।

ਦੂਜੀ ਲਾਈਨ `<html>` ਟੈਗ ਦੀ ਖੁੱਲ੍ਹਣ ਵਾਲੀ ਲਾਈਨ ਹੋਣੀ ਚਾਹੀਦੀ ਹੈ, ਜਿਸਦੇ ਤੁਰੰਤ ਬਾਅਦ ਇਸਦੀ ਬੰਦ ਕਰਨ ਵਾਲੀ ਲਾਈਨ `</html>` ਹੋਵੇਗੀ। ਇਹ ਟੈਗ ਤੁਹਾਡੇ ਇੰਟਰਫੇਸ ਦੇ ਰੂਟ ਐਲੀਮੈਂਟ ਹਨ।

### ਕੰਮ

ਆਪਣੀ `index.html` ਫਾਈਲ ਦੇ ਉੱਪਰ ਇਹ ਲਾਈਨਾਂ ਸ਼ਾਮਲ ਕਰੋ:

```HTML
<!DOCTYPE html>
<html></html>
```

✅ DocType ਨੂੰ ਇੱਕ ਕਵੈਰੀ ਸਟ੍ਰਿੰਗ ਨਾਲ ਸੈਟ ਕਰਕੇ ਕੁਝ ਵੱਖ-ਵੱਖ ਮੋਡ ਨਿਰਧਾਰਤ ਕੀਤੇ ਜਾ ਸਕਦੇ ਹਨ: [Quirks Mode ਅਤੇ Standards Mode](https://developer.mozilla.org/docs/Web/HTML/Quirks_Mode_and_Standards_Mode)। ਇਹ ਮੋਡ ਪੁਰਾਣੇ ਬ੍ਰਾਊਜ਼ਰਾਂ (Netscape Navigator 4 ਅਤੇ Internet Explorer 5) ਨੂੰ ਸਹਾਇਤਾ ਦੇਣ ਲਈ ਵਰਤੇ ਜਾਂਦੇ ਸਨ ਜੋ ਹੁਣ ਆਮ ਤੌਰ 'ਤੇ ਵਰਤੇ ਨਹੀਂ ਜਾਂਦੇ। ਤੁਸੀਂ ਸਟੈਂਡਰਡ doctype ਡਿਕਲੇਰੇਸ਼ਨ 'ਤੇ ਟਿਕੇ ਰਹੋ।

---

## ਦਸਤਾਵੇਜ਼ ਦਾ 'head'

HTML ਦਸਤਾਵੇਜ਼ ਦਾ 'head' ਖੇਤਰ ਤੁਹਾਡੇ ਵੈੱਬ ਪੇਜ ਬਾਰੇ ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਸ਼ਾਮਲ ਕਰਦਾ ਹੈ, ਜਿਸਨੂੰ [metadata](https://developer.mozilla.org/docs/Web/HTML/Element/meta) ਵੀ ਕਿਹਾ ਜਾਂਦਾ ਹੈ। ਸਾਡੇ ਮਾਮਲੇ ਵਿੱਚ, ਅਸੀਂ ਵੈੱਬ ਸਰਵਰ ਨੂੰ ਦੱਸਦੇ ਹਾਂ ਜਿਸ 'ਤੇ ਇਹ ਪੇਜ ਰੈਂਡਰ ਕਰਨ ਲਈ ਭੇਜਿਆ ਜਾਵੇਗਾ, ਇਹ ਚਾਰ ਚੀਜ਼ਾਂ:

-   ਪੇਜ ਦਾ ਸਿਰਲੇਖ
-   ਪੇਜ metadata ਜਿਸ ਵਿੱਚ ਸ਼ਾਮਲ ਹੈ:
    -   'character set', ਜੋ ਦੱਸਦਾ ਹੈ ਕਿ ਪੇਜ ਵਿੱਚ ਕਿਹੜਾ character encoding ਵਰਤਿਆ ਗਿਆ ਹੈ
    -   ਬ੍ਰਾਊਜ਼ਰ ਜਾਣਕਾਰੀ, ਜਿਸ ਵਿੱਚ `x-ua-compatible` ਸ਼ਾਮਲ ਹੈ ਜੋ ਦਰਸਾਉਂਦਾ ਹੈ ਕਿ IE=edge ਬ੍ਰਾਊਜ਼ਰ ਸਹਾਇਕ ਹੈ
    -   ਜਾਣਕਾਰੀ ਕਿ ਪੇਜ ਲੋਡ ਹੋਣ 'ਤੇ viewport ਕਿਵੇਂ ਵਰਤਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। viewport ਨੂੰ 1 ਦੀ ਸ਼ੁਰੂਆਤੀ ਸਕੇਲ ਦੇ ਨਾਲ ਸੈਟ ਕਰਨਾ ਪੇਜ ਲੋਡ ਹੋਣ 'ਤੇ ਜ਼ੂਮ ਲੈਵਲ ਨੂੰ ਨਿਯੰਤਰਿਤ ਕਰਦਾ ਹੈ।

### ਕੰਮ

ਆਪਣੇ ਦਸਤਾਵੇਜ਼ ਵਿੱਚ `<html>` ਟੈਗ ਦੇ ਖੁੱਲ੍ਹਣ ਅਤੇ ਬੰਦ ਕਰਨ ਵਾਲੇ ਟੈਗਾਂ ਦੇ ਵਿਚਕਾਰ 'head' ਬਲਾਕ ਸ਼ਾਮਲ ਕਰੋ।

```html
<head>
	<title>Welcome to my Virtual Terrarium</title>
	<meta charset="utf-8" />
	<meta http-equiv="X-UA-Compatible" content="IE=edge" />
	<meta name="viewport" content="width=device-width, initial-scale=1" />
</head>
```

✅ ਜੇ ਤੁਸੀਂ viewport meta ਟੈਗ ਨੂੰ ਇਸ ਤਰ੍ਹਾਂ ਸੈਟ ਕਰੋ: `<meta name="viewport" content="width=600">`, ਤਾਂ ਕੀ ਹੋਵੇਗਾ? [viewport](https://developer.mozilla.org/docs/Web/HTML/Viewport_meta_tag) ਬਾਰੇ ਹੋਰ ਪੜ੍ਹੋ।

---

## ਦਸਤਾਵੇਜ਼ ਦਾ `body`

### HTML ਟੈਗ

HTML ਵਿੱਚ, ਤੁਸੀਂ ਆਪਣੇ .html ਫਾਈਲ ਵਿੱਚ ਟੈਗ ਸ਼ਾਮਲ ਕਰਦੇ ਹੋ ਤਾਂ ਜੋ ਵੈੱਬ ਪੇਜ ਦੇ ਐਲੀਮੈਂਟ ਬਣ ਸਕਣ। ਹਰ ਟੈਗ ਆਮ ਤੌਰ 'ਤੇ ਇੱਕ ਖੁੱਲ੍ਹਣ ਅਤੇ ਬੰਦ ਕਰਨ ਵਾਲਾ ਟੈਗ ਹੁੰਦਾ ਹੈ, ਜਿਵੇਂ: `<p>hello</p>` ਇੱਕ ਪੈਰਾ ਦਰਸਾਉਣ ਲਈ। ਆਪਣੇ ਇੰਟਰਫੇਸ ਦਾ body ਬਣਾਉਣ ਲਈ `<html>` ਟੈਗ ਜੋੜੇ ਦੇ ਅੰਦਰ `<body>` ਟੈਗਾਂ ਦਾ ਇੱਕ ਸੈੱਟ ਸ਼ਾਮਲ ਕਰੋ; ਹੁਣ ਤੁਹਾਡਾ markup ਇਸ ਤਰ੍ਹਾਂ ਲੱਗੇਗਾ:

### ਕੰਮ

```html
<!DOCTYPE html>
<html>
	<head>
		<title>Welcome to my Virtual Terrarium</title>
		<meta charset="utf-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1" />
	</head>
	<body></body>
</html>
```

ਹੁਣ, ਤੁਸੀਂ ਆਪਣਾ ਪੇਜ ਬਣਾਉਣਾ ਸ਼ੁਰੂ ਕਰ ਸਕਦੇ ਹੋ। ਆਮ ਤੌਰ 'ਤੇ, ਤੁਸੀਂ ਪੇਜ ਵਿੱਚ ਵੱਖ-ਵੱਖ ਐਲੀਮੈਂਟ ਬਣਾਉਣ ਲਈ `<div>` ਟੈਗਾਂ ਦੀ ਵਰਤੋਂ ਕਰਦੇ ਹੋ। ਅਸੀਂ `<div>` ਐਲੀਮੈਂਟਾਂ ਦੀ ਇੱਕ ਲੜੀ ਬਣਾਵਾਂਗੇ ਜੋ ਚਿੱਤਰਾਂ ਨੂੰ ਸ਼ਾਮਲ ਕਰੇਗੀ।

### ਚਿੱਤਰ

ਇੱਕ html ਟੈਗ ਜਿਸਨੂੰ ਬੰਦ ਕਰਨ ਵਾਲੇ ਟੈਗ ਦੀ ਲੋੜ ਨਹੀਂ ਹੁੰਦੀ, ਉਹ ਹੈ `<img>` ਟੈਗ, ਕਿਉਂਕਿ ਇਸ ਵਿੱਚ ਇੱਕ `src` ਐਲੀਮੈਂਟ ਹੁੰਦਾ ਹੈ ਜੋ ਪੇਜ ਨੂੰ ਆਈਟਮ ਨੂੰ ਰੈਂਡਰ ਕਰਨ ਲਈ ਸਾਰੀ ਜਾਣਕਾਰੀ ਦਿੰਦਾ ਹੈ।

ਆਪਣੇ ਐਪ ਵਿੱਚ `images` ਨਾਮਕ ਫੋਲਡਰ ਬਣਾਓ ਅਤੇ ਇਸ ਵਿੱਚ [source code folder](../../../../3-terrarium/solution/images) ਦੇ ਸਾਰੇ ਚਿੱਤਰ ਸ਼ਾਮਲ ਕਰੋ; (ਪੌਦਿਆਂ ਦੇ 14 ਚਿੱਤਰ ਹਨ)।

### ਕੰਮ

ਇਹ ਪੌਦੇ ਦੇ ਚਿੱਤਰ `<body></body>` ਟੈਗਾਂ ਦੇ ਵਿਚਕਾਰ ਦੋ ਕਾਲਮਾਂ ਵਿੱਚ ਸ਼ਾਮਲ ਕਰੋ:

```html
<div id="page">
	<div id="left-container" class="container">
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant1" src="../../../../translated_images/plant1.d87946a2ca70cc4316bda6e6c3af7210fbe9ada5539a7885141a9ce0efaf7be3.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant2" src="../../../../translated_images/plant2.8daa1606c9c1ad896bb171212c7d1d882e504b76b8ec3a2d1c337d775cf50dc3.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant3" src="../../../../translated_images/plant3.8b0d484381a2a2a77c5c06ad97ab6ae5b7023da8c6c7678b0183bc0e46ea17a7.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant4" src="../../../../translated_images/plant4.656e16ae1df37be2af5f4e7b5ab6c5decc432c3d3ec2eb98b904ddbecad49db0.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant5" src="../../../../translated_images/plant5.2b41b9355f11ebccd62d327f5f14e56531ecda9c6f970bc89e386ee9f0273bb0.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant6" src="../../../../translated_images/plant6.3d1827d03b6569946be13ae5da1f32947ae56732638a43757a7c616a6adccc5d.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant7" src="../../../../translated_images/plant7.8152c302ac97f621a6c595bdf3939103568f9efc7d3b06a0f02a1ea66f479de0.pa.png" />
		</div>
	</div>
	<div id="right-container" class="container">
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant8" src="../../../../translated_images/plant8.38d6428174ffa850a47cd1b81d528fa528adda7d23f3ae0bb42f4a27356ca5e6.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant9" src="../../../../translated_images/plant9.f0e38d3327c37fc29cd2734d48d20c2cf69300898ece6d46708829e02ce540e3.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant10" src="../../../../translated_images/plant10.b159d6d6e985595f56d86b4b38061b8e7b4c9969c210c199fe967269cf935e7f.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant11" src="../../../../translated_images/plant11.2a03a1c2ec8ea84ef3a80c06cc6883f3960fbb669f2c0b0bd824ba33d7eb7d32.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant12" src="../../../../translated_images/plant12.60e9b53e538fbaf3e5797ebf800acb483baf5639e6cf378292ac2321ab8a5ea9.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant13" src="../../../../translated_images/plant13.07a51543c820bcf57f67a9a6c0acbd6211ff795e2e67a42a9718224534e95fab.pa.png" />
		</div>
		<div class="plant-holder">
			<img class="plant" alt="plant" id="plant14" src="../../../../translated_images/plant14.6e486371ba7d36ba3520d9828887993cb4c3edad8bdd8ff9b1b315717ff8cb63.pa.png" />
		</div>
	</div>
</div>
```

> ਨੋਟ: Spans vs. Divs. Divs ਨੂੰ 'block' ਐਲੀਮੈਂਟ ਮੰਨਿਆ ਜਾਂਦਾ ਹੈ, ਅਤੇ Spans ਨੂੰ 'inline'। ਜੇ ਤੁਸੀਂ ਇਹ divs ਨੂੰ spans ਵਿੱਚ ਬਦਲ ਦਿੰਦੇ ਹੋ ਤਾਂ ਕੀ ਹੋਵੇਗਾ?

ਇਸ markup ਨਾਲ, ਪੌਦੇ ਹੁਣ ਸਕ੍ਰੀਨ 'ਤੇ ਦਿਖਾਈ ਦੇਣਗੇ। ਇਹ ਕੁਝ ਖਰਾਬ ਲੱਗੇਗਾ, ਕਿਉਂਕਿ ਇਹਨਾਂ ਨੂੰ ਹਾਲੇ CSS ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਸਜਾਇਆ ਨਹੀਂ ਗਿਆ ਹੈ, ਅਤੇ ਅਸੀਂ ਇਹ ਅਗਲੇ ਪਾਠ ਵਿੱਚ ਕਰਾਂਗੇ।

ਹਰ ਚਿੱਤਰ ਵਿੱਚ alt ਟੈਕਸਟ ਹੁੰਦਾ ਹੈ ਜੋ ਉਸ ਸਮੇਂ ਵੀ ਦਿਖਾਈ ਦੇਵੇਗਾ ਜਦੋਂ ਤੁਸੀਂ ਚਿੱਤਰ ਨਹੀਂ ਦੇਖ ਸਕਦੇ ਜਾਂ ਰੈਂਡਰ ਨਹੀਂ ਕਰ ਸਕਦੇ। ਇਹ accessibility ਲਈ ਸ਼ਾਮਲ ਕਰਨ ਲਈ ਇੱਕ ਮਹੱਤਵਪੂਰਨ attribute ਹੈ। ਭਵਿੱਖ ਦੇ ਪਾਠਾਂ ਵਿੱਚ accessibility ਬਾਰੇ ਹੋਰ ਜਾਣੋ; ਇਸ ਸਮੇਂ ਲਈ, ਯਾਦ ਰੱਖੋ ਕਿ alt attribute ਚਿੱਤਰ ਲਈ ਵਿਕਲਪਿਕ ਜਾਣਕਾਰੀ ਪ੍ਰਦਾਨ ਕਰਦਾ ਹੈ ਜੇਕਰ ਕਿਸੇ ਕਾਰਨ ਕਰਕੇ ਯੂਜ਼ਰ ਚਿੱਤਰ ਨਹੀਂ ਦੇਖ ਸਕਦਾ (ਧੀਮੀ ਕਨੈਕਸ਼ਨ, src attribute ਵਿੱਚ ਗਲਤੀ, ਜਾਂ ਜੇ ਯੂਜ਼ਰ ਸਕ੍ਰੀਨ ਰੀਡਰ ਵਰਤਦਾ ਹੈ)।

✅ ਕੀ ਤੁਸੀਂ ਧਿਆਨ ਦਿੱਤਾ ਕਿ ਹਰ ਚਿੱਤਰ ਵਿੱਚ ਇੱਕੋ ਜਿਹਾ alt ਟੈਗ ਹੈ? ਕੀ ਇਹ ਚੰਗੀ ਪ੍ਰਥਾ ਹੈ? ਕਿਉਂ ਜਾਂ ਕਿਉਂ ਨਹੀਂ? ਕੀ ਤੁਸੀਂ ਇਸ ਕੋਡ ਨੂੰ ਬਿਹਤਰ ਬਣਾ ਸਕਦੇ ਹੋ?

---

## ਸੈਮੈਂਟਿਕ ਮਾਰਕਅਪ

ਆਮ ਤੌਰ 'ਤੇ, HTML ਲਿਖਣ ਸਮੇਂ ਅਰਥਪੂਰਨ 'ਸੈਮੈਂਟਿਕਸ' ਦੀ ਵਰਤੋਂ ਕਰਨਾ ਪਸੰਦ ਕੀਤਾ ਜਾਂਦਾ ਹੈ। ਇਸਦਾ ਕੀ ਅਰਥ ਹੈ? ਇਸਦਾ ਮਤਲਬ ਹੈ ਕਿ ਤੁਸੀਂ HTML ਟੈਗਾਂ ਦੀ ਵਰਤੋਂ ਉਸ ਤਰ੍ਹਾਂ ਕਰਦੇ ਹੋ ਜਿਵੇਂ ਉਹ ਡਾਟਾ ਜਾਂ ਇੰਟਰੈਕਸ਼ਨ ਦੀ ਕਿਸਮ ਨੂੰ ਦਰਸਾਉਣ ਲਈ ਡਿਜ਼ਾਈਨ ਕੀਤੇ ਗਏ ਸਨ। ਉਦਾਹਰਣ ਲਈ, ਪੇਜ ਦੇ ਮੁੱਖ ਸਿਰਲੇਖ ਟੈਕਸਟ ਨੂੰ `<h1>` ਟੈਗ ਦੀ ਵਰਤੋਂ ਕਰਨੀ ਚਾਹੀਦੀ ਹੈ।

ਆਪਣੇ ਖੁੱਲ੍ਹਣ ਵਾਲੇ `<body>` ਟੈਗ ਦੇ ਬਿਲਕੁਲ ਹੇਠਾਂ ਇਹ ਲਾਈਨ ਸ਼ਾਮਲ ਕਰੋ:

```html
<h1>My Terrarium</h1>
```

ਸੈਮੈਂਟਿਕ ਮਾਰਕਅਪ ਦੀ ਵਰਤੋਂ ਕਰਨਾ ਜਿਵੇਂ ਕਿ ਸਿਰਲੇਖਾਂ ਨੂੰ `<h1>` ਅਤੇ unordered lists ਨੂੰ `<ul>` ਵਜੋਂ ਰੈਂਡਰ ਕਰਨਾ ਸਕ੍ਰੀਨ ਰੀਡਰਾਂ ਨੂੰ ਪੇਜ ਵਿੱਚ ਨੈਵੀਗੇਟ ਕਰਨ ਵਿੱਚ ਮਦਦ ਕਰਦਾ ਹੈ। ਆਮ ਤੌਰ 'ਤੇ, ਬਟਨਾਂ ਨੂੰ `<button>` ਵਜੋਂ ਲਿਖਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ ਅਤੇ ਲਿਸਟਾਂ ਨੂੰ `<li>` ਹੋਣਾ ਚਾਹੀਦਾ ਹੈ। ਜਦੋਂ ਕਿ ਇਹ ਸੰਭਵ ਹੈ ਕਿ specially styled `<span>` ਐਲੀਮੈਂਟਾਂ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਬਟਨਾਂ ਨੂੰ ਮੌਕ ਕੀਤਾ ਜਾਵੇ, ਇਹ ਬਿਹਤਰ ਹੈ ਕਿ ਅਯੋਗ ਯੂਜ਼ਰ ਤਕਨਾਲੋਜੀਆਂ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਪੇਜ ਵਿੱਚ ਬਟਨ ਦੀ ਸਥਿਤੀ ਦਾ ਨਿਰਧਾਰਨ ਕਰਨ ਅਤੇ ਇਸ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਨ ਲਈ, ਜੇ ਐਲੀਮੈਂਟ ਬਟਨ ਵਜੋਂ ਦਿਖਾਈ ਦਿੰਦਾ ਹੈ। ਇਸ ਕਾਰਨ, ਜਿੰਨਾ ਹੋ ਸਕੇ ਸੈਮੈਂਟਿਕ ਮਾਰਕਅਪ ਦੀ ਵਰਤੋਂ ਕਰਨ ਦੀ ਕੋਸ਼ਿਸ਼ ਕਰੋ।

✅ ਇੱਕ ਸਕ੍ਰੀਨ ਰੀਡਰ ਦੇਖੋ ਅਤੇ [ਇਹ ਕਿਵੇਂ ਵੈੱਬ ਪੇਜ ਨਾਲ ਇੰਟਰੈਕਟ ਕਰਦਾ ਹੈ](https://www.youtube.com/watch?v=OUDV1gqs9GA)। ਕੀ ਤੁਸੀਂ ਦੇਖ ਸਕਦੇ ਹੋ ਕਿ ਗੈਰ-ਸੈਮੈਂਟਿਕ ਮਾਰਕਅਪ ਯੂਜ਼ਰ ਨੂੰ ਕਿਉਂ ਨਿਰਾਸ਼ ਕਰ ਸਕਦਾ ਹੈ?

## ਟੈਰੀਰੀਅਮ

ਇਸ ਇੰਟਰਫੇਸ ਦਾ ਆਖਰੀ ਹਿੱਸਾ ਮਾਰਕਅਪ ਬਣਾਉਣ ਵਿੱਚ ਸ਼ਾਮਲ ਹੈ ਜਿਸਨੂੰ ਸਜਾਇਆ ਜਾਵੇਗਾ ਤਾਂ ਜੋ ਇੱਕ ਟੈਰੀਰੀਅਮ ਬਣਾਇਆ ਜਾ ਸਕੇ।

### ਕੰਮ:

ਆਖਰੀ `</div>` ਟੈਗ ਦੇ ਉੱਪਰ ਇਹ ਮਾਰਕਅਪ ਸ਼ਾਮਲ ਕਰੋ:

```html
<div id="terrarium">
	<div class="jar-top"></div>
	<div class="jar-walls">
		<div class="jar-glossy-long"></div>
		<div class="jar-glossy-short"></div>
	</div>
	<div class="dirt"></div>
	<div class="jar-bottom"></div>
</div>
```

✅ ਹਾਲਾਂਕਿ ਤੁਸੀਂ ਸਕ੍ਰੀਨ 'ਤੇ ਇਹ ਮਾਰਕਅਪ ਸ਼ਾਮਲ ਕੀਤਾ ਹੈ, ਤੁਸੀਂ ਬਿਲਕੁਲ ਕੁਝ ਵੀ ਰੈਂਡਰ ਨਹੀਂ ਹੁੰਦਾ ਵੇਖਦੇ। ਕਿਉਂ?

---

## GitHub Copilot Agent ਚੈਲੈਂਜ 🚀

Agent ਮੋਡ ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਹੇਠਾਂ ਦਿੱਤੇ ਚੈਲੈਂਜ ਨੂੰ ਪੂਰਾ ਕਰੋ:

**ਵੇਰਵਾ:** ਟੈਰੀਰੀਅਮ ਪ੍ਰੋਜੈਕਟ ਵਿੱਚ ਸ਼ਾਮਲ ਕਰਨ ਲਈ ਪੌਦੇ ਦੀ ਦੇਖਭਾਲ ਗਾਈਡ ਸੈਕਸ਼ਨ ਲਈ ਇੱਕ ਸੈਮੈਂਟਿਕ HTML ਸਟ੍ਰਕਚਰ ਬਣਾਓ।

**ਪ੍ਰੇਰਣਾ:** ਇੱਕ ਸੈਮੈਂਟਿਕ HTML ਸੈਕਸ਼ਨ ਬਣਾਓ ਜਿਸ ਵਿੱਚ "Plant Care Guide" ਦਾ ਮੁੱਖ ਸਿਰਲੇਖ, "Watering", "Light Requirements", ਅਤੇ "Soil Care" ਦੇ ਤਿੰਨ ਉਪ-ਸੈਕਸ਼ਨ ਸ਼ਾਮਲ ਹਨ, ਹਰ ਇੱਕ ਵਿੱਚ ਪੌਦੇ ਦੀ ਦੇਖਭਾਲ ਦੀ ਜਾਣਕਾਰੀ ਵਾਲਾ ਇੱਕ ਪੈਰਾ ਸ਼ਾਮਲ ਹੈ। ਸਮਰਥਿਤ HTML ਟੈਗਾਂ ਜਿਵੇਂ `<section>`, `<h2>`, `<h3>`, ਅਤੇ `<p>` ਵਰਤ ਕੇ ਸਮੱਗਰੀ ਨੂੰ ਢੰਗ ਨਾਲ ਬਣਾਓ।

## 🚀ਚੈਲੈਂਜ

HTML ਵਿੱਚ ਕੁਝ ਪੁਰਾਣੇ 'ਟੈਗ' ਹਨ ਜੋ ਅਜੇ ਵੀ ਖੇਡਣ ਲਈ ਮਜ਼ੇਦਾਰ ਹਨ, ਹਾਲਾਂਕਿ ਤੁਹਾਨੂੰ ਆਪਣੇ ਮਾਰਕਅਪ ਵਿੱਚ [ਇਹ ਟੈਗ](https://developer.mozilla.org/docs/Web/HTML/Element#Obsolete_and_deprecated_elements) ਵਰਤਣ ਨਹੀਂ ਚਾਹੀਦੇ। ਫਿਰ ਵੀ, ਕੀ ਤੁਸੀਂ ਪੁਰਾਣੇ `<marquee>` ਟੈਗ ਦੀ ਵਰਤੋਂ ਕਰਕੇ h1 ਸਿਰਲੇਖ ਨੂੰ ਆੜ੍ਹੇ ਤੌਰ 'ਤੇ ਸਕ੍ਰੋਲ ਕਰ ਸਕਦੇ ਹੋ? (ਜੇ ਤੁਸੀਂ ਕਰਦੇ ਹੋ, ਤਾਂ ਇਸਨੂੰ ਬਾਅਦ ਵਿੱਚ ਹਟਾਉਣਾ ਨਾ ਭੁੱਲੋ)

## ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵਿਜ਼

[ਲੈਕਚਰ ਤੋਂ ਬਾਅਦ ਕਵਿਜ਼](https://ff-quizzes.netlify.app/web/quiz/16)

## ਸਮੀਖਿਆ ਅਤੇ ਖੁਦ ਅਧਿਐਨ

HTML 'ਤਜਰਬੇਕਾਰ ਅਤੇ ਸੱਚਾ' ਬਿਲਡਿੰਗ ਬਲਾਕ ਸਿਸਟਮ ਹੈ ਜਿਸਨੇ ਵੈੱਬ ਨੂੰ ਅੱਜ ਦੇ ਰੂਪ ਵਿੱਚ ਬਣਾਉਣ ਵਿੱਚ ਮਦਦ ਕੀਤੀ ਹੈ। ਇਸਦੇ ਇਤਿਹਾਸ ਬਾਰੇ ਕੁਝ ਪੁਰਾਣੇ ਅਤੇ ਨਵੇਂ ਟੈਗਾਂ ਦਾ ਅਧਿਐਨ ਕਰਕੇ ਜਾਨੋ। ਕੀ ਤੁਸੀਂ ਪਤਾ ਲਗਾ ਸਕਦੇ ਹੋ ਕਿ ਕੁਝ ਟੈਗ ਕਿਉਂ ਰੱਦ ਕੀਤੇ ਗਏ ਅਤੇ ਕੁਝ ਸ਼ਾਮਲ ਕੀਤੇ ਗਏ? ਭਵਿੱਖ ਵਿੱਚ ਕਿਹੜੇ ਟੈਗ ਸ਼ਾਮਲ ਕੀਤੇ ਜਾ ਸਕਦੇ ਹਨ?

ਵੈੱਬ ਅਤੇ ਮੋਬਾਈਲ ਡਿਵਾਈਸਾਂ ਲਈ ਸਾਈਟਾਂ ਬਣਾਉਣ ਬਾਰੇ ਹੋਰ ਜਾਣੋ [Microsoft Learn](https://docs.microsoft.com/learn/modules/build-simple-website/?WT.mc_id=academic-77807-sagibbon) 'ਤੇ।

## ਅਸਾਈਨਮੈਂਟ

[ਆਪਣੇ HTML ਦਾ ਅਭਿਆਸ ਕਰੋ: ਇੱਕ ਬਲੌਗ ਮੌਕਅਪ ਬਣਾਓ](assignment.md)

---

**ਅਸਵੀਕਰਤਾ**:  
ਇਹ ਦਸਤਾਵੇਜ਼ AI ਅਨੁਵਾਦ ਸੇਵਾ [Co-op Translator](https://github.com/Azure/co-op-translator) ਦੀ ਵਰਤੋਂ ਕਰਕੇ ਅਨੁਵਾਦ ਕੀਤਾ ਗਿਆ ਹੈ। ਜਦੋਂ ਕਿ ਅਸੀਂ ਸਹੀ ਹੋਣ ਦਾ ਯਤਨ ਕਰਦੇ ਹਾਂ, ਕਿਰਪਾ ਕਰਕੇ ਧਿਆਨ ਦਿਓ ਕਿ ਸਵੈਚਾਲਿਤ ਅਨੁਵਾਦਾਂ ਵਿੱਚ ਗਲਤੀਆਂ ਜਾਂ ਅਸੁੱਤੀਆਂ ਹੋ ਸਕਦੀਆਂ ਹਨ। ਇਸ ਦੀ ਮੂਲ ਭਾਸ਼ਾ ਵਿੱਚ ਮੂਲ ਦਸਤਾਵੇਜ਼ ਨੂੰ ਅਧਿਕਾਰਤ ਸਰੋਤ ਮੰਨਿਆ ਜਾਣਾ ਚਾਹੀਦਾ ਹੈ। ਮਹੱਤਵਪੂਰਨ ਜਾਣਕਾਰੀ ਲਈ, ਪੇਸ਼ੇਵਰ ਮਨੁੱਖੀ ਅਨੁਵਾਦ ਦੀ ਸਿਫਾਰਸ਼ ਕੀਤੀ ਜਾਂਦੀ ਹੈ। ਇਸ ਅਨੁਵਾਦ ਦੀ ਵਰਤੋਂ ਤੋਂ ਪੈਦਾ ਹੋਣ ਵਾਲੇ ਕਿਸੇ ਵੀ ਗਲਤਫਹਿਮੀ ਜਾਂ ਗਲਤ ਵਿਆਖਿਆ ਲਈ ਅਸੀਂ ਜ਼ਿੰਮੇਵਾਰ ਨਹੀਂ ਹਾਂ।