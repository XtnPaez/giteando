# 🚀 Subir una carpeta local a GitHub (desde cero)

## 🧠 Escenario

Tenés una carpeta en tu PC y querés convertirla en un repo en GitHub.

---

## 1. Crear el repo en GitHub

* Ir a https://github.com/
* Click en **New repository**
* Nombre (ej: `mi-proyecto`)
* ⚠️ **NO inicializar con README**
* Crear repo

---

## 2. Inicializar Git en tu carpeta local

cd ruta/a/tu/carpeta
git init

---

## 3. Agregar archivos al repo

git add .

---

## 4. Primer commit

git commit -m "init: primer commit"

---

## 5. Conectar con GitHub

git remote add origin https://github.com/usuario/mi-proyecto.git

---

## 6. Subir al repo

git branch -M main
git push -u origin main

---

## 🧨 Problemas comunes

### ❌ src refspec main does not match any

git commit -m "init"

---

### ❌ remote origin already exists

git remote remove origin
git remote add origin URL_NUEVA

---

### ❌ Migración GitLab → GitHub

git remote set-url origin https://github.com/usuario/mi-proyecto.git
git push -u origin main

---

## 🧩 Ver remoto actual

git remote -v

---

## 🧱 Concepto clave

* git init → convierte carpeta en repo
* git add . → prepara cambios
* git commit → guarda versión
* git remote → define destino
* git push → sube al remoto
