# 🔨 Cómo Compilar el Plugin All-in-One

## Opción 1: Usando Maven (Recomendado)

### Requisitos:
- Java 8 o superior
- Maven 3.6+

### Pasos:
```bash
# 1. Navegar al directorio del plugin
cd /ruta/del/plugin

# 2. Compilar el plugin
mvn clean package

# 3. El archivo .jar estará en:
target/AllInOnePlugin-1.0.0.jar
```

## Opción 2: Usando Gradle

### Requisitos:
- Java 8 o superior
- Gradle 7.0+

### Pasos:
```bash
# 1. Navegar al directorio del plugin
cd /ruta/del/plugin

# 2. Compilar el plugin
./gradlew build

# 3. El archivo .jar estará en:
build/libs/AllInOnePlugin-1.0.0.jar
```

## Opción 3: IDEs (Más Fácil)

### IntelliJ IDEA:
1. **Abrir proyecto** → Seleccionar la carpeta del plugin
2. **Esperar** a que se descarguen las dependencias
3. **Build** → **Build Artifacts** → **AllInOnePlugin:jar** → **Build**
4. El .jar estará en `out/artifacts/`

### Eclipse:
1. **Import** → **Existing Maven Project**
2. **Right-click** en el proyecto → **Run As** → **Maven build**
3. **Goals**: `clean package`
4. El .jar estará en `target/`

### Visual Studio Code:
1. **Instalar** Extension Pack for Java
2. **Abrir** la carpeta del plugin
3. **Ctrl+Shift+P** → **Java: Build Workspace**
4. **Terminal** → `mvn clean package`

## Opción 4: Servicios Online (Sin instalar nada)

### GitHub Actions (Gratis):
1. **Subir** el código a GitHub
2. **Crear** `.github/workflows/build.yml`:
```yaml
name: Build Plugin
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - name: Set up JDK 8
      uses: actions/setup-java@v3
      with:
        java-version: '8'
        distribution: 'temurin'
    - name: Build with Maven
      run: mvn clean package
    - name: Upload artifact
      uses: actions/upload-artifact@v3
      with:
        name: plugin-jar
        path: target/*.jar
```

### Replit (Online):
1. **Crear** nuevo Repl con Java
2. **Subir** todos los archivos
3. **Ejecutar**: `mvn clean package`

## Opción 5: Compilación Manual (Avanzado)

```bash
# 1. Descargar Spigot API
wget https://hub.spigotmc.org/nexus/content/repositories/snapshots/org/spigotmc/spigot-api/1.19.4-R0.1-SNAPSHOT/spigot-api-1.19.4-R0.1-20230620.200026-88.jar

# 2. Compilar clases Java
javac -cp "spigot-api-1.19.4-R0.1-20230620.200026-88.jar" -d build src/main/java/com/allinone/*.java src/main/java/com/allinone/*/*.java

# 3. Copiar recursos
cp plugin.yml build/
cp config.yml build/

# 4. Crear JAR
jar cf AllInOnePlugin.jar -C build .
```

## 📁 Estructura Final

Después de compilar, tendrás:
```
AllInOnePlugin-1.0.0.jar  ← Este es tu plugin listo
```

## 🚀 Instalación en el Servidor

1. **Copiar** el .jar a `plugins/` de tu servidor
2. **Reiniciar** el servidor
3. **¡Listo!** El plugin se configurará automáticamente

## ⚠️ Solución de Problemas

### Error: "Could not find or load main class"
- Verificar que `plugin.yml` esté en el JAR
- Verificar que la clase principal exista

### Error: "Unsupported major.minor version"
- Compilar con Java 8
- Verificar versión de Java del servidor

### Error de dependencias:
- Las dependencias son opcionales
- El plugin funciona sin Vault o PlaceholderAPI

## 🎯 Recomendación

**Para principiantes**: Usar IntelliJ IDEA Community (gratis) con Maven
**Para expertos**: Usar línea de comandos con Maven
**Para pruebas rápidas**: Usar GitHub Actions

---

**¡El plugin estará listo para usar en tu servidor de Minecraft!**