# 📄 Documentación técnica  
💻 *Laboratorio 1 – Tecnologías Web Modernas*  

*Nombre: Brasly Villarebia Moarales*  
*Carné: 2023105915*  
*Curso:* IC-8057 – Introducción al Desarrollo de Páginas Web  
*Fecha: 8 de agoesto del 2025*  

---

## 1. Frameworks de desarrollo web
### a. ¿Qué es un framework y qué problema resuelve?

Un framework es un modelo de trabajo que ofrece una base para la creacion de software, se puede decir que es una especie de plantilla para facilitar la organizacion y creacion del proyecto. 

Como se menciona anteriormente facilita la creación de aplicaciones al ofrecer soluciones a problemas comunes y al promover la reutilización de código, lo que resulta en un desarrollo más rápido y eficiente


**Ejemplo:**
React Native
React Native es un framework de programación de aplicaciones nativas multiplataforma que está basado en JavaScript y ReactJS.
En React existe un “VirtualDOM”, en el que tenemos nuestro JSX, en el cual definimos los documentos HTML, y estos se transforman en componentes del navegador a través de JavaScript.

### b. Arquitectura general y enfoque (MVC, SPA, SSR, etc.)
React Native utiliza un enfoque basado en componentes similar a una SPA , donde la interfaz se actualiza de forma dinámica sin recargar toda la aplicación.
Su arquitectura sigue el modelo Bridge, que conecta el código JavaScript con los componentes nativos mediante un canal de comunicación asíncrono, permitiendo crear aplicaciones móviles nativas reutilizando lógica y estructura.


### c. Ejemplo práctico documentado  

**Estructura de proyecto**
```
my-react-native-app/
├── node_modules/
├── android/
├── ios/
├── src/
│   ├── assets/
│   │   ├── images/
│   │   └── fonts/
│   ├── components/
│   │   ├── common/
│   │   │   └── Button/
│   │   │       └── Button.js
│   │   │       └── Button.styles.js
│   │   └── specific/
│   │       └── ProductCard/
│   │           └── ProductCard.js
│   │           └── ProductCard.styles.js
│   ├── screens/
│   │   ├── HomeScreen/
│   │   │   └── HomeScreen.js
│   │   │   └── HomeScreen.styles.js
│   │   ├── ProfileScreen/
│   │   │   └── ProfileScreen.js
│   │   └── AuthScreen/
│   │       └── AuthScreen.js
│   ├── navigation/
│   │   ├── AppNavigator.js
│   │   └── AuthNavigator.js
│   ├── services/
│   │   ├── api.js
│   │   └── authService.js
│   ├── utils/
│   │   ├── constants.js
│   │   └── helpers.js
│   ├── contexts/ (or redux/store/)
│   │   └── AuthContext.js
│   └── App.js
├── .env
├── .gitignore
├── app.json
├── babel.config.js
├── index.js
├── package.json
└── README.md    
```
**Fragmento de código comentado** 

Ejemplo de codigo de HomeScreen.js

```
// Importamos React y componentes básicos de React Native
import React from 'react';
import { View, Text, StyleSheet } from 'react-native';

// Componente funcional HomeScreen
export default function HomeScreen() {
  return (
    // Contenedor principal que centra el contenido
    <View style={styles.container}>
      {/* Título principal */}
      <Text style={styles.title}>Bienvenido a mi App</Text>
      
      {/* Subtítulo o descripción */}
      <Text style={styles.subtitle}>Esta es la pantalla principal</Text>
    </View>
  );
}
const styles = StyleSheet.create({
  container: {
    flex: 1,                 
    justifyContent: 'center', 
    alignItems: 'center',     
    backgroundColor: '#f0f0f0'
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold'
  },
  subtitle: {
    fontSize: 16,
    marginTop: 8
  }
});
```
### d. Comparación breve entre al menos dos frameworks
| Comparacion       | React Native                  | Angular                      |
|---------------------|------------------------------|------------------------------|
| Lenguaje            | JavaScript / JSX             | TypeScript                   |
| Plataforma          | Apps móviles nativas (iOS, Android) | Aplicaciones web            |
| Arquitectura        | Basado en componentes         | Basado en MVC / MVVM         |
| Curva de aprendizaje| Moderada, enfoque en UI       | Más pronunciada, completo framework |


## 2. Control de versiones y trabajo colaborativo
### a. ¿Qué es el control de versiones y por qué es esencial?

**¿Qué es el control de versiones?**
Es una práctica de seguimiento que registra los cambios en un proyecto. Al guardar y gestionar los cambios de un proyecto, permite volver a versiones anteriores si alguna versión nueva da fallo por alguna razón. También nos permite trabajar de manera colaborativa con otras personas sin afectar el trabajo de los demás..
**¿por qué es esencial?**
Debido a poder almacenar versiones previas, si sucede un problema se podrá devolver la versión, optimizando el tiempo que llevaría buscar el problema y solucionarlo.


### b. Conceptos clave  
- Repositorio: Un repositorio es donde se ubica el almacenamiento de los archivos de un proyecto, tambien contiene todas las versiones y su historial de cambios.
- Commit: Registra los cambios realizados en los archivos, al commit se le registra un identificador, el autor del cambio y el mensaje de confirmación.
- Branch: permite desarrollar de forma paralela permitiendo trabajar en cambion sin afectar la version principal.
- Merge: integra los cambios de una Branch en otra, combinando el trabajo de diferentes líneas de desarrollo en una sola. 
- Pull Request: Es una solicitud para proponer la integración de cambios de una Branch a otra. Permite que los miembros del equipo revisen, comenten y aprueben los cambios antes de realizar el Merge.


### c. Flujos de trabajo comunes  
- Git Flow: Es un modelo de trabajo en Git que define una estrategia de branching más estructurada. Implica el uso de branch específicas para funcionalidades y múltiples branch principales, con reglas claras sobre cómo y cuándo hacer Merge entre ellas.
- Trunk-Based : es una practica de control de versiones en la que los desarrolladores fucionan pequeñas actualizaciones de de forma frecuente.
- Feature Branches: Esto permite trabajar en una feature branch sin afectar la rama principal. Cuando la funcionalidad está lista y probada, se hace un merge de la feature branch a la rama principal para integrar los cambios.
### d. Ejemplo de uso de Git en un proyecto  
**Inicialización**
```
git init
```
Este comando permite c rear un nuevo repositorio en git.

**Commits**

```
git add . 
git commit -m "Mensaje descriptivo del cambio"
```

Esto guarda los cambios actuales en el repositorio con un mensaje descriptivo.


**Ramas**
```
git branch nombre 
git checkout nombre
```

Crea una nueva rama y cambia a ella para trabajar aislado del código principal.

### e. Herramientas recomendadas  
- GitHub: plataforma que permite alojar repositorios git, con funcionalidades de intregracion CI/CD y gestion de proyecto.
- GitLab: Ofrece repositorio git y incluye herraminetas de integracion y gestion de proyectos con seguriidad 
- Bitbucket: integrado con Atlassian, ideal para equipos de desarrollo que usen administradores de tareas como lo es Jira y Trello, soporta repositorios git y Mercurial.

*Funete*
*https://rewind.com/blog/github-vs-bitbucket-vs-gitlab-comparison/*

---

## 3. Autenticación y seguridad moderna
### a. Conceptos  
- Autenticación: Proceso de verificacion y autentificacion de usuario
- Autorización: Determina que recursos o acciones se le tiene permito al usuario
- Tokens: pequeña calve generada que representa la indetificacion y permiso de un usuario durante la sesión.
- JWT (JSON Web Token): Una especie de token que contiene la informacion codificada y firmada, usado para autenticación y autorización segura.
- OAuth: Es un estándar abierto que permite flujos simples de autorización para sitios web o aplicaciones informáticas.
### b. Diagrama de flujo explicativo del proceso de autenticación con JWT
### c. Buenas prácticas en seguridad web
- Implantar políticas estrictas de seguridad de contenidos (CSP)
- Activar HTTP Strict Transport Security (HSTS)
- Utilizar la Integridad de Subrecursos (SRI) para guiones externos
- Implementar la seguridad del DNS (DNSSEC)
*Fuente*
*https://powerdmarc.com/es/web-security-website-security-explained/*


### d. Aplicaciones reales en plataformas modernas
- Aplicaciones como Google, Facebook y Twitter utilizan login social con OAuth para que los desarrolladores accedan a datos de forma segura
- Algunas plataformas como Firebase Authentication, Auth0 y Okta ofrecen servicios completos de autenticación y autorización para aplicaciones web y móviles.


*fuente*
*https://nimbustech.es/productos-servicios/mejores-sistemas-de-autenticacion-de-usuarios-para-empresas/*


---

## 4. Gestores de contenido desacoplados (Headless CMS)
### a. Definición: Headless CMS vs CMS tradicional
**CMS tradicional**
Es un sistema que gde gestion de contenido donde el backend esta completamente vinculado al fronted
Ejemplos
- WordPress
- Joomla
- Drupal

**Headless CMS**
Es un sistema de gestión de contenido que separa la capa de "frontend de la capa del backend.
Ejemplos
- Ghost
- Netlify CMS

### b. Arquitectura basada en APIs
El contenido se gestiona en el backend y se consume en el frontend mediante APIs REST o GraphQL, facilitando la integración con múltiples canales
### c. Ventajas, limitaciones y casos de uso comunes

**Ventajas:** Flexibilidad en el frontend, escalabilidad, fácil integración multicanal.  
**Limitaciones:** Requiere más trabajo para construir el frontend, dependencia de la API.  
**Casos comunes:** Aplicaciones web modernas, apps móviles, sitios con múltiples puntos de entrega.

*Fuente*
*https://www.canidium.com/es/pros-and-cons-of-using-apis-with-sap-commissions*

### d. Ejemplo de conexión del frontend a un CMS headless

un exelente ejmplo es react que consume contenido desde un CMS headless como Contentful usando llamadas API para mostrar artículos dinámicos.

---

## 5. Pasarelas de pago en aplicaciones web
### a. ¿Qué es una pasarela de pago? ¿Qué rol cumple en una aplicación moderna?
Una pasarela de pago es un servicio qque realiza pagos electronicos, conectando a la aplicación con bancos y sistemas de tarjetas, asegurando transacciones seguras y confiables.

*Fuente*
*https://stripe.com/es/resources/more/payment-gateways-101*
### b. Requisitos comunes  
- Cuenta de comercio: permite realizar pagos en linea.
- Seguridad: Cumplimiento de estándares como PCI DSS para proteger datos financieros.
- Integración técnica : APIs y SDKs para integrar pagos en la aplicación.
### c. Ventajas y limitaciones de integrar pagos en línea
- Ventajas: Facilita ventas globales, automatiza cobros, mejora experiencia usuario.

- Limitaciones: Costos por transacción, dependencia de terceros, cumplimiento legal y de seguridad.

### d. Comparación entre pasarelas  
- Stripe: muy conocido por su facilidad de integración y soporte global.
- TiloPay: Enfocada en mercados específicos, ofrece opciones de pago locales.
- Bancos: Pasarelas propias con integración directa pero menos flexibilidad.
- Otras: PayPal, Square, Adyen, entre otras, con diferentes características según región y negocio.


https://connect.tilopay.com/es-cr/stripe-o-paypal/
https://connect.tilopay.com/plataformas-de-pago-en-lnea/ 
---

## 6. Automatización del despliegue y hosting moderno
### a. ¿Qué es CI/CD y por qué se usa en desarrollo web?
CI/CD, que significa Integración Continua / Entrega Continua (Continuous Integration / Continuous Delivery), es un conjunto de prácticas de desarrollo de software que automatizan la integración y entrega de código.
**En desarrollo web se usa para:**
- Reducir errores humanos.
- Acelerar el tiempo de entrega.
- Garantizar calidad en cada actualización.
### b. Hosting estático vs dinámico

| Tipo              | Descripción                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| **Estático**      | Sirve archivos HTML, CSS y JS preconstruidos, sin generación en tiempo real. | 
| **Dinámico**      | Genera contenido en tiempo real usando código del servidor y, normalmente, una base de datos. | 
### c. Flujo de despliegue automatizado

El flujo de despliegue automatizado es un proceso que ayuda a pasar los cambios en el código desde que un desarrollador los termina hasta que se publican en la aplicación en línea, todo de forma automática y rápida.

**Pasos básicos:**
- Guardar cambios: El desarrollador guarda y sube su código al repositorio (como GitHub).
- Construir y probar: El sistema crea la aplicación y ejecuta pruebas para asegurarse de que todo funciona bien.
- Desplegar: Si las pruebas pasan, la aplicación se actualiza automáticamente en el servidor o en la nube.
- Monitorear: Se revisa que la aplicación funcione correctamente después del despliegue.

### d. Documentar el proceso seguido para desplegar la parte 2 del laboratorio
# Pasos a seguir
1. Crear un repositorio en GitHub con el nombre `desarrollo-moderno-nombre`.
2. Agregar el archivo `README.md` y el `index.html` proporcionados por el docente.
3. Realizar commit para que se almacene en el repositorio.
4. Dirigirse a [https://www.netlify.com/](https://www.netlify.com/).
5. Iniciar sesión con la cuenta de GitHub.
6. Seleccionar **Proyectos** en el menú de la izquierda.
7. Presionar **Agregar nuevo proyecto** y después **Importar un proyecto existente**.
8. Seleccionar la opción de GitHub.
9. Escoger el repositorio `desarrollo-moderno-nombre`.
10. Ingresar un nombre válido para el proyecto y presionar **Desplegar nombredelproyecto**.



---

## ✅ Principios aplicados en este proyecto

---

## 📎 Créditos y referencias
