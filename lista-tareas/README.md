# Aplicación de Lista de Tareas con Vue.js

Proyecto desarrollado como parte de la investigación y exploración de tecnologías modernas de desarrollo para el curso **IF0009 Desarrollo de Software VI** de la Universidad de Costa Rica (Sede de Occidente, Recinto de Tacares).

Consiste en una aplicación web interactiva de gestión de tareas construida con **Vue 3** y **Vite**, utilizando la *Composition API* y componentes modulares. Permite agregar, marcar como completas y eliminar tareas.

---

## Requisitos Básicos

Asegúrate de tener instalado en tu computadora el siguiente software antes de clonar y ejecutar el repositorio:

1. **Git** (para clonar el repositorio).
2. **Node.js** versión 22.18 o superior, o 24.12 en adelante (incluye `npm`).
   Puedes comprobarlo con `node --version` y `npm --version`.
3. **Visual Studio Code** (editor de código recomendado).
   * *Extensión recomendada:* **Vue (Official)**, antes llamada Volar, para el soporte de los archivos `.vue`.

---

## Instrucciones de Ejecución

Sigue estos pasos en tu terminal para descargar y ejecutar el proyecto localmente:

1. **Clona el repositorio y entra a la carpeta del proyecto:**
   ```bash
   git clone https://github.com/amandabolanos/ProyectoVue.git
   cd ProyectoVue/lista-tareas
   ```

2. **Instala las dependencias del proyecto:**
   ```bash
   npm install
   ```
   *(Este comando descarga los paquetes necesarios en la carpeta `node_modules`)*

3. **Inicia el servidor de desarrollo local con Vite:**
   ```bash
   npm run dev
   ```

4. **Abre la aplicación en el navegador:**
   Haz clic en la dirección que muestra la terminal (generalmente **`http://localhost:5173`**) o cópiala en tu navegador web de preferencia.

Para detener el servidor, presiona `Ctrl + C` en la terminal.

---

## Dependencias

Se instalan automáticamente con `npm install`:

| Paquete | Uso |
|---|---|
| `vue` | Framework para construir la interfaz |
| `vite` | Servidor de desarrollo y compilación |
| `@vitejs/plugin-vue` | Permite que Vite procese los archivos `.vue` |
| `vite-plugin-vue-devtools` | Herramientas de Vue para el navegador |

---

## Estructura del Proyecto

* `src/App.vue`: Componente principal. Guarda la lista de tareas y contiene las funciones para agregar, marcar y eliminar tareas.
* `src/components/TareaItem.vue`: Componente hijo que muestra cada tarea como una tarjeta y avisa al componente principal, mediante eventos, cuando se marca o se elimina una tarea.
* `src/assets/main.css`: Estilos globales de la aplicación.
* `src/main.js`: Punto de entrada que crea la aplicación y la monta en la página.

---

## Créditos y Autores
* Amanda Bolaños Alfaro
* Angely Castro Ureña
* Valeria Sánchez Roldán
* Sebastián Villegas Araya