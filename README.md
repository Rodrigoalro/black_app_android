# SIGVC - Sistema Integral de Gestión y Venta de Consumibles (Cliente Android)

El SIGVC es una plataforma en la nube (SaaS) desarrollada a la medida para centralizar la administración multi-sucursal, automatizar el control de inventarios y agilizar los procesos de venta. Este repositorio contiene el frontend móvil desarrollado para dispositivos Android, diseñado para operar como Punto de Venta (POS) en mostrador y panel de control administrativo.

## Características y Beneficios Principales

* Punto de Venta Ágil: Interfaz nativa optimizada para reducir los tiempos de espera en el mostrador a unos pocos segundos, permitiendo cobros rápidos mediante un catálogo táctil.

* Sincronización en Tiempo Real: Conexión directa mediante API REST al backend principal, garantizando que el inventario se descuente de forma automática al registrar una venta.

* Seguridad por Roles: Interfaces dinámicas que restringen la información financiera confidencial a los cajeros y otorgan control de mando y reportes de rentabilidad al administrador.

* Diseño Ergonomico: Interfaz construida bajo el estándar Material Design y la paleta corporativa "Índigo Minimalista", previniendo la fatiga visual en turnos largos.

## Stack Tecnológico (Frontend Móvil)

Este proyecto móvil está diseñado para consumir la API Web (construida en ASP.NET Core 8) y conectarse a la base de datos central en PostgreSQL.

* Entorno de Desarrollo: Android Studio
* Lenguaje: Kotlin / Java
* Arquitectura Sugerida: MVVM (Model-View-ViewModel)
* Interfaz de Usuario: XML / Material Design Components
* Consumo de API: Retrofit / OkHttp (para comunicación con el backend en C#)

## Configuración e Instalación (Entorno de Desarrollo)

### Prerrequisitos

* Android Studio (versión más reciente recomendada Iguana o superior)
* Android SDK (API Level 24 o superior)
* Dispositivo físico Android o Emulador configurado (AVD)
* Acceso local o remoto a la API Web del SIGVC ejecutándose en IIS/Kestrel.

### Pasos para ejecutar el proyecto

1. Clonar el repositorio:
   git clone https://github.com/tu-usuario/SIGVC-Android.git

2. Abrir en Android Studio:
   * Inicia Android Studio.
   * Selecciona "Open" y navega hasta la carpeta del proyecto clonado.
   * Espera a que Gradle sincronice todas las dependencias del proyecto.

3. Configurar la conexión a la API:
   * Localiza el archivo de configuración de red (usualmente un archivo de constantes o `build.gradle`).
   * Actualiza la URL base de la API para que apunte a tu servidor local de .NET o a tu entorno de producción. Por ejemplo: `http://10.0.2.2:5000/api/` (si usas el emulador local).

4. Compilar y Ejecutar:
   * Selecciona tu dispositivo físico conectado o tu emulador en la barra superior.
   * Presiona el botón "Run" (Shift + F10) para compilar el APK e instalarlo en el dispositivo.

## Notas Adicionales

El backend de este proyecto (API y Base de Datos PostgreSQL) debe estar en ejecución para que la aplicación móvil pueda autenticar usuarios, cargar el catálogo de productos y registrar ventas.
