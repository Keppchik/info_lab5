# Отчёт по лабораторной работе №5
## Задание 1 - Автоматизация проверки формата файлов при коммите
Для проверки txt файлов в коммите нам надо изменить файл pre-commit, который по умолчанию Git хранит в папке .git/hooks. Перемещаемся в папку hooks и открываем файл pre-commit

<img width="573" alt="Screenshot 2024-12-19 at 01 14 44" src="https://github.com/user-attachments/assets/d3c7b2de-708c-42e6-af99-c0df8028ebcb" />

В файле записываем следующий код:

<img width="576" alt="Screenshot 2024-12-19 at 01 18 46" src="https://github.com/user-attachments/assets/ba46d0b4-4313-431b-a750-f37f9ab98990" />

```git diff --cached --name-only --diff-filter=ACM``` - получаем все txt файлы, которые были добавлены, изменены или копированы.

```if [[ -z "$files" ]]``` - проверяем есть ли txt файлы в коммите

Далее для каждого файла делаем проверку
```if ! grep -q "Автор" "$file"; then``` - ищем строку со словом "Автор" и если такой нет то выводим ```Ошибка: в файле $file нет подписи```

Если код нигде не завершился ошибкой, то выводим ```Все файлы прошли проверку```

Пример работы:
<img width="1229" alt="Screenshot 2024-12-19 at 01 22 26" src="https://github.com/user-attachments/assets/2c00513a-4900-4f4b-a60f-5f16f9072c6f" />

## Задание 2 - Использование Git Flow в проекте
В результате всех действий для задания 2 получилось такие древа для созданных веток:
<img width="1001" alt="Screenshot 2024-12-19 at 02 27 22" src="https://github.com/user-attachments/assets/755d8f08-1b56-4050-88de-e697b14b1956" />
<img width="1001" alt="Screenshot 2024-12-19 at 02 27 42" src="https://github.com/user-attachments/assets/b9ace1d1-5805-45ea-901f-831e2d6864bc" />
<img width="1001" alt="Screenshot 2024-12-19 at 02 27 38" src="https://github.com/user-attachments/assets/b5e46d2b-4160-4450-a545-5926aa1a545a" />
<img width="1001" alt="Screenshot 2024-12-19 at 02 27 34" src="https://github.com/user-attachments/assets/733202a5-2a62-4b82-b4d0-1dd948df8cd8" />


