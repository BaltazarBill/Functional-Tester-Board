# PPS - Sistema Automatizado de Testeo de Placas Electrónicas

Proyecto desarrollado en el marco de las **Prácticas Profesionales Supervisadas (PPS)** de la carrera de **Ingeniería Electrónica** de la Universidad Tecnológica Nacional - Facultad Regional Paraná.

El objetivo del proyecto es diseñar e implementar un sistema automatizado para el ensayo funcional de placas electrónicas, integrando hardware, firmware, una interfaz mecánica de testeo y software de supervisión.

---

## Objetivo del proyecto

Desarrollar un sistema capaz de realizar ensayos eléctricos y funcionales sobre placas electrónicas mediante una plataforma de testeo dedicada.

El sistema está diseñado para:

- Detectar y acceder a puntos de prueba del PCB.
- Medir tensiones de entrada y salida.
- Verificar condiciones eléctricas de funcionamiento.
- Asistir en procesos de calibración.
- Ejecutar ensayos sobre fusibles programables.
- Automatizar secuencias de prueba.
- Comunicar resultados hacia un sistema externo.
- Generar resultados de tipo **Pasa / No Pasa**.
- Registrar y exportar los resultados de los ensayos.

---

## Arquitectura general

El sistema se divide en distintos subsistemas:

```text
┌──────────────────────┐
│    PCB bajo prueba   │
└──────────┬───────────┘
           │
        Pogo Pins
           │
┌──────────▼───────────┐
│  Fixture / Test Jig  │
└──────────┬───────────┘
           │
┌──────────▼───────────┐
│   Tester Mainboard   │
│     ATmega1280       │
│                      │
│ - ADC                │
│ - Multiplexación     │
│ - Acondicionamiento  │
│ - Control            │
└──────────┬───────────┘
           │ UART
┌──────────▼───────────┐
│   Software de PC     │
│                      │
│ - Monitoreo          │
│ - Debug              │
│ - Registro           │
│ - Reportes           │
└──────────────────────┘
