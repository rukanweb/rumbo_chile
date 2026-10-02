# Criterios de valoración de acciones

Reglas para decidir si una acción está a un precio razonable. Las va a usar el módulo
de análisis y alertas (fases 5 y 6). Los umbrales también están en
`app/criterios_valoracion.json`, en un formato que la app puede leer.

**Fuente:** video de YouTube de Franco Martini (@fmartini), educador financiero.
Los umbrales son una **referencia general para el mercado chileno**.

---

## 1. PER: precio sobre utilidad

Precio de la acción ÷ utilidad por acción de los **últimos 12 meses**.
Un PER de 10 significa que pagas 10 años de utilidades. Más bajo suele ser mejor,
aunque hay excepciones. No hay un rango fijo: depende del crecimiento de la empresa.

| PER | Lectura |
|---|---|
| Bajo 10 a 12 | Bueno |
| Entre 12 y 15 | Aceptable |
| Sobre 15 | Empieza a estar cara |

## 2. ROE: rentabilidad sobre el patrimonio

Utilidad ÷ patrimonio. Mide cuánta utilidad genera la empresa con la plata de los
dueños. Más alto es mejor.

| ROE | Lectura |
|---|---|
| Bajo 5 % | Pésimo: rinde menos que un depósito a plazo o la tasa del Banco Central |
| Entre 5 % y 10 % | No compensa el riesgo |
| Entre 10 % y 15 % | Aceptable |
| Sobre 15 % | Buena empresa, compensa totalmente |

## 3. P/VL: precio sobre valor libro

Precio de la acción ÷ patrimonio por acción. Dice cuánto pagas por cada $1 de
patrimonio de la empresa.

| P/VL | Lectura |
|---|---|
| Bajo 1 | Bueno |
| Entre 1 y 2 | Sano, si lo justifica un buen ROE |
| Sobre 2 o 3 | Sobreprecio; puede justificarse con un ROE muy alto |

---

## Cómo se relacionan: P/VL = PER × ROE

Los tres indicadores no son independientes. Con dos de ellos se obtiene el tercero:

> P/VL = PER × ROE  (con el ROE como decimal)

Ejemplo: un PER de 10 y un ROE de 15 % dan un P/VL de 1,5. Esto tiene dos usos:

- **Control de calidad de los datos:** si la fuente entrega los tres y no cuadran,
  alguno está mal o usa periodos distintos.
- **Lectura conjunta:** un P/VL bajo 1 solo es "barato" si el ROE es razonable. Un
  P/VL de 0,6 con un ROE de 3 % implica un PER de 20: no es barata, es una empresa
  que rinde poco.

## Advertencias al aplicar las reglas

Estas reglas son un filtro inicial, no una señal de compra por sí solas.

1. **Empresas cíclicas (commodities, navieras):** el PER engaña en el peak del ciclo.
   Con utilidades extraordinarias, el PER se ve muy bajo justo antes de que caigan.
   Vapores en 2021-2022 es el caso típico. En estas empresas conviene mirar
   utilidades promedio de varios años, no solo los últimos 12 meses.
2. **Bancos (Banco de Chile, BCI):** son el caso donde mejor funcionan P/VL y ROE
   juntos. Es la forma estándar de valorizarlos.
3. **Holdings (Quiñenco):** suelen transarse bajo su valor libro de forma
   permanente (descuento de holding). Un P/VL bajo 1 en un holding no es una
   oportunidad automática.
4. **Utilidad negativa:** el PER no tiene sentido y no se debe calcular.
5. **Acciones de EE. UU. (Racional):** estos umbrales son para Chile. El mercado
   estadounidense transa con PER más altos de forma estructural (el S&P 500 ronda
   20 o más), así que con estos rangos casi todo se vería "caro".
6. **ETF y fondos (IPSA, S&P 500, Nasdaq, CFI):** no aplican. Para ellos, la señal
   de compra es el rebalanceo por bandas.
7. **Umbrales fijos vs. historia propia:** conviene complementar con la comparación
   contra el promedio histórico de la misma empresa. Por ejemplo, el PER actual
   frente a su promedio de 5 años.

## Cómo lo usará la app (fase 5-6)

- Calcular PER, ROE y P/VL de cada acción de la lista de seguimiento.
- Clasificar cada indicador con los rangos de arriba.
- Aplicar las advertencias según el tipo de empresa: cíclica, banco o holding.
- Avisar cuando una acción pase a la zona "bueno" en los tres indicadores
  (o según la regla que definas tú).

Datos necesarios: utilidad de los últimos 12 meses, patrimonio y número de
acciones (de los estados financieros de la CMF), más el precio diario (Yahoo).
