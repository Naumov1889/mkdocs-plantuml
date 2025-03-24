## Установка MkDocs
MkDocs можно установить с помощью менеджера пакетов `pip`. Выполните следующую команду в терминале:
```BASH
pip install mkdocs 
```

Убедитесь, что MkDocs установлен правильно, выполнив команду:
```BASH
mkdocs --version 
```

Перейдите в директорию вашего проекта и выполните команду для создания нового проекта MkDocs:
```BASH
mkdocs new docs 
```
Эта команда создаст новую директорию `docs` с базовой структурой проекта.

Чтобы настроить проект, откройте файл `docs/mkdocs.yml` и добавьте базовую конфигурацию:
```YAML
site_name: FitLife Documentation
theme: readthedocs
markdown_extensions:
  - md_in_html
  - plantuml_markdown
plugins:
  - search 
```

Организуйте структуру документации.
```MARKDOWN
docs/
├── index.md
├── architecture/
│   ├── context.md
│   ├── container.md
│   ├── component.md
│   └── code.md
└── mkdocs.yml 
```



## Интеграция PlantUML с MkDocs
Теперь, когда всё готово, попробуйте интегрировать PlantUML в несколько шагов:

Установите плагин `mkdocs-plantuml` для интеграции PlantUML с MkDocs.
```BASH
pip install mkdocs-plantuml 
```

Установите плагин:
```BASH
pip install mkdocs_puml 
```

Добавьте плагин `plantuml` в файл `mkdocs.yml`:
```YML
plugins:
    - plantuml:
        puml_url: https://www.plantuml.com/plantuml/ 
```


Для предварительного просмотра документации запустите локальный сервер MkDocs:

```BASH
mkdocs serve 
```

- Откройте браузер и перейдите по адресу `http://127.0.0.1:8000`, чтобы увидеть сгенерированную документацию.
- Для генерации статического сайта выполните команду:

```BASH
mkdocs build 
```

## Docker
forget all above and do this:
to serve:
```bash
docker compose up
```

to build:
```bash
docker compose run --rm mkdocs mkdocs build
```
