# Git-base-commands
### 0. Клонирование существующего репозитория
```
git clone https://github.com/doroGU-Ylitkam/Git-base-commands.git
cd Git-base-commands
```
_______
### 1. Создание файла
```
echo "Base algorithms:" > algorithms.txt
git add algorithms.txt
git commit -m "Create a file with algorithms"
```
_______
### 2. Добавление нового алгоритма
```
echo "1. Line search" >> algorithms.txt
git add .
git commit -m "Added Line search"
```
_______
### 3. Создание feature ветки
```
git checkout -b feature/sorting
echo "2. Bubble sort" >> algorithms.txt
git add .
git commit -m "Added Bubble sort"
git push -u origin feature/sorting 
```
_______
### 4. Слияние feature в develop
```
git checkout develop
git push -u origin develop
git merge feature/sorting --no-ff -m "Merge feature/sorting"
```
_______
### 5. Создание релиза
```
git checkout -b release/1.1
echo "Version 1.1" >> version.txt
git add .
git commit -m "Prepare to release v1.1"
git push origin release/1.1
```
_______
### 6. Слияние релиза в Main
```
git checkout main
git merge release/1.1 --no-ff -m "Release v1.1"
git tag -a v1.1 -m "Version 1.1"
git push origin main
git push --tags
```
