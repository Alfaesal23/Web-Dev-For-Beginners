<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "862f7f2ef320f6f8950fae379e6ece45",
  "translation_date": "2025-10-22T22:30:05+00:00",
  "source_file": "6-space-game/1-introduction/README.md",
  "language_code": "ru"
}
-->
# Создаем космическую игру. Часть 1: Введение

![Анимация космической игры, показывающая игровой процесс](../../../../6-space-game/images/pewpew.gif)

Точно так же, как центр управления полетами NASA координирует работу множества систем во время запуска космического корабля, мы создадим космическую игру, которая продемонстрирует, как разные части программы могут работать вместе без сбоев. Создавая что-то, во что вы действительно сможете играть, вы изучите основные концепции программирования, которые применимы к любому программному проекту.

Мы изучим два фундаментальных подхода к организации кода: наследование и композицию. Это не просто академические концепции – это те же самые шаблоны, которые используются в создании всего, от видеоигр до банковских систем. Мы также реализуем систему коммуникации, называемую pub/sub, которая работает как сети связи, используемые в космических аппаратах, позволяя различным компонентам обмениваться информацией без создания зависимостей.

К концу этой серии вы поймете, как создавать приложения, которые могут масштабироваться и развиваться – будь то разработка игр, веб-приложений или любых других программных систем.

## Тест перед лекцией

[Тест перед лекцией](https://ff-quizzes.netlify.app/web/quiz/29)

## Наследование и композиция в разработке игр

По мере роста сложности проектов организация кода становится критически важной. То, что начинается как простой скрипт, может стать трудным для поддержки без надлежащей структуры – так же, как миссии "Аполлон" требовали тщательной координации между тысячами компонентов.

Мы изучим два фундаментальных подхода к организации кода: наследование и композицию. У каждого из них есть свои преимущества, и понимание обоих подходов поможет вам выбрать правильный подход для разных ситуаций. Мы продемонстрируем эти концепции через нашу космическую игру, где герои, враги, усиления и другие объекты должны эффективно взаимодействовать.

✅ Одна из самых известных книг по программированию посвящена [шаблонам проектирования](https://en.wikipedia.org/wiki/Design_Patterns).

В любой игре есть `игровые объекты` – интерактивные элементы, которые наполняют игровой мир. Герои, враги, усиления и визуальные эффекты – это все игровые объекты. Каждый из них существует в определенных координатах экрана, используя значения `x` и `y`, аналогично нанесению точек на координатную плоскость.

Несмотря на их визуальные различия, эти объекты часто имеют общие базовые поведения:

- **Они существуют где-то** – У каждого объекта есть координаты x и y, чтобы игра знала, где его отобразить.
- **Многие могут двигаться** – Герои бегают, враги преследуют, пули летят по экрану.
- **У них есть срок жизни** – Некоторые остаются навсегда, другие (например, взрывы) появляются на короткое время и исчезают.
- **Они реагируют на события** – Когда объекты сталкиваются, усиления собираются, индикаторы здоровья обновляются.

✅ Подумайте о такой игре, как Pac-Man. Можете ли вы определить четыре типа объектов, перечисленных выше, в этой игре?

### Выражение поведения через код

Теперь, когда вы понимаете общие поведения, которые разделяют игровые объекты, давайте изучим, как реализовать эти поведения на JavaScript. Вы можете выразить поведение объектов через методы, прикрепленные либо к классам, либо к отдельным объектам, и для этого существует несколько подходов.

**Подход на основе классов**

Классы и наследование предоставляют структурированный подход к организации игровых объектов. Как и таксономическая система классификации, разработанная Карлом Линнеем, вы начинаете с базового класса, содержащего общие свойства, а затем создаете специализированные классы, которые наследуют эти основы, добавляя при этом специфические возможности.

✅ Наследование – это важная концепция для понимания. Узнайте больше в [статье MDN о наследовании](https://developer.mozilla.org/docs/Web/JavaScript/Inheritance_and_the_prototype_chain).

Вот как можно реализовать игровые объекты, используя классы и наследование:

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

**Разберем это шаг за шагом:**
- Мы создаем базовый шаблон, который может использовать каждый игровой объект.
- Конструктор сохраняет, где находится объект (`x`, `y`) и что это за объект.
- Это становится основой, на которой будут строиться все ваши игровые объекты.

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

**В приведенном выше примере мы:**
- **Расширили** класс GameObject, чтобы добавить функциональность движения.
- **Вызвали** родительский конструктор с помощью `super()`, чтобы инициализировать унаследованные свойства.
- **Добавили** метод `moveTo()`, который обновляет позицию объекта.

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

**Понимание этих концепций:**
- **Создает** специализированные типы объектов, которые наследуют соответствующие поведения.
- **Демонстрирует**, как наследование позволяет избирательно включать функции.
- **Показывает**, что герои могут двигаться, а деревья остаются неподвижными.
- **Иллюстрирует**, как иерархия классов предотвращает выполнение неподходящих действий.

✅ Потратьте несколько минут, чтобы представить героя из Pac-Man (например, Инки, Пинки или Блинки) и как его можно было бы написать на JavaScript.

**Подход с использованием композиции**

Композиция следует модульной философии проектирования, аналогично тому, как инженеры проектируют космические аппараты с взаимозаменяемыми компонентами. Вместо наследования от родительского класса вы комбинируете определенные поведения, чтобы создать объекты с точно необходимой функциональностью. Этот подход предлагает гибкость без жестких иерархических ограничений.

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

**Что делает этот код:**
- **Определяет** базовый объект `gameObject` со свойствами позиции и типа.
- **Создает** отдельный объект поведения `movable` с функциональностью движения.
- **Разделяет** обязанности, сохраняя данные о позиции и логику движения отдельно.

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

**В приведенном выше примере мы:**
- **Объединили** свойства базового объекта с поведением движения, используя синтаксис spread.
- **Создали** фабричные функции, которые возвращают настраиваемые объекты.
- **Обеспечили** гибкость создания объектов без жестких иерархий классов.
- **Позволили** объектам иметь только те поведения, которые им нужны.

```javascript
// Step 4: Create and use your composed objects
const hero = createHero(10, 10);
hero.moveTo(5, 5); // Works perfectly!

const tree = createStatic(0, 0, 'Tree');
// tree.moveTo() is undefined - no movement behavior was composed
```

**Ключевые моменты, которые нужно запомнить:**
- **Комбинирует** объекты, смешивая поведения, а не наследуя их.
- **Обеспечивает** больше гибкости, чем жесткие иерархии наследования.
- **Позволяет** объектам иметь только те функции, которые им нужны.
- **Использует** современный синтаксис spread в JavaScript для чистого объединения объектов.

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

**Разберем, что здесь происходит:**
- **Создает** центральную систему управления событиями с использованием простого класса.
- **Хранит** слушателей в объекте, организованном по типу сообщений.
- **Регистрирует** новых слушателей с помощью метода `on()`.
- **Рассылает** сообщения всем заинтересованным слушателям с помощью метода `emit()`.
- **Поддерживает** необязательные данные для передачи соответствующей информации.

### Собираем все вместе: практический пример

Хорошо, давайте посмотрим, как это работает на практике! Мы создадим простую систему движения, которая покажет, насколько чистым и гибким может быть pub/sub:

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

**Что делает этот код:**
- **Определяет** объект констант, чтобы избежать опечаток в названиях сообщений.
- **Создает** экземпляр эмиттера событий для обработки всей коммуникации.
- **Инициализирует** объект героя в начальной позиции.

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

**В приведенном выше примере мы:**
- **Зарегистрировали** слушателей событий, которые реагируют на сообщения о движении.
- **Обновили** позицию героя в зависимости от направления движения.
- **Добавили** вывод в консоль для отслеживания изменений позиции героя.
- **Разделили** логику движения и обработки ввода.

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

**Понимание этих концепций:**
- **Соединяет** ввод с клавиатуры с игровыми событиями без жесткой связи.
- **Позволяет** системе ввода взаимодействовать с игровыми объектами косвенно.
- **Дает возможность** нескольким системам реагировать на одни и те же события клавиатуры.
- **Упрощает** изменение привязки клавиш или добавление новых методов ввода.

> 💡 **Полезный совет**: Прелесть этого шаблона – в его гибкости! Вы можете легко добавить звуковые эффекты, тряску экрана или эффекты частиц, просто добавив больше слушателей событий – без необходимости изменять существующий код обработки клавиш или движения.
> 
**Почему вам понравится этот подход:**
- Добавлять новые функции становится очень просто – просто слушайте нужные события.
- Несколько элементов могут реагировать на одно и то же событие, не мешая друг другу.
- Тестирование становится намного проще, так как каждая часть работает независимо.
- Если что-то ломается, вы точно знаете, где искать проблему.

### Почему Pub/Sub эффективно масштабируется

Шаблон pub/sub сохраняет простоту по мере роста сложности приложений. Будь то управление десятками врагов, динамическими обновлениями интерфейса или звуковыми системами, этот шаблон справляется с увеличением масштаба без изменений в архитектуре. Новые функции легко интегрируются в существующую систему событий, не влияя на уже установленную функциональность.

> ⚠️ **Распространенная ошибка**: Не создавайте слишком много специфичных типов сообщений на ранних этапах. Начните с широких категорий и уточняйте их по мере того, как потребности вашей игры станут яснее.
> 
**Лучшие практики:**
- **Группируйте** связанные сообщения в логические категории.
- **Используйте** описательные названия, которые четко указывают, что произошло.
- **Делайте** данные сообщений простыми и целенаправленными.
- **Документируйте** типы сообщений для командной работы.

---

## Вызов для GitHub Copilot Agent 🚀

Используйте режим Agent, чтобы выполнить следующий вызов:

**Описание:** Создайте простую систему игровых объектов, используя как наследование, так и шаблон pub/sub. Вы реализуете базовую игру, где разные объекты могут общаться через события, не зная друг о друге напрямую.

**Задание:** Создайте систему игры на JavaScript с следующими требованиями: 1) Создайте базовый класс GameObject с координатами x, y и свойством type. 2) Создайте класс Hero, который наследует GameObject и может двигаться. 3) Создайте класс Enemy, который наследует GameObject и может преследовать героя. 4) Реализуйте класс EventEmitter для шаблона pub/sub. 5) Настройте слушателей событий так, чтобы при движении героя ближайшие враги получали событие 'HERO_MOVED' и обновляли свою позицию, чтобы двигаться к герою. Включите вывод в консоль, чтобы показать взаимодействие между объектами.

Узнайте больше о [режиме Agent](https://code.visualstudio.com/blogs/2025/02/24/introducing-copilot-agent-mode) здесь.

## 🚀 Задание

Подумайте, как шаблон pub/sub может улучшить архитектуру игры. Определите, какие компоненты должны генерировать события и как система должна на них реагировать. Разработайте концепцию игры и спланируйте схемы коммуникации между ее компонентами.

## Тест после лекции

[Тест после лекции](https://ff-quizzes.netlify.app/web/quiz/30)

## Обзор и самостоятельное изучение

Узнайте больше о Pub/Sub, [прочитав об этом](https://docs.microsoft.com/azure/architecture/patterns/publisher-subscriber/?WT.mc_id=academic-77807-sagibbon).

## Задание

[Создайте макет игры](assignment.md)

---

**Отказ от ответственности**:  
Этот документ был переведен с использованием сервиса автоматического перевода [Co-op Translator](https://github.com/Azure/co-op-translator). Несмотря на наши усилия обеспечить точность, автоматические переводы могут содержать ошибки или неточности. Оригинальный документ на его родном языке следует считать авторитетным источником. Для получения критически важной информации рекомендуется профессиональный перевод человеком. Мы не несем ответственности за любые недоразумения или неправильные интерпретации, возникающие в результате использования данного перевода.