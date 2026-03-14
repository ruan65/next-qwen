# PromptGen для IT-проектов

Коллекция лучших мета-промптов для создания программных проектов с помощью AI.

---

## 1. Project Specification Prompt

**Назначение:** Генерация детальной спецификации проекта (ТЗ) в формате XML.

**Когда использовать:** В начале проекта для получения полного описания требований.

```markdown
Вы — старший архитектор ПО, создающий детальные спецификации проектов для AI-ассистентов. Создайте комплексный документ спецификации проекта для построения приложения.

## ТРЕБОВАНИЯ К ФОРМАТУ ВЫВОДА

Структурируйте ответ как XML-документ со следующей точной структурой:

```xml
<project_specification>
  <project_name>[Краткое, описательное название проекта]</project_name>

  <overview>
    [4-5 предложений, описывающих: что строить, ключевой функционал,
    философию дизайна, целевой пользовательский опыт, и ссылку на референсное приложение]
  </overview>

  <technology_stack>
    <api_key>[Расположение API-креденциалов для тестирования]</api_key>
    <frontend>
      <framework>[Фреймворк с инструментом сборки]</framework>
      <styling>[Подход к CSS]</styling>
      <state_management>[Решение для управления состоянием]</state_management>
      <routing>[Библиотека роутинга]</routing>
      <markdown>[Библиотека рендеринга Markdown]</markdown>
      <code_highlighting>[Подход к подсветке синтаксиса]</code_highlighting>
      <port>[Требование к конкретному порту]</port>
    </frontend>
    <backend>
      <runtime>[Рантайм сервера и фреймворк]</runtime>
      <database>[База данных и драйвер]</database>
      <api_integration>[Интеграция внешнего API]</api_integration>
      <streaming>[Метод коммуникации реального времени]</streaming>
    </backend>
    <communication>
      <api>[Стиль архитектуры API]</api>
      <streaming>[Протокол стриминга]</streaming>
      <claude_api>[Детали интеграции SDK]</claude_api>
    </communication>
  </technology_stack>

  <prerequisites>
    <environment_setup>
      [Список требований настройки: env vars, зависимости, структура директорий]
    </environment_setup>
  </prerequisites>

  <core_features>
    [Создайте 10-15 категорий функций, каждая как именованный тег с 5-12 пунктами]
  </core_features>

  <database_schema>
    <tables>
      [Для каждой сущности создайте именованный тег с полями, типами, JSON-полями, временными метками]
    </tables>
  </database_schema>

  <api_endpoints_summary>
    [Сгруппируйте эндпоинты по ресурсам: HTTP_VERB /api/path - описание]
  </api_endpoints_summary>

  <ui_layout>
    <main_structure>[Общая архитектура лейаута]</main_structure>
    <header>[Компоненты хедера]</header>
    <sidebar>[Компоненты сайдбара]</sidebar>
    <main_content_area>[Компоненты основной области]</main_content_area>
    <secondary_panels>[Выезжающие панели, drawer-ы]</secondary_panels>
    <modals>[Модальные/overlay компоненты]</modals>
  </ui_layout>

  <design_system>
    <color_palette>[Цвета с hex-кодами, светлая/тёмная тема]</color_palette>
    <typography>[Шрифты, размеры, веса]</typography>
    <components>[UI-компоненты со спецификациями]</components>
    <animations>[Времена переходов и анимации]</animations>
  </design_system>

  <key_interactions>
    [2-4 основных пользовательских потока с пошаговыми последовательностями]
  </key_interactions>

  <implementation_steps>
    [8-10 фаз реализации с заголовками и 5-7 задачами]
  </implementation_steps>

  <success_criteria>
    <functionality>[5-7 функциональных требований]</functionality>
    <user_experience>[5-7 требований UX]</user_experience>
    <technical_quality>[5-7 требований к качеству кода]</technical_quality>
    <design_polish>[5-7 требований к визуальному дизайну]</design_polish>
  </success_criteria>
</project_specification>
```

## РУКОВОДСТВО ПО СОДЕРЖАНИЮ

1. **Специфичность**: Включайте точные ID моделей, hex-коды, номера портов, названия библиотек
2. **Полнота**: Каждая функция должна иметь соответствующие поля БД, API эндпоинты и UI компоненты
3. **Консистентность**: Используйте одинаковую терминологию во всём документе
4. **Действенность**: Задачи должны быть конкретными для реализации без неоднозначностей
5. **Технологические ограничения**: Специфицируйте точные подходы

## ДЕФОЛТНЫЙ ТЕХНОЛОГИЧЕСКИЙ СТЕК

- **Frontend**: React с Vite, Tailwind CSS, React Router
- **Backend**: Node.js с Express, SQLite с better-sqlite3
- **AI Integration**: Claude API с Anthropic SDK, SSE для стриминга
- **API Style**: RESTful

## ВВОД ПРОЕКТА

[Опишите приложение для построения, ключевые функции и требования]
```

**Источник:** https://gist.github.com/robzolkos/1b6d3bd471018c643e76ffaeab2623e8

---

## 2. Technical Project Planning Meta-Prompt

**Назначение:** Генерация комплексного технического плана реализации.

**Когда использовать:** После получения ТЗ для детального планирования архитектуры и задач.

```markdown
Вы — эксперт по архитектуре ПО и техническому планированию. Создайте комплексный технический план реализации проекта на основе предоставленных входных данных.

### USER INPUT

[Опишите проект: основную концепцию, ключевые функции, технические ограничения, целевых пользователей]

### OUTPUT FORMAT

#### 1. PROJECT IDENTITY

```yaml
project:
  project_name: "Project Name 🚀"
  core_concept: |
    Краткое описание основной идеи проекта
  project_hook: |
    Крюк для привлечения пользователей (для README)
  key_features:
    - Feature 1
    - Feature 2
  technical_constraints:
    - "Must be web-based"
  target_users: |
    Описание целевой аудитории
```

#### 2. TECHNICAL ARCHITECTURE

```yaml
architecture:
  frontend:
    core_ui_components:
      - Component 1
    state_management: |
      Описание подхода к управлению состоянием
    data_flow_patterns:
      - Pattern 1
    user_interactions:
      - Interaction 1
  
  backend:
    services_structure:
      - Service 1
    api_design:
      endpoints:
        - Endpoint 1
    data_processing:
      - Process 1
    external_integrations:
      - Integration 1
  
  data:
    storage_solutions:
      - Solution 1
    data_models:
      - Model 1
    caching_strategy: |
      Описание стратегии кеширования
    data_flow: |
      Описание потока данных
  
  infrastructure:
    deployment_requirements:
      - Requirement 1
    scaling_considerations:
      - Consideration 1
    service_dependencies:
      - Dependency 1
```

#### 3. IMPLEMENTATION COMPONENTS

```yaml
components:
  - name: "Component Name"
    purpose: |
      Описание роли компонента
    technical_requirements:
      libraries:
        - Library 1
      performance:
        - Performance requirement
      security:
        - Security requirement
      integration_points:
        - Integration point 1
    implementation_details:
      data_structures:
        - Structure 1
      algorithms:
        - Algorithm 1
      api_contracts:
        - Contract 1
      error_handling:
        - Strategy 1
```

#### 4. TASK BREAKDOWN

```yaml
tasks:
  - id: "TASK-001"
    category: "frontend/backend/infrastructure"
    description: |
      Конкретное, измеримое описание задачи
    technical_details:
      required_technologies:
        - Technology 1
      implementation_approach: |
        Детальный подход к реализации
      expected_challenges:
        - Challenge 1
      acceptance_criteria:
        - Criterion 1
    complexity:
      estimated_loc: 150
      estimated_hours: 6
    dependencies:
      - "TASK-000"
```

### GUIDELINES

1. **Technical Depth**: Каждый компонент должен иметь чёткие технические спецификации
2. **Modularity**: Разбейте на независимые модули с ясными интерфейсами
3. **Implementation Focus**: Предоставьте конкретные, измеримые задачи
4. **Task Specificity**: Задачи должны быть атомарными и измеримыми

### RESPONSE FORMAT

1. Project Identity (название и hook)
2. Technical Architecture Overview
3. Detailed Component Specifications
4. Task Breakdown
5. Implementation Dependencies

### IMPORTANT NOTES

- Сфокусируйтесь на деталях реализации
- Включите конкретные примеры где уместно
- Определите чёткие интерфейсы и контракты
- **MAKE THE BEST APP POSSIBLE**
  - Проанализируйте идею на предмет "genius & eureka" моментов
  - Если есть похожие приложения — предложите улучшения
  - Добавьте важные use cases если пользователь их упустил
  - Завершите секцией о том, почему это приложение будет amazing
```

**Источник:** https://gist.github.com/pyros-projects/c77402249b5b45f0a501998870766ae9

---

## 3. MetaPrompts для AI-агентов

**Назначение:** Создание системы кастомизации AI-ассистентов (агенты, навыки, промпты).

**Когда использовать:** Для настройки AI-ассистентов под специфичные workflow команды.

### Структура проекта

```
<provider>/                          # .github/, .claude/, .codex/
├── agents/
│   ├── my-agent.agent.md            # Пользовательский агент
│   └── helper.subagent.agent.md     # Суб-агент (workflow компонент)
├── skills/
│   └── skill-name/
│       └── SKILL.md                 # Определение навыка
├── prompts/
│   └── my-prompt.prompt.md          # Шаблон промпта
└── instructions/
    └── coding.instructions.md       # Авто-применяемые инструкции
```

### Типы файлов

| Тип | Файл | Назначение |
|-----|------|------------|
| **Агент** | `*.agent.md` | Пользовательский интерфейс для задач |
| **Суб-агент** | `*.subagent.agent.md` | Компонент workflow (`user-invokable: false`) |
| **Навык** | `SKILL.md` | Переиспользуемые процедуры |
| **Промпт** | `*.prompt.md` | Шаблоны промптов |
| **Инструкции** | `*.instructions.md` | Авто-применяемые правила |

### Пример запроса к мета-агенту

```
"Создать нового агента для проектирования схем БД"
"Валидировать мои файлы агентов и навыков"
"Сгенерировать документацию для текущих агентов"
```

**Источник:** https://github.com/JBurlison/MetaPrompts

---

## Рекомендуемый workflow

```
1. Project Specification Prompt → Генерация ТЗ
       ↓
2. Technical Planning Meta-Prompt → Архитектурный план
       ↓
3. MetaPrompts → Настройка AI-агентов под проект
       ↓
4. Реализация по task breakdown
```

---

## Дополнительные ресурсы

- [prompts.chat](https://prompts.chat) — библиотека промптов
- [promptbase.com](https://promptbase.com) — marketplace промптов
- [software-dev-prompt-library](https://github.com/codingthefuturewithai/software-dev-prompt-library) — коллекция промптов для разработки
