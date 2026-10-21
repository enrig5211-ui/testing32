# Casos de prueba de caja negra

Aplicación: [SauceDemo](https://www.saucedemo.com/)  
Fecha de ejecución: 20/10/2026  
Ambiente: navegador de escritorio; sitio de demostración.

## TC-01 - Inicio de sesión con credenciales válidas

### Diseño del caso

| Campo | Detalle |
|---|---|
| ID del TC | TC-01 |
| Título | Inicio de sesión con credenciales válidas |
| Prioridad | Alta |
| Tipo | Funcional positiva |
| Módulo | Inicio de sesión |
| Ambiente | SauceDemo |
| Objetivo | Comprobar que un usuario de demostración válido accede al catálogo. |
| Estado inicial | Página de inicio de sesión disponible. |
| Usuario / permisos | standard_user, habilitado para la demostración. |
| Configuración | Navegador de escritorio; conexión a SauceDemo. |

#### Datos de prueba

| Dato | Valor | Origen | Observación |
|---|---|---|---|
| Datos utilizados | Usuario: standard_user; contraseña: secret_sauce. | Preparados para la prueba | Ver detalle del caso |

#### Pasos y resultados esperados

| # | Paso / acción | Resultado esperado |
|---:|---|---|
| 1 | Ingresar standard_user en Username. | Acción completada en la interfaz. |
| 2 | Ingresar secret_sauce en Password. | Acción completada en la interfaz. |
| 3 | Pulsar Login. | Se muestra el catálogo y la URL termina en /inventory.html. |
| Criterio de éxito | Se muestra el catálogo y la URL termina en /inventory.html. |

### Ejecución del caso

| Campo | Resultado |
|---|---|
| Ejecutado por | Jose Enrqiue Maita Guzman |
| Fecha / hora | 20/10/2026 / no registrada |
| Ambiente / versión | Windows, navegador de escritorio / no aplica |
| Estado de ejecución | PASS |
| Resultado observado | Se abrió /inventory.html y se mostró la lista de productos. |
| Comparación | Coincide con el resultado esperado. |

#### Registro de ejecución

| # | Paso ejecutado | Resultado observado | Estado |
|---:|---|---|---|
| 1 | Ingresar standard_user en Username. | Acción realizada; el flujo continuó. | PASS |
| 2 | Ingresar secret_sauce en Password. | Acción realizada; el flujo continuó. | PASS |
| 3 | Pulsar Login. | Se abrió /inventory.html y se mostró la lista de productos. | PASS |

#### Evidencia y cierre

| Campo | Detalle |
|---|---|
| Tipo | Estado visible de la interfaz |
| Referencia | TC-01 - SauceDemo |
| Evidencia | Estado visible en /inventory.html; Products y catálogo visibles. |
| Desviación encontrada | Ninguna. |
| Referencia del defecto | N/A - no se encontró defecto reproducible. |
| Observaciones | Inicio con usuario público de pruebas. |

## TC-02 - Rechazo de credenciales inválidas

### Diseño del caso

| Campo | Detalle |
|---|---|
| ID del TC | TC-02 |
| Título | Rechazo de credenciales inválidas |
| Prioridad | Media |
| Tipo | Funcional negativa |
| Módulo | Inicio de sesión |
| Ambiente | SauceDemo |
| Objetivo | Verificar que se impide el acceso con credenciales inválidas. |
| Estado inicial | Página de login visible; sin sesión abierta. |
| Usuario / permisos | Sin autenticación. |
| Configuración | Navegador de escritorio; conexión a SauceDemo. |

#### Datos de prueba

| Dato | Valor | Origen | Observación |
|---|---|---|---|
| Datos utilizados | Usuario: invalid_user; contraseña: wrong_password. | Preparados para la prueba | Ver detalle del caso |

#### Pasos y resultados esperados

| # | Paso / acción | Resultado esperado |
|---:|---|---|
| 1 | Ingresar invalid_user. | Acción completada en la interfaz. |
| 2 | Ingresar wrong_password. | Acción completada en la interfaz. |
| 3 | Pulsar Login. | Permanece en login y aparece mensaje de error. |
| Criterio de éxito | Permanece en login y aparece mensaje de error. |

### Ejecución del caso

| Campo | Resultado |
|---|---|
| Ejecutado por | Jose Enrqiue Maita Guzman |
| Fecha / hora | 20/10/2026 / no registrada |
| Ambiente / versión | Windows, navegador de escritorio / no aplica |
| Estado de ejecución | PASS |
| Resultado observado | Permaneció en login y mostró el mensaje de credenciales no coincidentes. |
| Comparación | Coincide con el resultado esperado. |

#### Registro de ejecución

| # | Paso ejecutado | Resultado observado | Estado |
|---:|---|---|---|
| 1 | Ingresar invalid_user. | Acción realizada; el flujo continuó. | PASS |
| 2 | Ingresar wrong_password. | Acción realizada; el flujo continuó. | PASS |
| 3 | Pulsar Login. | Permaneció en login y mostró el mensaje de credenciales no coincidentes. | PASS |

#### Evidencia y cierre

| Campo | Detalle |
|---|---|
| Tipo | Estado visible de la interfaz |
| Referencia | TC-02 - SauceDemo |
| Evidencia | URL / y mensaje de error visibles luego de Login. |
| Desviación encontrada | Ninguna. |
| Referencia del defecto | N/A - no se encontró defecto reproducible. |
| Observaciones | La contraseña se mostró enmascarada. |

## TC-03 - Agregar producto al carrito

### Diseño del caso

| Campo | Detalle |
|---|---|
| ID del TC | TC-03 |
| Título | Agregar producto al carrito |
| Prioridad | Alta |
| Tipo | Funcional positiva |
| Módulo | Catálogo y carrito |
| Ambiente | SauceDemo |
| Objetivo | Comprobar que un producto se agrega y aparece con cantidad correcta. |
| Estado inicial | Sesión iniciada; catálogo disponible; carrito vacío. |
| Usuario / permisos | standard_user. |
| Configuración | Navegador de escritorio; producto disponible. |

#### Datos de prueba

| Dato | Valor | Origen | Observación |
|---|---|---|---|
| Datos utilizados | Sauce Labs Backpack, $29.99; cantidad 1. | Preparados para la prueba | Ver detalle del caso |

#### Pasos y resultados esperados

| # | Paso / acción | Resultado esperado |
|---:|---|---|
| 1 | Pulsar Add to cart en Sauce Labs Backpack. | Acción completada en la interfaz. |
| 2 | Abrir el carrito. | El contador muestra 1 y Your Cart lista el producto con cantidad 1. |
| Criterio de éxito | El contador muestra 1 y Your Cart lista el producto con cantidad 1. |

### Ejecución del caso

| Campo | Resultado |
|---|---|
| Ejecutado por | Jose Enrqiue Maita Guzman |
| Fecha / hora | 20/10/2026 / no registrada |
| Ambiente / versión | Windows, navegador de escritorio / no aplica |
| Estado de ejecución | PASS |
| Resultado observado | El contador mostró 1 items y el carrito listó Sauce Labs Backpack, cantidad 1. |
| Comparación | Coincide con el resultado esperado. |

#### Registro de ejecución

| # | Paso ejecutado | Resultado observado | Estado |
|---:|---|---|---|
| 1 | Pulsar Add to cart en Sauce Labs Backpack. | Acción realizada; el flujo continuó. | PASS |
| 2 | Abrir el carrito. | El contador mostró 1 items y el carrito listó Sauce Labs Backpack, cantidad 1. | PASS |

#### Evidencia y cierre

| Campo | Detalle |
|---|---|
| Tipo | Estado visible de la interfaz |
| Referencia | TC-03 - SauceDemo |
| Evidencia | URL /cart.html; nombre y cantidad visibles. |
| Desviación encontrada | Ninguna. |
| Referencia del defecto | N/A - no se encontró defecto reproducible. |
| Observaciones | Producto estándar del catálogo. |

## TC-04 - Quitar producto del carrito

### Diseño del caso

| Campo | Detalle |
|---|---|
| ID del TC | TC-04 |
| Título | Quitar producto del carrito |
| Prioridad | Media |
| Tipo | Funcional positiva |
| Módulo | Catálogo y carrito |
| Ambiente | SauceDemo |
| Objetivo | Comprobar que se puede retirar un producto antes del checkout. |
| Estado inicial | Sesión iniciada; Sauce Labs Backpack agregado. |
| Usuario / permisos | standard_user. |
| Configuración | Navegador de escritorio. |

#### Datos de prueba

| Dato | Valor | Origen | Observación |
|---|---|---|---|
| Datos utilizados | Sauce Labs Backpack; cantidad inicial 1. | Preparados para la prueba | Ver detalle del caso |

#### Pasos y resultados esperados

| # | Paso / acción | Resultado esperado |
|---:|---|---|
| 1 | Pulsar Remove en el producto. | El contador queda vacío y el botón del producto vuelve a Add to cart. |
| Criterio de éxito | El contador queda vacío y el botón del producto vuelve a Add to cart. |

### Ejecución del caso

| Campo | Resultado |
|---|---|
| Ejecutado por | Jose Enrqiue Maita Guzman |
| Fecha / hora | 20/10/2026 / no registrada |
| Ambiente / versión | Windows, navegador de escritorio / no aplica |
| Estado de ejecución | PASS |
| Resultado observado | El contador mostró Cart, empty; el botón volvió a Add to cart. |
| Comparación | Coincide con el resultado esperado. |

#### Registro de ejecución

| # | Paso ejecutado | Resultado observado | Estado |
|---:|---|---|---|
| 1 | Pulsar Remove en el producto. | El contador mostró Cart, empty; el botón volvió a Add to cart. | PASS |

#### Evidencia y cierre

| Campo | Detalle |
|---|---|
| Tipo | Estado visible de la interfaz |
| Referencia | TC-04 - SauceDemo |
| Evidencia | URL /inventory.html; carrito vacío. |
| Desviación encontrada | Ninguna. |
| Referencia del defecto | N/A - no se encontró defecto reproducible. |
| Observaciones | El producto se puede agregar otra vez después. |

## TC-05 - Completar checkout de demostración

### Diseño del caso

| Campo | Detalle |
|---|---|
| ID del TC | TC-05 |
| Título | Completar checkout de demostración |
| Prioridad | Alta |
| Tipo | Flujo funcional |
| Módulo | Carrito y checkout |
| Ambiente | SauceDemo |
| Objetivo | Validar el flujo desde un artículo en carrito hasta la confirmación. |
| Estado inicial | Sesión iniciada; Sauce Labs Backpack agregado. |
| Usuario / permisos | standard_user. |
| Configuración | Checkout simulado de SauceDemo. |

#### Datos de prueba

| Dato | Valor | Origen | Observación |
|---|---|---|---|
| Datos utilizados | Backpack $29.99; Test / Usuario; código 00000; datos ficticios. | Preparados para la prueba | Ver detalle del caso |

#### Pasos y resultados esperados

| # | Paso / acción | Resultado esperado |
|---:|---|---|
| 1 | Abrir carrito y Checkout. | Acción completada en la interfaz. |
| 2 | Completar nombre, apellido y código postal; pulsar Continue. | Acción completada en la interfaz. |
| 3 | Revisar resumen y pulsar Finish. | Se muestra Checkout: Complete!, Thank you for your order! y el carrito vacío. |
| Criterio de éxito | Se muestra Checkout: Complete!, Thank you for your order! y el carrito vacío. |

### Ejecución del caso

| Campo | Resultado |
|---|---|
| Ejecutado por | Jose Enrqiue Maita Guzman |
| Fecha / hora | 20/10/2026 / no registrada |
| Ambiente / versión | Windows, navegador de escritorio / no aplica |
| Estado de ejecución | PASS |
| Resultado observado | Se mostró confirmación final y carrito vacío; total mostrado $32.39. |
| Comparación | Coincide con el resultado esperado. |

#### Registro de ejecución

| # | Paso ejecutado | Resultado observado | Estado |
|---:|---|---|---|
| 1 | Abrir carrito y Checkout. | Acción realizada; el flujo continuó. | PASS |
| 2 | Completar nombre, apellido y código postal; pulsar Continue. | Acción realizada; el flujo continuó. | PASS |
| 3 | Revisar resumen y pulsar Finish. | Se mostró confirmación final y carrito vacío; total mostrado $32.39. | PASS |

#### Evidencia y cierre

| Campo | Detalle |
|---|---|
| Tipo | Estado visible de la interfaz |
| Referencia | TC-05 - SauceDemo |
| Evidencia | URL /checkout-complete.html; confirmación visible. |
| Desviación encontrada | Ninguna. |
| Referencia del defecto | N/A - no se encontró defecto reproducible. |
| Observaciones | Flujo de demostración; no hubo transacción comercial. |

