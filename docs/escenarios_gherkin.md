# Escenarios Gherkin

```gherkin
Feature: Inicio de sesión en SauceDemo
  Como usuario de demostración
  Quiero iniciar sesión
  Para acceder al catálogo

  Scenario: Acceso exitoso
    Given que estoy en la página de inicio de sesión de SauceDemo
    When ingreso el usuario "standard_user" y la contraseña "secret_sauce"
    And pulso el botón "Login"
    Then se muestra el catálogo de productos

  Scenario: Rechazo de credenciales incorrectas
    Given que estoy en la página de inicio de sesión de SauceDemo
    When ingreso un usuario y una contraseña no válidos
    And pulso el botón "Login"
    Then permanezco en la página de inicio de sesión
    And se muestra un mensaje indicando que las credenciales no coinciden
```
