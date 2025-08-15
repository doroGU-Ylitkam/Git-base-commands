# Git-base-commands
### 0. Pull существующего репозитория
```
git pull https://github.com/doroGU-Ylitkam/Git-base-commands.git
cd Git-base-commands
```
_______
### 1. Создание файла
```
echo "Базовые алгоритмы:" > algorithms.txt
git add algorithms.txt
git commit -m "Создан файл с алгоритмами"
```
_______
### 2. Добавление нового алгоритма
```
echo "1. Линейный поиск" >> algorithms.txt
git add .
git commit -m "Добавлен линейный поиск"
```
_______
### 3. Создание feature ветки
```
git checkout -b feature/sorting
echo "2. Сортировка пузырьком" >> algorithms.txt
git add .
git commit -m "Добавлена сортировка пузырьком"
git push -u origin feature/sorting 
```
_______
### 4. Слияние feature в develop
```
git checkout develop
git merge feature/sorting --no-ff -m "Merge feature/sorting"
```
_______
### 5. Создание релиза
```
git checkout -b release/1.0
echo "Версия 1.0" >> version.txt
git add .
git commit -m "Подготовка к релизу v1.0"
git push origin release/1.0
```
_______
### 6. Слияние релиза в Main
```
git checkout main
git pull origin main  # Получаем тег
git tag -a v1.0 -m "Версия 1.0"
git push --tags
```
