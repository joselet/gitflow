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

