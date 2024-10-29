# Reporte de Vulnerabilidades - GPSMapAppSAB

**Fecha de análisis**: 29/10/2024  
**Puntaje de seguridad**: 44/100  
**Calificación**: C

---

## Vulnerabilidades Identificadas

### 1. Vulnerabilidad de Ejecución - Severidad Alta
- **Descripción**: Se detecta vulnerabilidad **StrandHogg 2.0** activa en las siguientes actividades:
    - `.SplashActivity`
    - `.MainActivity`
- **Recomendación**: Proteger las actividades con controles adicionales y realizar pruebas de mitigación para prevenir ataques de escalamiento de privilegios.

### 2. Permiso de Respaldos - Severidad Media
- **Descripción**: La aplicación permite respaldo de datos en tiempo de ejecución, lo cual representa un riesgo en caso de ataques que aprovechen respaldos de datos sensibles.
- **Recomendación**: Deshabilitar el respaldo de datos sensibles o implementar un cifrado fuerte en los datos de respaldo.

### 3. Permisos en Tiempo de Ejecución y Uso de APIs
- **Acceso a Ubicación**: Activo en tiempo de ejecución.
    - **Recomendación**: Verificar el uso y la necesidad del permiso de ubicación.
- **Permisos de Red**: Utiliza conexión a internet con transmisión de datos sensibles.
    - **Recomendación**: Revisar los logs y asegurar que se empleen protocolos seguros como HTTPS en lugar de HTTP.
- **Acceso a Cámara y Almacenamiento**: No se detectaron permisos para acceder a cámara o almacenamiento.

### 4. Comunicación con Servidores Externos - Severidad Media
- **Descripción**: Se detectaron conexiones salientes hacia servidores externos.
- **Recomendación**: Revisar las conexiones externas para prevenir fugas de datos y posibles accesos no autorizados.

---

## Resumen de Riesgos

| Severidad | Cantidad |
| --------- | -------- |
| Alta      | 2        |
| Media     | 2        |
| Info      | 0        |
| Segura    | 1        |

---

## Recomendaciones Generales

1. Implementar controles adicionales en permisos críticos como el acceso a la ubicación.
2. Asegurar el uso de **HTTPS** para todas las comunicaciones de red.
3. Revisar los permisos y las conexiones de red para minimizar posibles fugas de datos y prevenir accesos no autorizados.
4. Validar que las actividades vulnerables estén protegidas y aseguradas contra ataques conocidos como StrandHogg 2.0.

---

**Generado por**: Mobile Security Framework (MobSF) v4.0.7  
**© 2024** - Ajin Abraham | OpenSecurity

---

