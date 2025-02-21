# Проект Translator

## Обзор
Этот проект представляет собой компилятор/интерпретатор, который обрабатывает программный код на пользовательском языке программирования с помощью нескольких этапов:
- **Лексический анализ**: Разбивает входной код на токены.
- **Синтаксический анализ**: Проверяет структуру и корректность синтаксиса.
- **Семантический анализ**: Обеспечивает контроль типов и правильность использования переменных и функций.
- **Генерация промежуточного представления**: Создаёт код в Обратной Польской Нотации (POLIZ).
- **Исполнение**: Выполняет сгенерированные POLIZ-инструкции.

## Возможности
- Поддержка переменных, арифметических и логических операций.
- Реализация управляющих конструкций (`if`, `while`, `for`).
- Поддержка пользовательских функций.
- Чтение входных данных из `input-data.txt` и запись результатов в `output-data.txt`.

## Структура проекта
```plaintext
├── lexical-analyzer.h      # Лексический анализатор
├── syntax-analyzer.h       # Синтаксический анализатор
├── semantic-analyzer.h     # Семантический анализатор
├── poliz-generator.h       # Генератор кода в формате POLIZ
├── executor-program.h      # Исполнитель POLIZ-кода
├── main.cpp                # Главный файл программы
├── Lexeme.h                # Структура лексем
├── input-file.txt          # Пример входного файла
├── input-data.txt          # Входные данные для исполнения
├── output-data.txt         # Результаты выполнения
```

## Как это работает
1. **Лексический анализатор (`lexical-analyzer.h`)**
   - Читает `input-file.txt` и преобразует его в лексемы.
   - Определяет ключевые слова, идентификаторы, числа и операторы.
   
2. **Синтаксический анализатор (`syntax-analyzer.h`)**
   - Разбирает лексемы и строит синтаксическое дерево.
   - Выявляет ошибки, такие как отсутствие скобок или неопределённые переменные.
   
3. **Семантический анализатор (`semantic-analyzer.h`)**
   - Проверяет корректность типов данных и использование функций.
   - Управляет областями видимости и таблицей символов.
   
4. **Генератор POLIZ (`poliz-generator.h`)**
   - Преобразует выражения в Обратную Польскую Нотацию.
   - Подготавливает операции для стекового выполнения.
   
5. **Исполнитель (`executor-program.h`)**
   - Интерпретирует и выполняет POLIZ-инструкции.
   - Управляет переменными и выполняет операции ввода/вывода.
   
## Пример
### Входные данные (`input-file.txt`):
```cpp
int main() {
    int a = 10;
    int b = 5;
    print(a + b);
    return 0;
}
```

### Ожидаемый вывод (`output-data.txt`):
```plaintext
15
```

## Заметки
- Изменяйте `input-file.txt`, чтобы тестировать различные программы.
- При возникновении ошибки компилятор укажет строку с ошибкой.
- Используется стековый подход к выполнению команд.

