# 🔀 Trabajar con dos remotos (GitHub + GitLab)

## 🧠 Escenario

Querés usar:

* GitHub → backup / visibilidad / open
* GitLab (asimov) → institucional / interno

Un solo repo local, dos destinos. Git no se queja, al contrario: le gusta la poligamia.

---

## 1. Ver remotos actuales

git remote -v

---

## 2. Si ya tenés `origin` apuntando a GitLab (asimov)

Renombralo:

git remote rename origin gitlab

---

## 3. Agregar GitHub como nuevo `origin`

git remote add origin https://github.com/USUARIO/REPO.git

---

## 4. Verificar

git remote -v

Resultado esperado:

gitlab  https://asimov.cncps.gob.ar/usuario/proyecto.git (fetch)
gitlab  https://asimov.cncps.gob.ar/usuario/proyecto.git (push)
origin  https://github.com/USUARIO/REPO.git (fetch)
origin  https://github.com/USUARIO/REPO.git (push)

---

## 5. Subir a GitHub (origin)

git branch -M main
git push -u origin main

---

## 6. Subir también a GitLab

git push -u gitlab main

---

# 🔁 Flujo de trabajo recomendado

## Caso típico (laburando tranquilo)

git add .
git commit -m "feat: cambios importantes"
git push origin main

(opcional backup institucional)
git push gitlab main

---

# ⚡ Pro tip: push a ambos remotos en un solo comando

git remote set-url --add --push origin https://github.com/USUARIO/REPO.git
git remote set-url --add --push origin https://asimov.cncps.gob.ar/usuario/proyecto.git

Ahora esto:

git push origin main

👉 empuja a los dos al mismo tiempo

---

# 🧨 Problemas comunes

## ❌ push falla en uno de los remotos

No se cae todo el comando, pero ojo:

* GitHub puede subir OK
* GitLab puede fallar (ej: servidor caído)

👉 Solución: push manual separado

git push origin main
git push gitlab main

---

## ❌ ramas distintas entre remotos

Asegurate de estar en la misma rama:

git branch

---

## ❌ conflictos por historial distinto

Si uno de los remotos ya tenía commits:

git pull --rebase origin main

---

# 🧱 Concepto clave

* Un repo local puede tener múltiples remotos
* `origin` es solo un nombre (no tiene magia)
* Podés tener: `origin`, `gitlab`, `backup`, lo que quieras
* `push` define a dónde mandás los cambios

---

# 🧩 Resumen express

git remote rename origin gitlab
git remote add origin https://github.com/USUARIO/REPO.git
git push origin main
git push gitlab main

---

Si esto no entra en tu cheatsheet, nada entra.
