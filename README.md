# 💬 Chat TCP/UDP en Java

> Proyecto Final · Redes  · ITSON

Aplicación de chat cliente-servidor desarrollada en Java que permite comunicación en tiempo real mediante sockets TCP y UDP, con soporte para mensajes grupales y privados entre múltiples clientes.

---

## 📋 Descripción

El sistema implementa una arquitectura cliente-servidor donde un servidor central gestiona las conexiones y retransmite mensajes entre los clientes conectados. Se utilizan hilos independientes para manejar cada cliente de forma concurrente, permitiendo que varios usuarios chatíen simultáneamente sin bloqueos.

---

## 👥 Integrantes

| Nombre | Matrícula |
|--------|-----------|
| Nombre Integrante 1 | 000000001 |
| Nombre Integrante 2 | 000000002 |

---

## 🛠️ Tecnologías utilizadas

- **Java 17+**
- **TCP Sockets** — conexión confiable orientada a flujo
- **UDP Sockets** — comunicación sin conexión de baja latencia
- **Multihilos** (`Thread` / `Runnable`) — manejo concurrente de clientes
- **Maven / IntelliJ IDEA / Eclipse** *(según corresponda)*

---

## 📁 Estructura del proyecto

```
chat-tcp-udp-java/
├── src/
│   ├── servidor/
│   │   ├── ServidorMain.java       # Punto de entrada del servidor
│   │   ├── ServidorTCP.java        # Lógica del servidor TCP
│   │   └── ManejadorCliente.java   # Hilo por cliente conectado
│   ├── cliente/
│   │   ├── ClienteMain.java        # Punto de entrada del cliente
│   │   ├── ClienteTCP.java         # Lógica del cliente TCP
│   │   └── InterfazChat.java       # Consola del usuario
│   └── util/
│       └── Protocolo.java          # Constantes y formato de mensajes
├── screenshots/
│   ├── servidor_activo.png
│   ├── registro_usuario.png
│   ├── chat_grupal.png
│   └── mensaje_privado.png
├── .gitignore
└── README.md
```

---

## 🚀 Cómo ejecutar

### Requisitos previos

- Java JDK 17 o superior instalado
- Terminal / Git Bash

### Compilar el proyecto

```bash
javac -d bin src/**/*.java
```

### Iniciar el servidor

```bash
java -cp bin servidor.ServidorMain
```

El servidor escuchará en el puerto `5000` (TCP) y `5001` (UDP) por defecto.

### Conectar un cliente

```bash
java -cp bin cliente.ClienteMain
```

Se te pedirá ingresar la IP del servidor y tu nombre de usuario.

---

## ⚙️ Funcionalidades

- [x] Registro de usuario con nombre único
- [x] Mensajes grupales visibles para todos los conectados
- [x] Mensajes privados entre usuarios (`/msg <usuario> <mensaje>`)
- [x] Lista de usuarios conectados (`/usuarios`)
- [x] Desconexión controlada (`/salir`)
- [ ] Historial de mensajes persistente *(en desarrollo)*
- [ ] Interfaz gráfica *(en desarrollo)*

---

## 📸 Capturas de pantalla

### Servidor activo
![Servidor activo](screenshots/servidor_activo.png)

### Registro de usuario
![Registro de usuario](screenshots/registro_usuario.png)

### Chat grupal
![Chat grupal](screenshots/chat_grupal.png)

### Mensaje privado
![Mensaje privado](screenshots/mensaje_privado.png)

---

## 🌐 Protocolo de comunicación

Los mensajes siguen el formato:

```
TIPO|ORIGEN|DESTINO|CONTENIDO
```

| Tipo | Descripción |
|------|-------------|
| `MSG` | Mensaje grupal |
| `PRIV` | Mensaje privado |
| `REG` | Registro de nuevo usuario |
| `BYE` | Desconexión de usuario |
| `LIST` | Solicitud de lista de usuarios |

---

## 📄 Licencia

Proyecto académico — ITSON · Redes de Computadoras · 2025
