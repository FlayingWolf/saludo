# 🎮 EloCheck API

> API REST para comparar hardware con requisitos de videojuegos

---

## 📋 Descripción

**EloCheck** es una API REST desarrollada con **Spring Boot** que permite a los usuarios verificar si su hardware es compatible con los requisitos de videojuegos populares. La aplicación proporciona endpoints para consultar especificaciones de juegos y comparar el equipo del usuario con los requisitos mínimos y recomendados.

### Características principales

- ✅ **Consulta de requisitos de juegos** - Accede a una base de datos de especificaciones de juegos
- ✅ **Comparación de hardware** - Verifica si tu equipo cumple con los requisitos
- ✅ **API REST robusta** - Endpoints bien documentados y fáciles de usar
- ✅ **Base de datos relacional** - Almacenamiento seguro con MySQL
- ✅ **Validación de datos** - Validación automática de entrada con Jakarta Validation
- ✅ **Desarrollo flexible** - Soporte para H2 en desarrollo sin necesidad de MySQL

---

## 🛠️ Tecnologías

- **Java 21** - Lenguaje de programación
- **Spring Boot 3.4.5** - Framework REST
- **Spring Data JPA** - Acceso a datos
- **MySQL** - Base de datos relacional
- **Maven** - Gestor de dependencias
- **Lombok** - Reducción de código boilerplate
- **H2 Database** - Base de datos en memoria para desarrollo
- **Jakarta Validation** - Validación de datos

---

## 📦 Requisitos previos

Antes de comenzar, asegúrate de tener instalados:

- **Java 21** o superior
- **Maven 3.6+**
- **MySQL 8.0+** (opcional si usas H2 para desarrollo)
- **Git**

---

## 🚀 Inicio rápido

### 1. Clonar el repositorio

```bash
git clone https://github.com/Migueldinho/EloCheck.git
cd EloCheck
```

### 2. Configurar la base de datos

#### Opción A: MySQL (Producción)

Crea una base de datos y actualiza `src/main/resources/application.properties`:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/elocheck
spring.datasource.username=root
spring.datasource.password=tucontraseña
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=false
```

#### Opción B: H2 (Desarrollo)

H2 está preconfigurado. Solo ejecuta la aplicación:

```properties
spring.datasource.url=jdbc:h2:mem:testdb
spring.h2.console.enabled=true
```

### 3. Ejecutar la aplicación

```bash
./mvnw spring-boot:run
```

O con Maven:

```bash
mvn spring-boot:run
```

La API estará disponible en: `http://localhost:8080`

---

## 📚 Documentación de API

### Endpoints principales

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/api/juegos` | Obtener lista de juegos |
| `GET` | `/api/juegos/{id}` | Obtener detalles de un juego |
| `POST` | `/api/comparar` | Comparar hardware con requisitos |
| `GET` | `/api/requisitos/{juegoId}` | Obtener requisitos de un juego |

### Ejemplo de solicitud

```bash
curl -X GET http://localhost:8080/api/juegos
```

---

## 🏗️ Estructura del proyecto

```
EloCheck/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/duoc/elocheck/
│   │   │       ├── controller/    # Controladores REST
│   │   │       ├── service/       # Lógica de negocio
│   │   │       ├── repository/    # Acceso a datos
│   │   │       ├── model/         # Entidades JPA
│   │   │       └── dto/           # Objetos de transferencia
│   │   └── resources/
│   │       └── application.properties
│   └── test/                      # Tests unitarios
├── postman/                       # Colección de Postman
├── pom.xml                        # Configuración Maven
└── README.md                      # Este archivo
```

---

## 🧪 Testing

### Ejecutar pruebas

```bash
./mvnw test
```

### Usar Postman

Importa la colección desde la carpeta `postman/` para probar todos los endpoints.

---

## 🔧 Configuración

### Variables de entorno

Puedes configurar la aplicación usando variables de entorno:

```bash
export SERVER_PORT=8080
export SPRING_DATASOURCE_URL=jdbc:mysql://localhost:3306/elocheck
export SPRING_DATASOURCE_USERNAME=root
export SPRING_DATASOURCE_PASSWORD=password
```

### Propiedades personalizadas

Edita `src/main/resources/application.properties`:

```properties
# Puerto
server.port=8080

# Base de datos
spring.datasource.url=jdbc:mysql://localhost:3306/elocheck
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA/Hibernate
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL8Dialect
```

---

## 🐛 Troubleshooting

### Error de conexión a MySQL

```
com.mysql.cj.jdbc.exceptions.CommunicationsException
```

**Solución:** Verifica que MySQL esté ejecutándose y que las credenciales sean correctas.

### Puerto 8080 en uso

```
Port already in use
```

**Solución:** Cambia el puerto en `application.properties`:

```properties
server.port=9090
```

---

## 📝 Licencia

Este proyecto está disponible bajo la licencia MIT. Ver `LICENSE` para más detalles.

---

## 👨‍💻 Autor

Desarrollado por **[Migueldinho](https://github.com/Migueldinho)**

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Por favor:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/nueva-caracteristica`)
3. Commit tus cambios (`git commit -m 'Agregar nueva característica'`)
4. Push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

---

## 📞 Soporte

Si tienes preguntas o problemas, abre un [issue](https://github.com/Migueldinho/EloCheck/issues) en el repositorio.

---

**⭐ Si te resulta útil, no olvides dejar una estrella!**
