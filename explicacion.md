# 01-HU Comprensión del Problema para la App de Gestión de Vuelos

## Explicación General  
Las aerolíneas enfrentan múltiples desafíos en la gestión y control de vuelos debido a la falta de un sistema móvil eficiente. Actualmente, los pasajeros, el personal de aeropuertos y la tripulación dependen de sistemas desactualizados y canales de comunicación fragmentados, lo que genera demoras, desinformación y una experiencia deficiente para los usuarios.  

La aplicación móvil propuesta permitirá **centralizar la información en tiempo real** para mejorar la eficiencia operativa y la experiencia del pasajero. Entre sus funciones clave se encuentran el seguimiento del estado de los vuelos, la recepción de notificaciones automáticas sobre cambios en el itinerario, la gestión de check-in y tarjetas de embarque digitales, la comunicación directa entre aerolínea y usuarios, y la integración con servicios aeroportuarios.  

---

## Comportamiento a Nivel de Base de Datos  
El siguiente **modelo de base de datos** soporta la gestión de vuelos, permitiendo la administración de información clave como pasajeros, vuelos, reservas y notificaciones en tiempo real:

📌 **Modelo de Base de Datos**  
![Modelo de Base de Datos](/recursos-adicionales/modelo_DB_vuelos.png)

---

## Comportamiento a Nivel de Modelo Relacional  
El modelo relacional define las entidades y relaciones necesarias para la gestión eficiente de los vuelos y pasajeros.  

### **Entidades Principales:**  
- **Pasajero**: ID, nombre, correo, teléfono.  
- **Vuelo**: ID, número de vuelo, origen, destino, fecha, hora de salida y llegada, estado.  
- **Reserva**: ID, pasajero, vuelo, asiento, estado de reserva.  
- **Notificación**: ID, pasajero, mensaje, tipo, fecha de envío.  
- **Tripulación**: ID, vuelo asignado, rol, estado.  
- **Puerta_Embarque**: ID, vuelo asignado, terminal, número de puerta.  

### **Relaciones Clave:**  
- Un **pasajero** puede tener múltiples **reservas**.  
- Un **vuelo** puede tener múltiples **reservas** y **notificaciones** asociadas.  
- Un **vuelo** tiene asignada una **puerta de embarque**.  
- Un **vuelo** tiene asignada una **tripulación** específica.  

📌 **Modelo Relacional**  
![Modelo Relacional](/recursos-adicionales/MER_vuelos.png)

---

## Comportamiento a Nivel de Casos de Uso  
Los casos de uso describen las interacciones principales dentro de la aplicación móvil de gestión de vuelos:  

### **1️⃣ Gestión de Pasajeros**  
- Registro y autenticación de pasajeros.  
- Visualización de información del vuelo.  
- Recepción de notificaciones y alertas en tiempo real.  

### **2️⃣ Gestión de Vuelos**  
- Consulta de vuelos disponibles con información detallada.  
- Estado actualizado de vuelos (retrasos, cancelaciones, puertas de embarque).  

### **3️⃣ Gestión de Reservas**  
- Creación, modificación y cancelación de reservas.  
- Asignación de asientos en el vuelo.  

### **4️⃣ Gestión de Check-in y Tarjeta de Embarque**  
- Check-in digital desde la aplicación.  
- Generación y visualización de la tarjeta de embarque.  

### **5️⃣ Gestión de Notificaciones**  
- Recepción de alertas sobre cambios en el vuelo.  
- Comunicación con la aerolínea para asistencia y soporte.  

📌 **Casos de Uso**  
![Casos de Uso](/recursos-adicionales/casos_de_uso_vuelos.png)