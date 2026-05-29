# 🏆 Titans — Stat Trackers

Trackers de estadísticas en vivo para todos los equipos Titans — Básquetbol y Fútbol.

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

## GitHub Pages URLs

| Equipo | URL |
|--------|-----|
| 🏀 Basket Sub 18 — Copa Talento | `https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2018/Copa%20Talento%20Sub%2018/` |
| 🏀 Basket Sub 18 — Ludos | `https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2018/Ludos%20Sub%2018/` |
| 🏀 Basket Sub 16 — Copa Talento | `https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2016/Copa%20Talento%20Sub%2016/` |
| 🏀 Basket Sub 14 — Ludos | `https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2014/Ludos%20Sub%2014/` |
| 🏀 Basket Sub 12 — Copa Talento | `https://tommyhanono.github.io/Titans/Hombres/Basket/Sub%2012/Copa%20Talento%20Sub%2012/` |
| ⚽ Fútbol Hombres Sub 14 | `https://tommyhanono.github.io/Titans/Hombres/Soccer/Sub%2014/Copa%20Talento%20Sub%2014/` |
| ⚽ Fútbol Hombres Sub 10 | `https://tommyhanono.github.io/Titans/Hombres/Soccer/Sub%2010/Copa%20Talento%20Sub%2010/` |
| ⚽ Fútbol Mujeres Sub 18 | `https://tommyhanono.github.io/Titans/Mujeres/Soccer/Sub%2018/Copa%20Talento%20Sub%2018/` |
| ⚽ Fútbol Mujeres Sub 10 | `https://tommyhanono.github.io/Titans/Mujeres/Soccer/Sub%2010/Copa%20Talento%20Sub%2010/` |

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
