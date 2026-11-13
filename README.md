# 💵 Dólar Blue ESJS

Aplicación de consola que consulta la cotización del dólar blue en Argentina, escrita en [EsJS](https://github.com/es-js/esjs) (JavaScript con sintaxis en español) y ejecutada en el navegador con Vite.

## Qué hace

1. Pide el **DNI** y una **palabra secreta** del usuario.
2. Valida la palabra secreta y, si es incorrecta, termina el programa.
3. Consulta la API REST pública de [DolarAPI](https://dolarapi.com) (`/v1/dolares/blue`).
4. Muestra el precio de **compra**, de **venta**, el **promedio** entre ambos y la **fecha de actualización**.
5. Si la API no responde, muestra un mensaje de error en lugar de cortarse (`intentar` / `capturar`, el equivalente de `try` / `catch`).

## Tecnologías

- EsJS (JavaScript en español) con [`@es-js/terminal`](https://github.com/es-js/esjs) para la interfaz de consola
- Vite 5 con el plugin `@es-js/vite-plugin-esjs`
- Consumo de API REST y JSON con `async` / `await`
- Dev container listo para GitHub Codespaces

## Estructura

```
├── .devcontainer/      # Configuración para GitHub Codespaces
├── public/             # Ícono de la página
├── src/
│   ├── app.esjs        # Lógica del programa (EsJS)
│   └── main.js         # Punto de entrada que carga app.esjs
├── index.html          # Página que monta la terminal <es-terminal>
├── vite.config.js
└── package.json
```

## Cómo ejecutarlo

Requiere Node.js 18 o superior.

```bash
git clone https://github.com/Benjarodz/dolar-blue-esjs.git
cd dolar-blue-esjs
npm install
npm run dev
```

Luego abre `http://localhost:3000` en el navegador.

También se puede abrir directamente en **GitHub Codespaces**: el dev container instala las dependencias y levanta el servidor solo.

## Consideraciones de seguridad

Este proyecto es una práctica y tiene limitaciones conocidas:

- **Dependencias remotas sin verificar:** `validarSecreto` y `obtenerJson` se importan en tiempo de ejecución desde una URL externa (`desarrollo-aplicaciones.vercel.app`). Si ese archivo cambiara, cambiaría el comportamiento de la app sin que el repositorio se entere. En un proyecto real convendría copiar el código al repositorio o fijar su versión y verificar su integridad.
- **La validación ocurre del lado del cliente:** cualquier persona puede leer el código en el navegador, por lo que no es un control de acceso real.
- **La palabra secreta se pide como texto común**, sin ocultar los caracteres.

## Objetivo

Práctica de JavaScript moderno: funciones asíncronas, consumo de APIs, manejo de errores y uso de módulos.

## Autor

**Benjamín Rodríguez**: [github.com/Benjarodz](https://github.com/Benjarodz)

## Licencia

Distribuido con fines educativos.
