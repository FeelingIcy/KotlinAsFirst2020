загружаем на комп
```
git clone https://github.com/kursor1337/KotlinAsFirst2020`
cd KotlinAsFirst2020
```
добавляем upstream
```
git remote add upstream-my https://github.com/kursor1337/KotlinAsFirst2021
git fetch upstream-my
```
создаем ветку backport и переходим в неё
```
git checkout -b backport
```
перекидываем в текущую ветку все коммиты с того, что указан в задании до последнего коммита
```
git cherry-pick d535f3592006b8f2593c9f881d72c05164aadc13...FETCH_HEAD
```
добавляем upstream партнёра
```
git remote add upstream-theirs https://github.com/FeelingIcy/KotlinAsFirst2021
git fetch upstream-theirs
```
переходим в ветку master
```
git checkout  master
```
мерджим
```
git merge upstream-theirs/master backport
```
исправляем конфликты в vs code, коммитим и пушим
```
git commit -m "o"
git push
```
заливаем все, что нам выдает git remote -v в файл remotes
```
git remote -v > remotes
```
создаем файл howto.md и заполняем, добавляем remotes и howto.md в гит чтобы он за ним следил
```
git add remotes
git add howto.md
```
коммитим и пушим
```
git commit -m ":)"
git push
```