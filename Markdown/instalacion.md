# 🛠️ Guía de Instalación - CotareloManage

Manual completo para instalar y configurar el sistema educativo.

## Requisitos del Sistema

| Componente | Versión Mínima | Recomendada | Estado |
| ---------- | -------------- | ----------- | ------ |
| Node.js    | 16.x           | 18.x LTS    | ✅     |
| npm        | 8.x            | 9.x         | ✅     |
| MongoDB    | 5.0            | 6.0+        | ⚠      |
| Redis      | 6.x            | 7.x         |        |

## 💻 Sistemas Operativos Soportados

- ✅ Windows 10/11
- ✅ macOS Monterey+
- ✅ Ubuntu 20.04 LTS+
- ✅ CentOS 8+

## 🎯 Métodos de Instalación

### Opción 1: Instalación Automática (Recomendado)

**Descargar script de instalación:**

```bash
curl -fsSL https://install.CotareloManage.es/setup.sh | bash
```

O usando wget:

```bash
wget -qO- https://install.CotareloManage.es/setup.sh | bash
```

### Opción 2: Instalación Manual

#### Paso 1: Clonar el Repositorio

```bash
git clone https://github.com/CotareloManage/sistema-escolar.git
cd sistema-escolar
```

#### Paso 2: Configurar Variables de Entorno

Crea un archivo `.env` con la siguiente configuración:

```plaintext
# Base de datos
DATABASE_URL=mongodb://localhost:27017/CotareloManage
REDIS_URL=redis://localhost:6379

# Autenticación
JWT_SECRET=tu_clave_super_secreta_aqui_2024
JWT_EXPIRY=24h

# Email (opcional)
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=tu-email@gmail.com
SMTP_PASS=tu-contraseña-app
```

#### Paso 3: Instalar Dependencias

```bash
# Instalar dependencias del backend
npm install

# Instalar dependencias del frontend
cd client && npm install && cd ..
```

## 🐳 Instalación con Docker

### Docker Compose (Más Fácil)

```yaml
version: "3.8"
services:
  app:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=production
    depends_on:
      - mongodb
      - redis

  mongodb:
    image: mongo:6.0
    ports:
      - "27017:27017"
    volumes:
      - mongodb_data:/data/db

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

volumes:
  mongodb_data:
```

Ejecutar con:

```bash
docker-compose up -d
```

## Checklist Post-Instalación

1. Servicios Básicos

   - Base de datos conectada
   - Redis funcionando
   - Servidor web iniciado
   - SSL configurado

2. Funcionalidades Core
   - Login de usuarios
   - Dashboard principal
   - Módulo de calificaciones
   - Sistema de notificaciones

## 🚨 Solución de Problemas Comunes

**Error:** "Cannot connect to MongoDB"  
**Causa:** MongoDB no está iniciado o la URL de conexión es incorrecta.  
**Soluciones:**

1. Verificar que MongoDB esté ejecutándose:

   ```bash
   sudo systemctl status mongodb
   ```

2. Revisar la variable `DATABASE_URL` en el archivo `.env`.
3. Comprobar permisos de red:

   ```bash
   telnet localhost 27017
   ```

## 🔄 Actualizaciones

### Actualización Automática

```bash
# Activar auto-updates (recomendado para desarrollo)
npm run enable-auto-update

# Desactivar
npm run disable-auto-update
```

### Actualización Manual

```bash
# Backup antes de actualizar
npm run backup

# Descargar nueva versión
git pull origin main

# Instalar dependencias nuevas
npm install

# Migrar base de datos si es necesario
npm run migrate

# Reiniciar servicio
npm run restart
```

## 🏁 Siguientes Pasos

Una vez completada la instalación:

1. Configura tu primer usuario administrador.
2. Personaliza la configuración del centro educativo.
3. Importa datos existentes (si los hay).
4. Capacita al personal en el uso del sistema.

## 💡 Tip

Mantén siempre actualizada la documentación y realiza backups regulares.

¿Problemas con la instalación? Contacta con soporte: <support@CotareloManage.es>

**Instalación completada exitosamente** ✅
