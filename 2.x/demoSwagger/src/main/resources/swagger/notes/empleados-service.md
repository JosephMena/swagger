## Implementation Notes

### Acerca de la funcionalidad expuesta
___
La funcionalidad permite realizar dos validaciones de monto límite del cliente en una operación monetaria:

* **Validación límite por operación** : Se encarga de validar que el monto a transaccionar no sea mayor al monto límite permitido del horario actual, en caso de no existir límite permitido para el horario actual validará con un monto límite por defecto.

* **Validación limite por día** : Se encarga de validar que la sumatoria del monto acumulado de la operación y el monto a transaccionar, no sea mayor al monto límite permitido por día.

### URI de acceso a la API
| Metodo | URI |
|-------------|-------------|
|POST|/cross-channel/transaction-authorization/v1/transaction-limits/verify|
___

### Precondiciones para el consumo de esta versión de la API
Tomar en cuenta las siguientes consideraciones:
1. Debe existir configuración de limites del cliente o del banco.
___

### Headers Requeridos
| Header | Ejemplo |
|-------------|-------------|
|Content-Type|application/json|
|Request-ID|689db112-bfae-487f-abeb-0996539162c9|
|app-code|HK|
|caller-name|HK|
|client-code|HK|
___

### Query Parameters válidos en esta versión de la API
No aplica.
___

### Usos válidos de Query Parameters
No aplica.
___

### Variantes válidas del Payload (Cuerpo del mesaje)
No aplica.
___

### Lista de Valores usadas en esta versión de la API
A continuación se listan aquellos campos que tienen mas de un valor posible. Para poder acceder a la lista de valores completa por favor contactar a la mesa de gobierno.

| Atributo |
|--------|
| transactionType.code |
| currency.code |
| customer.segment.code |
___

### Código de errores del Servicio
| Código | Descripción |
|--------|-------------|
| TL0001 | Error de conexión con base de datos. |
| TL0002 | No existe la configuración del límite del banco. |
| TL0003 | Datos incorrectos.   |
| TL0004 | Error inesperado en el servicio de límites.  |
