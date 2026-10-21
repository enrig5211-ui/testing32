# Casos de prueba de caja negra

Aplicación: https://www.saucedemo.com/  
Fecha de ejecución: 20/10/2026  
Ambiente: navegador de escritorio; aplicación de demostración.

## TC-01 - Inicio de sesión con credenciales válidas
- **Objetivo:** Acceder al catálogo con el usuario estándar.
- **Precondiciones:** Página de login disponible; usuario estándar.
- **Datos:** standard_user / secret_sauce
- **Pasos:** 1) Ingresar usuario y contraseña. 2) Pulsar Login.
- **Resultado esperado:** Abrir el catálogo /inventory.html y mostrar Products.
- **Resultado observado:** Se abrió /inventory.html y se mostró la lista de productos. PASS.
- **Estado:** PASS
- **Evidencia observable:** Catálogo visible; URL /inventory.html.

## TC-02 - Rechazo de credenciales inválidas
- **Objetivo:** Impedir el acceso con credenciales que no pertenecen a un usuario habilitado.
- **Precondiciones:** Página de login visible y sesión cerrada.
- **Datos:** invalid_user / wrong_password
- **Pasos:** 1) Ingresar credenciales no válidas. 2) Pulsar Login.
- **Resultado esperado:** Permanecer en login y mostrar un mensaje de error.
- **Resultado observado:** Permaneció en login y mostró “Epic sadface: Username and password do not match any user in this service”. PASS.
- **Estado:** PASS
- **Evidencia observable:** URL /; mensaje de error visible.

## TC-03 - Agregar un producto al carrito
- **Objetivo:** Confirmar que el catálogo permite añadir un producto.
- **Precondiciones:** Sesión de standard_user; catálogo visible; carrito vacío.
- **Datos:** Sauce Labs Backpack, $29.99
- **Pasos:** 1) Pulsar Add to cart en Sauce Labs Backpack. 2) Abrir el carrito.
- **Resultado esperado:** El indicador del carrito muestra 1; el producto y cantidad 1 aparecen en Your Cart.
- **Resultado observado:** El indicador mostró 1 items y el carrito listó Sauce Labs Backpack con cantidad 1. PASS.
- **Estado:** PASS
- **Evidencia observable:** URL /cart.html; producto y cantidad visibles.

## TC-04 - Quitar un producto del carrito
- **Objetivo:** Confirmar que el producto puede retirarse antes de la compra.
- **Precondiciones:** Sesión de standard_user; Sauce Labs Backpack agregado.
- **Datos:** Sauce Labs Backpack
- **Pasos:** 1) Pulsar Remove en el producto agregado.
- **Resultado esperado:** El indicador vuelve a vacío y el producto deja de estar en el carrito.
- **Resultado observado:** El indicador mostró Cart, empty; el control cambió a Add to cart. PASS.
- **Estado:** PASS
- **Evidencia observable:** URL /inventory.html; carrito vacío.

## TC-05 - Completar checkout de demostración
- **Objetivo:** Verificar el flujo funcional desde el carrito hasta la confirmación final.
- **Precondiciones:** Sesión de standard_user; un producto agregado.
- **Datos:** Sauce Labs Backpack; nombre Jose; apellido Tester; código 00000. Datos ficticios de prueba.
- **Pasos:** 1) Abrir carrito y Checkout. 2) Completar First Name, Last Name y Zip/Postal Code. 3) Pulsar Continue. 4) Revisar resumen y pulsar Finish.
- **Resultado esperado:** Mostrar Checkout: Complete!, “Thank you for your order!” y carrito vacío.
- **Resultado observado:** Se mostró Checkout: Complete!, “Thank you for your order!” y el carrito quedó vacío. El total mostrado fue $32.39. PASS.
- **Estado:** PASS
- **Evidencia observable:** URL /checkout-complete.html; confirmación y carrito vacío. Flujo de demostración, sin transacción real.
