# Rizo-Arias-post1-u5
# RetrofitLab - Consumo de API con Retrofit y OkHttp

**Post-Contenido 1 - Unidad 5: Consumo de Servicios y Comunicación con Backend**  
**Asignatura:** Aplicaciones Móviles  
**Carrera:** Ingeniería de Sistemas  
**Universidad de Santander - 2026**

## Descripción del Proyecto

Esta aplicación Android es un cliente HTTP robusto que consume la API pública **JSONPlaceholder** (`https://jsonplaceholder.typicode.com`).  

Se implementa una lista de posts con **paginación simulada**, gestión completa de estados de UI (Loading, Success, Error, Empty) y un **manejo tipado de errores** mediante `sealed class`.

### Tecnologías y Arquitectura utilizadas

- **Arquitectura**: MVVM + Clean Architecture (capas: data / domain / presentation)
- **Networking**: Retrofit 2 + OkHttp 4 + Kotlinx Serialization
- **Interceptors**: Logging (BODY) + Interceptor de headers simulando autenticación
- **Asincronía**: Kotlin Coroutines + `viewModelScope`
- **Gestión de estado**: StateFlow + Jetpack Compose
- **Manejo de errores**: Sealed class `AppError` con mapper desde excepciones
- **UI**: Jetpack Compose + LazyColumn + estados reactivos

## Características implementadas

- Consumo de endpoint `/posts` con parámetros de paginación (`_page` y `_limit`)
- Interceptor de logging que muestra requests y responses completos en Logcat
- Interceptor personalizado que agrega headers (`Accept`, `X-App-Version`)
- Mapeo DTO → Modelo de dominio (con excerpt del body)
- Manejo robusto de errores de red, servidor, no autorizado, no encontrado, etc.
- Estados de UI completos: Loading, Success, Error y Empty
- Paginación manual con botón "Cargar más" (acumula los posts sin reemplazar)
- Reconexión automática (botón Reintentar cuando no hay conexión)

## Requisitos

- Android Studio Hedgehog (2023.1.1) o superior
- JDK 17
- Dispositivo o emulador con Android 8.0+ (API 26)
- Conexión a internet

## Cómo ejecutar el proyecto

1. Clona el repositorio:
   ```bash
   git clone https://github.com/TU_USUARIO/TU_APELLIDO-post1-u5.git
