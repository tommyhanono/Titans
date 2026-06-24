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

## 📊 Sistema de actividad (basket)

Los 5 trackers de basket (+ los 3 de MBA en el repo [MBA](https://github.com/tommyhanono/MBA)) registran eventos en Firebase Realtime Database automáticamente. El panel de admin muestra toda la actividad en tiempo real.

### Eventos registrados automáticamente

| Evento | Cuándo |
|--------|--------|
| `app_open` | Al cargar cualquier tracker de basket |
| `history_save` | Al guardar un partido al historial |

### Panel de admin

- **URL:** `https://tommyhanono.github.io/Titans/admin/`
- Acceso por contraseña (solo admin)
- Muestra eventos de los 8 trackers: 5 Titans + 3 MBA (Sub 13, 15, 17)
- Filtros por tracker, tipo de evento y búsqueda libre
- Contadores: total eventos, app opens, partidos guardados, trackers activos

### Firebase

- **Proyecto:** `titans-tracker` — Realtime Database
- **Base URL:** `https://titans-tracker-default-rtdb.firebaseio.com`
- **Nodos por tracker:** `titans_copa18`, `titans_ludos18`, `titans_copa16`, `titans_ludos14`, `titans_copa12`
- **Actividad:** `/activity_log` (escritura pública, leída solo desde el admin)
- **Reglas:** públicas para lectura y escritura — los trackers no requieren login

## 📚 Tutoriales para entrenadores

| Tutorial | Link |
|----------|------|
| 🏀 Básquet — Guía del Entrenador | [Ver tutorial](https://tommyhanono.github.io/Titans/Tutorial_Basket_Entrenadores.html) |
| ⚽ Fútbol — Guía del Entrenador | [Ver tutorial](https://tommyhanono.github.io/Titans/Tutorial_Futbol_Entrenadores.html) |

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
