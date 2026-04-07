# Post-Contenido 1 - Unidad 5  
## Aplicaciones Móviles - Ingeniería de Sistemas

**Proyecto:** RetrofitLab  
**Estudiante:** Miguel Angel Rizo Arias  
**Repositorio:** `RIZO-post1-u5`

---
## Capturas de pantalla

### 1. Pantalla de carga (Loading)
![Loading](screenshots/loading.png)

### 2. Lista de posts cargada correctamente (Success)
![Success](screenshots/success.png)

### 3. Manejo de error de red (Error) + botón Reintentar
![Error](screenshots/error.png)

## Descripción del Flujo Implementado

Esta aplicación es un cliente HTTP desarrollado en Android con Jetpack Compose que consume la API pública **JSONPlaceholder** (`https://jsonplaceholder.typicode.com`).

**Flujo principal implementado:**

1. Al iniciar la aplicación se muestra el estado **Loading** mientras se realiza la petición a la API.
2. Una vez cargados los datos, se presenta la lista de posts usando `LazyColumn`.
3. El usuario puede presionar el botón **"Cargar más"** para obtener la siguiente página de posts. Los nuevos posts se agregan al final de la lista (paginación acumulativa).
4. Si no hay conexión a internet, se muestra el estado **Error** con un mensaje claro y un botón de **"Reintentar"**.
5. Todos los estados de la interfaz (Loading, Success, Error, Empty) se manejan de forma reactiva mediante `StateFlow`.
6. Se utiliza `HttpLoggingInterceptor` para visualizar en Logcat todas las solicitudes y respuestas HTTP (incluyendo headers y body).

**Componentes clave implementados:**
- Retrofit + OkHttp con interceptors (logging y simulación de autenticación)
- Kotlinx Serialization para DTOs y mapeo a modelo de dominio
- Sealed class `AppError` para manejo tipado y amigable de errores
- Arquitectura MVVM con ViewModel y StateFlow
- Jetpack Compose para la interfaz (Scaffold, LazyColumn y gestión de estados)

---

## Requisitos

- Android Studio Hedgehog (2023.1.1) o superior
- JDK 17
- Dispositivo físico con Android 8.0+ o emulador (API 26+)
- Conexión a internet para consumir la API

## Instrucciones de Configuración y Ejecución

