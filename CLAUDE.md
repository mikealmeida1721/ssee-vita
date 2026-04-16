# SSEE VITA — Sleep Guide

## Qué es este proyecto
App web single-file (`index.html`) de guía de sueño profundo con ciclos biológicos ultradiano de 90 minutos. Desplegada en GitHub Pages (Jekyll). Sin dependencias externas, todo embebido.

## Objetivo actual
Transformar de un motor de síntesis algorítmica básica a una **app comercial de soporte de sueño** con:
- Voz guía angelical en español (Web Speech API — gratuita/offline)
- Sonidos ambientales orgánicos sintetizados (lluvia, bosque, océano, puro)
- Audio mejorado con reverb convolutivo y binaural beats
- UI profesional con 3 pantallas (Setup → Activo → Despertar)

## Arquitectura de audio (3 capas)
1. **Ambiental**: Pink/white noise sintetizado → lluvia / bosque / océano / puro
2. **Frecuencias**: Carrier 75Hz + ISO Modulator (1.5–10Hz según fase) + Binaural beats (200Hz L / 200+beat Hz R) + ConvolverNode reverb
3. **Voz**: Web Speech API, voz ES mejor disponible, pitch 1.15, rate 0.75

## Ciclo de sueño (90min = 5400s)
| Fase | cyclePos | ISO Freq | Nombre |
|------|----------|----------|--------|
| Inducción | 0–20% | 10→6 Hz | Alpha→Theta |
| Sueño profundo | 20–70% | 1.5 Hz | Delta |
| REM/Ligero | 70–100% | 6→9 Hz | Theta |
| Rampa despertar | diff < 3600s | 12→20 Hz | Beta |

## Script narrativo (español, voz angelical)
- t=0.5s: Bienvenida y respiración
- t=100s: Visualización campo de luz
- t=240s: Soltar pensamientos
- t=480s: Flotando entre mundos
- t=780s: Descanso profundo
- wake-60min: Amanecer y regreso suave
- wake-15min: Preparar despertar
- wake-2min: Buenos días

## Archivo único
- `/home/user/ssee-vita/index.html` — toda la app (HTML + CSS + JS embebidos)

## Branch de trabajo
`claude/review-audio-frontend-4gtT5`

## Paleta de colores
- Fondo: `#080810`
- Accent violeta: `#7c6ee0`
- Accent teal: `#00d4aa`
- Surface: `rgba(255,255,255,0.04)`
- Border: `rgba(255,255,255,0.08)`

## Estado del desarrollo
- [x] CLAUDE.md creado
- [ ] Reescritura completa de index.html (UI + audio + voz)
- [ ] Commit y push a branch
