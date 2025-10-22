<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "46d665af66e51524598af34a42b9b663",
  "translation_date": "2025-10-22T14:12:57+00:00",
  "source_file": "9-chat-project/README.md",
  "language_code": "ar"
}
-->
# بناء مساعد دردشة باستخدام الذكاء الاصطناعي

هل تتذكر في مسلسل "ستار تريك" عندما كان الطاقم يتحدث بشكل عادي مع كمبيوتر السفينة، يطرحون عليه أسئلة معقدة ويحصلون على إجابات مدروسة؟ ما كان يبدو كخيال علمي في الستينيات أصبح الآن شيئًا يمكنك بناؤه باستخدام تقنيات الويب التي تعرفها بالفعل.

في هذه الدرس، سنقوم بإنشاء مساعد دردشة بالذكاء الاصطناعي باستخدام HTML، CSS، JavaScript وبعض التكامل الخلفي. ستكتشف كيف يمكن للمهارات التي تعلمتها أن تتصل بخدمات ذكاء اصطناعي قوية تفهم السياق وتولد ردودًا ذات معنى.

فكر في الذكاء الاصطناعي كأنه مكتبة ضخمة يمكنها ليس فقط العثور على المعلومات ولكن أيضًا صياغتها في إجابات متماسكة ومخصصة لأسئلتك المحددة. بدلاً من البحث في آلاف الصفحات، تحصل على ردود مباشرة وسياقية.

يحدث التكامل من خلال تقنيات الويب المألوفة التي تعمل معًا. HTML ينشئ واجهة الدردشة، CSS يتولى التصميم البصري، JavaScript يدير التفاعلات مع المستخدم، وواجهة برمجية خلفية تربط كل شيء بخدمات الذكاء الاصطناعي. يشبه الأمر كيف تعمل أقسام مختلفة من الأوركسترا معًا لتكوين سيمفونية.

نحن نبني جسرًا بين التواصل البشري الطبيعي ومعالجة الآلة. ستتعلم التنفيذ الفني لتكامل خدمات الذكاء الاصطناعي وأنماط التصميم التي تجعل التفاعلات تبدو بديهية.

بنهاية هذا الدرس، سيصبح تكامل الذكاء الاصطناعي أقل غموضًا وأكثر كأنه واجهة برمجية أخرى يمكنك العمل معها. ستفهم الأنماط الأساسية التي تشغل تطبيقات مثل ChatGPT وClaude باستخدام نفس مبادئ تطوير الويب التي تعلمتها.

إليك كيف سيبدو مشروعك النهائي:

![واجهة تطبيق الدردشة تظهر محادثة بين المستخدم ومساعد الذكاء الاصطناعي](../../../translated_images/screenshot.0a1ee0d123df681b4501eb53ffb267519fcc20aa653eabecef1e7561ddfb1cab.ar.png)

## فهم الذكاء الاصطناعي: من الغموض إلى الإتقان

قبل الغوص في الكود، دعونا نفهم ما نعمل عليه. إذا كنت قد استخدمت واجهات برمجية من قبل، فأنت تعرف النمط الأساسي: إرسال طلب، تلقي استجابة.

واجهات برمجية الذكاء الاصطناعي تتبع هيكلًا مشابهًا، ولكن بدلاً من استرجاع بيانات مخزنة مسبقًا من قاعدة بيانات، فإنها تولد ردودًا جديدة بناءً على أنماط تعلمتها من كميات هائلة من النصوص. فكر في الأمر كأنه الفرق بين نظام فهرسة مكتبة وأمين مكتبة يعرف كيفية صياغة المعلومات من مصادر متعددة.

### ما هو "الذكاء الاصطناعي التوليدي" حقًا؟

فكر في كيف سمحت حجر رشيد للعلماء بفهم الهيروغليفية المصرية من خلال العثور على أنماط بين اللغات المعروفة وغير المعروفة. نماذج الذكاء الاصطناعي تعمل بطريقة مشابهة – فهي تجد أنماطًا في كميات هائلة من النصوص لفهم كيفية عمل اللغة، ثم تستخدم تلك الأنماط لتوليد ردود مناسبة على أسئلة جديدة.

**دعني أوضح هذا بمقارنة بسيطة:**
- **قاعدة بيانات تقليدية**: مثل طلب شهادة ميلادك – تحصل على نفس الوثيقة في كل مرة
- **محرك بحث**: مثل طلب أمين مكتبة العثور على كتب عن القطط – يظهر لك ما هو متاح
- **الذكاء الاصطناعي التوليدي**: مثل سؤال صديق مطلع عن القطط – يخبرك بأشياء مثيرة للاهتمام بكلماته الخاصة، مخصصة لما تريد معرفته

```mermaid
graph LR
    A[Your Question] --> B[AI Model]
    B --> C[Pattern Recognition]
    C --> D[Content Generation]
    D --> E[Contextual Response]
    
    F[Training Data<br/>Books, Articles, Web] --> B
```

### كيف تتعلم نماذج الذكاء الاصطناعي (النسخة البسيطة)

تتعلم نماذج الذكاء الاصطناعي من خلال التعرض لمجموعات بيانات ضخمة تحتوي على نصوص من كتب، مقالات، ومحادثات. من خلال هذه العملية، تحدد الأنماط في:
- كيفية هيكلة الأفكار في التواصل الكتابي
- الكلمات التي تظهر عادةً معًا
- كيفية تدفق المحادثات عادةً
- الفروقات السياقية بين التواصل الرسمي وغير الرسمي

**يشبه الأمر كيف يفك علماء الآثار رموز اللغات القديمة**: يحللون آلاف الأمثلة لفهم القواعد، المفردات، والسياق الثقافي، ليصبحوا في النهاية قادرين على تفسير نصوص جديدة باستخدام تلك الأنماط المكتسبة.

### لماذا نماذج GitHub؟

نستخدم نماذج GitHub لسبب عملي جدًا – فهي تمنحنا الوصول إلى ذكاء اصطناعي على مستوى المؤسسات دون الحاجة إلى إعداد بنية تحتية للذكاء الاصطناعي الخاصة بنا (والتي، صدقني، لا تريد القيام بها الآن!). فكر في الأمر كأنه استخدام واجهة برمجية للطقس بدلاً من محاولة التنبؤ بالطقس بنفسك عن طريق إعداد محطات الطقس في كل مكان.

إنه أساسًا "الذكاء الاصطناعي كخدمة"، وأفضل جزء؟ يمكنك البدء مجانًا، لذا يمكنك التجربة دون القلق بشأن تكاليف كبيرة.

```mermaid
graph LR
    A[Frontend Chat UI] --> B[Your Backend API]
    B --> C[GitHub Models API]
    C --> D[AI Model Processing]
    D --> C
    C --> B
    B --> A
```

سنستخدم نماذج GitHub لتكاملنا الخلفي، والتي توفر الوصول إلى قدرات ذكاء اصطناعي على مستوى احترافي من خلال واجهة سهلة الاستخدام للمطورين. [GitHub Models Playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground) يعمل كبيئة اختبار حيث يمكنك تجربة نماذج ذكاء اصطناعي مختلفة وفهم قدراتها قبل تنفيذها في الكود.

![واجهة GitHub Models AI Playground مع اختيار النموذج ومنطقة الاختبار](../../../translated_images/playground.d2b927122224ff8ff4028fc842176e353c339147d8925455f36c92fb1655c477.ar.png)

**إليك ما يجعل الملعب مفيدًا للغاية:**
- **جرب** نماذج ذكاء اصطناعي مختلفة مثل GPT-4o-mini، Claude، وغيرها (كلها مجانية!)
- **اختبر** أفكارك ومطالباتك قبل كتابة أي كود
- **احصل على** مقتطفات كود جاهزة للاستخدام بلغتك البرمجية المفضلة
- **عدل** الإعدادات مثل مستوى الإبداع وطول الرد لترى كيف تؤثر على النتائج

بمجرد أن تجرب قليلاً، فقط انقر على علامة التبويب "Code" واختر لغتك البرمجية للحصول على كود التنفيذ الذي تحتاجه.

![اختيار الملعب يظهر خيارات توليد الكود للغات البرمجة المختلفة](../../../translated_images/playground-choice.1d23ba7d407f47584c9f446c77f0bcf70cae794cc9c8d7849a3cca4a3693e6c4.ar.png)

## إعداد تكامل الخلفية باستخدام Python

الآن دعونا ننفذ التكامل مع الذكاء الاصطناعي باستخدام Python. Python ممتازة لتطبيقات الذكاء الاصطناعي بسبب بساطة صياغتها ومكتباتها القوية. سنبدأ بالكود من ملعب نماذج GitHub ثم نعيد صياغته ليصبح وظيفة قابلة لإعادة الاستخدام وجاهزة للإنتاج.

### فهم التنفيذ الأساسي

عندما تحصل على كود Python من الملعب، سيبدو شيئًا كهذا. لا تقلق إذا بدا كثيرًا في البداية – دعونا نمر عليه خطوة بخطوة:

```python
"""Run this model in Python

> pip install openai
"""
import os
from openai import OpenAI

# To authenticate with the model you will need to generate a personal access token (PAT) in your GitHub settings. 
# Create your PAT token by following instructions here: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens
client = OpenAI(
    base_url="https://models.github.ai/inference",
    api_key=os.environ["GITHUB_TOKEN"],
)

```python
response = client.chat.completions.create(
    messages=[
        {
            "role": "system",
            "content": "",
        },
        {
            "role": "user",
            "content": "What is the capital of France?",
        }
    ],
    model="openai/gpt-4o-mini",
    temperature=1,
    max_tokens=4096,
    top_p=1
)

print(response.choices[0].message.content)
```

**إليك ما يحدث في هذا الكود:**
- **نستورد** الأدوات التي نحتاجها: `os` لقراءة متغيرات البيئة و`OpenAI` للتواصل مع الذكاء الاصطناعي
- **نقوم بإعداد** عميل OpenAI للإشارة إلى خوادم الذكاء الاصطناعي الخاصة بـ GitHub بدلاً من OpenAI مباشرة
- **نقوم بالمصادقة** باستخدام رمز GitHub خاص (المزيد عن ذلك لاحقًا!)
- **نهيكل** محادثتنا بأدوار مختلفة – فكر فيها كأنك تعد مشهدًا لمسرحية
- **نرسل** طلبنا إلى الذكاء الاصطناعي مع بعض معلمات الضبط الدقيقة
- **نستخرج** النص الفعلي للرد من جميع البيانات التي تعود

### فهم أدوار الرسائل: إطار عمل المحادثة مع الذكاء الاصطناعي

المحادثات مع الذكاء الاصطناعي تستخدم هيكلًا محددًا بأدوار مختلفة تخدم أغراضًا متميزة:

```python
messages=[
    {
        "role": "system",
        "content": "You are a helpful assistant who explains things simply."
    },
    {
        "role": "user", 
        "content": "What is machine learning?"
    }
]
```

**فكر فيها كأنك توجه مسرحية:**
- **دور النظام**: مثل تعليمات المسرح للممثل – يخبر الذكاء الاصطناعي كيف يتصرف، وما الشخصية التي يجب أن يتبناها، وكيف يرد
- **دور المستخدم**: السؤال الفعلي أو الرسالة من الشخص الذي يستخدم التطبيق
- **دور المساعد**: رد الذكاء الاصطناعي (لا ترسله، لكنه يظهر في تاريخ المحادثة)

**تشبيه في العالم الحقيقي**: تخيل أنك تقدم صديقًا لشخص ما في حفلة:
- **رسالة النظام**: "هذا صديقي سارة، هي طبيبة رائعة في شرح المفاهيم الطبية بطريقة بسيطة"
- **رسالة المستخدم**: "هل يمكنك شرح كيفية عمل اللقاحات؟"
- **رد المساعد**: سارة ترد كطبيبة ودودة، وليس كمحامية أو طاهية

### فهم معلمات الذكاء الاصطناعي: ضبط سلوك الرد

المعلمات الرقمية في طلبات واجهات برمجية الذكاء الاصطناعي تتحكم في كيفية توليد النموذج للردود. هذه الإعدادات تسمح لك بضبط سلوك الذكاء الاصطناعي لحالات استخدام مختلفة:

#### درجة الحرارة (0.0 إلى 2.0): مؤشر الإبداع

**ما الذي تفعله**: تتحكم في مدى إبداع أو توقع ردود الذكاء الاصطناعي.

**فكر فيها كأنها مستوى ارتجال عازف الجاز:**
- **درجة الحرارة = 0.1**: يعزف نفس اللحن تمامًا في كل مرة (متوقع للغاية)
- **درجة الحرارة = 0.7**: يضيف بعض التغييرات اللطيفة مع البقاء مألوفًا (إبداع متوازن)
- **درجة الحرارة = 1.5**: ارتجال كامل مع منعطفات غير متوقعة (غير متوقع للغاية)

```python
# Very predictable responses (good for factual questions)
response = client.chat.completions.create(
    messages=[{"role": "user", "content": "What is 2+2?"}],
    temperature=0.1  # Will almost always say "4"
)

# Creative responses (good for brainstorming)
response = client.chat.completions.create(
    messages=[{"role": "user", "content": "Write a creative story opening"}],
    temperature=1.2  # Will generate unique, unexpected stories
)
```

#### الحد الأقصى للرموز (1 إلى 4096+): التحكم في طول الرد

**ما الذي تفعله**: تحدد حدًا لطول رد الذكاء الاصطناعي.

**فكر في الرموز كأنها تعادل الكلمات تقريبًا** (حوالي 1 رمز = 0.75 كلمة في الإنجليزية):
- **max_tokens=50**: قصير وموجز (مثل رسالة نصية)
- **max_tokens=500**: فقرة أو اثنتين
- **max_tokens=2000**: شرح مفصل مع أمثلة

```python
# Short, concise answers
response = client.chat.completions.create(
    messages=[{"role": "user", "content": "Explain JavaScript"}],
    max_tokens=100  # Forces a brief explanation
)

# Detailed, comprehensive answers  
response = client.chat.completions.create(
    messages=[{"role": "user", "content": "Explain JavaScript"}],
    max_tokens=1500  # Allows for detailed explanations with examples
)
```

#### Top_p (0.0 إلى 1.0): مؤشر التركيز

**ما الذي تفعله**: تتحكم في مدى تركيز الذكاء الاصطناعي على الردود الأكثر احتمالًا.

**تخيل الذكاء الاصطناعي لديه مفردات ضخمة، مرتبة حسب مدى احتمال كل كلمة:**
- **top_p=0.1**: يأخذ في الاعتبار أعلى 10% من الكلمات الأكثر احتمالًا (مركز جدًا)
- **top_p=0.9**: يأخذ في الاعتبار 90% من الكلمات الممكنة (أكثر إبداعًا)
- **top_p=1.0**: يأخذ في الاعتبار كل شيء (أقصى تنوع)

**على سبيل المثال**: إذا سألت "السماء عادةً..."
- **Top_p منخفض**: يقول "زرقاء" بالتأكيد
- **Top_p مرتفع**: قد يقول "زرقاء"، "غائمة"، "واسعة"، "متغيرة"، "جميلة"، إلخ.

### الجمع بين كل شيء: تركيبات المعلمات لحالات استخدام مختلفة

```python
# For factual, consistent answers (like a documentation bot)
factual_params = {
    "temperature": 0.2,
    "max_tokens": 300,
    "top_p": 0.3
}

# For creative writing assistance
creative_params = {
    "temperature": 1.1,
    "max_tokens": 1000,
    "top_p": 0.9
}

# For conversational, helpful responses (balanced)
conversational_params = {
    "temperature": 0.7,
    "max_tokens": 500,
    "top_p": 0.8
}
```

**فهم لماذا هذه المعلمات مهمة**: التطبيقات المختلفة تحتاج إلى أنواع مختلفة من الردود. بوت خدمة العملاء يجب أن يكون متسقًا وواقعيًا (درجة حرارة منخفضة)، بينما مساعد الكتابة الإبداعية يجب أن يكون خياليًا ومتغيرًا (درجة حرارة عالية). فهم هذه المعلمات يمنحك التحكم في شخصية الذكاء الاصطناعي وأسلوب الرد.

```

**Here's what's happening in this code:**
- **We import** the tools we need: `os` for reading environment variables and `OpenAI` for talking to the AI
- **We set up** the OpenAI client to point to GitHub's AI servers instead of OpenAI directly
- **We authenticate** using a special GitHub token (more on that in a minute!)
- **We structure** our conversation with different "roles" – think of it like setting the scene for a play
- **We send** our request to the AI with some fine-tuning parameters
- **We extract** the actual response text from all the data that comes back

> 🔐 **Security Note**: Never hardcode API keys in your source code! Always use environment variables to store sensitive credentials like your `GITHUB_TOKEN`.

### Creating a Reusable AI Function

Let's refactor this code into a clean, reusable function that we can easily integrate into our web application:

```python
import asyncio
from openai import AsyncOpenAI

# Use AsyncOpenAI for better performance
client = AsyncOpenAI(
    base_url="https://models.github.ai/inference",
    api_key=os.environ["GITHUB_TOKEN"],
)

async def call_llm_async(prompt: str, system_message: str = "You are a helpful assistant."):
    """
    Sends a prompt to the AI model asynchronously and returns the response.
    
    Args:
        prompt: The user's question or message
        system_message: Instructions that define the AI's behavior and personality
    
    Returns:
        str: The AI's response to the prompt
    """
    try:
        response = await client.chat.completions.create(
            messages=[
                {
                    "role": "system",
                    "content": system_message,
                },
                {
                    "role": "user",
                    "content": prompt,
                }
            ],
            model="openai/gpt-4o-mini",
            temperature=1,
            max_tokens=4096,
            top_p=1
        )
        return response.choices[0].message.content
    except Exception as e:
        logger.error(f"AI API error: {str(e)}")
        return "I'm sorry, I'm having trouble processing your request right now."

# Backward compatibility function for synchronous calls
def call_llm(prompt: str, system_message: str = "You are a helpful assistant."):
    """Synchronous wrapper for async AI calls."""
    return asyncio.run(call_llm_async(prompt, system_message))
```

**فهم هذه الوظيفة المحسنة:**
- **تقبل** معلمين: طلب المستخدم ورسالة النظام الاختيارية
- **توفر** رسالة نظام افتراضية لسلوك مساعد عام
- **تستخدم** تلميحات نوع Python لتحسين توثيق الكود
- **تتضمن** وصفًا تفصيليًا للوظيفة يشرح الغرض منها ومعلماتها
- **تعيد** فقط محتوى الرد، مما يجعل استخدامها في واجهة برمجية الويب سهلًا
- **تحافظ** على نفس معلمات النموذج لسلوك ذكاء اصطناعي متسق

### سحر رسائل النظام: برمجة شخصية الذكاء الاصطناعي

إذا كانت المعلمات تتحكم في كيفية تفكير الذكاء الاصطناعي، فإن رسائل النظام تتحكم في من يعتقد الذكاء الاصطناعي أنه هو. هذا بصراحة أحد أكثر الأجزاء إثارة للعمل مع الذكاء الاصطناعي – أنت في الأساس تمنح الذكاء الاصطناعي شخصية كاملة، مستوى خبرة، وأسلوب تواصل.

**فكر في رسائل النظام كأنها اختيار ممثلين لأدوار مختلفة**: بدلًا من وجود مساعد عام، يمكنك إنشاء خبراء متخصصين لحالات مختلفة. تحتاج إلى معلم صبور؟ شريك إبداعي في العصف الذهني؟ مستشار أعمال جاد؟ فقط قم بتغيير رسالة النظام!

#### لماذا رسائل النظام قوية جدًا

إليك الجزء المثير: تم تدريب نماذج الذكاء الاصطناعي على عدد لا يحصى من المحادثات حيث يتبنى الناس أدوارًا ومستويات خبرة مختلفة. عندما تعطي الذكاء الاصطناعي دورًا معينًا، يشبه الأمر تشغيل مفتاح ينشط كل تلك الأنماط المكتسبة.

**يشبه التمثيل المنهجي للذكاء الاصطناعي**: أخبر ممثلًا "أنت أستاذ حكيم كبير في السن" وشاهد كيف يضبط تلقائيًا وضعه، مفرداته، وسلوكياته. الذكاء الاصطناعي يفعل شيئًا مشابهًا بشكل ملحوظ مع أنماط اللغة.

#### صياغة رسائل نظام فعالة: الفن والعلم

**تشريح رسالة نظام رائعة:**
1. **الدور/الهوية**: من هو الذكاء الاصطناعي؟
2. **الخبرة**: ماذا يعرف؟
3. **أسلوب التواصل**: كيف يتحدث؟
4. **تعليمات محددة**: على ماذا يجب أن يركز؟

```python
# ❌ Vague system prompt
"You are helpful."

# ✅ Detailed, effective system prompt
"You are Dr. Sarah Chen, a senior software engineer with 15 years of experience at major tech companies. You explain programming concepts using real-world analogies and always provide practical examples. You're patient with beginners and enthusiastic about helping them understand complex topics."
```

#### أمثلة رسائل النظام مع السياق

دعونا نرى كيف تخلق رسائل النظام المختلفة شخصيات ذكاء اصطناعي مختلفة تمامًا:

```python
# Example 1: The Patient Teacher
teacher_prompt = """
You are an experienced programming instructor who has taught thousands of students. 
You break down complex concepts into simple steps, use analogies from everyday life, 
and always check if the student understands before moving on. You're encouraging 
and never make students feel bad for not knowing something.
"""

# Example 2: The Creative Collaborator  
creative_prompt = """
You are a creative writing partner who loves brainstorming wild ideas. You're 
enthusiastic, imaginative, and always build on the user's ideas rather than 
replacing them. You ask thought-provoking questions to spark creativity and 
offer unexpected perspectives that make stories more interesting.
"""

# Example 3: The Strategic Business Advisor
business_prompt = """
You are a strategic business consultant with an MBA and 20 years of experience 
helping startups scale. You think in frameworks, provide structured advice, 
and always consider both short-term tactics and long-term strategy. You ask 
probing questions to understand the full business context before giving advice.
"""
```

#### رؤية رسائل النظام أثناء العمل

لنختبر نفس السؤال مع رسائل نظام مختلفة لنرى الفروقات الكبيرة:

**السؤال**: "كيف أتعامل مع مصادقة المستخدم في تطبيقي الويب؟"

```python
# With teacher prompt:
teacher_response = call_llm(
    "How do I handle user authentication in my web app?",
    teacher_prompt
)
# Typical response: "Great question! Let's break authentication down into simple steps. 
# Think of it like a nightclub bouncer checking IDs..."

# With business prompt:
business_response = call_llm(
    "How do I handle user authentication in my web app?", 
    business_prompt
)
# Typical response: "From a strategic perspective, authentication is crucial for user 
# trust and regulatory compliance. Let me outline a framework considering security, 
# user experience, and scalability..."
```

#### تقنيات متقدمة لرسائل النظام

**1. إعداد السياق**: أعط الذكاء الاصطناعي معلومات خلفية
```python
system_prompt = """
You are helping a junior developer who just started their first job at a startup. 
They know basic HTML/CSS/JavaScript but are new to backend development and databases. 
Be encouraging and explain things step-by-step without being condescending.
"""
```

**2. تنسيق الإخراج**: أخبر الذكاء الاصطناعي كيف يهيكل الردود
```python
system_prompt = """
You are a technical mentor. Always structure your responses as:
1. Quick Answer (1-2 sentences)
2. Detailed Explanation 
3. Code Example
4. Common Pitfalls to Avoid
5. Next Steps for Learning
"""
```

**3. إعداد القيود**: حدد ما يجب أن لا يفعله الذكاء الاصطناعي
```python
system_prompt = """
You are a coding tutor focused on teaching best practices. Never write complete 
solutions for the user - instead, guide them with hints and questions so they 
learn by doing. Always explain the 'why' behind coding decisions.
"""
```

#### لماذا هذا مهم لمساعد الدردشة الخاص بك

فهم رسائل النظام يمنحك قوة هائلة لإنشاء مساعدين ذكاء اصطناعي متخصصين:
- **بوت خدمة العملاء**: مفيد، صبور، واعٍ بالسياسات
- **مدرس تعليمي**: مشجع، خطوة بخطوة، يتحقق من الفهم
- **شريك إبداعي**: خيالي، يبني على الأفكار، يسأل "ماذا لو؟"
- **خبير تقني**: دقيق، مفصل، واعٍ بالأمان

**الفكرة الرئيسية**: أنت لا تستدعي واجهة برمجية ذكاء اصطناعي فقط – أنت تصنع شخصية ذكاء اصطناعي مخصصة تخدم حالة الاستخدام الخاصة بك. هذا ما يجعل تطبيقات الذكاء الاصطناعي الحديثة تبدو مخصصة ومفيدة بدلًا من أن تكون عامة.

## بناء واجهة برمجية الويب باستخدام FastAPI: مركز اتصال عالي الأداء مع الذكاء الاصطناعي

الآن دعونا نبني الخلفية التي تربط واجهة المستخدم بخدمات الذكاء الاصطناعي. سنستخدم FastAPI، إطار عمل Python حديث يتميز ببناء واجهات برمجية لتطبيقات الذكاء الاصطناعي.

FastAPI يقدم عدة مزايا لهذا النوع من المشاريع: دعم مدمج للعمليات غير المتزامنة لمعالجة الطلبات المتزامنة، توليد تلقائي لتوثيق الواجهة البرمجية، وأداء ممتاز. يعمل خادم FastAPI كوسيط يستقبل الطلبات من الواجهة الأمامية، يتواصل مع خدمات الذكاء الاصطناعي، ويعيد الردود المهيكلة.

### لماذا FastAPI لتطبيقات الذكاء الاصطناعي؟

قد تتساءل: "ألا يمكنني فقط استدعاء الذكاء الاصطناعي مباشرة من JavaScript في الواجهة الأمامية؟" أو "لماذا FastAPI بدلًا من Flask أو Django؟" أسئلة رائعة!
**لماذا FastAPI مثالي لما نقوم ببنائه:**
- **البرمجة غير المتزامنة بشكل افتراضي**: يمكنه التعامل مع طلبات متعددة للذكاء الاصطناعي في نفس الوقت دون التعطل
- **توثيق تلقائي**: قم بزيارة `/docs` واحصل على صفحة توثيق API تفاعلية وجميلة مجانًا
- **التحقق المدمج**: يكتشف الأخطاء قبل أن تسبب مشاكل
- **سرعة فائقة**: من أسرع أطر العمل في Python
- **Python حديث**: يستخدم أحدث ميزات Python وأفضلها

**لماذا نحتاج إلى واجهة خلفية أساسًا:**

**الأمان**: مفتاح API الخاص بالذكاء الاصطناعي يشبه كلمة المرور – إذا وضعته في JavaScript في الواجهة الأمامية، يمكن لأي شخص يرى كود المصدر لموقعك سرقته واستخدام أرصدة الذكاء الاصطناعي الخاصة بك. الواجهة الخلفية تحافظ على أمان البيانات الحساسة.

**الحد من الطلبات والتحكم**: تتيح لك الواجهة الخلفية التحكم في عدد مرات إرسال المستخدمين للطلبات، تنفيذ مصادقة المستخدم، وإضافة تسجيل لتتبع الاستخدام.

**معالجة البيانات**: قد ترغب في حفظ المحادثات، تصفية المحتوى غير المناسب، أو دمج خدمات ذكاء اصطناعي متعددة. الواجهة الخلفية هي المكان الذي تعيش فيه هذه المنطقية.

**تشبه البنية نموذج العميل-الخادم:**
- **الواجهة الأمامية**: طبقة واجهة المستخدم للتفاعل
- **واجهة API الخلفية**: طبقة معالجة الطلبات والتوجيه
- **خدمة الذكاء الاصطناعي**: الحساب الخارجي وتوليد الردود
- **متغيرات البيئة**: تخزين آمن للإعدادات والبيانات السرية

### فهم تدفق الطلب والاستجابة

دعونا نتتبع ما يحدث عندما يرسل المستخدم رسالة:

```mermaid
sequenceDiagram
    participant User as 👤 User
    participant Frontend as 🌐 Frontend
    participant API as 🔧 FastAPI Server
    participant AI as 🤖 AI Service
    
    User->>Frontend: Types "Hello AI!"
    Frontend->>API: POST /hello {"message": "Hello AI!"}
    Note over API: Validates request<br/>Adds system prompt
    API->>AI: Sends formatted request
    AI->>API: Returns AI response
    Note over API: Processes response<br/>Logs conversation
    API->>Frontend: {"response": "Hello! How can I help?"}
    Frontend->>User: Displays AI message
```

**فهم كل خطوة:**
1. **تفاعل المستخدم**: يكتب الشخص في واجهة الدردشة
2. **معالجة الواجهة الأمامية**: يلتقط JavaScript الإدخال ويقوم بتنسيقه كـ JSON
3. **التحقق من الطلب**: يقوم FastAPI بالتحقق تلقائيًا من الطلب باستخدام نماذج Pydantic
4. **دمج الذكاء الاصطناعي**: تضيف الواجهة الخلفية السياق (النظام الأساسي) وتستدعي خدمة الذكاء الاصطناعي
5. **معالجة الردود**: تتلقى API رد الذكاء الاصطناعي ويمكن تعديلها إذا لزم الأمر
6. **عرض الواجهة الأمامية**: يعرض JavaScript الرد في واجهة الدردشة

### فهم بنية API

```mermaid
sequenceDiagram
    participant Frontend
    participant FastAPI
    participant AI Function
    participant GitHub Models
    
    Frontend->>FastAPI: POST /hello {"message": "Hello AI!"}
    FastAPI->>AI Function: call_llm(message, system_prompt)
    AI Function->>GitHub Models: API request
    GitHub Models->>AI Function: AI response
    AI Function->>FastAPI: response text
    FastAPI->>Frontend: {"response": "Hello! How can I help?"}
```

### إنشاء تطبيق FastAPI

دعونا نبني API خطوة بخطوة. قم بإنشاء ملف يسمى `api.py` مع الكود التالي لـ FastAPI:

```python
# api.py
from fastapi import FastAPI, HTTPException
from fastapi.middleware.cors import CORSMiddleware
from pydantic import BaseModel
from llm import call_llm
import logging

# Configure logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

# Create FastAPI application
app = FastAPI(
    title="AI Chat API",
    description="A high-performance API for AI-powered chat applications",
    version="1.0.0"
)

# Configure CORS
app.add_middleware(
    CORSMiddleware,
    allow_origins=["*"],  # Configure appropriately for production
    allow_credentials=True,
    allow_methods=["*"],
    allow_headers=["*"],
)

# Pydantic models for request/response validation
class ChatMessage(BaseModel):
    message: str

class ChatResponse(BaseModel):
    response: str

@app.get("/")
async def root():
    """Root endpoint providing API information."""
    return {
        "message": "Welcome to the AI Chat API",
        "docs": "/docs",
        "health": "/health"
    }

@app.get("/health")
async def health_check():
    """Health check endpoint."""
    return {"status": "healthy", "service": "ai-chat-api"}

@app.post("/hello", response_model=ChatResponse)
async def chat_endpoint(chat_message: ChatMessage):
    """Main chat endpoint that processes messages and returns AI responses."""
    try:
        # Extract and validate message
        message = chat_message.message.strip()
        if not message:
            raise HTTPException(status_code=400, detail="Message cannot be empty")
        
        logger.info(f"Processing message: {message[:50]}...")
        
        # Call AI service (note: call_llm should be made async for better performance)
        ai_response = await call_llm_async(message, "You are a helpful and friendly assistant.")
        
        logger.info("AI response generated successfully")
        return ChatResponse(response=ai_response)
        
    except HTTPException:
        raise
    except Exception as e:
        logger.error(f"Error processing chat message: {str(e)}")
        raise HTTPException(status_code=500, detail="Internal server error")

if __name__ == "__main__":
    import uvicorn
    uvicorn.run(app, host="0.0.0.0", port=5000, reload=True)
```

**فهم تنفيذ FastAPI:**
- **يستورد** FastAPI لوظائف إطار العمل الحديث وPydantic للتحقق من البيانات
- **ينشئ** توثيق API تلقائي (متاح في `/docs` عند تشغيل الخادم)
- **يُمكّن** CORS middleware للسماح بطلبات الواجهة الأمامية من أصول مختلفة
- **يُعرّف** نماذج Pydantic للتحقق التلقائي من الطلبات/الردود والتوثيق
- **يستخدم** نقاط نهاية غير متزامنة لتحسين الأداء مع الطلبات المتزامنة
- **ينفذ** رموز حالة HTTP المناسبة ومعالجة الأخطاء باستخدام HTTPException
- **يتضمن** تسجيل منظم للمراقبة وتصحيح الأخطاء
- **يوفر** نقطة تحقق صحية لمراقبة حالة الخدمة

**مزايا FastAPI الرئيسية مقارنة بالأطر التقليدية:**
- **التحقق التلقائي**: تضمن نماذج Pydantic سلامة البيانات قبل المعالجة
- **توثيق تفاعلي**: قم بزيارة `/docs` للحصول على توثيق API تلقائي وقابل للاختبار
- **سلامة الأنواع**: تمنع تلميحات الأنواع في Python الأخطاء أثناء التشغيل وتحسن جودة الكود
- **دعم البرمجة غير المتزامنة**: التعامل مع طلبات الذكاء الاصطناعي المتعددة في نفس الوقت دون حظر
- **الأداء**: معالجة الطلبات بسرعة كبيرة للتطبيقات في الوقت الفعلي

### فهم CORS: حارس أمان الويب

CORS (مشاركة الموارد عبر الأصول) يشبه حارس أمان في مبنى يتحقق مما إذا كان الزوار مسموح لهم بالدخول. دعونا نفهم لماذا هذا مهم وكيف يؤثر على تطبيقك.

#### ما هو CORS ولماذا يوجد؟

**المشكلة**: تخيل لو أن أي موقع يمكنه إرسال طلبات إلى موقع البنك الخاص بك نيابة عنك دون إذنك. سيكون ذلك كابوسًا أمنيًا! المتصفحات تمنع هذا افتراضيًا من خلال "سياسة الأصل نفسه".

**سياسة الأصل نفسه**: تسمح المتصفحات فقط لصفحات الويب بإرسال طلبات إلى نفس النطاق، المنفذ، والبروتوكول الذي تم تحميلها منه.

**تشبيه واقعي**: إنه مثل أمان المبنى السكني – فقط السكان (الأصل نفسه) يمكنهم الوصول إلى المبنى افتراضيًا. إذا كنت تريد السماح لصديق (أصل مختلف) بالزيارة، تحتاج إلى إخبار الأمن صراحةً أنه لا بأس بذلك.

#### CORS في بيئة التطوير الخاصة بك

أثناء التطوير، تعمل الواجهة الأمامية والخلفية على منافذ مختلفة:
- الواجهة الأمامية: `http://localhost:3000` (أو file:// إذا فتحت HTML مباشرة)
- الواجهة الخلفية: `http://localhost:5000`

تُعتبر هذه "أصول مختلفة" حتى لو كانت على نفس الكمبيوتر!

```python
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI(__name__)
CORS(app)   # This tells browsers: "It's okay for other origins to make requests to this API"
```

**ما يفعله تكوين CORS عمليًا:**
- **يضيف** رؤوس HTTP خاصة إلى ردود API تخبر المتصفحات "هذا الطلب عبر الأصول مسموح به"
- **يتعامل** مع طلبات "التحقق المسبق" (تتحقق المتصفحات أحيانًا من الأذونات قبل إرسال الطلب الفعلي)
- **يمنع** الخطأ المزعج "محظور بواسطة سياسة CORS" في وحدة التحكم بالمتصفح

#### أمان CORS: التطوير مقابل الإنتاج

```python
# 🚨 Development: Allows ALL origins (convenient but insecure)
CORS(app)

# ✅ Production: Only allow your specific frontend domain
CORS(app, origins=["https://yourdomain.com", "https://www.yourdomain.com"])

# 🔒 Advanced: Different origins for different environments
if app.debug:  # Development mode
    CORS(app, origins=["http://localhost:3000", "http://127.0.0.1:3000"])
else:  # Production mode
    CORS(app, origins=["https://yourdomain.com"])
```

**لماذا هذا مهم**: في التطوير، `CORS(app)` يشبه ترك بابك الأمامي مفتوحًا – مريح ولكنه غير آمن. في الإنتاج، تريد تحديد المواقع التي يمكنها التحدث إلى API الخاص بك.

#### سيناريوهات CORS الشائعة وحلولها

| السيناريو | المشكلة | الحل |
|----------|---------|----------|
| **التطوير المحلي** | لا يمكن للواجهة الأمامية الوصول إلى الواجهة الخلفية | أضف CORSMiddleware إلى FastAPI |
| **GitHub Pages + Heroku** | لا يمكن للواجهة الأمامية المنشورة الوصول إلى API | أضف عنوان URL الخاص بـ GitHub Pages إلى أصول CORS |
| **النطاق المخصص** | أخطاء CORS في الإنتاج | قم بتحديث أصول CORS لتطابق نطاقك |
| **تطبيق الهاتف المحمول** | لا يمكن للتطبيق الوصول إلى API الويب | أضف نطاق التطبيق الخاص بك أو استخدم `*` بحذر |

**نصيحة احترافية**: يمكنك التحقق من رؤوس CORS في أدوات المطور الخاصة بالمتصفح ضمن علامة التبويب الشبكة. ابحث عن رؤوس مثل `Access-Control-Allow-Origin` في الرد.

### معالجة الأخطاء والتحقق

لاحظ كيف تتضمن API الخاصة بنا معالجة الأخطاء بشكل صحيح:

```python
# Validate that we received a message
if not message:
    return jsonify({"error": "Message field is required"}), 400
```

**مبادئ التحقق الرئيسية:**
- **يتحقق** من الحقول المطلوبة قبل معالجة الطلبات
- **يعيد** رسائل خطأ ذات معنى بتنسيق JSON
- **يستخدم** رموز حالة HTTP المناسبة (400 للطلبات السيئة)
- **يوفر** ملاحظات واضحة لمساعدة مطوري الواجهة الأمامية في تصحيح الأخطاء

## إعداد وتشغيل الواجهة الخلفية الخاصة بك

الآن بعد أن أصبح لدينا تكامل الذكاء الاصطناعي وخادم FastAPI جاهزًا، دعونا نبدأ تشغيل كل شيء. تتضمن عملية الإعداد تثبيت تبعيات Python، تكوين متغيرات البيئة، وتشغيل خادم التطوير الخاص بك.

### إعداد بيئة Python

دعونا نعد بيئة تطوير Python الخاصة بك. البيئات الافتراضية تشبه نهج المشروع المخصص – كل مشروع يحصل على مساحته المعزولة الخاصة به مع أدوات وتبعيات محددة، مما يمنع التعارض بين المشاريع المختلفة.

```bash
# Navigate to your backend directory
cd backend

# Create a virtual environment (like creating a clean room for your project)
python -m venv venv

# Activate it (Linux/Mac)
source ./venv/bin/activate

# On Windows, use:
# venv\Scripts\activate

# Install the good stuff
pip install openai fastapi uvicorn python-dotenv
```

**ما فعلناه للتو:**
- **أنشأنا** فقاعة Python الخاصة بنا حيث يمكننا تثبيت الحزم دون التأثير على أي شيء آخر
- **قمنا بتفعيلها** حتى يعرف الطرفية استخدام هذه البيئة المحددة
- **قمنا بتثبيت الأساسيات**: OpenAI للسحر الذكاء الاصطناعي، FastAPI لـ API الويب، Uvicorn لتشغيله فعليًا، وpython-dotenv لإدارة الأسرار بأمان

**تفسير التبعيات الرئيسية:**
- **FastAPI**: إطار عمل ويب حديث وسريع مع توثيق API تلقائي
- **Uvicorn**: خادم ASGI سريع جدًا لتشغيل تطبيقات FastAPI
- **OpenAI**: مكتبة رسمية لنماذج GitHub وتكامل API الخاص بـ OpenAI
- **python-dotenv**: تحميل متغيرات البيئة بأمان من ملفات .env

### تكوين البيئة: الحفاظ على الأسرار بأمان

قبل أن نبدأ API الخاصة بنا، نحتاج إلى الحديث عن أحد أهم الدروس في تطوير الويب: كيفية الحفاظ على الأسرار بالفعل سرية. متغيرات البيئة تشبه خزنة آمنة لا يمكن الوصول إليها إلا لتطبيقك.

#### ما هي متغيرات البيئة؟

**فكر في متغيرات البيئة مثل صندوق ودائع آمن** – تضع أشياءك القيمة فيه، وفقط أنت (وتطبيقك) لديك المفتاح للوصول إليها. بدلًا من كتابة معلومات حساسة مباشرة في الكود الخاص بك (حيث يمكن لأي شخص رؤيتها حرفيًا)، تخزنها بأمان في البيئة.

**إليك الفرق:**
- **الطريقة الخاطئة**: كتابة كلمة المرور الخاصة بك على ورقة لاصقة ووضعها على شاشتك
- **الطريقة الصحيحة**: الاحتفاظ بكلمة المرور الخاصة بك في مدير كلمات مرور آمن لا يمكن الوصول إليه إلا لك

#### لماذا متغيرات البيئة مهمة

```python
# 🚨 NEVER DO THIS - API key visible to everyone
client = OpenAI(
    api_key="ghp_1234567890abcdef...",  # Anyone can steal this!
    base_url="https://models.github.ai/inference"
)

# ✅ DO THIS - API key stored securely
client = OpenAI(
    api_key=os.environ["GITHUB_TOKEN"],  # Only your app can access this
    base_url="https://models.github.ai/inference"
)
```

**ما يحدث عندما تقوم بتضمين الأسرار في الكود:**
1. **تعرض التحكم في الإصدار**: أي شخص لديه حق الوصول إلى مستودع Git الخاص بك يرى مفتاح API الخاص بك
2. **المستودعات العامة**: إذا دفعت إلى GitHub، يصبح مفتاحك مرئيًا للإنترنت بأكمله
3. **مشاركة الفريق**: يحصل المطورون الآخرون الذين يعملون على مشروعك على حق الوصول إلى مفتاح API الخاص بك
4. **اختراقات الأمان**: إذا سرق أحدهم مفتاح API الخاص بك، يمكنه استخدام أرصدة الذكاء الاصطناعي الخاصة بك

#### إعداد ملف البيئة الخاص بك

قم بإنشاء ملف `.env` في دليل الواجهة الخلفية الخاص بك. يخزن هذا الملف أسرارك محليًا:

```bash
# .env file - This should NEVER be committed to Git
GITHUB_TOKEN=your_github_personal_access_token_here
FASTAPI_DEBUG=True
ENVIRONMENT=development
```

**فهم ملف .env:**
- **سر واحد لكل سطر** بتنسيق `KEY=value`
- **لا توجد مسافات** حول علامة المساواة
- **لا حاجة إلى علامات اقتباس** حول القيم (عادةً)
- **التعليقات** تبدأ بـ `#`

#### إنشاء رمز الوصول الشخصي الخاص بك على GitHub

رمز GitHub الخاص بك يشبه كلمة مرور خاصة تمنح تطبيقك الإذن باستخدام خدمات الذكاء الاصطناعي الخاصة بـ GitHub:

**خطوات إنشاء الرمز:**
1. **اذهب إلى إعدادات GitHub** → إعدادات المطور → رموز الوصول الشخصي → الرموز (الكلاسيكية)
2. **انقر على "إنشاء رمز جديد (كلاسيكي)"**
3. **حدد تاريخ انتهاء الصلاحية** (30 يومًا للاختبار، أطول للإنتاج)
4. **حدد النطاقات**: تحقق من "repo" وأي أذونات أخرى تحتاجها
5. **قم بإنشاء الرمز** ونسخه فورًا (لا يمكنك رؤيته مرة أخرى!)
6. **الصقه في ملف .env الخاص بك**

```bash
# Example of what your token looks like (this is fake!)
GITHUB_TOKEN=ghp_1A2B3C4D5E6F7G8H9I0J1K2L3M4N5O6P7Q8R
```

#### تحميل متغيرات البيئة في Python

```python
import os
from dotenv import load_dotenv

# Load environment variables from .env file
load_dotenv()

# Now you can access them securely
api_key = os.environ.get("GITHUB_TOKEN")
if not api_key:
    raise ValueError("GITHUB_TOKEN not found in environment variables!")

client = OpenAI(
    api_key=api_key,
    base_url="https://models.github.ai/inference"
)
```

**ما يفعله هذا الكود:**
- **يحمل** ملف .env الخاص بك ويجعل المتغيرات متاحة لـ Python
- **يتحقق** مما إذا كان الرمز المطلوب موجودًا (معالجة أخطاء جيدة!)
- **يرفع** خطأ واضحًا إذا كان الرمز مفقودًا
- **يستخدم** الرمز بأمان دون كشفه في الكود

#### أمان Git: ملف .gitignore

يخبر ملف `.gitignore` Git الملفات التي لا يجب تتبعها أو تحميلها:

```bash
# .gitignore - Add these lines
.env
*.env
.env.local
.env.production
__pycache__/
venv/
.vscode/
```

**لماذا هذا مهم**: بمجرد إضافة `.env` إلى `.gitignore`، سيتجاهل Git ملف البيئة الخاص بك، مما يمنعك من تحميل أسرارك إلى GitHub عن طريق الخطأ.

#### بيئات مختلفة، أسرار مختلفة

تستخدم التطبيقات الاحترافية مفاتيح API مختلفة لبيئات مختلفة:

```bash
# .env.development
GITHUB_TOKEN=your_development_token
DEBUG=True

# .env.production  
GITHUB_TOKEN=your_production_token
DEBUG=False
```

**لماذا هذا مهم**: لا تريد أن تؤثر تجارب التطوير الخاصة بك على حصة استخدام الذكاء الاصطناعي في الإنتاج، وتريد مستويات أمان مختلفة لبيئات مختلفة.

### بدء تشغيل خادم التطوير الخاص بك: إحياء FastAPI الخاص بك

الآن تأتي اللحظة المثيرة – بدء تشغيل خادم تطوير FastAPI الخاص بك ورؤية تكامل الذكاء الاصطناعي الخاص بك ينبض بالحياة! يستخدم FastAPI Uvicorn، وهو خادم ASGI سريع جدًا مصمم خصيصًا لتطبيقات Python غير المتزامنة.

#### فهم عملية بدء تشغيل خادم FastAPI

```bash
# Method 1: Direct Python execution (includes auto-reload)
python api.py

# Method 2: Using Uvicorn directly (more control)
uvicorn api:app --host 0.0.0.0 --port 5000 --reload
```

عندما تقوم بتشغيل هذا الأمر، إليك ما يحدث خلف الكواليس:

**1. يقوم Python بتحميل تطبيق FastAPI الخاص بك**:
- يستورد جميع المكتبات المطلوبة (FastAPI، Pydantic، OpenAI، إلخ.)
- يحمل متغيرات البيئة من ملف `.env` الخاص بك
- ينشئ مثيل تطبيق FastAPI مع توثيق تلقائي

**2. يقوم Uvicorn بتكوين خادم ASGI**:
- يرتبط بالمنفذ 5000 مع قدرات معالجة الطلبات غير المتزامنة
- يقوم بإعداد توجيه الطلبات مع التحقق التلقائي
- يُمكّن إعادة التحميل السريع للتطوير (إعادة التشغيل عند تغييرات الملفات)
- يُنشئ توثيق API تفاعلي

**3. يبدأ الخادم في الاستماع**:
- يظهر في الطرفية: `INFO: Uvicorn running on http://0.0.0.0:5000`
- يمكن للخادم معالجة طلبات الذكاء الاصطناعي المتزامنة
- تصبح API الخاصة بك جاهزة مع توثيق تلقائي في `http://localhost:5000/docs`

#### ما يجب أن تراه عندما يعمل كل شيء

```bash
$ python api.py
INFO:     Will watch for changes in these directories: ['/your/project/path']
INFO:     Uvicorn running on http://0.0.0.0:5000 (Press CTRL+C to quit)
INFO:     Started reloader process [12345] using WatchFiles
INFO:     Started server process [12346]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
```

**فهم إخراج FastAPI:**
- **سيشاهد التغييرات**: إعادة التحميل التلقائي مفعلة للتطوير
- **Uvicorn يعمل**: خادم ASGI عالي الأداء نشط
- **عملية إعادة التحميل بدأت**: مراقب الملفات لإعادة التشغيل التلقائي
- **اكتمال بدء تشغيل التطبيق**: تم تهيئة تطبيق FastAPI بنجاح
- **التوثيق التفاعلي متاح**: قم بزيارة `/docs` للحصول على توثيق API تلقائي

#### اختبار FastAPI الخاص بك: طرق قوية متعددة

يوفر FastAPI عدة طرق مريحة لاختبار API الخاص بك، بما في ذلك التوثيق التفاعلي التلقائي:

**الطريقة الأولى: توثيق API التفاعلي (موصى به)**
1. افتح متصفحك وانتقل إلى `http://localhost:5000/docs`
2. سترى واجهة Swagger UI مع جميع نقاط النهاية الخاصة بك موثقة
3. انقر على `/hello` → "جربها" → أدخل رسالة اختبار → "تنفيذ"
4. شاهد الرد مباشرة في المتصفح مع التنسيق المناسب

**الطريقة الثانية: اختبار المتصفح الأساسي**
1. انتقل إلى `http://localhost:5000` لنقطة النهاية الجذرية
2. انتقل إلى `http://localhost:5000/health` للتحقق من صحة الخادم
3. هذا يؤكد أن خادم FastAPI الخاص بك يعمل بشكل صحيح

**الطريقة الثالثة: اختبار سطر الأوامر (متقدم)**
```bash
# Test with curl (if available)
curl -X POST http://localhost:5000/hello \
  -H "Content-Type: application/json" \
  -d '{"message": "Hello AI!"}'

# Expected response:
# {"response": "Hello! I'm your AI assistant. How can I help you today?"}
```

**الطريقة الرابعة: سكريبت اختبار Python**
```python
# test_api.py - Create this file to test your API
import requests
import json

# Test the API endpoint
url = "http://localhost:5000/hello"
data = {"message": "Tell me a joke about programming"}

response = requests.post(url, json=data)
if response.status_code == 200:
    result = response.json()
    print("AI Response:", result['response'])
else:
    print("Error:", response.status_code, response.text)
```

#### استكشاف الأخطاء الشائعة عند بدء التشغيل

| رسالة الخطأ | معناها | كيفية الإصلاح |
|-------------|--------|--------------|
| `ModuleNotFoundError: No module named 'fastapi'` | لم يتم تثبيت FastAPI | قم بتشغيل `pip install fastapi uvicorn` في بيئة العمل الافتراضية |
| `ModuleNotFoundError: No module named 'uvicorn'` | لم يتم تثبيت خادم ASGI | قم بتشغيل `pip install uvicorn` في بيئة العمل الافتراضية |
| `KeyError: 'GITHUB_TOKEN'` | لم يتم العثور على متغير البيئة | تحقق من ملف `.env` واستدعاء `load_dotenv()` |
| `Address already in use` | المنفذ 5000 مشغول | قم بإنهاء العمليات الأخرى التي تستخدم المنفذ 5000 أو قم بتغيير المنفذ |
| `ValidationError` | بيانات الطلب لا تتطابق مع نموذج Pydantic | تحقق من أن تنسيق الطلب يتطابق مع المخطط المتوقع |
| `HTTPException 422` | كيان غير قابل للمعالجة | فشل التحقق من الطلب، تحقق من `/docs` للحصول على التنسيق الصحيح |
| `OpenAI API error` | فشل مصادقة خدمة الذكاء الاصطناعي | تحقق من صحة رمز GitHub الخاص بك وأن لديه الأذونات المناسبة |

#### أفضل الممارسات للتطوير

**إعادة التحميل التلقائي**: يوفر FastAPI مع Uvicorn إعادة تحميل تلقائية عند حفظ تغييرات ملفات Python. هذا يعني أنه يمكنك تعديل الكود واختباره فورًا دون الحاجة إلى إعادة التشغيل يدويًا.

```python
# Enable hot reloading explicitly
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)  # debug=True enables hot reload
```

**التسجيل أثناء التطوير**: أضف تسجيلًا لفهم ما يحدث:

```python
import logging

# Set up logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

@app.route("/hello", methods=["POST"])
def hello():
    data = request.get_json()
    message = data.get("message", "")
    
    logger.info(f"Received message: {message}")
    
    if not message:
        logger.warning("Empty message received")
        return jsonify({"error": "Message field is required"}), 400
    
    try:
        response = call_llm(message, "You are a helpful and friendly assistant.")
        logger.info(f"AI response generated successfully")
        return jsonify({"response": response})
    except Exception as e:
        logger.error(f"AI API error: {str(e)}")
        return jsonify({"error": "AI service temporarily unavailable"}), 500
```

**لماذا يساعد التسجيل**: أثناء التطوير، يمكنك رؤية الطلبات التي تصل، وكيف يستجيب الذكاء الاصطناعي، وأين تحدث الأخطاء. هذا يجعل عملية تصحيح الأخطاء أسرع بكثير.

### إعداد GitHub Codespaces: تطوير سحابي بسهولة

GitHub Codespaces يشبه امتلاك جهاز كمبيوتر قوي للتطوير في السحابة يمكنك الوصول إليه من أي متصفح. إذا كنت تعمل في Codespaces، هناك بعض الخطوات الإضافية لجعل الواجهة الخلفية الخاصة بك متاحة للواجهة الأمامية.

#### فهم الشبكات في Codespaces

في بيئة التطوير المحلية، كل شيء يعمل على نفس الكمبيوتر:
- الواجهة الخلفية: `http://localhost:5000`
- الواجهة الأمامية: `http://localhost:3000` (أو file://)

في Codespaces، بيئة التطوير الخاصة بك تعمل على خوادم GitHub، لذا فإن "localhost" له معنى مختلف. يقوم GitHub تلقائيًا بإنشاء روابط عامة لخدماتك، ولكن تحتاج إلى إعدادها بشكل صحيح.

#### خطوات إعداد Codespaces

**1. قم بتشغيل خادم الواجهة الخلفية**:
```bash
cd backend
python api.py
```

سترى رسالة بدء التشغيل المعتادة لـ FastAPI/Uvicorn، ولكن لاحظ أنها تعمل داخل بيئة Codespace.

**2. إعداد رؤية المنفذ**:
- ابحث عن علامة التبويب "Ports" في اللوحة السفلية لـ VS Code
- ابحث عن المنفذ 5000 في القائمة
- انقر بزر الماوس الأيمن على المنفذ 5000
- اختر "Port Visibility" → "Public"

**لماذا تجعلها عامة؟** بشكل افتراضي، منافذ Codespace خاصة (يمكن الوصول إليها فقط من قبلك). جعلها عامة يسمح للواجهة الأمامية (التي تعمل في المتصفح) بالتواصل مع الواجهة الخلفية.

**3. احصل على الرابط العام الخاص بك**:
بعد جعل المنفذ عامًا، سترى رابطًا مثل:
```
https://your-codespace-name-5000.app.github.dev
```

**4. قم بتحديث إعدادات الواجهة الأمامية**:
```javascript
// In your frontend app.js, update the BASE_URL:
this.BASE_URL = "https://your-codespace-name-5000.app.github.dev";
```

#### فهم روابط Codespace

روابط Codespace تتبع نمطًا متوقعًا:
```
https://[codespace-name]-[port].app.github.dev
```

**تفصيل هذا النمط:**
- `codespace-name`: معرف فريد لـ Codespace الخاص بك (عادةً يتضمن اسم المستخدم الخاص بك)
- `port`: رقم المنفذ الذي تعمل عليه الخدمة الخاصة بك (5000 لتطبيق FastAPI الخاص بنا)
- `app.github.dev`: نطاق GitHub لتطبيقات Codespace

#### اختبار إعداد Codespace الخاص بك

**1. اختبر الواجهة الخلفية مباشرةً**:
افتح الرابط العام الخاص بك في علامة تبويب جديدة في المتصفح. يجب أن ترى:
```
Welcome to the AI Chat API. Send POST requests to /hello with JSON payload containing 'message' field.
```

**2. اختبر باستخدام أدوات المطور في المتصفح**:
```javascript
// Open browser console and test your API
fetch('https://your-codespace-name-5000.app.github.dev/hello', {
  method: 'POST',
  headers: {'Content-Type': 'application/json'},
  body: JSON.stringify({message: 'Hello from Codespaces!'})
})
.then(response => response.json())
.then(data => console.log(data));
```

#### Codespaces مقابل التطوير المحلي

| الجانب | التطوير المحلي | GitHub Codespaces |
|--------|----------------|-------------------|
| **وقت الإعداد** | أطول (تثبيت Python، التبعيات) | فوري (بيئة مُعدة مسبقًا) |
| **الوصول إلى الرابط** | `http://localhost:5000` | `https://xyz-5000.app.github.dev` |
| **إعداد المنفذ** | تلقائي | يدوي (جعل المنافذ عامة) |
| **استمرارية الملفات** | جهاز الكمبيوتر المحلي | مستودع GitHub |
| **التعاون** | صعب مشاركة البيئة | سهل مشاركة رابط Codespace |
| **الاعتماد على الإنترنت** | فقط لطلبات API الذكاء الاصطناعي | مطلوب لكل شيء |

#### نصائح لتطوير Codespace

**متغيرات البيئة في Codespaces**:
ملف `.env` الخاص بك يعمل بنفس الطريقة في Codespaces، ولكن يمكنك أيضًا إعداد متغيرات البيئة مباشرةً في Codespace:

```bash
# Set environment variable for the current session
export GITHUB_TOKEN="your_token_here"

# Or add to your .bashrc for persistence
echo 'export GITHUB_TOKEN="your_token_here"' >> ~/.bashrc
```

**إدارة المنافذ**:
- يكتشف Codespaces تلقائيًا عندما تبدأ تطبيقك في الاستماع على منفذ
- يمكنك إعادة توجيه منافذ متعددة في نفس الوقت (مفيد إذا أضفت قاعدة بيانات لاحقًا)
- تظل المنافذ متاحة طالما أن Codespace الخاص بك يعمل

**سير عمل التطوير**:
1. قم بإجراء تغييرات على الكود في VS Code
2. يقوم FastAPI بإعادة التحميل تلقائيًا (بفضل وضع إعادة التحميل في Uvicorn)
3. اختبر التغييرات فورًا عبر الرابط العام
4. قم بالتزام التغييرات ودفعها عندما تكون جاهزًا

> 💡 **نصيحة احترافية**: قم بحفظ رابط الواجهة الخلفية لـ Codespace أثناء التطوير. نظرًا لأن أسماء Codespace مستقرة، لن يتغير الرابط طالما أنك تستخدم نفس Codespace.

## إنشاء واجهة الدردشة الأمامية: حيث يلتقي البشر بالذكاء الاصطناعي

الآن سنقوم ببناء واجهة المستخدم – الجزء الذي يحدد كيفية تفاعل الأشخاص مع مساعد الذكاء الاصطناعي الخاص بك. مثل تصميم واجهة iPhone الأصلية، نحن نركز على جعل التكنولوجيا المعقدة تبدو بديهية وطبيعية للاستخدام.

### فهم بنية الواجهة الأمامية الحديثة

واجهة الدردشة الخاصة بنا ستكون ما يسمى بـ "تطبيق صفحة واحدة" أو SPA. بدلاً من النهج القديم حيث يتم تحميل صفحة جديدة مع كل نقرة، يقوم تطبيقنا بالتحديث بسلاسة وفورًا:

**المواقع القديمة**: مثل قراءة كتاب مادي – تقلب إلى صفحات جديدة تمامًا
**تطبيق الدردشة الخاص بنا**: مثل استخدام هاتفك – كل شيء يتدفق ويتحدث بسلاسة

```mermaid
graph TD
    A[User Types Message] --> B[JavaScript Captures Input]
    B --> C[Validate & Format Data]
    C --> D[Send to Backend API]
    D --> E[Display Loading State]
    E --> F[Receive AI Response]
    F --> G[Update Chat Interface]
    G --> H[Ready for Next Message]
```

### الركائز الثلاث لتطوير الواجهة الأمامية

كل تطبيق واجهة أمامية – من المواقع البسيطة إلى التطبيقات المعقدة مثل Discord أو Slack – يعتمد على ثلاث تقنيات أساسية. فكر فيها كأساس لكل ما تراه وتتفاعل معه على الويب:

**HTML (الهيكل)**: هذا هو الأساس
- يحدد العناصر الموجودة (الأزرار، مناطق النص، الحاويات)
- يعطي معنى للمحتوى (هذا عنوان، هذا نموذج، إلخ)
- ينشئ الهيكل الأساسي الذي يبني عليه كل شيء آخر

**CSS (العرض)**: هذا هو المصمم الداخلي
- يجعل كل شيء يبدو جميلًا (الألوان، الخطوط، التخطيطات)
- يتعامل مع أحجام الشاشات المختلفة (الهاتف مقابل الكمبيوتر المحمول مقابل الجهاز اللوحي)
- ينشئ الرسوم المتحركة السلسة والتغذية البصرية

**JavaScript (السلوك)**: هذا هو العقل
- يستجيب لما يفعله المستخدمون (النقرات، الكتابة، التمرير)
- يتحدث إلى الواجهة الخلفية ويحدث الصفحة
- يجعل كل شيء تفاعليًا وديناميكيًا

**فكر فيها كتصميم معماري:**
- **HTML**: المخطط الهيكلي (تحديد المساحات والعلاقات)
- **CSS**: التصميم الجمالي والبيئي (النمط البصري وتجربة المستخدم)
- **JavaScript**: الأنظمة الميكانيكية (الوظائف والتفاعلية)

### لماذا تهم بنية JavaScript الحديثة

تطبيق الدردشة الخاص بنا سيستخدم أنماط JavaScript الحديثة التي ستراها في التطبيقات الاحترافية. فهم هذه المفاهيم سيساعدك على النمو كمطور:

**بنية قائمة على الفئات**: سننظم الكود الخاص بنا في فئات، وهو مثل إنشاء مخططات للكائنات
**Async/Await**: الطريقة الحديثة للتعامل مع العمليات التي تستغرق وقتًا (مثل استدعاءات API)
**البرمجة القائمة على الأحداث**: تطبيقنا يستجيب لإجراءات المستخدم (النقرات، ضغط المفاتيح) بدلاً من التشغيل في حلقة
**التلاعب بـ DOM**: تحديث محتوى صفحة الويب ديناميكيًا بناءً على تفاعلات المستخدم واستجابات API

### إعداد هيكل المشروع

قم بإنشاء دليل للواجهة الأمامية مع هذا الهيكل المنظم:

```text
frontend/
├── index.html      # Main HTML structure
├── app.js          # JavaScript functionality
└── styles.css      # Visual styling
```

**فهم الهيكل:**
- **يفصل** بين الهيكل (HTML)، السلوك (JavaScript)، والعرض (CSS)
- **يحافظ** على هيكل ملفات بسيط وسهل التنقل والتعديل
- **يتبع** أفضل ممارسات تطوير الويب للتنظيم وقابلية الصيانة

### بناء أساس HTML: هيكل دلالي للوصول

لنبدأ بهيكل HTML. يركز تطوير الويب الحديث على "HTML الدلالي" – استخدام عناصر HTML التي تصف بوضوح غرضها، وليس فقط مظهرها. هذا يجعل تطبيقك متاحًا لقراء الشاشة ومحركات البحث والأدوات الأخرى.

**لماذا يهم HTML الدلالي**: تخيل أنك تصف تطبيق الدردشة الخاص بك لشخص عبر الهاتف. ستقول "هناك رأس يحتوي على العنوان، منطقة رئيسية حيث تظهر المحادثات، ونموذج في الأسفل لكتابة الرسائل." يستخدم HTML الدلالي عناصر تتطابق مع هذا الوصف الطبيعي.

قم بإنشاء `index.html` مع هذا الترميز المنظم بعناية:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Chat Assistant</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="chat-container">
        <header class="chat-header">
            <h1>AI Chat Assistant</h1>
            <p>Ask me anything!</p>
        </header>
        
        <main class="chat-messages" id="messages" role="log" aria-live="polite">
            <!-- Messages will be dynamically added here -->
        </main>
        
        <form class="chat-form" id="chatForm">
            <div class="input-group">
                <input 
                    type="text" 
                    id="messageInput" 
                    placeholder="Type your message here..." 
                    required
                    aria-label="Chat message input"
                >
                <button type="submit" id="sendBtn" aria-label="Send message">
                    Send
                </button>
            </div>
        </form>
    </div>
    <script src="app.js"></script>
</body>
</html>
```

**فهم كل عنصر HTML وغرضه:**

#### هيكل الوثيقة
- **`<!DOCTYPE html>`**: يخبر المتصفح أن هذا HTML5 حديث
- **`<html lang="en">`**: يحدد لغة الصفحة لقراء الشاشة وأدوات الترجمة
- **`<meta charset="UTF-8">`**: يضمن ترميز الأحرف الصحيح للنصوص الدولية
- **`<meta name="viewport"...>`**: يجعل الصفحة متجاوبة مع الأجهزة المحمولة من خلال التحكم في التكبير والتصغير

#### العناصر الدلالية
- **`<header>`**: يحدد بوضوح القسم العلوي مع العنوان والوصف
- **`<main>`**: يخصص منطقة المحتوى الرئيسية (حيث تحدث المحادثات)
- **`<form>`**: صحيح دلاليًا لإدخال المستخدم، يتيح التنقل الصحيح عبر لوحة المفاتيح

#### ميزات الوصول
- **`role="log"`**: يخبر قراء الشاشة أن هذه المنطقة تحتوي على سجل زمني للرسائل
- **`aria-live="polite"`**: يعلن عن الرسائل الجديدة لقراء الشاشة دون مقاطعة
- **`aria-label`**: يوفر تسميات وصفية لعناصر التحكم في النموذج
- **`required`**: يتحقق المتصفح من أن المستخدمين يدخلون رسالة قبل الإرسال

#### تكامل CSS وJavaScript
- **`class` attributes**: توفر نقاط ربط للتنسيق باستخدام CSS (مثل `chat-container`, `input-group`)
- **`id` attributes**: تسمح لـ JavaScript بالعثور على عناصر محددة ومعالجتها
- **وضع السكربت**: يتم تحميل ملف JavaScript في النهاية حتى يتم تحميل HTML أولاً

**لماذا يعمل هذا الهيكل:**
- **تدفق منطقي**: الرأس → المحتوى الرئيسي → نموذج الإدخال يتطابق مع ترتيب القراءة الطبيعي
- **قابلية الوصول عبر لوحة المفاتيح**: يمكن للمستخدمين التنقل عبر جميع العناصر التفاعلية
- **صديق لقراء الشاشة**: معالم واضحة وأوصاف للمستخدمين ضعاف البصر
- **متجاوب مع الأجهزة المحمولة**: علامة meta viewport تمكن التصميم المتجاوب
- **تحسين تدريجي**: يعمل حتى إذا فشل تحميل CSS أو JavaScript

### إضافة JavaScript التفاعلي: منطق تطبيق ويب حديث

الآن دعونا نبني JavaScript الذي يجعل واجهة الدردشة الخاصة بنا تنبض بالحياة. سنستخدم أنماط JavaScript الحديثة التي ستواجهها في تطوير الويب الاحترافي، بما في ذلك الفئات ES6، async/await، والبرمجة القائمة على الأحداث.

#### فهم بنية JavaScript الحديثة

بدلاً من كتابة كود إجرائي (سلسلة من الوظائف التي تعمل بالترتيب)، سننشئ **بنية قائمة على الفئات**. فكر في الفئة كمخطط لإنشاء الكائنات – مثل كيف يمكن استخدام مخطط المهندس المعماري لبناء منازل متعددة.

**لماذا نستخدم الفئات لتطبيقات الويب؟**
- **التنظيم**: يتم تجميع جميع الوظائف ذات الصلة معًا
- **إعادة الاستخدام**: يمكنك إنشاء مثيلات متعددة للدردشة على نفس الصفحة
- **سهولة الصيانة**: أسهل في تصحيح الأخطاء وتعديل الميزات المحددة
- **المعيار الاحترافي**: يتم استخدام هذا النمط في أطر العمل مثل React, Vue, وAngular

قم بإنشاء `app.js` مع هذا JavaScript الحديث والمنظم جيدًا:

```javascript
// app.js - Modern chat application logic

class ChatApp {
    constructor() {
        // Get references to DOM elements we'll need to manipulate
        this.messages = document.getElementById("messages");
        this.form = document.getElementById("chatForm");
        this.input = document.getElementById("messageInput");
        this.sendButton = document.getElementById("sendBtn");
        
        // Configure your backend URL here
        this.BASE_URL = "http://localhost:5000"; // Update this for your environment
        this.API_ENDPOINT = `${this.BASE_URL}/hello`;
        
        // Set up event listeners when the chat app is created
        this.initializeEventListeners();
    }
    
    initializeEventListeners() {
        // Listen for form submission (when user clicks Send or presses Enter)
        this.form.addEventListener("submit", (e) => this.handleSubmit(e));
        
        // Also listen for Enter key in the input field (better UX)
        this.input.addEventListener("keypress", (e) => {
            if (e.key === "Enter" && !e.shiftKey) {
                e.preventDefault();
                this.handleSubmit(e);
            }
        });
    }
    
    async handleSubmit(event) {
        event.preventDefault(); // Prevent form from refreshing the page
        
        const messageText = this.input.value.trim();
        if (!messageText) return; // Don't send empty messages
        
        // Provide user feedback that something is happening
        this.setLoading(true);
        
        // Add user message to chat immediately (optimistic UI)
        this.appendMessage(messageText, "user");
        
        // Clear input field so user can type next message
        this.input.value = '';
        
        try {
            // Call the AI API and wait for response
            const reply = await this.callAPI(messageText);
            
            // Add AI response to chat
            this.appendMessage(reply, "assistant");
        } catch (error) {
            console.error('API Error:', error);
            this.appendMessage("Sorry, I'm having trouble connecting right now. Please try again.", "error");
        } finally {
            // Re-enable the interface regardless of success or failure
            this.setLoading(false);
        }
    }
    
    async callAPI(message) {
        const response = await fetch(this.API_ENDPOINT, {
            method: "POST",
            headers: { 
                "Content-Type": "application/json" 
            },
            body: JSON.stringify({ message })
        });
        
        if (!response.ok) {
            throw new Error(`HTTP error! status: ${response.status}`);
        }
        
        const data = await response.json();
        return data.response;
    }
    
    appendMessage(text, role) {
        const messageElement = document.createElement("div");
        messageElement.className = `message ${role}`;
        messageElement.innerHTML = `
            <div class="message-content">
                <span class="message-text">${this.escapeHtml(text)}</span>
                <span class="message-time">${new Date().toLocaleTimeString()}</span>
            </div>
        `;
        
        this.messages.appendChild(messageElement);
        this.scrollToBottom();
    }
    
    escapeHtml(text) {
        const div = document.createElement('div');
        div.textContent = text;
        return div.innerHTML;
    }
    
    scrollToBottom() {
        this.messages.scrollTop = this.messages.scrollHeight;
    }
    
    setLoading(isLoading) {
        this.sendButton.disabled = isLoading;
        this.input.disabled = isLoading;
        this.sendButton.textContent = isLoading ? "Sending..." : "Send";
    }
}

// Initialize the chat application when the page loads
document.addEventListener("DOMContentLoaded", () => {
    new ChatApp();
});
```

#### فهم كل مفهوم JavaScript

**بنية الفئات ES6**:
```javascript
class ChatApp {
    constructor() {
        // This runs when you create a new ChatApp instance
        // It's like the "setup" function for your chat
    }
    
    methodName() {
        // Methods are functions that belong to the class
        // They can access class properties using "this"
    }
}
```

**نمط Async/Await**:
```javascript
// Old way (callback hell):
fetch(url)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error(error));

// Modern way (async/await):
try {
    const response = await fetch(url);
    const data = await response.json();
    console.log(data);
} catch (error) {
    console.error(error);
}
```

**البرمجة القائمة على الأحداث**:
بدلاً من التحقق باستمرار مما إذا كان قد حدث شيء ما، نستمع إلى الأحداث:
```javascript
// When form is submitted, run handleSubmit
this.form.addEventListener("submit", (e) => this.handleSubmit(e));

// When Enter key is pressed, also run handleSubmit
this.input.addEventListener("keypress", (e) => { /* ... */ });
```

**التلاعب بـ DOM**:
```javascript
// Create new elements
const messageElement = document.createElement("div");

// Modify their properties
messageElement.className = "message user";
messageElement.innerHTML = "Hello world!";

// Add to the page
this.messages.appendChild(messageElement);
```

#### الأمن وأفضل الممارسات

**منع XSS**:
```javascript
escapeHtml(text) {
    const div = document.createElement('div');
    div.textContent = text;  // This automatically escapes HTML
    return div.innerHTML;
}
```

**لماذا يهم هذا**: إذا كتب المستخدم `<script>alert('hack')</script>`، فإن هذه الوظيفة تضمن عرضه كنص بدلاً من تنفيذه ككود.

**معالجة الأخطاء**:
```javascript
try {
    const reply = await this.callAPI(messageText);
    this.appendMessage(reply, "assistant");
} catch (error) {
    // Show user-friendly error instead of breaking the app
    this.appendMessage("Sorry, I'm having trouble...", "error");
}
```

**اعتبارات تجربة المستخدم**:
- **واجهة مستخدم متفائلة**: أضف رسالة المستخدم فورًا، لا تنتظر استجابة الخادم
- **حالات التحميل**: تعطيل الأزرار وعرض "جارٍ الإرسال..." أثناء الانتظار
- **التمرير التلقائي**: حافظ على ظهور الرسائل الجديدة
- **التحقق من الإدخال**: لا ترسل رسائل فارغة
- **اختصارات لوحة المفاتيح**: مفتاح Enter يرسل الرسائل (مثل تطبيقات الدردشة الحقيقية)

#### فهم تدفق التطبيق

1. **تحميل الصفحة** → يتم تشغيل حدث `DOMContentLoaded` → يتم إنشاء `new ChatApp()`
2. **تشغيل المُنشئ** → يحصل على مراجع عناصر DOM → إعداد مستمعي الأحداث
3. **يكتب المستخدم رسالة** → يضغط Enter أو ينقر على إرسال → يتم تشغيل `handleSubmit`
4. **handleSubmit** → يتحقق من صحة الإدخال → يعرض حالة التحميل → يستدعي API
5. **استجابة API** → إضافة رسالة الذكاء الاصطناعي إلى الدردشة → إعادة تمكين الواجهة
6. **جاهز للرسالة التالية** → يمكن للمستخدم متابعة المحادثة
هذا التصميم قابل للتوسع – يمكنك بسهولة إضافة ميزات مثل تعديل الرسائل، تحميل الملفات، أو إنشاء محادثات متعددة دون الحاجة لإعادة كتابة الهيكل الأساسي.

### تنسيق واجهة الدردشة الخاصة بك

الآن دعونا ننشئ واجهة دردشة حديثة وجذابة بصريًا باستخدام CSS. التنسيق الجيد يجعل تطبيقك يبدو احترافيًا ويحسن تجربة المستخدم بشكل عام. سنستخدم ميزات CSS الحديثة مثل Flexbox، CSS Grid، والخصائص المخصصة لتصميم مستجيب وسهل الوصول.

قم بإنشاء ملف `styles.css` باستخدام هذه الأنماط الشاملة:

```css
/* styles.css - Modern chat interface styling */

:root {
    --primary-color: #2563eb;
    --secondary-color: #f1f5f9;
    --user-color: #3b82f6;
    --assistant-color: #6b7280;
    --error-color: #ef4444;
    --text-primary: #1e293b;
    --text-secondary: #64748b;
    --border-radius: 12px;
    --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    min-height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 20px;
}

.chat-container {
    width: 100%;
    max-width: 800px;
    height: 600px;
    background: white;
    border-radius: var(--border-radius);
    box-shadow: var(--shadow);
    display: flex;
    flex-direction: column;
    overflow: hidden;
}

.chat-header {
    background: var(--primary-color);
    color: white;
    padding: 20px;
    text-align: center;
}

.chat-header h1 {
    font-size: 1.5rem;
    margin-bottom: 5px;
}

.chat-header p {
    opacity: 0.9;
    font-size: 0.9rem;
}

.chat-messages {
    flex: 1;
    padding: 20px;
    overflow-y: auto;
    display: flex;
    flex-direction: column;
    gap: 15px;
    background: var(--secondary-color);
}

.message {
    display: flex;
    max-width: 80%;
    animation: slideIn 0.3s ease-out;
}

.message.user {
    align-self: flex-end;
}

.message.user .message-content {
    background: var(--user-color);
    color: white;
    border-radius: var(--border-radius) var(--border-radius) 4px var(--border-radius);
}

.message.assistant {
    align-self: flex-start;
}

.message.assistant .message-content {
    background: white;
    color: var(--text-primary);
    border-radius: var(--border-radius) var(--border-radius) var(--border-radius) 4px;
    border: 1px solid #e2e8f0;
}

.message.error .message-content {
    background: var(--error-color);
    color: white;
    border-radius: var(--border-radius);
}

.message-content {
    padding: 12px 16px;
    box-shadow: var(--shadow);
    position: relative;
}

.message-text {
    display: block;
    line-height: 1.5;
    word-wrap: break-word;
}

.message-time {
    display: block;
    font-size: 0.75rem;
    opacity: 0.7;
    margin-top: 5px;
}

.chat-form {
    padding: 20px;
    border-top: 1px solid #e2e8f0;
    background: white;
}

.input-group {
    display: flex;
    gap: 10px;
    align-items: center;
}

#messageInput {
    flex: 1;
    padding: 12px 16px;
    border: 2px solid #e2e8f0;
    border-radius: var(--border-radius);
    font-size: 1rem;
    outline: none;
    transition: border-color 0.2s ease;
}

#messageInput:focus {
    border-color: var(--primary-color);
}

#messageInput:disabled {
    background: #f8fafc;
    opacity: 0.6;
    cursor: not-allowed;
}

#sendBtn {
    padding: 12px 24px;
    background: var(--primary-color);
    color: white;
    border: none;
    border-radius: var(--border-radius);
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background-color 0.2s ease;
    min-width: 80px;
}

#sendBtn:hover:not(:disabled) {
    background: #1d4ed8;
}

#sendBtn:disabled {
    background: #94a3b8;
    cursor: not-allowed;
}

@keyframes slideIn {
    from {
        opacity: 0;
        transform: translateY(10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

/* Responsive design for mobile devices */
@media (max-width: 768px) {
    body {
        padding: 10px;
    }
    
    .chat-container {
        height: calc(100vh - 20px);
        border-radius: 8px;
    }
    
    .message {
        max-width: 90%;
    }
    
    .input-group {
        flex-direction: column;
        gap: 10px;
    }
    
    #messageInput {
        width: 100%;
    }
    
    #sendBtn {
        width: 100%;
    }
}

/* Accessibility improvements */
@media (prefers-reduced-motion: reduce) {
    .message {
        animation: none;
    }
    
    * {
        transition: none !important;
    }
}

/* Dark mode support */
@media (prefers-color-scheme: dark) {
    .chat-container {
        background: #1e293b;
        color: #f1f5f9;
    }
    
    .chat-messages {
        background: #0f172a;
    }
    
    .message.assistant .message-content {
        background: #334155;
        color: #f1f5f9;
        border-color: #475569;
    }
    
    .chat-form {
        background: #1e293b;
        border-color: #475569;
    }
    
    #messageInput {
        background: #334155;
        color: #f1f5f9;
        border-color: #475569;
    }
}
```

**فهم بنية CSS:**
- **استخدام** الخصائص المخصصة لـ CSS (المتغيرات) لتوحيد التصميم وسهولة الصيانة
- **تطبيق** تخطيط Flexbox لتصميم مستجيب ومحاذاة صحيحة
- **تضمين** حركات سلسة لظهور الرسائل دون أن تكون مشتتة
- **توفير** تمييز بصري بين رسائل المستخدم، ردود الذكاء الاصطناعي، وحالات الخطأ
- **دعم** التصميم المستجيب الذي يعمل على أجهزة الكمبيوتر المكتبية والهواتف المحمولة
- **مراعاة** سهولة الوصول مع تفضيلات تقليل الحركة ونسب التباين المناسبة
- **تقديم** دعم الوضع الداكن بناءً على تفضيلات نظام المستخدم

### إعداد عنوان URL الخاص بالخادم الخلفي

الخطوة الأخيرة هي تحديث `BASE_URL` في JavaScript الخاص بك ليتطابق مع خادمك الخلفي:

```javascript
// For local development
this.BASE_URL = "http://localhost:5000";

// For GitHub Codespaces (replace with your actual URL)
this.BASE_URL = "https://your-codespace-name-5000.app.github.dev";
```

**تحديد عنوان URL الخاص بالخادم الخلفي:**
- **التطوير المحلي**: استخدم `http://localhost:5000` إذا كنت تقوم بتشغيل الواجهة الأمامية والخلفية محليًا
- **Codespaces**: ابحث عن عنوان URL الخاص بالخادم الخلفي في علامة تبويب المنافذ بعد جعل المنفذ 5000 عامًا
- **الإنتاج**: استبدل بعنوان نطاقك الفعلي عند النشر على خدمة استضافة

> 💡 **نصيحة للاختبار**: يمكنك اختبار الخادم الخلفي مباشرةً عن طريق زيارة عنوان URL الجذر في متصفحك. يجب أن ترى رسالة الترحيب من خادم FastAPI الخاص بك.

## الاختبار والنشر

الآن بعد أن قمت ببناء مكونات الواجهة الأمامية والخلفية، دعونا نختبر أن كل شيء يعمل معًا ونستكشف خيارات النشر لمشاركة مساعد الدردشة الخاص بك مع الآخرين.

### سير عمل الاختبار المحلي

اتبع هذه الخطوات لاختبار تطبيقك الكامل:

```mermaid
graph TD
    A[Start Backend Server] --> B[Configure Environment Variables]
    B --> C[Test API Endpoints]
    C --> D[Open Frontend in Browser]
    D --> E[Test Chat Functionality]
    E --> F[Debug Any Issues]
```

**عملية الاختبار خطوة بخطوة:**

1. **ابدأ خادمك الخلفي**:
   ```bash
   cd backend
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   python api.py
   ```

2. **تحقق من عمل واجهة برمجة التطبيقات**:
   - افتح `http://localhost:5000` في متصفحك
   - يجب أن ترى رسالة الترحيب من خادم FastAPI الخاص بك

3. **افتح واجهتك الأمامية**:
   - انتقل إلى دليل الواجهة الأمامية الخاص بك
   - افتح `index.html` في متصفح الويب الخاص بك
   - أو استخدم إضافة Live Server في VS Code لتجربة تطوير أفضل

4. **اختبر وظيفة الدردشة**:
   - اكتب رسالة في حقل الإدخال
   - انقر على "إرسال" أو اضغط على Enter
   - تحقق من أن الذكاء الاصطناعي يرد بشكل مناسب
   - تحقق من وحدة التحكم في المتصفح لأي أخطاء JavaScript

### استكشاف المشكلات الشائعة وإصلاحها

| المشكلة | الأعراض | الحل |
|---------|----------|----------|
| **خطأ CORS** | الواجهة الأمامية لا يمكنها الوصول إلى الخادم الخلفي | تأكد من تكوين FastAPI CORSMiddleware بشكل صحيح |
| **خطأ مفتاح API** | ردود غير مصرح بها 401 | تحقق من متغير البيئة `GITHUB_TOKEN` الخاص بك |
| **رفض الاتصال** | أخطاء الشبكة في الواجهة الأمامية | تحقق من عنوان URL الخاص بالخادم الخلفي وأن خادم Flask يعمل |
| **لا يوجد رد من الذكاء الاصطناعي** | ردود فارغة أو بها أخطاء | تحقق من سجلات الخادم الخلفي لمشاكل الحصة أو المصادقة |

**خطوات تصحيح الأخطاء الشائعة:**
- **تحقق** من وحدة التحكم في أدوات المطور في المتصفح لأخطاء JavaScript
- **تأكد** من أن علامة الشبكة تظهر طلبات واستجابات API ناجحة
- **راجع** مخرجات الطرفية للخادم الخلفي لأخطاء Python أو مشاكل API
- **تأكد** من تحميل متغيرات البيئة بشكل صحيح وقابلة للوصول

## تحدي وكيل GitHub Copilot 🚀

استخدم وضع الوكيل لإكمال التحدي التالي:

**الوصف:** قم بتحسين مساعد الدردشة عن طريق إضافة سجل المحادثات واستمرارية الرسائل. سيساعدك هذا التحدي على فهم كيفية إدارة الحالة في تطبيقات الدردشة وتنفيذ تخزين البيانات لتحسين تجربة المستخدم.

**المهمة:** قم بتعديل تطبيق الدردشة ليشمل سجل المحادثات الذي يستمر بين الجلسات. أضف وظيفة لحفظ رسائل الدردشة في التخزين المحلي، عرض سجل المحادثات عند تحميل الصفحة، وتضمين زر "مسح السجل". قم أيضًا بتنفيذ مؤشرات الكتابة وأوقات إرسال الرسائل لجعل تجربة الدردشة أكثر واقعية.

تعرف على المزيد حول [وضع الوكيل](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) هنا.

## المهمة: بناء مساعد الذكاء الاصطناعي الشخصي الخاص بك

الآن ستقوم بإنشاء تطبيق مساعد الذكاء الاصطناعي الخاص بك. بدلاً من مجرد تكرار كود الدرس، هذه فرصة لتطبيق المفاهيم أثناء بناء شيء يعكس اهتماماتك وحالات الاستخدام الخاصة بك.

### متطلبات المشروع

دعونا نُعد مشروعك بهيكل نظيف ومنظم:

```text
my-ai-assistant/
├── backend/
│   ├── api.py          # Your FastAPI server
│   ├── llm.py          # AI integration functions
│   ├── .env            # Your secrets (keep this safe!)
│   └── requirements.txt # Python dependencies
├── frontend/
│   ├── index.html      # Your chat interface
│   ├── app.js          # The JavaScript magic
│   └── styles.css      # Make it look amazing
└── README.md           # Tell the world about your creation
```

### مهام التنفيذ الأساسية

**تطوير الخادم الخلفي:**
- **استخدم** كود FastAPI الخاص بنا واجعله خاصًا بك
- **أنشئ** شخصية فريدة للذكاء الاصطناعي – ربما مساعد طهي مفيد، شريك كتابة إبداعي، أو زميل دراسة؟
- **أضف** معالجة أخطاء قوية حتى لا يتعطل تطبيقك عند حدوث مشاكل
- **اكتب** وثائق واضحة لأي شخص يريد فهم كيفية عمل واجهة برمجة التطبيقات الخاصة بك

**تطوير الواجهة الأمامية:**
- **قم ببناء** واجهة دردشة تبدو بديهية ومرحبة
- **اكتب** JavaScript حديث ونظيف يمكنك أن تفخر بعرضه على المطورين الآخرين
- **صمم** تنسيقًا مخصصًا يعكس شخصية الذكاء الاصطناعي الخاص بك – مرح وملون؟ نظيف وبسيط؟ الأمر متروك لك تمامًا!
- **تأكد** من أنه يعمل بشكل رائع على كل من الهواتف وأجهزة الكمبيوتر

**متطلبات التخصيص:**
- **اختر** اسمًا وشخصية فريدة لمساعد الذكاء الاصطناعي الخاص بك – ربما شيء يعكس اهتماماتك أو المشاكل التي تريد حلها
- **خصص** التصميم المرئي ليتناسب مع طابع مساعدك
- **اكتب** رسالة ترحيب جذابة تجعل الناس يرغبون في بدء الدردشة
- **اختبر** مساعدك مع أنواع مختلفة من الأسئلة لترى كيف يرد

### أفكار تحسين (اختياري)

هل تريد رفع مستوى مشروعك؟ إليك بعض الأفكار الممتعة لاستكشافها:

| الميزة | الوصف | المهارات التي ستتدرب عليها |
|---------|-------------|------------------------|
| **سجل الرسائل** | تذكر المحادثات حتى بعد تحديث الصفحة | العمل مع التخزين المحلي، التعامل مع JSON |
| **مؤشرات الكتابة** | عرض "الذكاء الاصطناعي يكتب..." أثناء انتظار الردود | حركات CSS، البرمجة غير المتزامنة |
| **طوابع زمنية للرسائل** | عرض وقت إرسال كل رسالة | تنسيق التاريخ/الوقت، تصميم تجربة المستخدم |
| **تصدير الدردشة** | السماح للمستخدمين بتنزيل محادثاتهم | التعامل مع الملفات، تصدير البيانات |
| **تبديل السمات** | تبديل الوضع الفاتح/الداكن | متغيرات CSS، تفضيلات المستخدم |
| **إدخال صوتي** | إضافة وظيفة تحويل الكلام إلى نص | واجهات برمجة التطبيقات، سهولة الوصول |

### الاختبار والتوثيق

**ضمان الجودة:**
- **اختبر** تطبيقك مع أنواع مختلفة من المدخلات والحالات الحافة
- **تحقق** من أن التصميم المستجيب يعمل على أحجام شاشات مختلفة
- **افحص** سهولة الوصول باستخدام التنقل عبر لوحة المفاتيح وقارئات الشاشة
- **تحقق** من صحة HTML وCSS للامتثال للمعايير

**متطلبات التوثيق:**
- **اكتب** ملف README.md يشرح مشروعك وكيفية تشغيله
- **قم بتضمين** لقطات شاشة لواجهة الدردشة الخاصة بك أثناء العمل
- **وثق** أي ميزات فريدة أو تخصيصات أضفتها
- **قدم** تعليمات إعداد واضحة للمطورين الآخرين

### إرشادات التقديم

**مخرجات المشروع:**
1. مجلد المشروع الكامل مع جميع الكود المصدري
2. README.md مع وصف المشروع وتعليمات الإعداد
3. لقطات شاشة توضح مساعد الدردشة الخاص بك أثناء العمل
4. انعكاس موجز لما تعلمته وما التحديات التي واجهتها

**معايير التقييم:**
- **الوظائف**: هل يعمل مساعد الدردشة كما هو متوقع؟
- **جودة الكود**: هل الكود منظم جيدًا، معلق عليه، وقابل للصيانة؟
- **التصميم**: هل الواجهة جذابة بصريًا وسهلة الاستخدام؟
- **الإبداع**: ما مدى تفرد وتخصيص تنفيذك؟
- **التوثيق**: هل تعليمات الإعداد واضحة وكاملة؟

> 💡 **نصيحة للنجاح**: ابدأ بالمتطلبات الأساسية أولاً، ثم أضف التحسينات بمجرد أن يعمل كل شيء. ركز على إنشاء تجربة أساسية مصقولة قبل إضافة ميزات متقدمة.

## الحل

[الحل](./solution/README.md)

## تحديات إضافية

هل أنت مستعد لرفع مستوى مساعد الذكاء الاصطناعي الخاص بك؟ جرب هذه التحديات المتقدمة التي ستعمق فهمك لتكامل الذكاء الاصطناعي وتطوير الويب.

### تخصيص الشخصية

السحر الحقيقي يحدث عندما تمنح مساعد الذكاء الاصطناعي شخصية فريدة. جرب إعدادات النظام المختلفة لإنشاء مساعدين متخصصين:

**مثال مساعد محترف:**
```python
call_llm(message, "You are a professional business consultant with 20 years of experience. Provide structured, actionable advice with specific steps and considerations.")
```

**مثال مساعد الكتابة الإبداعية:**
```python
call_llm(message, "You are an enthusiastic creative writing coach. Help users develop their storytelling skills with imaginative prompts and constructive feedback.")
```

**مثال مرشد تقني:**
```python
call_llm(message, "You are a patient senior developer who explains complex programming concepts using simple analogies and practical examples.")
```

### تحسينات الواجهة الأمامية

حول واجهة الدردشة الخاصة بك باستخدام هذه التحسينات البصرية والوظيفية:

**ميزات CSS المتقدمة:**
- **قم بتطبيق** حركات الرسائل السلسة والانتقالات
- **أضف** تصميم فقاعات الدردشة المخصصة باستخدام أشكال CSS والتدرجات
- **أنشئ** حركة مؤشر الكتابة عندما يكون الذكاء الاصطناعي "يفكر"
- **صمم** ردود فعل الرموز التعبيرية أو نظام تقييم الرسائل

**تحسينات JavaScript:**
- **أضف** اختصارات لوحة المفاتيح (Ctrl+Enter للإرسال، Escape لمسح الإدخال)
- **قم بتنفيذ** وظيفة البحث والتصفية للرسائل
- **أنشئ** ميزة تصدير المحادثة (تنزيل كملف نصي أو JSON)
- **أضف** الحفظ التلقائي إلى التخزين المحلي لمنع فقدان الرسائل

### تكامل الذكاء الاصطناعي المتقدم

**شخصيات ذكاء اصطناعي متعددة:**
- **أنشئ** قائمة منسدلة للتبديل بين شخصيات الذكاء الاصطناعي المختلفة
- **احفظ** الشخصية المفضلة للمستخدم في التخزين المحلي
- **قم بتنفيذ** تبديل السياق الذي يحافظ على تدفق المحادثة

**ميزات الرد الذكي:**
- **أضف** وعيًا بسياق المحادثة (يتذكر الذكاء الاصطناعي الرسائل السابقة)
- **قم بتنفيذ** اقتراحات ذكية بناءً على موضوع المحادثة
- **أنشئ** أزرار الرد السريع للأسئلة الشائعة

> 🎯 **هدف التعلم**: تساعدك هذه التحديات الإضافية على فهم أنماط تطوير الويب المتقدمة وتقنيات تكامل الذكاء الاصطناعي المستخدمة في التطبيقات الإنتاجية.

## الملخص والخطوات التالية

تهانينا! لقد قمت ببناء مساعد دردشة كامل مدعوم بالذكاء الاصطناعي من البداية. هذا المشروع منحك تجربة عملية مع تقنيات تطوير الويب الحديثة وتكامل الذكاء الاصطناعي – مهارات ذات قيمة متزايدة في مشهد التكنولوجيا اليوم.

### ما الذي أنجزته

خلال هذا الدرس، أتقنت العديد من التقنيات والمفاهيم الرئيسية:

**تطوير الخادم الخلفي:**
- **تكامل** مع واجهة برمجة تطبيقات نماذج GitHub للحصول على وظائف الذكاء الاصطناعي
- **بناء** واجهة برمجة تطبيقات RESTful باستخدام Flask مع معالجة الأخطاء بشكل صحيح
- **تنفيذ** مصادقة آمنة باستخدام متغيرات البيئة
- **تكوين** CORS لطلبات عبر الأصل بين الواجهة الأمامية والخلفية

**تطوير الواجهة الأمامية:**
- **إنشاء** واجهة دردشة مستجيبة باستخدام HTML دلالي
- **تنفيذ** JavaScript حديث باستخدام async/await وبنية قائمة على الفئات
- **تصميم** واجهة مستخدم جذابة باستخدام CSS Grid، Flexbox، والحركات
- **إضافة** ميزات سهولة الوصول ومبادئ التصميم المستجيب

**التكامل الكامل:**
- **ربط** الواجهة الأمامية والخلفية من خلال طلبات واجهة برمجة التطبيقات HTTP
- **معالجة** تفاعلات المستخدم في الوقت الفعلي وتدفق البيانات غير المتزامن
- **تنفيذ** معالجة الأخطاء وردود الفعل للمستخدم في جميع أنحاء التطبيق
- **اختبار** سير عمل التطبيق الكامل من إدخال المستخدم إلى رد الذكاء الاصطناعي

### نتائج التعلم الرئيسية

```mermaid
mindmap
  root((AI Chat App Skills))
    API Integration
      Authentication
      Error Handling
      Async Programming
    Web Development
      HTML5 Semantics
      Modern CSS
      ES6+ JavaScript
    User Experience
      Responsive Design
      Accessibility
      Real-time Interaction
    AI Understanding
      Prompt Engineering
      Model Parameters
      Conversation Flow
```

هذا المشروع قدم لك أساسيات بناء تطبيقات مدعومة بالذكاء الاصطناعي، وهو يمثل مستقبل تطوير الويب. الآن تفهم كيفية دمج قدرات الذكاء الاصطناعي في التطبيقات التقليدية، مما يخلق تجارب مستخدم جذابة تبدو ذكية ومستجيبة.

### التطبيقات المهنية

المهارات التي طورتها في هذا الدرس قابلة للتطبيق مباشرةً في وظائف تطوير البرمجيات الحديثة:

- **تطوير الويب الكامل** باستخدام أطر عمل حديثة وواجهات برمجة التطبيقات
- **تكامل الذكاء الاصطناعي** في تطبيقات الويب وتطبيقات الهواتف المحمولة
- **تصميم وتطوير واجهات برمجة التطبيقات** لهياكل الخدمات المصغرة
- **تطوير واجهات المستخدم** مع التركيز على سهولة الوصول والتصميم المستجيب
- **ممارسات DevOps** بما في ذلك تكوين البيئة والنشر

### متابعة رحلتك في تطوير الذكاء الاصطناعي

**خطوات التعلم التالية:**
- **استكشاف** نماذج الذكاء الاصطناعي وواجهات برمجة التطبيقات المتقدمة (GPT-4، Claude، Gemini)
- **تعلم** تقنيات هندسة التعليمات للحصول على ردود أفضل من الذكاء الاصطناعي
- **دراسة** تصميم المحادثات ومبادئ تجربة المستخدم للروبوتات
- **التحقيق** في أمان الذكاء الاصطناعي، الأخلاقيات، وممارسات تطوير الذكاء الاصطناعي المسؤول
- **بناء** تطبيقات أكثر تعقيدًا مع ذاكرة المحادثة والوعي بالسياق

**أفكار مشاريع متقدمة:**
- غرف دردشة متعددة المستخدمين مع إدارة الذكاء الاصطناعي
- روبوتات خدمة العملاء المدعومة بالذكاء الاصطناعي
- مساعدي التدريس التعليمي مع تعلم شخصي
- شركاء الكتابة الإبداعية مع شخصيات ذكاء اصطناعي مختلفة
- مساعدي توثيق تقني للمطورين

## البدء مع GitHub Codespaces

هل تريد تجربة هذا المشروع في بيئة تطوير سحابية؟ يوفر GitHub Codespaces إعداد تطوير كامل في متصفحك، وهو مثالي لتجربة تطبيقات الذكاء الاصطناعي دون الحاجة إلى إعداد محلي.

### إعداد بيئة التطوير الخاصة بك

**الخطوة 1: الإنشاء من القالب**
- **انتقل** إلى [مستودع Web Dev For Beginners](https://github.com/microsoft/Web-Dev-For-Beginners)
- **انقر** على "Use this template" في الزاوية العلوية اليمنى (تأكد من تسجيل الدخول إلى GitHub)

![واجهة الإنشاء من القالب تظهر زر "Use this template" الأخضر](../../../translated_images/template.67ad477109d29a2b04599a83c964c87fcde041256d4f04d3589cbb00c696f76c.ar.png)

**الخطوة 2: تشغيل Codespaces**
- **افتح** المستودع الذي أنشأته حديثًا
- **انقر** على الزر الأخضر "Code" واختر "Codespaces"
- **اختر** "Create codespace on main" لبدء بيئة التطوير الخاصة بك

![واجهة إنشاء Codespace مع خيارات لتشغيل بيئة التطوير السحابية](../../../translated_images/codespace.bcecbdf5d2747d3d17da67a78ad911c8853d68102e34748ec372cde1e9236e1d.ar.png)

**الخطوة 3: تكوين البيئة**
بمجرد تحميل Codespace الخاص بك، سيكون لديك إمكانية الوصول إلى:
- **Python، Node.js مثبت مسبقًا** وجميع أدوات التطوير اللازمة
- **واجهة VS Code** مع إضافات لتطوير الويب
- **وصول إلى الطرفية** لتشغيل خوادم الخلفية والواجهة الأمامية
- **إعادة توجيه المنافذ** لاختبار تطبيقاتك

**ما توفره Codespaces:**
- **يقضي** على مشاكل إعداد البيئة المحلية وتكوينها
- **يوفر** بيئة تطوير متسقة عبر الأجهزة المختلفة
- **يتضمن** أدوات وإضافات مُعدة مسبقًا لتطوير الويب
- **يقدم** تكامل سلس مع GitHub للتحكم في الإصدارات والتعاون

> 🚀 **نصيحة احترافية**: Codespaces مثالي لتعلم وتطوير تطبيقات الذكاء الاصطناعي لأنه يتولى إعداد البيئة المعقدة تلقائيًا، مما يتيح لك التركيز على البناء والتعلم بدلاً من مواجهة مشاكل التكوين.

---

**إخلاء المسؤولية**:  
تم ترجمة هذا المستند باستخدام خدمة الترجمة بالذكاء الاصطناعي [Co-op Translator](https://github.com/Azure/co-op-translator). بينما نسعى لتحقيق الدقة، يرجى العلم أن الترجمات الآلية قد تحتوي على أخطاء أو عدم دقة. يجب اعتبار المستند الأصلي بلغته الأصلية المصدر الرسمي. للحصول على معلومات حاسمة، يُوصى بالترجمة البشرية الاحترافية. نحن غير مسؤولين عن أي سوء فهم أو تفسير خاطئ ينشأ عن استخدام هذه الترجمة.