# Обработка серийных номеров оборудования в бухгалтерской и процессинговой выгрузках одного банка

#### Задача №1: Фильтрация серийных номеров POS-терминалов из выгрузки бухгалтерской программы
Имеется файл Выгрузка.xlsx со столбцами: Категория, Название и Серийный номер. Необходимо извлечь строки с серийными номерами из категории POS-терминалы, содержащие префикс "CT". Серийные номера могут быть указаны с использованием различных обозначений: "s/n", "sn", а также варианты на русском языке "с/н", "сн". Запись может быть как раздельной, так и слитной с серийным номером, с различными вариантами регистра, такими как "S/n", "S/N" и "s/n". Скрипт `01_filter_ct_prefix.py` применяется для фильтрации нужных строк. 

#### Задача №2: Выделение числовых серийных номеров POS-терминалов
Необходимо найти строки, относящиеся к категории POS-терминалы, в которых серийные номера указаны только в числовом формате, без буквенных символов и без обозначений серийного номера, таких как "s/n", "ST" и т.п. Для фильтрации используется скрипт `02_extract_numeric_serials.py`.

#### Задача №3: Комбинирование результатов двух методов обработки
Для объединения таблиц, полученных в результате выполнения задач №1 и №2, используется скрипт `03_combined_serials_pos.py`.

#### Задача №4: Сравнение серийных номеров из разных выгрузок
Теперь перед нами стоит задача сравнения серийных номеров из первой выгрузки (бухгалтерская программа) с данными из второй (процессинговое ПО). Из-за разнообразия в форматах записи серийных номеров требуется использовать сложную логику сопоставления шаг за шагом.

- **Первая выгрузка (Бухгалтерская программа):** `Выгрузка.xlsx`
- **Вторая выгрузка (Процессинговое ПО):** `Вторая_выгрузка.xlsx`

Файл `04_matched_serials.py` предназначен для выполнения этой задачи.
