# SIGVC - Sistema Integral de Gestión y Venta de Consumibles (SaaS)

El SIGVC es una plataforma en la nube (SaaS) desarrollada a la medida para centralizar la administración multi-sucursal, automatizar el control de inventarios, agilizar los procesos de venta en mostrador y proporcionar visibilidad financiera exacta sobre la rentabilidad neta real de cada local comercial.

## Características y Beneficios Principales

* Punto de Venta Ultrarrápido: Interfaces responsivas y amigables diseñadas para reducir los tiempos de espera en el mostrador a unos pocos segundos.

* Inventario Autónomo y Blindado: El stock se descuenta de forma automática y en tiempo real al registrar una venta (gestionado directamente mediante Triggers en la base de datos para erradicar el error humano).

* Precisión Financiera de Nivel Bancario: El sistema procesa los valores monetarios en centavos enteros para evitar pérdidas por problemas de redondeo de punto flotante, garantizando que la contabilidad cuadre a la perfección.

* Ganancia Neta Real: Módulo financiero exclusivo para registrar gastos operativos diarios (agua, gas, transporte), restándolos automáticamente de los ingresos para mostrar la utilidad diaria exacta.

* Seguridad por Roles: Interfaces dinámicas que restringen la información financiera a los cajeros y otorgan control de mando absoluto al administrador.

* El "Libro Mayor" Inmutable: Historial de auditoría (Kardex) para rastrear cada entrada, salida o merma y prevenir fugas de capital.

## Arquitectura y Stack Tecnológico

Este proyecto fue construido utilizando la metodología de Vertical Slicing (desarrollo por módulos) y una arquitectura Modelo-Vista-Controlador (MVC), garantizando escalabilidad y un alto rendimiento.

Backend:
* C#
* ASP.NET Core 8 MVC
* Entity Framework Core (Database First / Scaffolding)

Frontend:
* HTML5 / CSS3 / JavaScript
* Bootstrap (Personalizado con paleta corporativa "Índigo Minimalista")
* Diseño 100% Responsivo (Mobile-First)

Base de Datos:
* PostgreSQL (Diseño Relacional altamente normalizado en 3NF)
* Uso intensivo de lógica en base de datos (Triggers y Functions para automatización).

## Configuración e Instalación (Entorno de Desarrollo)

### Prerrequisitos

* .NET 8.0 SDK
* PostgreSQL (v14 o superior)
* Visual Studio 2022 (o IDE compatible)

### Pasos para ejecutar el proyecto

1. Clonar el repositorio:
   ```bash
   git clone https://github.com/tu-usuario/SIGVC.git
   ```

2. Configurar la Base de Datos:
   * Restaura el script de la base de datos `sigvc.sql` en tu servidor PostgreSQL para crear las 13 tablas, relaciones y triggers.

3. Configurar la Cadena de Conexión:
   * Abre el archivo `appsettings.json` en la raíz del proyecto web.
   * Actualiza el bloque de conexión con tus credenciales locales:
   ```json
   "ConnectionStrings": {
     "ConexionPostgres": "Host=localhost;Database=sigvc;Username=postgres;Password=TU_CONTRASEÑA"
   }
   ```

4. Restaurar Paquetes NuGet:
   Abre la Consola del Administrador de Paquetes en Visual Studio y ejecuta:
   ```powershell
   Update-Package -reinstall
   ```
   *(Asegúrate de tener instalados `Npgsql.EntityFrameworkCore.PostgreSQL` y `Microsoft.EntityFrameworkCore.Tools`).*

5. Compilar y Ejecutar:
   Presiona `F5` en Visual Studio para iniciar el proyecto en IIS Express o Kestrel.

## Despliegue (Producción)

El proyecto está optimizado para ser hospedado en IIS (Internet Information Services) de Windows utilizando el ASP.NET Core Hosting Bundle, o en cualquier servidor de aplicaciones en la nube (Azure, AWS) que soporte .NET 8.

Desarrollado con enfoque en la rentabilidad, la automatización y el control absoluto del negocio.
