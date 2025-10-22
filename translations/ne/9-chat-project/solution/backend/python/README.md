<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "0aaa930f076f2d83cc872ad157f8ffd3",
  "translation_date": "2025-10-22T16:57:22+00:00",
  "source_file": "9-chat-project/solution/backend/python/README.md",
  "language_code": "ne"
}
-->
# कोड चलाउनुहोस्

## सेट अप

भर्चुअल वातावरण बनाउनुहोस्

```sh
python -m venv venv
source ./venv/bin/activate
```

## निर्भरता स्थापना गर्नुहोस्

```sh
pip install openai fastapi uvicorn python-dotenv
```

## API चलाउनुहोस्

```sh
# Method 1: Direct execution
python api.py

# Method 2: Using uvicorn
uvicorn api:app --host 0.0.0.0 --port 5000 --reload
```

## API परीक्षण गर्नुहोस्

इन्टरएक्टिभ API डकुमेन्टेशनमा जानुहोस्: `http://localhost:5000/docs`

## फ्रन्टएन्ड चलाउनुहोस्

फ्रन्टएन्ड फोल्डरमा उभिनुहोस्

*app.js* फाइल खोज्नुहोस्, `BASE_URL` लाई तपाईंको ब्याकएन्ड URL मा परिवर्तन गर्नुहोस्

यसलाई चलाउनुहोस्

```
npx http-server -p 8000
```

च्याटमा सन्देश टाइप गर्न प्रयास गर्नुहोस्, तपाईंले प्रतिक्रिया देख्नुहुनेछ (यदि तपाईंले यो Codespace मा चलाउनु भएको छ वा पहुँच टोकन सेट अप गर्नुभएको छ भने)।

## पहुँच टोकन सेट अप गर्नुहोस् (यदि तपाईंले यो Codespace मा चलाउनुहुन्न भने)

[PAT सेट अप गर्नुहोस्](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) हेर्नुहोस्

---

**अस्वीकरण**:  
यो दस्तावेज AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको छ। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया ध्यान दिनुहोस् कि स्वचालित अनुवादहरूमा त्रुटिहरू वा अशुद्धताहरू हुन सक्छ। यसको मूल भाषा मा रहेको दस्तावेजलाई आधिकारिक स्रोत मानिनुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न हुने कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुनेछैनौं।