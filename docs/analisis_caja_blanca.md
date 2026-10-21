# Análisis de caja blanca

## Código analizado

```python
def validar_compra(edad, cuenta_activa, saldo, monto):
    if edad < 18:
        return "Compra no permitida: edad"
    if not cuenta_activa:
        return "Compra no permitida: cuenta"
    if saldo >= monto and monto > 0:
        return "Compra aprobada"
    return "Compra rechazada"
```

## Decisiones y condiciones

| Decisión | Condición | Salida verdadera | Salida falsa / continuación |
|---|---|---|---|
| D1 | `edad < 18` | Rechazo por edad | Evaluar D2 |
| D2 | `not cuenta_activa` | Rechazo por cuenta | Evaluar D3 |
| D3 | `saldo >= monto and monto > 0` | Compra aprobada | Compra rechazada |

Las condiciones simples son `edad < 18`, `not cuenta_activa`, `saldo >= monto` y `monto > 0`. D3 combina las dos últimas con `and`. Por el orden secuencial, D2 y D3 solo se evalúan cuando la edad es al menos 18; D3 solo se evalúa si la cuenta está activa.

## Criterio y mínimo

Se utiliza cobertura de decisiones: cada decisión debe producir al menos una vez un resultado verdadero y uno falso. Para recorrer ambas salidas de D1 y D2 y ambas de D3 hacen falta al menos cuatro ejecuciones: una por rechazo de edad, una por rechazo de cuenta, una aprobación y un rechazo por saldo o monto. No se pueden combinar las salidas de retorno anteriores con las decisiones posteriores porque estas quedan sin ejecutar.

La actividad solicita tres casos. Los siguientes tres cubren las tres salidas principales y el resultado verdadero de D3, pero no alcanzan cobertura completa de decisiones. Debe añadirse el caso de saldo insuficiente señalado abajo para llegar al mínimo de cuatro.

## Tres casos diseñados

| ID | edad | cuenta_activa | saldo | monto | Resultado esperado | Cobertura |
|---|---:|---|---:|---:|---|---|
| CB-01 | 17 | True | 100 | 50 | `Compra no permitida: edad` | D1 verdadero |
| CB-02 | 25 | False | 100 | 50 | `Compra no permitida: cuenta` | D1 falso; D2 verdadero |
| CB-03 | 25 | True | 100 | 50 | `Compra aprobada` | D1 falso; D2 falso; D3 verdadero |

## Ajuste necesario para completar el criterio

| ID adicional | edad | cuenta_activa | saldo | monto | Resultado esperado | Cobertura |
|---|---:|---|---:|---:|---|---|
| CB-04 | 25 | True | 20 | 50 | `Compra rechazada` | D1 falso; D2 falso; D3 falso (saldo menor que monto) |

Con CB-04, las tres decisiones tienen resultados verdaderos y falsos. Esto satisface cobertura de decisiones; no implica cobertura completa de las condiciones simples. Para cobertura de condiciones también habría que probar `monto <= 0` (por ejemplo, edad 25, cuenta activa, saldo 0, monto 0), que hace falsa `monto > 0`.
