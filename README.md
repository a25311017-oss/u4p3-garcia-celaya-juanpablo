# Práctica Final U4P3 – Categorías, Facturas y Reportes SQL

## Descripción del proyecto

Este proyecto consiste en la ampliación de un sistema web desarrollado con Django, en el cual se implementó un módulo de administración de categorías, facturas y reportes SQL, tomando como base el CRUD de servicios realizado anteriormente.

El objetivo principal fue mejorar la organización de la información, relacionar correctamente los datos mediante llaves foráneas y desarrollar consultas SQL que permitan obtener información útil sobre los servicios, las ventas y los clientes.

## Objetivos

- Implementar un sistema de categorías relacionadas con los servicios.
- Crear un módulo para registrar y consultar facturas.
- Administrar los detalles de cada factura.
- Desarrollar seis consultas SQL utilizando diferentes funciones y operaciones.
- Mejorar el rendimiento de las consultas mediante índices.
- Implementar una interfaz web para visualizar los reportes.
- Publicar el proyecto mediante GitHub y Render.

## Tecnologías utilizadas

- **Python:** lenguaje de programación principal.
- **Django:** framework para el desarrollo de la aplicación web.
- **MySQL:** sistema gestor de bases de datos.
- **HTML:** estructura de las páginas web.
- **Tailwind CSS:** diseño y presentación de las interfaces.
- **Git y GitHub:** control de versiones y almacenamiento del código.
- **Render:** alojamiento y despliegue de la aplicación.
- **Aiven:** servicio de base de datos MySQL.

## Funcionalidades implementadas

### 1. Administración de categorías
- Crear y administrar categorías.
- Relacionar los servicios con sus respectivas categorías.
- Migrar la información existente sin perder los datos anteriores.

### 2. Administración de facturas
- Registrar nuevas facturas.
- Asociar facturas con usuarios.
- Agregar varios servicios a una misma factura.
- Registrar cantidades y precios unitarios.
- Consultar el detalle y total de cada factura.

### 3. Reportes SQL

Se desarrollaron seis reportes utilizando consultas SQL escritas manualmente:

| N.º | Reporte | Técnica SQL |
|---|---|---|
| 1 | Ingresos por categoría | SUM() + GROUP BY |
| 2 | Servicios por categoría | COUNT() + GROUP BY + LEFT JOIN |
| 3 | Servicio más barato y más caro | MIN() + MAX() |
| 4 | Servicios que nunca se han facturado | LEFT JOIN + IS NULL |
| 5 | Clientes que gastan más que el promedio | HAVING + AVG() |
| 6 | Ranking de servicios más vendidos por categoría | CTE + RANK() |

Los reportes permiten consultar información de ventas, identificar servicios sin vender, comparar precios y analizar el comportamiento de los clientes.

### 4. Optimización de consultas
Se agregaron índices para mejorar el acceso a los datos y se utilizó `EXPLAIN` para observar los planes de ejecución de MySQL y analizar el uso de los índices.

### 5. Exportación de reportes
Se incorporó la opción de descargar los resultados de los reportes en formato CSV para facilitar su consulta y utilización en otras herramientas.

## Base de datos

El sistema utiliza cinco tablas principales:

- `auth_user`: almacena los usuarios del sistema.
- `core_categoria`: almacena las categorías.
- `core_servicio`: almacena los servicios registrados.
- `core_factura`: almacena las facturas.
- `core_detallefactura`: almacena los servicios, cantidades y precios correspondientes a cada factura.

Las tablas se encuentran relacionadas mediante llaves foráneas para mantener la integridad de la información.

## Instalación y ejecución local

1. Clonar el repositorio:

   ```bash
   git clone URL_DEL_REPOSITORIO
   ```

2. Entrar a la carpeta del proyecto:

   ```bash
   cd NOMBRE_DEL_PROYECTO
   ```

3. Crear y activar el entorno virtual:

   ```bash
   python -m venv venv
   ```

   En Windows PowerShell:

   ```powershell
   .\venv\Scripts\Activate.ps1
   ```

4. Instalar las dependencias:

   ```bash
   pip install -r requirements.txt
   ```

5. Configurar las variables de entorno necesarias para la conexión a MySQL y el funcionamiento de Django.

6. Aplicar las migraciones:

   ```bash
   python manage.py migrate
   ```

7. Crear un superusuario para acceder al panel administrativo:

   ```bash
   python manage.py createsuperuser
   ```

8. Iniciar el servidor:

   ```bash
   python manage.py runserver
   ```

9. Abrir en el navegador:

   ```text
   http://127.0.0.1:8000/
   ```

## Despliegue

El proyecto está preparado para su publicación mediante Render, utilizando GitHub como repositorio de código y MySQL como base de datos.

Para su despliegue se configura la instalación de dependencias, las migraciones de Django, los archivos estáticos y las variables de entorno necesarias.

## Control de versiones

Durante el desarrollo se utilizó Git para registrar los cambios realizados en cada etapa de la práctica, manteniendo un historial de commits que permite identificar las modificaciones e implementaciones del proyecto.

## Autor

**Juan Pablo García Celaya**

- Institución: Universidad Tecnológica de Hermosillo (UTH).
- Carrera: Desarrollo de Software.
- Grupo: DSM 4-1.
- Asignatura: Aplicaciones Web.
- Práctica: Unidad 4 – Práctica Final U4P3.

---

*Proyecto académico desarrollado como parte de las actividades de la Unidad 4 de la asignatura de Aplicaciones Web.*
