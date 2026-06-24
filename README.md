# 🏆 Titans — Stat Trackers

Trackers de estadísticas en vivo para todos los equipos Titans — Básquetbol y Fútbol. PWA instalable en cualquier dispositivo, funciona offline después del primer uso.

## 🔗 Apps por categoría

| Equipo | Link |
|--------|------|
| 🏀 Basket Sub 18 — Copa Talento | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2018/Copa%20Talento%20Sub%2018/) |
| 🏀 Basket Sub 18 — Ludos | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2018/Ludos%20Sub%2018/) |
| 🏀 Basket Sub 16 — Copa Talento | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2016/Copa%20Talento%20Sub%2016/) |
| 🏀 Basket Sub 14 — Ludos | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2014/Ludos%20Sub%2014/) |
| 🏀 Basket Sub 12 — Copa Talento | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2012/Copa%20Talento%20Sub%2012/) |
| ⚽ Fútbol Hombres Sub 14 | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Soccer/Sub%2014/Copa%20Talento%20Sub%2014/) |
| ⚽ Fútbol Hombres Sub 10 | [Abrir app](https://tommyhanono.github.io/Titans/Hombres/Soccer/Sub%2010/Copa%20Talento%20Sub%2010/) |
| ⚽ Fútbol Mujeres Sub 18 | [Abrir app](https://tommyhanono.github.io/Titans/Mujeres/Soccer/Sub%2018/Copa%20Talento%20Sub%2018/) |
| ⚽ Fútbol Mujeres Sub 10 | [Abrir app](https://tommyhanono.github.io/Titans/Mujeres/Soccer/Sub%2010/Copa%20Talento%20Sub%2010/) |
| 🔒 Admin — Activity Dashboard | [Abrir panel](https://tommyhanono.github.io/Titans/admin/) |

---

## 🔒 Admin Dashboard — Guía de uso

El panel de admin centraliza toda la actividad de los 8 trackers de basket (5 Titans + 3 MBA) en una sola pantalla.

### Acceso

1. Abrir `https://tommyhanono.github.io/Titans/admin/`
2. Ingresar la contraseña de admin
3. La sesión se mantiene activa mientras el tab esté abierto (sessionStorage)
4. Para cerrar sesión, click en **Cerrar sesión** (esquina superior derecha)

### Qué trackers aparecen

| Tracker | Organización |
|---------|-------------|
| Titans Copa Sub 18 | Titans |
| Titans Ludos Sub 18 | Titans |
| Titans Copa Sub 16 | Titans |
| Titans Ludos Sub 14 | Titans |
| Titans Copa Sub 12 | Titans |
| MBA Sub 13 | MBA Encestando Sueños |
| MBA Sub 15 | MBA Encestando Sueños |
| MBA Sub 17 | MBA Encestando Sueños |

### Eventos que se registran

| Evento | Qué significa |
|--------|--------------|
| `app_open` | Alguien abrió la app del tracker (en cualquier dispositivo) |
| `history_save` | Se guardó un partido completo al historial de Firebase |

Cada evento incluye: tracker de origen, timestamp exacto, y datos extra si los hay.

### Contadores (parte superior)

| Contador | Descripción |
|----------|------------|
| **Eventos totales** | Total de eventos según los filtros activos |
| **App opens** | Veces que se abrió algún tracker |
| **Partidos guardados** | Veces que se guardó un partido al historial |
| **Trackers activos** | Cuántos trackers distintos aparecen en los resultados |

### Filtros disponibles

- **Todos los trackers** — dropdown para ver solo un equipo específico
- **Todos los eventos** — dropdown para ver solo `app_open` o solo `history_save`
- **Buscar** — texto libre, busca en el nombre del tracker y el tipo de evento
- Los contadores se actualizan en tiempo real al cambiar filtros

### Actualizar los datos

Click en **↺ Actualizar** para recargar desde Firebase. Los datos no se refrescan solos — hay que hacer click manualmente cada vez que quieras ver actividad reciente.

### Tabla de eventos

Muestra los eventos más recientes primero (orden cronológico inverso). Columnas:

| Columna | Contenido |
|---------|-----------|
| **Fecha / Hora** | Timestamp local (zona horaria del dispositivo del admin) |
| **Evento** | `app_open` (azul) o `history_save` (verde) |
| **Tracker** | Nombre del equipo que generó el evento |
| **Extra** | Datos adicionales si los hay (generalmente vacío) |

---

## 📊 Sistema de actividad (técnico)

Los 5 trackers de basket Titans (+ los 3 de MBA en el repo [MBA](https://github.com/tommyhanono/MBA)) registran eventos automáticamente en Firebase Realtime Database sin requerir login de los entrenadores.

### Firebase

- **Proyecto:** `titans-tracker` — Realtime Database
- **Base URL:** `https://titans-tracker-default-rtdb.firebaseio.com`
- **Nodos por tracker:** `titans_copa18`, `titans_ludos18`, `titans_copa16`, `titans_ludos14`, `titans_copa12`
- **Log de actividad:** `/activity_log` (escritura pública, leída solo desde el admin)
- **Reglas actuales:** públicas (`true` / `true`) — los trackers no requieren login

---

## 📚 Tutoriales para entrenadores

| Tutorial | Link |
|----------|------|
| 🏀 Básquet — Guía del Entrenador | [Ver tutorial](https://tommyhanono.github.io/Titans/Tutorial_Basket_Entrenadores.html) |
| ⚽ Fútbol — Guía del Entrenador | [Ver tutorial](https://tommyhanono.github.io/Titans/Tutorial_Futbol_Entrenadores.html) |

---

## Estructura

```
Titans/
├── Hombres/
│   ├── Basket/
│   │   ├── Sub 18/
│   │   │   ├── Copa Talento Sub 18/   ✅ historial completo 2026 | Firebase: titans_copa18
│   │   │   └── Ludos Sub 18/          ✅ activo | Firebase: titans_ludos18
│   │   ├── Sub 16/
│   │   │   └── Copa Talento Sub 16/   ✅ activo | Firebase: titans_copa16
│   │   ├── Sub 14/
│   │   │   └── Ludos Sub 14/          ✅ activo | Firebase: titans_ludos14
│   │   └── Sub 12/
│   │       └── Copa Talento Sub 12/   ✅ activo | Firebase: titans_copa12
│   └── Soccer/
│       ├── Sub 14/
│       │   └── Copa Talento Sub 14/   ✅ activo
│       └── Sub 10/
│           └── Copa Talento Sub 10/   ✅ activo
├── Mujeres/
│   └── Soccer/
│       ├── Sub 18/
│       │   └── Copa Talento Sub 18/   ✅ activo
│       └── Sub 10/
│           └── Copa Talento Sub 10/   ✅ activo
├── admin/                             🔒 Panel de actividad (contraseña)
└── firebase-rules.json                Reglas Firebase (pegar en consola para deployar)
```

## Cómo configurar un tracker nuevo

1. Abrir el `index.html` del equipo correspondiente
2. Usar **＋** para agregar jugadores (básquet) o editar `DEFAULT_PLAYERS` en `app.js`
3. Para instalarlo como PWA: Safari → Compartir → Agregar a pantalla de inicio

## Notas técnicas

- Cada tracker tiene `localStorage` separado (claves únicas por equipo)
- Service workers con cache names distintos — no interfieren entre sí
- Los trackers de basket usan `app.js?v=4` (activity logging incluido)
- Para deployar reglas Firebase: pegar el contenido de `firebase-rules.json` en Firebase Console → Realtime Database → Reglas → Publicar

---
*Copa Talento 2026 — Titans*
