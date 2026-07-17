# Carta Gantt — Sistema de Escenario de Impacto (SENAPRED)

Tablero interactivo de seguimiento del proyecto SEI, pensado para publicarse en **GitHub Pages**.

## Archivos

- `index.html` — el tablero (diseño + lógica). Casi nunca se toca.
- `tareas.json` — **los datos**: tareas, fechas y estados. Este es el archivo que editas para actualizar.
- `README.md` — este instructivo.

---

## Publicar por primera vez (una sola vez, ~5 minutos)

1. Entra a https://github.com e inicia sesión (o crea una cuenta gratis).
2. Arriba a la derecha, **＋ → New repository**.
   - **Repository name:** por ejemplo `carta-gantt-sei`
   - Déjalo **Public** (necesario para GitHub Pages gratis).
   - Marca **Add a README** si quieres; da igual, lo reemplazaremos.
   - **Create repository**.
3. Sube los archivos: botón **Add file → Upload files**, arrastra `index.html`, `tareas.json` y `README.md`, y abajo aprieta **Commit changes**.
4. Activa Pages: pestaña **Settings → Pages** (menú lateral izquierdo).
   - En **Source** elige **Deploy from a branch**.
   - En **Branch** elige **main** y carpeta **/ (root)**. **Save**.
5. Espera ~1 minuto y recarga esa misma página de Settings → Pages: aparecerá el enlace
   `https://TU-USUARIO.github.io/carta-gantt-sei/`
6. Ábrelo y **guárdalo como favorito**. Ese es tu tablero en vivo.

---

## Actualizar el tablero (cada vez que avanzamos algo)

Solo editas `tareas.json`:

1. En el repo, abre **`tareas.json`**.
2. Aprieta el ícono de **lápiz** (Edit this file), arriba a la derecha.
3. Haz el cambio. Por ejemplo, marcar una tarea como terminada:
   ```json
   "status": "en_curso"   →   "status": "completada"
   ```
   Estados válidos: `completada`, `en_curso`, `en_pausa`, `pendiente`, `hito`.
4. **IMPORTANTE:** sube en 1 el número de `version` al inicio del archivo
   (de `"version": 4` a `"version": 5`). Esto obliga al tablero a mostrar los datos nuevos.
5. Abajo, **Commit changes**.
6. Espera unos segundos y **refresca** la URL del tablero. Listo.

> Si me pides a mí el cambio ("marca la etapa 7b como completada"), te devuelvo el
> `tareas.json` ya editado y con la versión subida; tú solo lo pegas y haces commit.

### Agregar una tarea nueva
Copia un bloque `{ ... }` dentro de `"tareas"`, cámbiale `id`, `name`, `start`, `end`,
`status` y `note`, y sube la `version`. El `phase` define en qué grupo aparece
(usa exactamente el mismo texto de un grupo existente para que caiga ahí).

---

## Notas

- Los clics directos sobre las barras (para avanzar estado) se guardan en tu navegador,
  pero **la fuente oficial es `tareas.json`**. Al subir la `version`, el archivo manda
  sobre los clics locales.
- El botón **↻ Restablecer datos** vuelve a lo que diga `tareas.json`.
- No necesitas descargar nada para ver la última versión: basta con refrescar la URL.
