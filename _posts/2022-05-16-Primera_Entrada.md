---
layout: post
author: H4tor
title: Primera entrada
---

En este primer artículo me anoto un script que es una pasada:
```bash
#!/bin/bash

echo "Por favor, introduce tu nombre: "
read name
echo "Bienvenid@ $name"
echo "Tienes que adivinar el usuario y password :)"
count=1
user="user"
password="pass"
while [[ $count -le 5 && $user != "admin" && $password != "password" ]]
do
  if [ $count -gt 1 ]
  then
    echo "Usuario o Contraseña errónea"
  fi
  echo "Este es el intento número $count"
  echo "Por favor, inserta el usuario"
  read user
  echo "Por favor, inserta el password"
  read password
  ((count++))
  echo "esperamos 5s para hacer las comprobaciones...."
##  sleep 5
done

if [[ ( $user == "admin" && $password  == "password" ) ]]
then
  echo "$name has acertado.... Ahora tienes privilegios totales..."
else
  echo "$name no has podido acertar.... Adiós!"
fi
```
