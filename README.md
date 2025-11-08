# Elysia Template

Plantilla inicial para proyectos con [Elysia](https://elysiajs.com/) y [Bun](https://bun.sh/). Un punto de partida rápido y optimizado para construir aplicaciones web modernas.

## 🚀 Características

- **Elysia**: Framework web ultrarrápido y moderno para Bun
- **TypeScript**: Tipado estático completo para mayor seguridad
- **Biome**: Linter y formateador de última generación
- **Build multiplataforma**: Soporte para compilar ejecutables nativos (Linux, macOS, Windows)
- **Configuración lista**: Todo preconfigurado para empezar a desarrollar inmediatamente

## 📋 Requisitos Previos

- [Bun](https://bun.sh/) v1.3.1 o superior

## 🛠️ Uso del Template

### Opción 1: Usar como plantilla

1. Haz clic en "Use this template" en GitHub
2. Clona tu nuevo repositorio
3. Instala las dependencias:

```bash
cd tu-proyecto
bun install
```

### Opción 2: Clonar directamente

```bash
# Clonar el repositorio
git clone https://github.com/4a4c53/elysia-template
cd elysia-template

# Instalar dependencias
bun install
```

## 🏃 Ejecución

### Modo Desarrollo

```bash
bun run dev
```

El servidor se ejecutará en `http://localhost:4453` con hot-reload automático.

### Modo Producción

```bash
# Compilar y ejecutar
bun run start
```

## 🔨 Build

### Build local (sistema actual)

```bash
bun run build
```

### Build para plataformas específicas

```bash
# Linux (x64)
bun run build:linux

# macOS (Intel)
bun run build:mac

# macOS (Apple Silicon)
bun run build:mac-arm

# Windows (x64)
bun run build:windows

# Windows (ARM)
bun run build:windows-arm

# Vercel
bun run build:vercel
```

## 🧹 Calidad de Código

```bash
# Verificar código con Biome
bun run lint

# Formatear código
bun run format
```

## 📁 Estructura del Proyecto

```
elysia-template/
├── src/
│   └── index.ts       # Punto de entrada de la aplicación
├── biome.json         # Configuración de Biome (linter/formatter)
├── package.json       # Dependencias y scripts
├── tsconfig.json      # Configuración de TypeScript
└── README.md          # Este archivo
```

## 🎯 Próximos Pasos

Después de clonar el template, puedes:

1. **Actualizar `package.json`**: Cambia el nombre, versión y autor del proyecto
2. **Modificar el puerto**: Ajusta el puerto en `package.json` > `config.port`
3. **Agregar rutas**: Extiende `src/index.ts` con tus endpoints
4. **Configurar plugins**: Añade plugins de Elysia según tus necesidades

### Ejemplo: Agregar una nueva ruta

```typescript
import { Elysia } from 'elysia'

const app = new Elysia()
  .get('/', () => 'Hello Elysia')
  .get('/user/:id', ({ params: { id } }) => id)
  .post('/user', ({ body }) => body)
  .listen(3000)
```

## ⚙️ Configuración

Puedes personalizar la configuración del proyecto en `package.json`:

```json
"config": {
  "port": "4453",      // Puerto en el que se ejecutará el servidor
  "outfile": "server"  // Nombre del archivo ejecutable compilado
}
```

- **`port`**: Puerto en el que se ejecutará el servidor (por defecto: `4453`)
- **`outfile`**: Nombre del archivo ejecutable que se genera al compilar el proyecto (sin extensión en Unix/Linux/macOS, `.exe` se añade automáticamente en Windows)

## 📝 Scripts Disponibles

| Script | Descripción |
|--------|-------------|
| `dev` | Ejecuta el servidor en modo desarrollo con hot-reload |
| `start` | Compila y ejecuta el servidor |
| `build` | Compila un ejecutable para el sistema actual |
| `build:linux` | Compila para Linux x64 |
| `build:mac` | Compila para macOS Intel |
| `build:mac-arm` | Compila para macOS Apple Silicon |
| `build:windows` | Compila para Windows x64 |
| `build:windows-arm` | Compila para Windows ARM |
| `build:vercel` | Compila para despliegue en Vercel |
| `lint` | Verifica el código con Biome |
| `format` | Formatea el código con Biome |

## 👤 Autor

**José L Silva**
- Email: joseluis@4a4c53.com
- Web: http://4a4c53.com

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - consulta el archivo [LICENSE](LICENSE) para más detalles.

Eres libre de usar este template para tus proyectos personales o comerciales.
