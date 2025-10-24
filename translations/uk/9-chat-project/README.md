<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "46d665af66e51524598af34a42b9b663",
  "translation_date": "2025-10-24T15:37:46+00:00",
  "source_file": "9-chat-project/README.md",
  "language_code": "uk"
}
-->
# Створення чат-асистента з AI

Пам'ятаєте, як у "Зоряному шляху" екіпаж спокійно спілкувався з комп'ютером корабля, задаючи складні питання і отримуючи вдумливі відповіді? Те, що здавалося чистою науковою фантастикою у 1960-х, тепер можна створити за допомогою веб-технологій, які ви вже знаєте.

У цьому уроці ми створимо чат-асистента з AI, використовуючи HTML, CSS, JavaScript і трохи інтеграції з бекендом. Ви дізнаєтеся, як ті ж навички, які ви вивчаєте, можуть бути використані для підключення до потужних AI-сервісів, які розуміють контекст і генерують змістовні відповіді.

Думайте про AI як про доступ до величезної бібліотеки, яка не тільки знаходить інформацію, але й синтезує її у зрозумілі відповіді, адаптовані до ваших конкретних питань. Замість того, щоб шукати серед тисяч сторінок, ви отримуєте прямі, контекстуальні відповіді.

Інтеграція відбувається через знайомі веб-технології, які працюють разом. HTML створює інтерфейс чату, CSS відповідає за візуальний дизайн, JavaScript керує взаємодією з користувачем, а бекенд API з'єднує все це з AI-сервісами. Це схоже на те, як різні секції оркестру працюють разом, щоб створити симфонію.

Ми фактично будуємо міст між природним людським спілкуванням і машинною обробкою. Ви навчитеся як технічній реалізації інтеграції AI-сервісів, так і шаблонам дизайну, які роблять взаємодію інтуїтивною.

До кінця цього уроку інтеграція AI буде здаватися менш загадковим процесом і більше схожою на ще один API, з яким ви можете працювати. Ви зрозумієте основні шаблони, які живлять такі додатки, як ChatGPT і Claude, використовуючи ті ж принципи веб-розробки, які ви вже вивчаєте.

Ось як виглядатиме ваш готовий проєкт:

![Інтерфейс чату, що показує розмову між користувачем і AI-асистентом](../../../translated_images/screenshot.0a1ee0d123df681b4501eb53ffb267519fcc20aa653eabecef1e7561ddfb1cab.uk.png)

## Розуміння AI: від загадки до майстерності

Перш ніж зануритися в код, давайте зрозуміємо, з чим ми працюємо. Якщо ви вже використовували API, то знаєте основний шаблон: відправити запит, отримати відповідь.

API AI працюють за схожою структурою, але замість отримання попередньо збережених даних з бази даних вони генерують нові відповіді на основі шаблонів, вивчених з величезної кількості текстів. Думайте про це як про різницю між системою каталогів бібліотеки і знаючим бібліотекарем, який може синтезувати інформацію з кількох джерел.

### Що таке "Генеративний AI" насправді?

Згадайте, як Розетський камінь дозволив ученим зрозуміти єгипетські ієрогліфи, знаходячи шаблони між відомими і невідомими мовами. Моделі AI працюють схожим чином – вони знаходять шаблони у величезних обсягах тексту, щоб зрозуміти, як працює мова, а потім використовують ці шаблони для генерації відповідних відповідей на нові питання.

**Давайте розберемо це на простому порівнянні:**
- **Традиційна база даних**: Як запит на свідоцтво про народження – ви отримуєте той самий документ кожного разу.
- **Пошукова система**: Як запит до бібліотекаря знайти книги про котів – вони показують вам, що доступно.
- **Генеративний AI**: Як запит до знаючого друга про котів – вони розповідають вам цікаві речі своїми словами, адаптовані до того, що ви хочете знати.

```mermaid
graph LR
    A[Your Question] --> B[AI Model]
    B --> C[Pattern Recognition]
    C --> D[Content Generation]
    D --> E[Contextual Response]
    
    F[Training Data<br/>Books, Articles, Web] --> B
```

### Як навчаються моделі AI (спрощена версія)

Моделі AI навчаються через ознайомлення з величезними наборами даних, що містять тексти з книг, статей і розмов. У процесі вони визначають шаблони в:
- Структурі думок у письмовій комунікації
- Словах, які часто зустрічаються разом
- Типовому потоці розмов
- Контекстуальних відмінностях між формальною і неформальною комунікацією

**Це схоже на те, як археологи розшифровують стародавні мови**: вони аналізують тисячі прикладів, щоб зрозуміти граматику, словниковий запас і культурний контекст, і врешті-решт стають здатними інтерпретувати нові тексти, використовуючи вивчені шаблони.

### Чому GitHub Models?

Ми використовуємо GitHub Models з практичної причини – це дає нам доступ до AI корпоративного рівня без необхідності налаштовувати власну AI-інфраструктуру (а це, повірте, зараз вам не потрібно!). Думайте про це як про використання API погоди замість спроби передбачити погоду самостійно, встановлюючи метеостанції всюди.

Це фактично "AI як сервіс", і найкраще? Це безкоштовно для початку, тому ви можете експериментувати, не турбуючись про величезні рахунки.

```mermaid
graph LR
    A[Frontend Chat UI] --> B[Your Backend API]
    B --> C[GitHub Models API]
    C --> D[AI Model Processing]
    D --> C
    C --> B
    B --> A
```

Ми будемо використовувати GitHub Models для інтеграції бекенду, що забезпечує доступ до AI професійного рівня через зручний для розробників інтерфейс. [GitHub Models Playground](https://github.com/marketplace/models/azure-openai/gpt-4o-mini/playground) слугує тестовим середовищем, де ви можете експериментувати з різними AI-моделями і зрозуміти їх можливості перед тим, як реалізувати їх у коді.

![Інтерфейс GitHub Models AI Playground з вибором моделі і тестовою зоною](../../../translated_images/playground.d2b927122224ff8ff4028fc842176e353c339147d8925455f36c92fb1655c477.uk.png)

**Ось чому цей майданчик такий корисний:**
- **Спробуйте** різні AI-моделі, такі як GPT-4o-mini, Claude та інші (усі безкоштовні!)
- **Тестуйте** свої ідеї і запити перед написанням коду
- **Отримуйте** готові фрагменти коду у вашій улюбленій мові програмування
- **Налаштовуйте** параметри, такі як рівень креативності і довжина відповіді, щоб побачити, як вони впливають на результат

Після того, як ви трохи пограєте, просто натисніть вкладку "Code" і виберіть свою мову програмування, щоб отримати код для реалізації.

![Вибір у майданчику, що показує варіанти генерації коду для різних мов програмування](../../../translated_images/playground-choice.1d23ba7d407f47584c9f446c77f0bcf70cae794cc9c8d7849a3cca4a3693e6c4.uk.png)

## Налаштування інтеграції бекенду на Python

Тепер давайте реалізуємо інтеграцію AI за допомогою Python. Python чудово підходить для AI-додатків завдяки простому синтаксису і потужним бібліотекам. Ми почнемо з коду з майданчика GitHub Models, а потім переробимо його у багаторазову функцію, готову до використання у виробництві.

### Розуміння базової реалізації

Коли ви отримуєте код на Python з майданчика, він виглядає приблизно так. Не хвилюйтеся, якщо спочатку це здається складним – давайте розберемо його по частинах:

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

**Ось що відбувається у цьому коді:**
- **Ми імпортуємо** необхідні інструменти: `os` для читання змінних середовища і `OpenAI` для взаємодії з AI
- **Налаштовуємо** клієнт OpenAI, щоб він звертався до серверів AI GitHub, а не безпосередньо до OpenAI
- **Аутентифікуємося** за допомогою спеціального токена GitHub (про це трохи пізніше!)
- **Структуруємо** нашу розмову з різними "ролями" – це як встановлення сцени для вистави
- **Відправляємо** наш запит до AI з деякими параметрами тонкої настройки
- **Витягуємо** фактичний текст відповіді з усіх даних, які повертаються

### Розуміння ролей повідомлень: структура AI-розмови

AI-розмови використовують специфічну структуру з різними "ролями", які виконують окремі функції:

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

**Думайте про це як про режисуру вистави:**
- **Роль системи**: Як сценічні вказівки для актора – це говорить AI, як себе вести, яку особистість мати і як відповідати
- **Роль користувача**: Фактичне питання або повідомлення від людини, яка використовує ваш додаток
- **Роль асистента**: Відповідь AI (ви не відправляєте це, але воно з'являється в історії розмови)

**Аналогія з реального життя**: Уявіть, що ви представляєте друга комусь на вечірці:
- **Повідомлення системи**: "Це моя подруга Сара, вона лікар, яка чудово пояснює медичні концепції простими словами"
- **Повідомлення користувача**: "Чи можете ви пояснити, як працюють вакцини?"
- **Відповідь асистента**: Сара відповідає як дружній лікар, а не як юрист чи кухар

### Розуміння параметрів AI: тонка настройка поведінки відповіді

Числові параметри у викликах API AI контролюють, як модель генерує відповіді. Ці налаштування дозволяють вам регулювати поведінку AI для різних випадків використання:

#### Temperature (0.0 до 2.0): Діапазон креативності

**Що це робить**: Контролює, наскільки креативними або передбачуваними будуть відповіді AI.

**Думайте про це як про рівень імпровізації джазового музиканта:**
- **Temperature = 0.1**: Грає одну й ту ж мелодію кожного разу (дуже передбачувано)
- **Temperature = 0.7**: Додає деякі варіації, залишаючись впізнаваним (збалансована креативність)
- **Temperature = 1.5**: Повна експериментальна імпровізація з несподіваними поворотами (дуже непередбачувано)

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

#### Max Tokens (1 до 4096+): Контролер довжини відповіді

**Що це робить**: Встановлює обмеження на те, наскільки довгою може бути відповідь AI.

**Думайте про токени як приблизно еквівалентні словам** (приблизно 1 токен = 0.75 слова англійською):
- **max_tokens=50**: Коротко і лаконічно (як текстове повідомлення)
- **max_tokens=500**: Гарний абзац або два
- **max_tokens=2000**: Детальне пояснення з прикладами

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

#### Top_p (0.0 до 1.0): Параметр фокусування

**Що це робить**: Контролює, наскільки AI зосереджується на найбільш ймовірних відповідях.

**Уявіть, що AI має величезний словниковий запас, ранжований за ймовірністю кожного слова:**
- **top_p=0.1**: Розглядає лише топ-10% найбільш ймовірних слів (дуже сфокусовано)
- **top_p=0.9**: Розглядає 90% можливих слів (більш креативно)
- **top_p=1.0**: Розглядає все (максимальна різноманітність)

**Наприклад**: Якщо ви запитаєте "Небо зазвичай..."
- **Низький top_p**: Майже напевно скаже "синє"
- **Високий top_p**: Може сказати "синє", "хмарне", "широке", "змінне", "гарне" тощо

### Об'єднання всього: комбінації параметрів для різних випадків використання

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

**Розуміння, чому ці параметри важливі**: Різні додатки потребують різних типів відповідей. Бот служби підтримки клієнтів має бути послідовним і фактичним (низька температура), тоді як асистент для творчого письма має бути уявним і різноманітним (висока температура). Розуміння цих параметрів дає вам контроль над особистістю і стилем відповіді AI.
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

**Розуміння цієї покращеної функції:**
- **Приймає** два параметри: запит користувача і необов'язкове системне повідомлення
- **Надає** стандартне системне повідомлення для загальної поведінки асистента
- **Використовує** правильні підказки типів Python для кращої документації коду
- **Включає** детальний docstring, що пояснює мету і параметри функції
- **Повертає** лише зміст відповіді, що робить її легкою у використанні в нашому веб-API
- **Підтримує** ті ж параметри моделі для послідовної поведінки AI

### Магія системних підказок: програмування особистості AI

Якщо параметри контролюють, як AI думає, то системні підказки контролюють, ким AI себе вважає. Це, чесно кажучи, одна з найцікавіших частин роботи з AI – ви фактично надаєте AI повну особистість, рівень експертизи і стиль комунікації.

**Думайте про системні підказки як про кастинг різних акторів для різних ролей**: Замість того, щоб мати одного загального асистента, ви можете створити спеціалізованих експертів для різних ситуацій. Потрібен терплячий вчитель? Творчий партнер для мозкового штурму? Діловий радник без зайвих слів? Просто змініть системну підказку!

#### Чому системні підказки такі потужні

Ось що захоплює: моделі AI були навчені на безлічі розмов, де люди приймають різні ролі і рівні експертизи. Коли ви надаєте AI конкретну роль, це як перемикання, яке активує всі ці вивчені шаблони.

**Це як методична акторська гра для AI**: Скажіть актору "ти мудрий старий професор" і подивіться, як він автоматично змінює свою поставу, словниковий запас і манери. AI робить щось надзвичайно схоже з мовними шаблонами.

#### Створення ефективних системних підказок: мистецтво і наука

**Анатомія чудової системної підказки:**
1. **Роль/Ідентичність**: Хто AI?
2. **Експертиза**: Що він знає?
3. **Стиль комунікації**: Як він говорить?
4. **Конкретні інструкції**: На чому він має зосередитися?

```python
# ❌ Vague system prompt
"You are helpful."

# ✅ Detailed, effective system prompt
"You are Dr. Sarah Chen, a senior software engineer with 15 years of experience at major tech companies. You explain programming concepts using real-world analogies and always provide practical examples. You're patient with beginners and enthusiastic about helping them understand complex topics."
```

#### Приклади системних підказок з контекстом

Давайте подивимося, як різні системні підказки створюють абсолютно різні особистості AI:

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

#### Перегляд системних підказок у дії

Давайте протестуємо одне і те ж питання з різними системними підказками, щоб побачити драматичні відмінності:

**Питання**: "Як мені впоратися з аутентифікацією користувачів у моєму веб-додатку?"

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

#### Розширені техніки системних підказок

**1. Налаштування контексту**: Надання AI фонової інформації
```python
system_prompt = """
You are helping a junior developer who just started their first job at a startup. 
They know basic HTML/CSS/JavaScript but are new to backend development and databases. 
Be encouraging and explain things step-by-step without being condescending.
"""
```

**2. Форматування виходу**: Вказівка AI, як структурувати відповіді
@@CODE_BLOCK_
**Ось чому FastAPI ідеально підходить для нашого проекту:**
- **Асинхронність за замовчуванням**: Може обробляти кілька запитів AI одночасно без затримок
- **Автоматична документація**: Перейдіть на `/docs` і отримайте красиву, інтерактивну сторінку документації API безкоштовно
- **Вбудована валідація**: Виявляє помилки до того, як вони спричинять проблеми
- **Блискавична швидкість**: Один із найшвидших фреймворків для Python
- **Сучасний Python**: Використовує всі найновіші функції Python

**І ось чому нам потрібен бекенд взагалі:**

**Безпека**: Ваш ключ API для AI схожий на пароль – якщо ви розмістите його у фронтенд JavaScript, будь-хто, хто перегляне вихідний код вашого сайту, може вкрасти його і використати ваші AI-кредити. Бекенд зберігає конфіденційні дані в безпеці.

**Обмеження запитів і контроль**: Бекенд дозволяє контролювати, як часто користувачі можуть надсилати запити, впроваджувати автентифікацію користувачів і додавати логування для відстеження використання.

**Обробка даних**: Ви можете захотіти зберігати розмови, фільтрувати недоречний контент або комбінувати кілька AI-сервісів. Логіка для цього знаходиться в бекенді.

**Архітектура нагадує модель клієнт-сервер:**
- **Фронтенд**: Шар інтерфейсу для взаємодії з користувачем
- **API бекенду**: Шар обробки запитів і маршрутизації
- **AI-сервіс**: Зовнішні обчислення і генерація відповідей
- **Змінні середовища**: Безпечне зберігання конфігурації та облікових даних

### Розуміння потоку запит-відповідь

Давайте простежимо, що відбувається, коли користувач надсилає повідомлення:

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

**Розуміння кожного кроку:**
1. **Взаємодія користувача**: Людина вводить текст у чаті
2. **Обробка фронтендом**: JavaScript захоплює введення і форматує його як JSON
3. **Валідація API**: FastAPI автоматично перевіряє запит за допомогою моделей Pydantic
4. **Інтеграція AI**: Бекенд додає контекст (системний промпт) і викликає AI-сервіс
5. **Обробка відповіді**: API отримує відповідь AI і може змінити її, якщо потрібно
6. **Відображення на фронтенді**: JavaScript показує відповідь у чаті

### Розуміння архітектури API

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

### Створення додатку FastAPI

Давайте створимо наш API крок за кроком. Створіть файл `api.py` з наступним кодом FastAPI:

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

**Розуміння реалізації FastAPI:**
- **Імпортує** FastAPI для сучасного функціоналу веб-фреймворку і Pydantic для валідації даних
- **Створює** автоматичну документацію API (доступну на `/docs`, коли сервер запущений)
- **Вмикає** CORS middleware для дозволу запитів фронтенду з різних джерел
- **Визначає** моделі Pydantic для автоматичної валідації запитів/відповідей і документації
- **Використовує** асинхронні кінцеві точки для кращої продуктивності при одночасних запитах
- **Реалізує** правильні HTTP статус-коди і обробку помилок за допомогою HTTPException
- **Включає** структуроване логування для моніторингу і налагодження
- **Надає** кінцеву точку перевірки стану для моніторингу статусу сервісу

**Основні переваги FastAPI над традиційними фреймворками:**
- **Автоматична валідація**: Моделі Pydantic забезпечують цілісність даних перед обробкою
- **Інтерактивна документація**: Перейдіть на `/docs` для автоматично згенерованої, тестованої документації API
- **Безпека типів**: Підказки типів Python запобігають помилкам під час виконання і покращують якість коду
- **Підтримка асинхронності**: Обробляйте кілька запитів AI одночасно без блокування
- **Продуктивність**: Значно швидша обробка запитів для додатків у реальному часі

### Розуміння CORS: Охоронець безпеки вебу

CORS (Cross-Origin Resource Sharing) схожий на охоронця в будівлі, який перевіряє, чи дозволено відвідувачам входити. Давайте зрозуміємо, чому це важливо і як це впливає на ваш додаток.

#### Що таке CORS і чому він існує?

**Проблема**: Уявіть, що будь-який сайт міг би надсилати запити до сайту вашого банку від вашого імені без вашого дозволу. Це був би кошмар безпеки! Браузери запобігають цьому за замовчуванням через "Політику однакового походження".

**Політика однакового походження**: Браузери дозволяють веб-сторінкам надсилати запити лише до того ж домену, порту і протоколу, з якого вони були завантажені.

**Аналогія з реального життя**: Це як охорона в багатоквартирному будинку – тільки мешканці (однакове походження) можуть отримати доступ до будівлі за замовчуванням. Якщо ви хочете, щоб друг (інше походження) зайшов, вам потрібно явно сказати охороні, що це дозволено.

#### CORS у вашому середовищі розробки

Під час розробки ваш фронтенд і бекенд працюють на різних портах:
- Фронтенд: `http://localhost:3000` (або file://, якщо відкриваєте HTML напряму)
- Бекенд: `http://localhost:5000`

Це вважається "різними походженнями", навіть якщо вони знаходяться на одному комп'ютері!

```python
from fastapi.middleware.cors import CORSMiddleware

app = FastAPI(__name__)
CORS(app)   # This tells browsers: "It's okay for other origins to make requests to this API"
```

**Що робить конфігурація CORS на практиці:**
- **Додає** спеціальні HTTP-заголовки до відповідей API, які повідомляють браузерам "цей запит з іншого походження дозволений"
- **Обробляє** "попередні" запити (браузери іноді перевіряють дозволи перед надсиланням фактичного запиту)
- **Запобігає** страшній помилці "заблоковано політикою CORS" у консолі вашого браузера

#### Безпека CORS: Розробка vs Продакшн

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

**Чому це важливо**: У розробці `CORS(app)` схоже на залишення дверей відкритими – зручно, але небезпечно. У продакшні ви хочете точно вказати, які сайти можуть взаємодіяти з вашим API.

#### Загальні сценарії CORS і рішення

| Сценарій | Проблема | Рішення |
|----------|---------|----------|
| **Локальна розробка** | Фронтенд не може дістатися до бекенду | Додайте CORSMiddleware до FastAPI |
| **GitHub Pages + Heroku** | Розгорнутий фронтенд не може дістатися до API | Додайте URL вашого GitHub Pages до походжень CORS |
| **Користувацький домен** | Помилки CORS у продакшні | Оновіть походження CORS, щоб відповідати вашому домену |
| **Мобільний додаток** | Додаток не може дістатися до веб-API | Додайте домен вашого додатку або обережно використовуйте `*` |

**Порада**: Ви можете перевірити заголовки CORS у Інструментах розробника вашого браузера на вкладці Мережа. Шукайте заголовки, такі як `Access-Control-Allow-Origin` у відповіді.

### Обробка помилок і валідація

Зверніть увагу, як наш API включає правильну обробку помилок:

```python
# Validate that we received a message
if not message:
    return jsonify({"error": "Message field is required"}), 400
```

**Основні принципи валідації:**
- **Перевіряє** обов'язкові поля перед обробкою запитів
- **Повертає** змістовні повідомлення про помилки у форматі JSON
- **Використовує** відповідні HTTP статус-коди (400 для некоректних запитів)
- **Надає** чіткий зворотний зв'язок, щоб допомогти розробникам фронтенду налагоджувати проблеми

## Налаштування і запуск вашого бекенду

Тепер, коли ми маємо інтеграцію AI і сервер FastAPI, давайте запустимо все. Процес налаштування включає встановлення залежностей Python, конфігурацію змінних середовища і запуск вашого сервера розробки.

### Налаштування середовища Python

Давайте налаштуємо ваше середовище розробки Python. Віртуальні середовища схожі на підхід Манхеттенського проекту – кожен проект отримує свій власний ізольований простір зі специфічними інструментами і залежностями, запобігаючи конфліктам між різними проектами.

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

**Що ми щойно зробили:**
- **Створили** власний маленький Python-бульбашку, де ми можемо встановлювати пакети, не впливаючи на інші
- **Активували** її, щоб наш термінал знав, що використовувати це конкретне середовище
- **Встановили** необхідне: OpenAI для магії AI, FastAPI для нашого веб-API, Uvicorn для його запуску і python-dotenv для безпечного управління секретами

**Основні залежності пояснені:**
- **FastAPI**: Сучасний, швидкий веб-фреймворк з автоматичною документацією API
- **Uvicorn**: Блискавично швидкий сервер ASGI, який запускає додатки FastAPI
- **OpenAI**: Офіційна бібліотека для моделей GitHub і інтеграції API OpenAI
- **python-dotenv**: Безпечне завантаження змінних середовища з файлів .env

### Конфігурація середовища: Збереження секретів у безпеці

Перед тим, як запустити наш API, нам потрібно поговорити про один із найважливіших уроків у веб-розробці: як зберігати ваші секрети дійсно секретними. Змінні середовища схожі на сейф, до якого має доступ лише ваш додаток.

#### Що таке змінні середовища?

**Думайте про змінні середовища як про сейф для зберігання цінностей** – ви кладете туди свої цінні речі, і тільки ви (і ваш додаток) маєте ключ, щоб їх дістати. Замість того, щоб писати конфіденційну інформацію прямо в коді (де її може побачити буквально кожен), ви зберігаєте її безпечно в середовищі.

**Ось різниця:**
- **Неправильний спосіб**: Написати свій пароль на стікері і приклеїти його до монітора
- **Правильний спосіб**: Зберігати свій пароль у безпечному менеджері паролів, до якого маєте доступ тільки ви

#### Чому змінні середовища важливі

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

**Що відбувається, коли ви жорстко кодуєте секрети:**
1. **Експозиція у версійному контролі**: Кожен, хто має доступ до вашого Git-репозиторію, бачить ваш ключ API
2. **Публічні репозиторії**: Якщо ви завантажуєте на GitHub, ваш ключ видно всьому інтернету
3. **Спільна робота в команді**: Інші розробники, які працюють над вашим проектом, отримують доступ до вашого особистого ключа API
4. **Порушення безпеки**: Якщо хтось краде ваш ключ API, він може використовувати ваші AI-кредити

#### Налаштування вашого файлу середовища

Створіть файл `.env` у вашій директорії бекенду. Цей файл зберігає ваші секрети локально:

```bash
# .env file - This should NEVER be committed to Git
GITHUB_TOKEN=your_github_personal_access_token_here
FASTAPI_DEBUG=True
ENVIRONMENT=development
```

**Розуміння файлу .env:**
- **Один секрет на рядок** у форматі `KEY=value`
- **Без пробілів** навколо знака рівності
- **Без лапок** навколо значень (зазвичай)
- **Коментарі** починаються з `#`

#### Створення вашого персонального токена доступу GitHub

Ваш токен GitHub схожий на спеціальний пароль, який дає вашому додатку дозвіл використовувати AI-сервіси GitHub:

**Покрокове створення токена:**
1. **Перейдіть до налаштувань GitHub** → Налаштування розробника → Персональні токени доступу → Токени (класичні)
2. **Натисніть "Створити новий токен (класичний)"**
3. **Встановіть термін дії** (30 днів для тестування, довше для продакшну)
4. **Виберіть області**: Позначте "repo" і будь-які інші дозволи, які вам потрібні
5. **Створіть токен** і скопіюйте його негайно (ви не зможете побачити його знову!)
6. **Вставте у ваш файл .env**

```bash
# Example of what your token looks like (this is fake!)
GITHUB_TOKEN=ghp_1A2B3C4D5E6F7G8H9I0J1K2L3M4N5O6P7Q8R
```

#### Завантаження змінних середовища у Python

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

**Що робить цей код:**
- **Завантажує** ваш файл .env і робить змінні доступними для Python
- **Перевіряє**, чи існує необхідний токен (хороша обробка помилок!)
- **Викликає** чітку помилку, якщо токен відсутній
- **Використовує** токен безпечно, не розкриваючи його в коді

#### Безпека Git: Файл .gitignore

Ваш файл `.gitignore` повідомляє Git, які файли ніколи не слід відстежувати або завантажувати:

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

**Чому це важливо**: Як тільки ви додасте `.env` до `.gitignore`, Git буде ігнорувати ваш файл середовища, запобігаючи випадковому завантаженню ваших секретів на GitHub.

#### Різні середовища, різні секрети

Професійні додатки використовують різні ключі API для різних середовищ:

```bash
# .env.development
GITHUB_TOKEN=your_development_token
DEBUG=True

# .env.production  
GITHUB_TOKEN=your_production_token
DEBUG=False
```

**Чому це важливо**: Ви не хочете, щоб ваші експерименти в розробці впливали на вашу квоту використання AI у продакшні, і ви хочете різні рівні безпеки для різних середовищ.

### Запуск вашого сервера розробки: Оживлення вашого FastAPI

Тепер настав захоплюючий момент – запуск сервера розробки FastAPI і спостереження за інтеграцією AI у дії! FastAPI використовує Uvicorn, блискавично швидкий сервер ASGI, спеціально розроблений для асинхронних додатків Python.

#### Розуміння процесу запуску сервера FastAPI

```bash
# Method 1: Direct Python execution (includes auto-reload)
python api.py

# Method 2: Using Uvicorn directly (more control)
uvicorn api:app --host 0.0.0.0 --port 5000 --reload
```

Коли ви запускаєте цю команду, ось що відбувається за лаштунками:

**1. Python завантажує ваш додаток FastAPI**:
- Імпортує всі необхідні бібліотеки (FastAPI, Pydantic, OpenAI тощо)
- Завантажує змінні середовища з вашого файлу `.env`
- Створює екземпляр додатку FastAPI з автоматичною документацією

**2. Uvicorn налаштовує сервер ASGI**:
- Прив'язується до порту 5000 з можливостями асинхронної обробки запитів
- Налаштовує маршрутизацію запитів з автоматичною валідацією
- Вмикає автоматичне перезавантаження для розробки (перезап
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

#### Вирішення поширених проблем запуску

| Повідомлення про помилку | Що це означає | Як виправити |
|--------------------------|---------------|--------------|
| `ModuleNotFoundError: No module named 'fastapi'` | FastAPI не встановлено | Запустіть `pip install fastapi uvicorn` у вашому віртуальному середовищі |
| `ModuleNotFoundError: No module named 'uvicorn'` | ASGI сервер не встановлено | Запустіть `pip install uvicorn` у вашому віртуальному середовищі |
| `KeyError: 'GITHUB_TOKEN'` | Змінна середовища не знайдена | Перевірте ваш файл `.env` і виклик `load_dotenv()` |
| `Address already in use` | Порт 5000 зайнятий | Завершіть інші процеси, які використовують порт 5000, або змініть порт |
| `ValidationError` | Дані запиту не відповідають моделі Pydantic | Перевірте, чи формат вашого запиту відповідає очікуваній схемі |
| `HTTPException 422` | Непридатна сутність | Валідація запиту не пройшла, перевірте `/docs` для правильного формату |
| `OpenAI API error` | Аутентифікація AI сервісу не вдалася | Перевірте, чи ваш GitHub токен правильний і має необхідні дозволи |

#### Найкращі практики розробки

**Автоматичне перезавантаження**: FastAPI з Uvicorn забезпечує автоматичне перезавантаження при збереженні змін у ваших Python файлах. Це дозволяє модифікувати код і тестувати його негайно без ручного перезапуску.

```python
# Enable hot reloading explicitly
if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000, debug=True)  # debug=True enables hot reload
```

**Логування для розробки**: Додайте логування, щоб зрозуміти, що відбувається:

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

**Чому логування допомагає**: Під час розробки ви можете бачити, які запити надходять, як відповідає AI, і де виникають помилки. Це значно прискорює процес налагодження.

### Налаштування для GitHub Codespaces: Розробка в хмарі стала простішою

GitHub Codespaces — це як потужний комп'ютер для розробки в хмарі, до якого ви можете отримати доступ з будь-якого браузера. Якщо ви працюєте в Codespaces, є кілька додаткових кроків, щоб зробити ваш бекенд доступним для фронтенду.

#### Розуміння мережі Codespaces

У локальному середовищі розробки все працює на одному комп'ютері:
- Бекенд: `http://localhost:5000`
- Фронтенд: `http://localhost:3000` (або file://)

У Codespaces ваше середовище розробки працює на серверах GitHub, тому "localhost" має інше значення. GitHub автоматично створює публічні URL-адреси для ваших сервісів, але їх потрібно правильно налаштувати.

#### Покрокова конфігурація Codespaces

**1. Запустіть сервер бекенду**:
```bash
cd backend
python api.py
```

Ви побачите знайоме повідомлення про запуск FastAPI/Uvicorn, але зверніть увагу, що воно працює всередині середовища Codespace.

**2. Налаштуйте видимість порту**:
- Знайдіть вкладку "Ports" у нижній панелі VS Code
- Знайдіть порт 5000 у списку
- Клацніть правою кнопкою миші на порт 5000
- Виберіть "Port Visibility" → "Public"

**Чому зробити його публічним?** За замовчуванням порти Codespace є приватними (доступні лише вам). Зробивши порт публічним, ви дозволяєте вашому фронтенду (який працює в браузері) спілкуватися з бекендом.

**3. Отримайте ваш публічний URL**:
Після того, як порт стане публічним, ви побачите URL-адресу, наприклад:
```
https://your-codespace-name-5000.app.github.dev
```

**4. Оновіть конфігурацію фронтенду**:
```javascript
// In your frontend app.js, update the BASE_URL:
this.BASE_URL = "https://your-codespace-name-5000.app.github.dev";
```

#### Розуміння URL-адрес Codespace

URL-адреси Codespace мають передбачуваний шаблон:
```
https://[codespace-name]-[port].app.github.dev
```

**Розшифровка:**
- `codespace-name`: Унікальний ідентифікатор вашого Codespace (зазвичай включає ваше ім'я користувача)
- `port`: Номер порту, на якому працює ваш сервіс (5000 для нашого додатка FastAPI)
- `app.github.dev`: Домен GitHub для додатків Codespace

#### Тестування налаштування Codespace

**1. Тестуйте бекенд безпосередньо**:
Відкрийте ваш публічний URL у новій вкладці браузера. Ви повинні побачити:
```
Welcome to the AI Chat API. Send POST requests to /hello with JSON payload containing 'message' field.
```

**2. Тестуйте за допомогою інструментів розробника браузера**:
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

#### Codespaces vs Локальна розробка

| Аспект | Локальна розробка | GitHub Codespaces |
|--------|-------------------|-------------------|
| **Час налаштування** | Довше (встановлення Python, залежностей) | Миттєво (попередньо налаштоване середовище) |
| **Доступ до URL** | `http://localhost:5000` | `https://xyz-5000.app.github.dev` |
| **Конфігурація порту** | Автоматична | Ручна (зробити порти публічними) |
| **Збереження файлів** | Локальний комп'ютер | Репозиторій GitHub |
| **Співпраця** | Важко поділитися середовищем | Легко поділитися посиланням на Codespace |
| **Залежність від Інтернету** | Тільки для викликів AI API | Потрібен для всього |

#### Поради для розробки в Codespaces

**Змінні середовища в Codespaces**:
Ваш файл `.env` працює так само в Codespaces, але ви також можете встановлювати змінні середовища безпосередньо в Codespace:

```bash
# Set environment variable for the current session
export GITHUB_TOKEN="your_token_here"

# Or add to your .bashrc for persistence
echo 'export GITHUB_TOKEN="your_token_here"' >> ~/.bashrc
```

**Управління портами**:
- Codespaces автоматично визначає, коли ваш додаток починає слухати порт
- Ви можете одночасно пересилати кілька портів (корисно, якщо ви додаєте базу даних пізніше)
- Порти залишаються доступними, поки ваш Codespace працює

**Робочий процес розробки**:
1. Внесіть зміни в код у VS Code
2. FastAPI автоматично перезавантажується (завдяки режиму перезавантаження Uvicorn)
3. Тестуйте зміни негайно через публічний URL
4. Зробіть коміт і пуш, коли будете готові

> 💡 **Порада**: Додайте в закладки URL вашого бекенду Codespace під час розробки. Оскільки назви Codespace стабільні, URL не зміниться, поки ви використовуєте той самий Codespace.

## Створення інтерфейсу чату: де люди зустрічаються з AI

Тепер ми створимо користувацький інтерфейс – частину, яка визначає, як люди взаємодіють з вашим AI-помічником. Як дизайн інтерфейсу оригінального iPhone, ми зосереджуємося на тому, щоб зробити складну технологію інтуїтивно зрозумілою та природною у використанні.

### Розуміння сучасної архітектури фронтенду

Наш інтерфейс чату буде тим, що ми називаємо "Односторінковим додатком" або SPA. Замість старомодного підходу, де кожен клік завантажує нову сторінку, наш додаток оновлюється плавно та миттєво:

**Старі вебсайти**: Як читання фізичної книги – ви перегортаєте на абсолютно нові сторінки
**Наш чат-додаток**: Як використання телефону – все плавно оновлюється

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

### Три основи фронтенд-розробки

Кожен фронтенд-додаток – від простих вебсайтів до складних додатків, таких як Discord або Slack – будується на трьох основних технологіях. Вони є фундаментом усього, що ви бачите та з чим взаємодієте в Інтернеті:

**HTML (Структура)**: Це ваш фундамент
- Визначає, які елементи існують (кнопки, текстові поля, контейнери)
- Надає зміст елементам (це заголовок, це форма тощо)
- Створює базову структуру, на якій все будується

**CSS (Оформлення)**: Це ваш дизайнер інтер'єру
- Робить все красивим (кольори, шрифти, макети)
- Підлаштовується під різні розміри екранів (телефон, ноутбук, планшет)
- Створює плавні анімації та візуальний зворотний зв'язок

**JavaScript (Поведінка)**: Це ваш мозок
- Реагує на дії користувачів (кліки, введення тексту, прокрутка)
- Спілкується з вашим бекендом і оновлює сторінку
- Робить все інтерактивним і динамічним

**Уявіть це як архітектурний дизайн:**
- **HTML**: Структурний план (визначення простору та взаємозв'язків)
- **CSS**: Естетичний дизайн (візуальний стиль і досвід користувача)
- **JavaScript**: Механічні системи (функціональність та інтерактивність)

### Чому важлива сучасна архітектура JavaScript

Наш чат-додаток буде використовувати сучасні шаблони JavaScript, які ви побачите в професійних додатках. Розуміння цих концепцій допоможе вам розвиватися як розробнику:

**Архітектура на основі класів**: Ми організуємо наш код у класи, що схоже на створення креслень для об'єктів
**Async/Await**: Сучасний спосіб обробки операцій, які займають час (наприклад, виклики API)
**Програмування на основі подій**: Наш додаток реагує на дії користувачів (кліки, натискання клавіш), а не працює в циклі
**Маніпуляція DOM**: Динамічне оновлення вмісту вебсторінки на основі взаємодій користувачів і відповідей API

### Налаштування структури проекту

Створіть каталог фронтенду з такою організованою структурою:

```text
frontend/
├── index.html      # Main HTML structure
├── app.js          # JavaScript functionality
└── styles.css      # Visual styling
```

**Розуміння архітектури:**
- **Розділяє** завдання між структурою (HTML), поведінкою (JavaScript) і оформленням (CSS)
- **Підтримує** просту структуру файлів, яку легко навігувати та модифікувати
- **Дотримується** найкращих практик веброзробки для організації та підтримки

### Створення HTML-фундації: семантична структура для доступності

Почнемо зі структури HTML. Сучасна веброзробка наголошує на "семантичному HTML" – використанні HTML-елементів, які чітко описують їхнє призначення, а не лише зовнішній вигляд. Це робить ваш додаток доступним для екранних читачів, пошукових систем та інших інструментів.

**Чому семантичний HTML важливий**: Уявіть, що ви описуєте ваш чат-додаток комусь по телефону. Ви б сказали: "є заголовок із назвою, основна область, де з'являються розмови, і форма внизу для введення повідомлень". Семантичний HTML використовує елементи, які відповідають цьому природному опису.

Створіть `index.html` з цією продуманою структурою розмітки:

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

**Розуміння кожного HTML-елемента та його призначення:**

#### Структура документа
- **`<!DOCTYPE html>`**: Повідомляє браузеру, що це сучасний HTML5
- **`<html lang="en">`**: Вказує мову сторінки для екранних читачів і інструментів перекладу
- **`<meta charset="UTF-8">`**: Забезпечує правильне кодування символів для міжнародного тексту
- **`<meta name="viewport"...>`**: Робить сторінку адаптивною для мобільних пристроїв, контролюючи масштабування

#### Семантичні елементи
- **`<header>`**: Чітко визначає верхню секцію з назвою та описом
- **`<main>`**: Позначає основну область контенту (де відбуваються розмови)
- **`<form>`**: Семантично правильний для введення користувачем, забезпечує правильну навігацію клавіатурою

#### Функції доступності
- **`role="log"`**: Повідомляє екранним читачам, що ця область містить хронологічний журнал повідомлень
- **`aria-live="polite"`**: Оголошує нові повідомлення екранним читачам без переривання
- **`aria-label`**: Надає описові мітки для елементів форми
- **`required`**: Браузер перевіряє, чи користувач ввів повідомлення перед відправкою

#### Інтеграція CSS і JavaScript
- **`class` атрибути**: Забезпечують точки прив'язки для стилізації CSS (наприклад, `chat-container`, `input-group`)
- **`id` атрибути**: Дозволяють JavaScript знаходити та маніпулювати конкретними елементами
- **Розташування скриптів**: Файл JavaScript завантажується в кінці, щоб HTML завантажувався спочатку

**Чому ця структура працює:**
- **Логічний потік**: Заголовок → Основний контент → Форма введення відповідає природному порядку читання
- **Доступність клавіатури**: Користувачі можуть переходити між усіма інтерактивними елементами
- **Зручність для екранних читачів**: Чіткі орієнтири та описи для користувачів із вадами зору
- **Адаптивність**: Мета-тег viewport забезпечує адаптивний дизайн
- **Прогресивне покращення**: Працює навіть якщо CSS або JavaScript не завантажуються

### Додавання інтерактивного JavaScript: логіка сучасного веб-додатка

Тепер створимо JavaScript, який оживить наш інтерфейс чату. Ми використаємо сучасні шаблони JavaScript, які зустрічаються в професійній веброзробці, включаючи класи ES6, async/await і програмування на основі подій.

#### Розуміння сучасної архітектури JavaScript

Замість написання процедурного коду (серії функцій, які виконуються по порядку), ми створимо **архітектуру на основі класів**. Уявіть клас як креслення для створення об'єктів – як креслення архітектора може бути використане для будівництва кількох будинків.

**Чому використовувати класи для веб-додатків?**
- **Організація**: Уся пов'язана функціональність згрупована разом
- **Повторне використання**: Ви можете створити кілька екземплярів чату на одній сторінці
- **Зручність підтримки**: Легше налагоджувати та модифікувати конкретні функції
- **Професійний стандарт**: Цей шаблон використовується у фреймворках, таких як React, Vue та Angular

Створіть `app.js` з цим сучасним, добре структурованим JavaScript:

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

#### Розуміння кожної концепції JavaScript

**Структура класу ES6**:
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

**Шаблон Async/Await**:
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

**Програмування на основі подій**:
Замість постійної перевірки, чи щось сталося, ми "слухаємо" події:
```javascript
// When form is submitted, run handleSubmit
this.form.addEventListener("submit", (e) => this.handleSubmit(e));

// When Enter key is pressed, also run handleSubmit
this.input.addEventListener("keypress", (e) => { /* ... */ });
```

**Маніпуляція DOM**:
```javascript
// Create new elements
const messageElement = document.createElement("div");

// Modify their properties
messageElement.className = "message user";
messageElement.innerHTML = "Hello world!";

// Add to the page
this.messages.appendChild(messageElement);
```

#### Безпека та найкращі практики

**Запобігання XSS**:
```javascript
escapeHtml(text) {
    const div = document.createElement('div');
    div.textContent = text;  // This automatically escapes HTML
    return div.innerHTML;
}
```

**Чому це важливо**: Якщо користувач введе `<script>alert('hack')</script>`, ця функція забезпечить відображення
Ця архітектура масштабована – ви легко можете додати функції, такі як редагування повідомлень, завантаження файлів або кілька потоків розмов, без переписування основної структури.

### Стилізація вашого інтерфейсу чату

Тепер створимо сучасний, візуально привабливий інтерфейс чату за допомогою CSS. Хороший дизайн робить ваш додаток професійним і покращує загальний досвід користувача. Ми використаємо сучасні функції CSS, такі як Flexbox, CSS Grid і власні властивості для адаптивного та доступного дизайну.

Створіть `styles.css` з такими стилями:

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

**Розуміння архітектури CSS:**
- **Використовує** власні властивості CSS (змінні) для узгодженого оформлення та легкого обслуговування
- **Реалізує** макет Flexbox для адаптивного дизайну та правильного вирівнювання
- **Включає** плавні анімації для появи повідомлень без відволікання
- **Забезпечує** візуальне розрізнення між повідомленнями користувача, відповідями AI та станами помилок
- **Підтримує** адаптивний дизайн, який працює як на настільних, так і на мобільних пристроях
- **Враховує** доступність із зменшеними налаштуваннями руху та правильними коефіцієнтами контрастності
- **Пропонує** підтримку темного режиму на основі системних налаштувань користувача

### Налаштування URL вашого бекенду

Останній крок – оновлення `BASE_URL` у вашому JavaScript, щоб він відповідав вашому серверу бекенду:

```javascript
// For local development
this.BASE_URL = "http://localhost:5000";

// For GitHub Codespaces (replace with your actual URL)
this.BASE_URL = "https://your-codespace-name-5000.app.github.dev";
```

**Визначення URL вашого бекенду:**
- **Локальна розробка**: Використовуйте `http://localhost:5000`, якщо фронтенд і бекенд працюють локально
- **Codespaces**: Знайдіть URL вашого бекенду на вкладці Ports після того, як зробите порт 5000 публічним
- **Продакшн**: Замініть на ваш фактичний домен при розгортанні на хостинговій платформі

> 💡 **Порада для тестування**: Ви можете протестувати ваш бекенд, перейшовши на кореневий URL у браузері. Ви повинні побачити вітальне повідомлення від вашого сервера FastAPI.

## Тестування та розгортання

Тепер, коли ви створили компоненти фронтенду та бекенду, давайте перевіримо, чи все працює разом, і розглянемо варіанти розгортання, щоб поділитися вашим чат-асистентом з іншими.

### Робочий процес локального тестування

Виконайте ці кроки, щоб протестувати ваш додаток:

```mermaid
graph TD
    A[Start Backend Server] --> B[Configure Environment Variables]
    B --> C[Test API Endpoints]
    C --> D[Open Frontend in Browser]
    D --> E[Test Chat Functionality]
    E --> F[Debug Any Issues]
```

**Покроковий процес тестування:**

1. **Запустіть сервер бекенду**:
   ```bash
   cd backend
   source venv/bin/activate  # or venv\Scripts\activate on Windows
   python api.py
   ```

2. **Перевірте роботу API**:
   - Відкрийте `http://localhost:5000` у вашому браузері
   - Ви повинні побачити вітальне повідомлення від вашого сервера FastAPI

3. **Відкрийте ваш фронтенд**:
   - Перейдіть до каталогу фронтенду
   - Відкрийте `index.html` у вашому веб-браузері
   - Або використовуйте розширення Live Server у VS Code для кращого досвіду розробки

4. **Перевірте функціональність чату**:
   - Введіть повідомлення у поле вводу
   - Натисніть "Відправити" або Enter
   - Переконайтеся, що AI відповідає належним чином
   - Перевірте консоль браузера на наявність помилок JavaScript

### Вирішення поширених проблем

| Проблема | Симптоми | Рішення |
|---------|----------|----------|
| **Помилка CORS** | Фронтенд не може підключитися до бекенду | Переконайтеся, що FastAPI CORSMiddleware налаштований правильно |
| **Помилка API Key** | Відповіді 401 Unauthorized | Перевірте змінну середовища `GITHUB_TOKEN` |
| **Відмова у підключенні** | Помилки мережі у фронтенді | Перевірте URL бекенду та чи працює сервер Flask |
| **Відсутність відповіді AI** | Порожні або помилкові відповіді | Перевірте логи бекенду на наявність проблем з квотою API або автентифікацією |

**Поширені кроки налагодження:**
- **Перевірте** консоль інструментів розробника браузера на помилки JavaScript
- **Переконайтеся**, що вкладка Network показує успішні запити та відповіді API
- **Перегляньте** термінал бекенду на помилки Python або проблеми API
- **Переконайтеся**, що змінні середовища правильно завантажені та доступні

## Виклик GitHub Copilot Agent 🚀

Використовуйте режим Agent, щоб виконати наступний виклик:

**Опис:** Покращіть чат-асистента, додавши історію розмов і збереження повідомлень. Цей виклик допоможе вам зрозуміти, як керувати станом у чат-додатках і реалізувати збереження даних для кращого досвіду користувача.

**Завдання:** Модифікуйте чат-додаток, щоб включити історію розмов, яка зберігається між сесіями. Додайте функціонал для збереження повідомлень чату в локальному сховищі, відображення історії розмов при завантаженні сторінки та кнопку "Очистити історію". Також реалізуйте індикатори набору тексту та часові мітки повідомлень, щоб зробити досвід чату більш реалістичним.

Дізнайтеся більше про [режим Agent](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) тут.

## Завдання: Створіть свого персонального AI-асистента

Тепер ви створите власну реалізацію AI-асистента. Замість простого копіювання коду з уроку, це можливість застосувати концепції, створюючи щось, що відображає ваші інтереси та випадки використання.

### Вимоги до проекту

Давайте налаштуємо ваш проект з чистою, організованою структурою:

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

### Основні завдання реалізації

**Розробка бекенду:**
- **Візьміть** наш код FastAPI і адаптуйте його під себе
- **Створіть** унікальну особистість AI – можливо, корисного кулінарного асистента, творчого партнера для написання текстів або навчального помічника?
- **Додайте** надійне оброблення помилок, щоб ваш додаток не ламався, коли щось піде не так
- **Напишіть** чітку документацію для тих, хто хоче зрозуміти, як працює ваш API

**Розробка фронтенду:**
- **Створіть** інтерфейс чату, який буде інтуїтивно зрозумілим і привітним
- **Напишіть** чистий, сучасний JavaScript, яким ви будете пишатися
- **Розробіть** унікальний стиль, який відображає особистість вашого AI – веселий і яскравий? Чистий і мінімалістичний? Вирішувати вам!
- **Переконайтеся**, що він чудово працює як на телефонах, так і на комп'ютерах

**Вимоги до персоналізації:**
- **Виберіть** унікальне ім'я та особистість для вашого AI-асистента – можливо, щось, що відображає ваші інтереси або проблеми, які ви хочете вирішити
- **Налаштуйте** візуальний дизайн, щоб він відповідав стилю вашого асистента
- **Напишіть** переконливе вітальне повідомлення, яке змусить людей почати спілкування
- **Протестуйте** вашого асистента з різними типами запитань, щоб побачити, як він відповідає

### Ідеї для покращення (опціонально)

Хочете вивести ваш проект на новий рівень? Ось кілька цікавих ідей для дослідження:

| Функція | Опис | Навички, які ви будете практикувати |
|---------|-------------|------------------------|
| **Історія повідомлень** | Запам'ятовувати розмови навіть після оновлення сторінки | Робота з localStorage, обробка JSON |
| **Індикатори набору тексту** | Показувати "AI набирає текст..." під час очікування відповіді | Анімації CSS, асинхронне програмування |
| **Часові мітки повідомлень** | Показувати, коли було надіслано кожне повідомлення | Форматування дати/часу, UX-дизайн |
| **Експорт чату** | Дозволити користувачам завантажувати їхню розмову | Обробка файлів, експорт даних |
| **Перемикання теми** | Перемикання між світлим і темним режимом | Змінні CSS, налаштування користувача |
| **Голосовий ввід** | Додати функціонал перетворення мови в текст | Веб-API, доступність |

### Тестування та документація

**Забезпечення якості:**
- **Протестуйте** ваш додаток з різними типами вводу та крайовими випадками
- **Переконайтеся**, що адаптивний дизайн працює на різних розмірах екрана
- **Перевірте** доступність за допомогою навігації клавіатурою та екранних читачів
- **Перевірте** HTML і CSS на відповідність стандартам

**Вимоги до документації:**
- **Напишіть** README.md, що пояснює ваш проект і як його запустити
- **Додайте** скріншоти вашого інтерфейсу чату в дії
- **Документуйте** будь-які унікальні функції або налаштування, які ви додали
- **Надайте** чіткі інструкції з налаштування для інших розробників

### Керівництво з подання

**Результати проекту:**
1. Повна папка проекту з усім вихідним кодом
2. README.md з описом проекту та інструкціями з налаштування
3. Скріншоти, що демонструють ваш чат-асистент у дії
4. Короткий опис того, чого ви навчилися і з якими викликами зіткнулися

**Критерії оцінювання:**
- **Функціональність**: Чи працює чат-асистент так, як очікується?
- **Якість коду**: Чи добре організований, прокоментований і підтримуваний код?
- **Дизайн**: Чи є інтерфейс візуально привабливим і зручним для користувача?
- **Креативність**: Наскільки унікальною та персоналізованою є ваша реалізація?
- **Документація**: Чи є інструкції з налаштування чіткими та повними?

> 💡 **Порада для успіху**: Почніть з основних вимог, а потім додавайте покращення, коли все буде працювати. Зосередьтеся на створенні якісного основного досвіду перед додаванням складних функцій.

## Рішення

[Рішення](./solution/README.md)

## Додаткові виклики

Готові вивести ваш AI-асистент на новий рівень? Спробуйте ці складні виклики, які поглиблять ваше розуміння інтеграції AI та веб-розробки.

### Налаштування особистості

Справжня магія відбувається, коли ви надаєте вашому AI-асистенту унікальну особистість. Експериментуйте з різними системними підказками, щоб створити спеціалізованих асистентів:

**Приклад професійного асистента:**
```python
call_llm(message, "You are a professional business consultant with 20 years of experience. Provide structured, actionable advice with specific steps and considerations.")
```

**Приклад помічника для творчого письма:**
```python
call_llm(message, "You are an enthusiastic creative writing coach. Help users develop their storytelling skills with imaginative prompts and constructive feedback.")
```

**Приклад технічного наставника:**
```python
call_llm(message, "You are a patient senior developer who explains complex programming concepts using simple analogies and practical examples.")
```

### Покращення фронтенду

Перетворіть ваш інтерфейс чату за допомогою цих візуальних і функціональних покращень:

**Розширені функції CSS:**
- **Реалізуйте** плавні анімації та переходи для повідомлень
- **Додайте** унікальні дизайни бульбашок чату за допомогою форм CSS і градієнтів
- **Створіть** анімацію індикатора набору тексту для моментів, коли AI "думає"
- **Розробіть** реакції на повідомлення або систему оцінки повідомлень

**Покращення JavaScript:**
- **Додайте** гарячі клавіші (Ctrl+Enter для відправки, Escape для очищення вводу)
- **Реалізуйте** функціонал пошуку та фільтрації повідомлень
- **Створіть** функцію експорту розмов (завантаження у вигляді тексту або JSON)
- **Додайте** автоматичне збереження в localStorage, щоб уникнути втрати повідомлень

### Розширена інтеграція AI

**Кілька особистостей AI:**
- **Створіть** випадаючий список для перемикання між різними особистостями AI
- **Збережіть** у localStorage улюблену особистість користувача
- **Реалізуйте** перемикання контексту, яке зберігає потік розмови

**Розумні функції відповіді:**
- **Додайте** обізнаність про контекст розмови (AI запам'ятовує попередні повідомлення)
- **Реалізуйте** розумні пропозиції на основі теми розмови
- **Створіть** кнопки швидких відповідей для поширених запитань

> 🎯 **Ціль навчання**: Ці додаткові виклики допоможуть вам зрозуміти розширені шаблони веб-розробки та техніки інтеграції AI, які використовуються у виробничих додатках.

## Підсумок і наступні кроки

Вітаємо! Ви успішно створили повного AI-асистента чату з нуля. Цей проект дав вам практичний досвід роботи з сучасними технологіями веб-розробки та інтеграції AI – навички, які стають все більш цінними в сучасному технологічному світі.

### Що ви досягли

Протягом цього уроку ви освоїли кілька ключових технологій і концепцій:

**Розробка бекенду:**
- **Інтеграція** з GitHub Models API для функціональності AI
- **Створення** RESTful API за допомогою Flask з належним обробленням помилок
- **Реалізація** безпечної автентифікації за допомогою змінних середовища
- **Налаштування** CORS для запитів між фронтендом і бекендом

**Розробка фронтенду:**
- **Створення** адаптивного інтерфейсу чату за допомогою семантичного HTML
- **Реалізація** сучасного JavaScript з async/await та архітектурою на основі класів
- **Розробка** привабливого інтерфейсу користувача за допомогою CSS Grid, Flexbox та анімацій
- **Додавання** функцій доступності та принципів адаптивного дизайну

**Інтеграція фронтенду та бекенду:**
- **Підключення** фронтенду та бекенду через HTTP-запити API
- **Обробка** взаємодії користувача в реальному часі та асинхронного потоку даних
- **Реалізація** оброблення помилок та зворотного зв’язку для користувача у всьому додатку
- **Тестування** повного робочого процесу додатку від вводу користувача до відповіді AI

### Основні результати навчання

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

Цей проект ознайомив вас з основами створення додатків на основі AI, що представляє майбутнє веб-розробки. Тепер ви розумієте
- **Переадресація портів** для тестування ваших додатків

**Що пропонує Codespaces:**
- **Усуває** проблеми налаштування та конфігурації локального середовища
- **Забезпечує** стабільне середовище розробки на різних пристроях
- **Включає** попередньо налаштовані інструменти та розширення для веб-розробки
- **Пропонує** безперебійну інтеграцію з GitHub для контролю версій та співпраці

> 🚀 **Порада професіонала**: Codespaces ідеально підходить для навчання та створення прототипів AI-додатків, оскільки автоматично вирішує всі складнощі налаштування середовища, дозволяючи вам зосередитися на створенні та навчанні, а не на вирішенні проблем конфігурації.

---

**Відмова від відповідальності**:  
Цей документ був перекладений за допомогою сервісу автоматичного перекладу [Co-op Translator](https://github.com/Azure/co-op-translator). Хоча ми прагнемо до точності, будь ласка, майте на увазі, що автоматичні переклади можуть містити помилки або неточності. Оригінальний документ на його рідній мові слід вважати авторитетним джерелом. Для критичної інформації рекомендується професійний людський переклад. Ми не несемо відповідальності за будь-які непорозуміння або неправильні тлумачення, що виникають внаслідок використання цього перекладу.