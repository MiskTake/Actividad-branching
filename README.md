# 🌿 Git Branching — Actividad Grupal

Investigación grupal sobre el flujo de trabajo con Git y GitHub: ramas, commits, pull requests y buenas prácticas de colaboración en equipo.

---

## 🎯 Objetivo

Que los alumnos investiguen y practiquen el flujo real de colaboración con Git:
- Comprender qué son las ramas y por qué se usan
- Aprender a hacer fork, branch, commit, push y pull request
- Entender qué hace quien revisa y acepta cambios

---

## 👥 Organización

| Alumno | Tema |
|--------|------|
| Alumno 1 | ¿Qué es una rama en Git? |
| Alumno 2 | ¿Qué diferencia hay entre branch y fork? |
| Alumno 3 | ¿Qué es `main` y por qué se protege? |
| Alumno 4 | ¿Qué es un commit y por qué es importante? |
| Alumno 5 | ¿Qué es push y qué relación tiene con GitHub? |
| Alumno 6 | ¿Qué es un Pull Request? |
| Alumno 7 | ¿Qué es merge y qué podría salir mal? |
| Alumno 8 | Buenas prácticas al trabajar con ramas |

---

## 📚 Investigación

### Alumno 1 — ¿Qué es una rama en Git?

Una rama (branch) en Git es una copia independiente del código donde puedes trabajar sin afectar la versión principal del proyecto.

- **Para qué sirve:** Permiten separar tareas sin mezclar todo.
- **Qué problema resuelve:** Evitan romper el código principal.
- **Por qué no trabajar siempre en `main`:** Porque `main` debe ser estable y sin errores.

**Ejemplo:**
> Estás desarrollando una página web. Tienes `main` funcionando, pero necesitas agregar un login. Creas una rama `login`, desarrollas ahí, y si hay errores no afectan el proyecto principal. Cuando todo funciona bien, unes la rama a `main`.

**Conclusión:** Las ramas son fundamentales porque permiten trabajar de forma ordenada y segura, evitando errores en el código principal y facilitando el desarrollo en equipo.

---

### Alumno 2 — ¿Qué diferencia hay entre branch y fork?

- **Branch:** Una rama dentro del mismo repositorio, para desarrollar funcionalidades sin tocar el código estable.
- **Fork:** Una copia completa de un repositorio ajeno en tu propia cuenta de GitHub.
- **Cuándo usar cada uno:** Branch para trabajo en tu propio proyecto; fork para contribuir a proyectos externos sin permisos de escritura.

**Ejemplo:**
> Encuentras un error en una librería open source. Haces fork del repositorio, corriges el bug en una rama dentro de tu fork, y abres un Pull Request hacia el repositorio original. El dueño revisa y decide si acepta tu cambio.

**Conclusión:** Branch y fork resuelven problemas similares pero en contextos distintos: branch es para trabajo interno en equipo, fork es para colaboración abierta con proyectos externos.

---

### Alumno 3 — ¿Qué es `main` y por qué se protege?

- **Qué representa:** Es la rama principal del proyecto. Contiene el código estable, probado y listo para producción.
- **Por qué es estable:** Es la versión que se despliega o entrega al cliente. Si tiene errores, el producto falla para todos.
- **Qué significa protegerla:** GitHub permite activar reglas que impiden cambios directos. Todo cambio debe pasar por un PR revisado.

**Ejemplo:**
> Un developer sube directamente un bug a `main`. La app se cae para todos los usuarios. Si hubiera habido protección de rama, ese cambio habría requerido revisión antes de entrar.

**Conclusión:** `main` es el código oficial del proyecto. Protegerla garantiza que solo cambios revisados y aprobados lleguen a producción, reduciendo el riesgo de errores graves.

---

### Alumno 4 — ¿Qué es un commit y por qué es importante?

- **Qué es:** Una fotografía del estado del código en un momento específico. Registra qué cambió, quién y cuándo.
- **Por qué hacerlos pequeños:** Son más fáciles de revisar, entender y revertir si algo sale mal.
- **Cómo ayuda al historial:** Cada commit tiene un mensaje descriptivo. Juntos forman una línea de tiempo del proyecto.

**Ejemplo:**
```
git commit -m "Add login form"
git commit -m "Connect form to API"
git commit -m "Add error validation"
```
> Si algo falla, identificas exactamente en qué commit ocurrió el problema y revertís solo ese cambio.

**Conclusión:** Los commits son la memoria del proyecto. Hacerlos frecuentes y con mensajes claros permite trabajar con seguridad y recuperarse de errores sin perder todo.

---

### Alumno 5 — ¿Qué es push y qué relación tiene con GitHub?

- **Local:** Tu código existe solo en tu computador. Nadie más puede verlo.
- **Remoto:** El código está en un servidor externo (como GitHub) accesible para el equipo.
- **Qué hace `git push`:** Envía los commits de tu máquina al repositorio remoto.
- **Por qué no aparece automáticamente:** Git separa lo local de lo remoto intencionalmente. Tú decides cuándo subir.

**Ejemplo:**
> Trabajas toda la tarde, haces 5 commits. Tu compañero entra a GitHub y no ve nada. Recién cuando ejecutas `git push`, tus cambios aparecen y el equipo puede verlos.

**Conclusión:** Push es el puente entre tu trabajo local y el repositorio compartido. Sin él, el código existe solo para ti.

---

### Alumno 6 — ¿Qué es un Pull Request?

- **Qué es:** Una solicitud formal para que tus cambios en una rama sean revisados y aceptados en otra (generalmente `main`).
- **Por qué no es solo subir código:** Incluye revisión: otros ven qué cambió, dejan comentarios y piden correcciones.
- **Qué permite revisar:** Errores de lógica, problemas de estilo, conflictos con el código existente.

**Ejemplo:**
> Terminas `feature/carrito` y abres un PR hacia `main`. Tu compañero nota que falta validar un campo y lo comenta. Tú lo corriges, el PR se aprueba. Recién entonces el código entra a `main`.

**Conclusión:** Un Pull Request es una conversación sobre el código. Permite mantener calidad y evitar errores antes de que lleguen a producción.

---

### Alumno 7 — ¿Qué es merge y qué podría salir mal?

- **Qué es:** Unir el contenido de una rama con otra, generalmente hacia `main` cuando los cambios están listos.
- **Qué es un conflicto:** Ocurre cuando dos personas modificaron el mismo fragmento en ramas distintas. Git no sabe cuál versión conservar.
- **Por qué ocurre:** Git no puede adivinar la intención detrás de cambios que colisionan en el mismo lugar.

**Ejemplo:**
> Alumno A y Alumno B editan la misma línea de `index.js` en ramas distintas. Al hacer merge, Git marca el conflicto y muestra ambas versiones. El equipo debe elegir cuál conservar.

**¿Cómo reducirlo?**
- Hacer merges frecuentes para que las ramas no diverjan demasiado.
- Comunicarse sobre qué archivos está editando cada uno.
- Trabajar en partes distintas del código cuando sea posible.

**Conclusión:** El merge convierte el trabajo individual en trabajo colectivo. Los conflictos son normales, pero con comunicación y ramas pequeñas se minimizan.

---

### Alumno 8 — Buenas prácticas al trabajar con ramas

- **Nombrar ramas:** Usar prefijos descriptivos: `feature/login`, `fix/error-validacion`, `hotfix/crash-pago`.
- **Commits atómicos:** Cada commit representa un solo cambio lógico.
- **Mensajes claros:** Verbos en imperativo: `Add login form`, `Fix null error`, `Update README`. Evitar: `fix`, `cambios`, `wip`.
- **No ramas eternas:** Una rama por funcionalidad y mergear pronto.
- **Revisar antes de mergear:** Siempre pasar por un Pull Request.

**Ejemplo:**
> Un equipo define: ramas con prefijo según tipo, commits con verbo al inicio, PRs con al menos una aprobación. Resultado: historial legible, conflictos raros y reviews rápidos.

**Conclusión:** Las buenas prácticas son la diferencia entre un proyecto que escala y uno que colapsa. Adoptarlas desde el inicio ahorra horas de confusión y conflictos innecesarios.

---

## 💡 TL;DR

| Concepto | En simple |
|----------|-----------|
| **Rama (branch)** | Copia independiente del código para trabajar sin afectar `main` |
| **Fork** | Copia de un repositorio ajeno en tu cuenta de GitHub |
| **`main`** | Rama estable y oficial del proyecto; debe protegerse de cambios directos |
| **Commit** | Fotografía del código en un momento dado; hacerlos pequeños y descriptivos |
| **Push** | Sube tus commits locales al repositorio remoto en GitHub |
| **Pull Request** | Solicitud de revisión antes de unir cambios a `main` |
| **Merge** | Une ramas; puede generar conflictos si dos personas editan lo mismo |
| **Buenas prácticas** | Nombres de ramas, commits atómicos y PRs revisados hacen funcionar al equipo |

---

> *"Cuando entiendes el flujo de Git, dejas de trabajar solo y empiezas a colaborar de verdad."*
