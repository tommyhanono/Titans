# 🏆 Titans — Stat Trackers

Trackers de estadísticas en vivo para todos los equipos Titans — Básquetbol y Fútbol.

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

## 📚 Tutoriales para entrenadores

Guías paso a paso para usar la app durante un partido, sin tecnicismos.

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
│   │   │   ├── Copa Talento Sub 18/   ✅ Titans Sub-18 (historial completo 2026)
│   │   │   └── Ludos Sub 18/          🆕 Listo para usar
│   │   ├── Sub 16/
│   │   │   └── Copa Talento Sub 16/   🆕 Listo para usar
│   │   ├── Sub 14/
│   │   │   └── Ludos Sub 14/          🆕 Listo para usar
│   │   └── Sub 12/
│   │       └── Copa Talento Sub 12/   🆕 Listo para usar
│   └── Soccer/
│       ├── Sub 14/
│       │   └── Copa Talento Sub 14/   🆕 Listo para usar
│       └── Sub 10/
│           └── Copa Talento Sub 10/   🆕 Listo para usar
└── Mujeres/
    └── Soccer/
        ├── Sub 18/
        │   └── Copa Talento Sub 18/   🆕 Listo para usar
        └── Sub 10/
            └── Copa Talento Sub 10/   🆕 Listo para usar
```

## Cómo configurar un tracker nuevo

1. Abrir el `index.html` del equipo correspondiente
2. Usar **＋** para agregar jugadores (básquet) o editar `DEFAULT_PLAYERS` en `app.js`
3. Para instalarlo como PWA: Safari → Compartir → Agregar a pantalla de inicio

## Notas técnicas

- Cada tracker tiene `localStorage` separado (claves únicas por equipo)
- Service workers con cache names distintos — no interfieren entre sí
- El único tracker con datos históricos es **Basket Sub 18 / Copa Talento Sub 18**

---
*Copa Talento 2026 — Titans*
