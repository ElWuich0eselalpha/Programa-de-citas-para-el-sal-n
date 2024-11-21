# Programa-de-citas-para-el-sal-n
Actividad 3 de certificación de freecodecamp base de datos relacional
# Proyecto de Base de Datos de Salón

Este proyecto es una práctica para crear y gestionar una base de datos para un salón de belleza utilizando PostgreSQL y un script en bash.

## Instrucciones del Proyecto

El objetivo del proyecto es completar las siguientes tareas:

1. Crear una base de datos llamada `salon`.
2. Conectarse a la base de datos y crear las tablas `customers`, `services`, y `appointments`.
3. Asegurandose de que cada tabla tenga una columna de clave primaria que se incremente automáticamente.
4. Establecer las relaciones necesarias entre las tablas mediante claves foráneas.
5. Crear un script en bash (`salon.sh`) para gestionar la interacción con la base de datos y permitir a los usuarios agendar citas.

## Estructura de las Tablas

- **customers**
  - `customer_id`: SERIAL PRIMARY KEY
  - `phone`: VARCHAR UNIQUE
  - `name`: VARCHAR

- **services**
  - `service_id`: SERIAL PRIMARY KEY
  - `name`: VARCHAR

- **appointments**
  - `appointment_id`: SERIAL PRIMARY KEY
  - `customer_id`: INT REFERENCES customers(customer_id)
  - `service_id`: INT REFERENCES services(service_id)
  - `time`: VARCHAR

## Datos Iniciales

Se insertaron los siguientes servicios en la tabla `services`:
- Corte de pelo (`cut`)
- Tinte (`color`)
- Permanente (`perm`)

## Script de Gestión (`salon.sh`)

El script `salon.sh` permite a los usuarios:
1. Ver una lista numerada de los servicios ofrecidos.
2. Seleccionar un servicio.
3. Introducir su número de teléfono para verificar si ya son clientes.
4. Si no son clientes, introducir su nombre y registrarse.
5. Introducir la hora deseada para la cita.
6. Confirmar la cita con un mensaje de éxito.

### Ejecución del Script

Para ejecutar el script, primero asegúrate de que tiene permisos de ejecución:

#bash
-chmod +x salon.sh 

## EJMEMPLO DE SU USO:
1) cut
2) color
3) perm

## El script confirma la cita con un mensaje similar a:
-Te he registrado para un(a) cut a las 10:30, Juan.


