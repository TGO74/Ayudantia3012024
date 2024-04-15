El README.md para la Ayudantía N°3 podría lucir así:

---

# Sistema de Gestión de Salas y Clientes de CineIndep

## Descripción del Problema

En CineIndep se necesita un sistema que permita gestionar las salas y clientes de un día. Se considera lo siguiente:

- Un cliente puede tener muchas entradas para múltiples salas de cine. Cada cliente se caracteriza por tener nombre, rut y correo electrónico.
- Una entrada puede ser VIP, normal o de IMAX, asociada a una sala de cine.
- Cada sala de cine tiene una cantidad de asientos, indicando su disponibilidad.
- Cada entrada está registrada en una sala. A cada entrada se le puede aplicar una promoción, con porcentaje de descuento y fecha de vencimiento para compras en CineIndep.

## Requerimientos

- Agregar cliente.
- Vender una entrada a un cliente.
- Reversar venta de una entrada.
- Ver el número de asientos de una sala y la cantidad vendida.
- Ver el número de entradas que tiene un cliente.
- Permitir el ingreso de un cliente a una sala si tiene entrada.

## Funcionalidades

1. Agregar un cliente al sistema con nombre, rut y correo electrónico.
2. Vender una entrada a un cliente, seleccionando el tipo de entrada y la sala.
3. Reversar una venta de entrada, devolviendo la entrada a la disponibilidad de la sala.
4. Verificar la disponibilidad de asientos en una sala y la cantidad de entradas vendidas.
5. Verificar el número de entradas que tiene un cliente.
6. Permitir el ingreso de un cliente a una sala si tiene una entrada válida.

## Diagrama de Clases

```
[Incluir aquí el diagrama de clases.]
```

## Clases, Atributos y Métodos

### Clase Cliente

- **Atributos:**
  - nombre: String
  - rut: String
  - correoElectronico: String

#### Métodos



### Clase Entrada

- **Atributos:**
  - tipo: Enum (VIP, Normal, IMAX)
  - sala: SalaCine
  - promocion: Promocion

#### Métodos

1. `venderEntrada(cliente: Cliente, tipo: Enum, sala: SalaCine): void`: Vende una entrada a un cliente.

## Enumeración TipoEntrada

El enum `TipoEntrada` define los tipos de entrada que pueden adquirirse para una sala de cine.

### Valores

- **VIP**: Entrada VIP.
- **NORMAL**: Entrada normal.
- **MAX**: Entrada para proyección IMAX.


### Clase SalaCine

- **Atributos:**
  - numeroAsientos: int
  - cantidadVendida: int

#### Métodos

1. `verDisponibilidad(): void`: Muestra la disponibilidad de asientos en la sala y la cantidad de entradas vendidas.

## Clase Asiento

La clase `Asiento` permite gestionar los asientos de una sala de cine.

### Atributos

- **asientoId**: Entero que representa el identificador único del asiento.
- **estado**: Enumeración del tipo `EstadoAsiento`, que puede ser VENDIDO o DISPONIBLE.

### Métodos

- **Constructor**: Permite inicializar un objeto de la clase `Asiento` con un identificador y un estado.
- **Getters y Setters**: Para acceder y modificar los atributos del asiento.
- **toString()**: Sobrescrito para imprimir información legible sobre el asiento.

## Enumeración EstadoAsiento

El enum `EstadoAsiento` define los posibles estados de un asiento en la sala de cine.

### Valores

- **VENDIDO**: Indica que el asiento ha sido vendido.
- **DISPONIBLE**: Indica que el asiento está disponible para la venta.
  

### Clase Promoción

- **Atributos:**
  - porcentajeDescuento: double
  - fechaVencimiento: LocalDate

### Clase CineIndep

- **Métodos:**
- `agregarCliente(nombre: String, rut: String, correoElectronico: String): void`: Agrega un cliente al sistema.
  - `ingresarClienteSala(cliente: Cliente, entrada: Entrada): boolean`: Ingresa cliente a una sala

## Relaciones entre Clases

- La clase Cliente tiene una relación de asociación con la clase Entrada.
- La clase Entrada tiene una relación de composición con la clase SalaCine.
- La clase Entrada tiene una relación de composición con la clase Promocion.
- La clase CineIndep tiene una relación de dependencia con la clase Cliente y la clase SalaCine.

---

Este README.md proporciona una estructura clara para el sistema de gestión de salas y clientes de CineIndep, incluyendo una descripción del problema, requerimientos, funcionalidades, diagrama de clases, y detalles de las clases, atributos y métodos, así como las relaciones entre ellas.
