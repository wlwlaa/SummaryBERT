# BERT2BERT для суммаризации русскоязычных текстов

Проект для обучения модели автоматической суммаризации на русском языке с использованием архитектуры Encoder-Decoder на базе `ruBERT` и библиотеки Transformers.

## Что делает проект

Модель принимает длинный текст или статью и генерирует краткое содержание.

Используется:

* `DeepPavlov/rubert-base-cased` как энкодер и декодер
* датасет `IlyaGusev/gazeta`
* библиотека Hugging Face Transformers
* метрика `ROUGE` для оценки качества

## Стек

* Python
* PyTorch
* Transformers
* Datasets
* Evaluate
* NLTK

## Структура ноутбука

| Этап               | Описание                        |
| ------------------ | ------------------------------- |
| Data preparation   | Загрузка и токенизация датасета |
| Model              | Сборка BERT2BERT модели         |
| Evaluation Metrics | Подключение ROUGE               |
| Train params       | Настройка обучения              |
| Evaluating results | Генерация суммаризации          |
| Save model         | Сохранение модели               |

## Установка

```bash
pip install torch transformers datasets evaluate nltk rouge_score
```

## Запуск

Откройте ноутбук:

```bash
jupyter notebook main.ipynb
```

## Параметры обучения

Основные настройки:

* `max_input_length = 512`
* `max_target_length = 128`
* `batch_size = 8`
* `num_train_epochs = 3`

## Пример генерации

```python
summary = generate_summary(text, model, tokenizer)
print(summary)
```

## Результат

После обучения модель сохраняется в:

```bash
./bert2bert/result/
```

## Возможные улучшения

* Добавить inference API
* Использовать более крупные модели
* Настроить beam search
* Добавить логирование через WandB
* Провести fine-tuning на других корпусах


<i>p.s.: Личный Pet-проект для экспериментов с NLP и BERT</i>
