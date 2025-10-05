# 🦫 BeaverClock

<div align="center">

![Ionic](https://img.shields.io/badge/Ionic-7-3880FF?style=for-the-badge&logo=ionic&logoColor=white)
![Angular](https://img.shields.io/badge/Angular-17-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![Capacitor](https://img.shields.io/badge/Capacitor-5-119EFF?style=for-the-badge&logo=capacitor&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white)

**Un reloj despertador digital moderno con estilo retro-futurista**

[Demo](#demo) • [Características](#características) • [Instalación](#instalación) • [Uso](#uso)

</div>

---

## 📱 Descripción

**BeaverClock** es una aplicación de reloj digital para Android diseñada para funcionar como reloj despertador de mesita de noche. Con un diseño inspirado en los clásicos relojes LED de los años 80 pero con un toque moderno y minimalista.

### ✨ Características destacadas

- 🎨 **6 colores LED brillantes** - Cambia el color tocando la pantalla
- ⏰ **Display de 12 horas** con indicador AM/PM
- 📅 **Fecha en español** con formato largo
- 🔒 **Pantalla siempre encendida** - Ideal para mesita de noche
- 📱 **Fullscreen inmersivo** - Usa toda la pantalla sin barras
- 🔄 **Solo modo horizontal** - Optimizado para uso en mesa
- 💫 **Efectos LED realistas** - Glow y sombras para simular displays LED
- ⚡ **Animación de parpadeo** en el separador de segundos
- 🎯 **Diseño responsive** - Se adapta a cualquier tamaño de pantalla

---

## 🎥 Demo

<!-- Agrega aquí screenshots o un GIF de la app en funcionamiento -->
```
[Agrega capturas de pantalla aquí]
```

**Colores disponibles:**
- 🔵 Azul cyan (#00bfff)
- 🔴 Rojo (#ff0000)
- 🟢 Verde (#00ff00)
- 🔵 Azul (#0000ff)
- 🟡 Amarillo (#ffff00)
- 🟣 Magenta (#ff00ff)

---

## 🛠️ Tecnologías

Este proyecto está construido con:

- **[Ionic Framework 7](https://ionicframework.com/)** - Framework UI para apps híbridas
- **[Angular 17](https://angular.io/)** - Framework web
- **[Capacitor 5](https://capacitorjs.com/)** - Runtime nativo para apps web
- **[TypeScript 5](https://www.typescriptlang.org/)** - Lenguaje de programación
- **SCSS** - Preprocesador CSS

### Plugins de Capacitor utilizados:

- `@capacitor/screen-orientation` - Control de orientación de pantalla
- `@capacitor-community/keep-awake` - Mantener pantalla encendida

---

## 📦 Instalación

### Prerrequisitos

- Node.js 18+ y npm
- Ionic CLI: `npm install -g @ionic/cli`
- Android Studio (para build de Android)
- Java JDK 11+

### Pasos

1. **Clonar el repositorio**
```bash
git clone https://github.com/tu-usuario/beaverclock.git
cd beaverclock
```

2. **Instalar dependencias**
```bash
npm install
```

3. **Ejecutar en el navegador** (modo desarrollo)
```bash
ionic serve
```

4. **Agregar plataforma Android**
```bash
ionic cap add android
```

5. **Sincronizar cambios**
```bash
ionic cap sync android
```

---

## 📱 Generar APK para Android

### Método 1: Con Android Studio (Recomendado)

```bash
# 1. Build de producción
ionic build --prod

# 2. Sincronizar con Android
ionic cap sync android

# 3. Abrir Android Studio
ionic cap open android

# 4. En Android Studio:
# Build → Build Bundle(s) / APK(s) → Build APK(s)
```

### Método 2: Desde la terminal

```bash
ionic build --prod
ionic cap sync android
cd android
./gradlew assembleDebug
```

El APK se generará en: `android/app/build/outputs/apk/debug/app-debug.apk`

---

## 🚀 Uso

1. **Instalar el APK** en tu dispositivo Android
2. **Abrir la aplicación** - Automáticamente se pondrá en modo horizontal
3. **Tocar la pantalla** para cambiar entre los 6 colores disponibles
4. **Colocar el dispositivo** en tu mesita de noche

### Configuración en el dispositivo

Para mejor experiencia:
- ✅ Activa "No molestar" o modo nocturno
- ✅ Ajusta el brillo de la pantalla a tu preferencia
- ✅ Desactiva la rotación automática (la app solo funciona horizontal)

---

## 📁 Estructura del Proyecto

```
beaverclock/
├── src/
│   ├── app/
│   │   ├── home/
│   │   │   ├── home.page.html          # Template del reloj
│   │   │   ├── home.page.scss          # Estilos LED/display
│   │   │   ├── home.page.ts            # Lógica del reloj
│   │   │   └── home.page.spec.ts       # Tests unitarios
│   │   ├── app.component.ts
│   │   ├── app.module.ts
│   │   └── app-routing.module.ts
│   ├── assets/
│   │   └── fonts/                       # Fuentes personalizadas
│   ├── theme/
│   └── index.html
├── android/                             # Proyecto Android nativo
├── capacitor.config.ts                  # Configuración Capacitor
├── ionic.config.json                    # Configuración Ionic
└── package.json
```

---

## 🎨 Personalización

### Cambiar colores

Edita el array de colores en `src/app/home/home.page.ts`:

```typescript
colors: string[] = [
  '#00bfff',  // Cyan
  '#ff0000',  // Rojo
  '#00ff00',  // Verde
  '#0000ff',  // Azul
  '#ffff00',  // Amarillo
  '#ff00ff',  // Magenta
];
```

### Cambiar fuente

El proyecto usa la fuente **Orbitron** de Google Fonts. Para cambiarla:

1. Edita `src/index.html` y cambia el link de Google Fonts
2. Actualiza `font-family` en `src/app/home/home.page.scss`

### Formato de fecha

Cambia el locale en `home.page.ts`:

```typescript
this.date = now.toLocaleDateString('es-ES', { // Cambia 'es-ES' por tu locale
  day: 'numeric',
  month: 'long',
  year: 'numeric',
});
```

---

## 🧪 Tests

Ejecutar tests unitarios:

```bash
npm test
```

Ejecutar tests con cobertura:

```bash
npm run test:coverage
```

---

## 🐛 Resolución de problemas

### La app no se mantiene en horizontal
- Verifica que `android:screenOrientation="sensorLandscape"` esté en `AndroidManifest.xml`
- Asegúrate de haber sincronizado con `ionic cap sync android`

### La pantalla se apaga
- Verifica que el plugin `@capacitor-community/keep-awake` esté instalado
- Revisa que los permisos estén correctamente configurados

### El fullscreen no funciona
- Asegúrate de haber modificado `MainActivity.java` con el código de ocultamiento de barras
- Verifica el tema en `styles.xml`

---

## 🤝 Contribuir

Las contribuciones son bienvenidas! Si tienes ideas para mejorar BeaverClock:

1. Fork el proyecto
2. Crea una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. Commit tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. Push a la rama (`git push origin feature/AmazingFeature`)
5. Abre un Pull Request

---

## 📝 Roadmap

Características planeadas para futuras versiones:

- [ ] Alarmas configurables
- [ ] Múltiples zonas horarias
- [ ] Temas personalizables
- [ ] Widget para pantalla de inicio
- [ ] Sonidos de alarma personalizados
- [ ] Modo 24 horas
- [ ] Soporte para iOS

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 👤 Autor

**Tu Nombre**

- GitHub: [@tu-usuario](https://github.com/tu-usuario)
- Email: tu-email@ejemplo.com

---

## 🙏 Agradecimientos

- Diseño inspirado en los clásicos relojes despertadores LED de los años 80
- Fuente [Orbitron](https://fonts.google.com/specimen/Orbitron) por Matt McInerney
- Comunidad de Ionic Framework
- Iconos por [Lucide Icons](https://lucide.dev/)

---

<div align="center">

**⭐ Si te gusta este proyecto, dale una estrella en GitHub! ⭐**

Hecho con ❤️ y ☕

</div>
