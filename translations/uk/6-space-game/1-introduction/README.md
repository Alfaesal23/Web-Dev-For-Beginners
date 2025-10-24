<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-24T15:58:39+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "uk"
}
-->
# Створення космічної гри Частина 1: Вступ

![Анімація космічної гри, що показує ігровий процес](../../../../6-space-game/images/pewpew.gif)

Як і центр управління NASA координує кілька систем під час запуску космічного корабля, ми створимо космічну гру, яка демонструє, як різні частини програми можуть працювати разом бездоганно. Під час створення гри, яку ви зможете грати, ви навчитеся основним концепціям програмування, які застосовуються до будь-якого програмного проєкту.

Ми дослідимо два фундаментальні підходи до організації коду: наслідування та композицію. Це не просто академічні концепції – це ті самі шаблони, які використовуються у всьому, від відеоігор до банківських систем. Ми також реалізуємо систему комунікації, яка називається pub/sub, що працює як мережі зв'язку, які використовуються в космічних кораблях, дозволяючи різним компонентам обмінюватися інформацією без створення залежностей.

До кінця цієї серії ви зрозумієте, як створювати програми, які можуть масштабуватися та розвиватися – незалежно від того, чи розробляєте ви ігри, веб-додатки чи будь-які інші програмні системи.

## Тест перед лекцією

[Тест перед лекцією](https://ff-quizzes.netlify.app/web/quiz/29)

## Наслідування та композиція в розробці ігор

Коли проєкти стають складнішими, організація коду стає критично важливою. Те, що починається як простий скрипт, може стати важким для підтримки без належної структури – так само, як місії Apollo вимагали ретельної координації між тисячами компонентів.

Ми дослідимо два фундаментальні підходи до організації коду: наслідування та композицію. Кожен має свої переваги, і розуміння обох допоможе вам вибрати правильний підхід для різних ситуацій. Ми продемонструємо ці концепції через нашу космічну гру, де герої, вороги, бонуси та інші об'єкти повинні ефективно взаємодіяти.

✅ Одна з найвідоміших книг про програмування стосується [шаблонів проєктування](https://en.wikipedia.org/wiki/Design_Patterns).

У будь-якій грі є `ігрові об'єкти` – інтерактивні елементи, які наповнюють ваш ігровий світ. Герої, вороги, бонуси та візуальні ефекти – це все ігрові об'єкти. Кожен існує в певних координатах екрану, використовуючи значення `x` та `y`, подібно до нанесення точок на координатну площину.

Незважаючи на їхні візуальні відмінності, ці об'єкти часто мають спільні фундаментальні поведінки:

- **Вони існують десь** – Кожен об'єкт має координати x та y, щоб гра знала, де його намалювати
- **Багато з них можуть рухатися** – Герої бігають, вороги переслідують, кулі летять через екран
- **Вони мають тривалість життя** – Деякі залишаються назавжди, інші (наприклад, вибухи) з'являються на короткий час і зникають
- **Вони реагують на щось** – Коли об'єкти стикаються, бонуси збираються, шкали здоров'я оновлюються

✅ Подумайте про гру, як-от Pac-Man. Чи можете ви визначити чотири типи об'єктів, зазначених вище, у цій грі?

### Вираження поведінки через код

Тепер, коли ви розумієте спільні поведінки, які мають ігрові об'єкти, давайте дослідимо, як реалізувати ці поведінки в JavaScript. Ви можете виразити поведінку об'єктів через методи, прикріплені до класів або окремих об'єктів, і є кілька підходів на вибір.

**Підхід на основі класів**

Класи та наслідування забезпечують структурований підхід до організації ігрових об'єктів. Як і таксономічна система класифікації, розроблена Карлом Ліннеєм, ви починаєте з базового класу, що містить загальні властивості, а потім створюєте спеціалізовані класи, які успадковують ці основи, додаючи конкретні можливості.

✅ Наслідування – це важлива концепція для розуміння. Дізнайтеся більше у [статті MDN про наслідування](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

Ось як ви можете реалізувати ігрові об'єкти, використовуючи класи та наслідування:

```javascript
// Step 1: Create the base GameObject class
class GameObject {
  constructor(x, y, type) {
    this.x = x;
    this.y = y;
    this.type = type;
  }
}
```

**Розберемо це крок за кроком:**
- Ми створюємо базовий шаблон, який може використовувати кожен ігровий об'єкт
- Конструктор зберігає, де знаходиться об'єкт (`x`, `y`) і що це за об'єкт
- Це стає основою, на якій будуть будуватися всі ваші ігрові об'єкти

```javascript
// Step 2: Add movement capability through inheritance
class Movable extends GameObject {
  constructor(x, y, type) {
    super(x, y, type); // Call parent constructor
  }

  // Add the ability to move to a new position
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
}
```

**У наведеному вище ми:**
- **Розширили** клас GameObject, щоб додати функціональність руху
- **Викликали** конструктор батьківського класу за допомогою `super()`, щоб ініціалізувати успадковані властивості
- **Додали** метод `moveTo()`, який оновлює позицію об'єкта

```javascript
// Step 3: Create specific game object types
class Hero extends Movable {
  constructor(x, y) {
    super(x, y, 'Hero'); // Set type automatically
  }
}

class Tree extends GameObject {
  constructor(x, y) {
    super(x, y, 'Tree'); // Trees don't need movement
  }
}

// Step 4: Use your game objects
const hero = new Hero(0, 0);
hero.moveTo(5, 5); // Hero can move!

const tree = new Tree(10, 15);
// tree.moveTo() would cause an error - trees can't move
```

**Розуміння цих концепцій:**
- **Створює** спеціалізовані типи об'єктів, які успадковують відповідні поведінки
- **Демонструє**, як наслідування дозволяє вибіркове включення функцій
- **Показує**, що герої можуть рухатися, а дерева залишаються нерухомими
- **Ілюструє**, як ієрархія класів запобігає недоречним діям

✅ Приділіть кілька хвилин, щоб переосмислити героя Pac-Man (наприклад, Inky, Pinky або Blinky) і як його можна було б написати в JavaScript.

**Підхід композиції**

Композиція слідує філософії модульного дизайну, подібно до того, як інженери проектують космічні кораблі з взаємозамінними компонентами. Замість наслідування від батьківського класу, ви комбінуєте конкретні поведінки, щоб створити об'єкти з точною функціональністю, яка їм потрібна. Цей підхід пропонує гнучкість без жорстких ієрархічних обмежень.

```javascript
// Step 1: Create base behavior objects
const gameObject = {
  x: 0,
  y: 0,
  type: ''
};

const movable = {
  moveTo(x, y) {
    this.x = x;
    this.y = y;
  }
};
```

**Ось що робить цей код:**
- **Визначає** базовий `gameObject` з властивостями позиції та типу
- **Створює** окремий об'єкт поведінки `movable` з функціональністю руху
- **Розділяє** завдання, зберігаючи дані позиції та логіку руху незалежними

```javascript
// Step 2: Compose objects by combining behaviors
const movableObject = { ...gameObject, ...movable };

// Step 3: Create factory functions for different object types
function createHero(x, y) {
  return {
    ...movableObject,
    x,
    y,
    type: 'Hero'
  };
}

function createStatic(x, y, type) {
  return {
    ...gameObject,
    x,
    y,
    type
  };
}
```

**У наведеному вище ми:**
- **Об'єднали** базові властивості об'єкта з поведінкою руху, використовуючи синтаксис spread
- **Створили** фабричні функції, які повертають налаштовані об'єкти
- **Надали** гнучке створення об'єктів без жорстких ієрархій класів
- **Дозволили** об'єктам мати саме ті поведінки, які їм потрібні

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**Ключові моменти для запам'ятовування:**
- **Комбінує** об'єкти, змішуючи поведінки, а не успадковуючи їх
- **Забезпечує** більше гнучкості, ніж жорсткі ієрархії наслідування
- **Дозволяє** об'єктам мати саме ті функції, які їм потрібні
- **Використовує** сучасний синтаксис spread у JavaScript для чистого об'єднання об'єктів 
```

**Which Pattern Should You Choose?**

> 💡 **Pro Tip**: Both patterns have their place in modern JavaScript development. Classes work well for clearly defined hierarchies, while composition shines when you need maximum flexibility.
> 
**Here's when to use each approach:**
- **Choose** inheritance when you have clear "is-a" relationships (a Hero *is-a* Movable object)
- **Select** composition when you need "has-a" relationships (a Hero *has* movement abilities)
- **Consider** your team's preferences and project requirements
- **Remember** that you can mix both approaches in the same application

## Communication Patterns: The Pub/Sub System

As applications grow complex, managing communication between components becomes challenging. The publish-subscribe pattern (pub/sub) solves this problem using principles similar to radio broadcasting – one transmitter can reach multiple receivers without knowing who's listening.

Consider what happens when a hero takes damage: the health bar updates, sound effects play, visual feedback appears. Rather than coupling the hero object directly to these systems, pub/sub allows the hero to broadcast a "damage taken" message. Any system that needs to respond can subscribe to this message type and react accordingly.

✅ **Pub/Sub** stands for 'publish-subscribe'

### Understanding the Pub/Sub Architecture

The pub/sub pattern keeps different parts of your application loosely coupled, meaning they can work together without being directly dependent on each other. This separation makes your code more maintainable, testable, and flexible to changes.

**The key players in pub/sub:**
- **Messages** – Simple text labels like `'PLAYER_SCORED'` that describe what happened (plus any extra info)
- **Publishers** – The objects that shout out "Something happened!" to anyone who's listening
- **Subscribers** – The objects that say "I care about that event" and react when it happens
- **Event System** – The middleman that makes sure messages get to the right listeners

### Building an Event System

Let's create a simple but powerful event system that demonstrates these concepts:

```javascript
// Step 1: Create the EventEmitter class
class EventEmitter {
  constructor() {
    this.listeners = {}; // Store all event listeners
  }
  
  // Register a listener for a specific message type
  on(message, listener) {
    if (!this.listeners[message]) {
      this.listeners[message] = [];
    }
    this.listeners[message].push(listener);
  }
  
  // Send a message to all registered listeners
  emit(message, payload = null) {
    if (this.listeners[message]) {
      this.listeners[message].forEach(listener => {
        listener(message, payload);
      });
    }
  }
}
```

**Розбираємо, що тут відбувається:**
- **Створює** центральну систему управління подіями за допомогою простого класу
- **Зберігає** слухачів у об'єкті, організованому за типом повідомлення
- **Реєструє** нових слухачів за допомогою методу `on()`
- **Передає** повідомлення всім зацікавленим слухачам за допомогою `emit()`
- **Підтримує** необов'язкові дані для передачі відповідної інформації

### Об'єднуємо все разом: Практичний приклад

Добре, давайте побачимо це в дії! Ми створимо просту систему руху, яка показує, наскільки чистим і гнучким може бути pub/sub:

```javascript
// Step 1: Define your message types
const Messages = {
  HERO_MOVE_LEFT: 'HERO_MOVE_LEFT',
  HERO_MOVE_RIGHT: 'HERO_MOVE_RIGHT',
  ENEMY_SPOTTED: 'ENEMY_SPOTTED'
};

// Step 2: Create your event system and game objects
const eventEmitter = new EventEmitter();
const hero = createHero(0, 0);
```

**Ось що робить цей код:**
- **Визначає** об'єкт констант, щоб уникнути помилок у назвах повідомлень
- **Створює** екземпляр емітера подій для обробки всієї комунікації
- **Ініціалізує** об'єкт героя на стартовій позиції

```javascript
// Step 3: Set up event listeners (subscribers)
eventEmitter.on(Messages.HERO_MOVE_LEFT, () => {
  hero.moveTo(hero.x - 5, hero.y);
  console.log(`Hero moved to position: ${hero.x}, ${hero.y}`);
});

eventEmitter.on(Messages.HERO_MOVE_RIGHT, () => {
  hero.moveTo(hero.x + 5, hero.y);
  console.log(`Hero moved to position: ${hero.x}, ${hero.y}`);
});
```

**У наведеному вище ми:**
- **Зареєстрували** слухачів подій, які реагують на повідомлення про рух
- **Оновили** позицію героя залежно від напрямку руху
- **Додали** логування в консоль для відстеження змін позиції героя
- **Розділили** логіку руху від обробки введення

```javascript
// Step 4: Connect keyboard input to events (publishers)
window.addEventListener('keydown', (event) => {
  switch(event.key) {
    case 'ArrowLeft':
      eventEmitter.emit(Messages.HERO_MOVE_LEFT);
      break;
    case 'ArrowRight':
      eventEmitter.emit(Messages.HERO_MOVE_RIGHT);
      break;
  }
});
```

**Розуміння цих концепцій:**
- **З'єднує** введення з клавіатури з ігровими подіями без жорсткого зв'язку
- **Дозволяє** системі введення спілкуватися з ігровими об'єктами опосередковано
- **Дозволяє** кільком системам реагувати на ті самі події клавіатури
- **Робить** зміну прив'язок клавіш або додавання нових методів введення легким

> 💡 **Корисна порада**: Краса цього шаблону – у його гнучкості! Ви можете легко додати звукові ефекти, тряску екрану або частинкові ефекти, просто додавши більше слухачів подій – не потрібно змінювати існуючий код клавіатури або руху.
> 
**Ось чому вам сподобається цей підхід:**
- Додавати нові функції стає дуже легко – просто слухайте потрібні події
- Кілька речей можуть реагувати на ту саму подію, не заважаючи одна одній
- Тестування стає набагато простішим, оскільки кожна частина працює незалежно
- Коли щось ламається, ви точно знаєте, де шукати

### Чому Pub/Sub ефективно масштабується

Шаблон pub/sub зберігає простоту, коли додатки стають складнішими. Незалежно від того, чи керуєте ви десятками ворогів, динамічними оновленнями інтерфейсу користувача або звуковими системами, шаблон справляється зі збільшенням масштабу без змін архітектури. Нові функції інтегруються в існуючу систему подій без впливу на встановлену функціональність.

> ⚠️ **Поширена помилка**: Не створюйте занадто багато специфічних типів повідомлень на ранніх етапах. Починайте з широких категорій і уточнюйте їх, коли потреби вашої гри стануть зрозумілішими.
> 
**Найкращі практики:**
- **Групує** пов'язані повідомлення в логічні категорії
- **Використовує** описові назви, які чітко вказують, що сталося
- **Зберігає** дані повідомлень простими та сфокусованими
- **Документує** типи повідомлень для співпраці в команді

---

## Виклик GitHub Copilot Agent 🚀

Використовуйте режим Agent, щоб виконати наступний виклик:

**Опис:** Створіть просту систему ігрових об'єктів, використовуючи як наслідування, так і шаблон pub/sub. Ви реалізуєте базову гру, де різні об'єкти можуть спілкуватися через події, не знаючи безпосередньо один про одного.

**Завдання:** Створіть систему гри на JavaScript з наступними вимогами: 1) Створіть базовий клас GameObject з координатами x, y та властивістю типу. 2) Створіть клас Hero, який розширює GameObject і може рухатися. 3) Створіть клас Enemy, який розширює GameObject і може переслідувати героя. 4) Реалізуйте клас EventEmitter для шаблону pub/sub. 5) Налаштуйте слухачів подій так, щоб коли герой рухається, найближчі вороги отримували подію 'HERO_MOVED' і оновлювали свою позицію, щоб рухатися до героя. Додайте console.log для демонстрації комунікації між об'єктами.

Дізнайтеся більше про [режим Agent](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) тут.

## 🚀 Виклик

Розгляньте, як шаблон pub-sub може покращити архітектуру гри. Визначте, які компоненти повинні передавати події і як система повинна реагувати. Розробіть концепцію гри та сплануйте комунікаційні шаблони між її компонентами.

## Тест після лекції

[Тест після лекції](https://ff-quizzes.netlify.app/web/quiz/30)

## Огляд і самостійне навчання

Дізнайтеся більше про Pub/Sub, [прочитавши про це](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## Завдання

[Створіть макет гри](assignment.md)

---

**Відмова від відповідальності**:  
Цей документ був перекладений за допомогою сервісу автоматичного перекладу [Co-op Translator](https://github.com/Azure/co-op-translator). Хоча ми прагнемо до точності, будь ласка, майте на увазі, що автоматичні переклади можуть містити помилки або неточності. Оригінальний документ на його рідній мові слід вважати авторитетним джерелом. Для критичної інформації рекомендується професійний людський переклад. Ми не несемо відповідальності за будь-які непорозуміння або неправильні тлумачення, що виникають внаслідок використання цього перекладу.