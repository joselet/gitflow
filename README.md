# gitflow
prácticas git flow
# proceso
## desarrollo normal: Rama develop
nada más crear tu repositorio, muevete a la rama develop
git checkout develop (primero, crea la rama:git branch develop)
```
#trabajar normalmente
git add .
git commit -m "desarrollo x cosa"
git push
#quizá tengas que poner esta línea:
git push --set-upstream origin develop
```
## sacar una release, llevarlo a main
```
git checkout main
git pull
git merge --squash develop
git commit -m "versión 1"
git push
#y ahora volver a develop para continuar trabajando
git checkout develop
git merge main
git push #opcional (para llevar el cambio también en el remoto)
```
# Herramientas útiles
Ver el log en árbol
```
jose@penguin:~/sd/www/gitflow$ git log --oneline --graph --all
*   3b9f54e (HEAD -> develop, origin/develop) Merge branch 'main' into develop
|\  
| * 6637081 (origin/main, origin/HEAD, main) version 2
* | 41ea523 añadido casos especiales
* | d4abd66 Merge branch 'main' into develop
|\| 
| * 4ad4124 version 1.1
* | 9f7efb9  modificacion
|/  
* 62fa5e0 Versión 1.0
* 91d5da0 Initial commit
```
# Casos especiales
## En caso de necesitar un hotfix en producción:
```
git checkout main
# arreglar el bug
git commit
git push
# volver a la rama develop y traerte a develop el cambio que has hecho en main
git checkout develop
git merge main
```

