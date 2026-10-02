# Rumbo Chile

Fork de [danidm98/rumbo](https://github.com/danidm98/rumbo) (MIT) adaptado a Chile.
Panel local de patrimonio: Python + Flask, panel en HTML/JS sin librerías.

- Moneda base: `BASE = "CLP"` en `app/motor.py`. Todo se calcula y se muestra en esa moneda.
- Plataformas del dueño: Zesty (Bolsa de Santiago, `.SN`), Racional (EE. UU., USD),
  Sunix (cripto) y cuentas remuneradas (saldos manuales).
- Se trabaja por fases, con una rama y un pull request por fase. Commits en español.
- Criterios para analizar acciones (PER, ROE, P/VL y advertencias):
  `docs/conocimiento/criterios-valoracion.md`, con los umbrales en `app/criterios_valoracion.json`.
  Úsalos al analizar empresas o al construir el módulo de valoración.
