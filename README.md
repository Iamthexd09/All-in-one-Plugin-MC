# All-in-One Plugin para Minecraft

## Descripción
Plugin completo que incluye teletransporte, economía, tienda, subastas, crates, rangos, protecciones y mucho más.

## Dependencias

### Dependencias Obligatorias
**NINGUNA** - El plugin funciona completamente independiente.

### Dependencias Opcionales (Recomendadas)
- **Vault** (Opcional): Para integración con otros plugins de economía
- **PlaceholderAPI** (Opcional): Para usar placeholders en otros plugins

## Funcionalidades Incluidas

### ✅ Sistema de Economía Propio
- Base de datos SQLite integrada
- Comandos: `/money`, `/pay` (mínimo $10)
- **Sistema /withdraw**: Convierte dinero en billetes físicos
- Balance inicial de $1000 para nuevos jugadores
- **NO requiere Vault** (pero es compatible)

### ✅ Sistema de Teletransporte
- `/tpa <jugador>` - Solicitar teletransporte a un jugador
- `/tpaccept [jugador]` - Aceptar solicitud de teletransporte
- `/tpacancel [jugador]` - Rechazar/cancelar solicitud
- `/rtp` - Teletransporte aleatorio seguro
- `/spawn` - Ir al spawn del servidor
- Verificación de protecciones automática

### ✅ Sistema de Homes y Warps
- `/sethome [nombre]` - Establecer casa
- `/home [nombre]` - Ir a casa
- `/setwarp <nombre>` - Crear warp (admin)
- `/warp <nombre>` - Usar warp

### ✅ Piedras Protectoras
- **Mena de Carbón Encantada**: Protección Ultimate ($30,000 - 21x21 área)
- **Bloque de Diamante**: Protección Premium ($15,000 - 15x15 área)
- **Bloque de Esmeralda**: Protección VIP ($8,000 - 12x12 área)
- **Bloque de Oro**: Protección Gold ($3,000 - 10x10 área)
- **Bloque de Hierro**: Protección Básica ($1,000 - 8x8 área)
- **Completamente personalizable** desde `protections.yml`

### ✅ Sistema de Tienda
- `/shop` - Abrir tienda gráfica
- Compra y venta de items
- Precios configurables

### ✅ Casa de Subastas
- `/ah` - Casa de subastas estilo NexusAuctionHouse
- `/ah sell <precio> [cantidad]` - Vender items
- Aliases: `/auctionhouse`, `/auch`
- Sistema de pujas en tiempo real
- Interfaz gráfica profesional

### ✅ Sistema de Crates
- `/crate` - Abrir GUI de crates (estilo ExcellentCrates)
- Crates: básico ($100), premium ($500), legendario ($2000)
- Animación de apertura profesional
- Sistema de rareza con colores
- Anuncios automáticos para premios raros

### ✅ Encantamientos Custom
- **Lightning** - Invoca rayos al atacar
- **Explosive** - Causa explosiones
- **Vampire** - Roba vida del enemigo
- **Freeze** - Congela enemigos
- **Poison** - Envenena enemigos
- **Speed** - Otorga velocidad
- **Jump** - Impulsa enemigos
- **Blind** - Ciega enemigos
- **Fire** - Fuego intenso
- **Teleport** - Teletransporta enemigos

### ✅ Sistema de Rangos y Chat
- Rangos: Usuario, VIP, Premium, Admin
- `/nick <nombre>` - Cambiar nickname
- `/chatcolor <código>` - Colores en chat (&1, &2, etc.)
- Prefijos y sufijos personalizables

### ✅ Sistema de Kits
- `/kit` - Abrir GUI de kits (estilo PlayerKits2)
- Kits: starter, vip, premium, pvp con cooldowns
- Interfaz gráfica con preview de items
- Sistema de cooldowns visual

### ✅ Sistema de Mochila
- `/backpack` - Abrir mochila personal
- Inventario expandido
- Tamaño configurable

### ✅ Scoreboard en Tiempo Real
- Información del jugador
- Balance actualizado
- Rango y estadísticas
- Jugadores online
- Hora actual

### ✅ Sistema de NPCs
- `/npc crear` - Crear NPC
- `/npc eliminar` - Eliminar NPC
- NPCs interactivos

## Instalación

1. **Descargar el plugin** (archivo .jar compilado)
2. **Colocar en** `plugins/` de tu servidor
3. **Reiniciar** el servidor
4. **¡Listo!** - Los nuevos jugadores recibirán kit inicial automáticamente

## Instalación Opcional de Dependencias

### Para Vault (Opcional)
```bash
# Descargar Vault desde:
# https://www.spigotmc.org/resources/vault.34315/
```

### Para PlaceholderAPI (Opcional)
```bash
# Descargar PlaceholderAPI desde:
# https://www.spigotmc.org/resources/placeholderapi.6245/
```

## Configuración

El archivo `config.yml` se genera automáticamente con valores por defecto. Puedes modificar:

- Balance inicial de jugadores ($5,000 por defecto)
- Precios de tienda
- Cooldowns de kits
- Piedras de protección (desde `protections.yml`)
- Mensajes del plugin
- Y mucho más...

## Kit Inicial para Nuevos Jugadores

Los nuevos jugadores reciben automáticamente:
- 💰 **$5,000** de saldo inicial
- 🛡️ **Armadura de hierro completa** con Protección I
- ⚔️ **Espada de hierro** con Filo I
- 🔧 **Herramientas completas** (pico, hacha, pala con Eficiencia I)
- 🌾 **Azada de hierro** con Fortuna I
- 🥩 **64 carnes de cerdo** cocidas
- 🛡️ **Piedra de protección de carbón** ($30,000 de valor)

## Permisos

### Permisos Básicos (Por defecto: true)
- `allinone.tpa` - Solicitar teletransporte
- `allinone.tpaccept` - Aceptar teletransporte
- `allinone.tpacancel` - Cancelar teletransporte
- `allinone.home` - Usar homes
- `allinone.shop` - Usar tienda
- `allinone.rtp` - Usar RTP
- `allinone.kit` - Usar kits
- `allinone.warp` - Usar warps
- `allinone.nick` - Cambiar nick
- `allinone.chatcolor` - Usar colores en chat
- `allinone.spawn` - Usar spawn
- `allinone.withdraw` - Retirar dinero

### Permisos de Administrador (Por defecto: op)
- `allinone.rank` - Manejar rangos
- `allinone.npc` - Manejar NPCs
- `allinone.setspawn` - Establecer spawn
- `allinone.*` - Todos los permisos

## Comandos Principales

```
/tpa <jugador>         - Solicitar teletransporte a un jugador
/tpaccept [jugador]    - Aceptar solicitud de teletransporte
/tpacancel [jugador]   - Rechazar/cancelar solicitud
/sethome [nombre]      - Establecer casa
/home [nombre]         - Ir a casa
/shop                  - Abrir tienda gráfica
/ah [sell <precio> [cantidad]] - Casa de subastas
/crate [tipo]          - Abrir GUI de crates o crate específico
/backpack              - Abrir mochila
/rtp                   - Teletransporte aleatorio
/kit [nombre]          - Abrir GUI de kits o kit específico
/warp <nombre>         - Usar warp
/nick <nombre>         - Cambiar nickname
/chatcolor <código>    - Cambiar color del chat
/money                 - Ver dinero
/pay <jugador> <cantidad> - Pagar a jugador
/spawn                 - Ir al spawn del servidor
/setspawn              - Establecer spawn (admin)
/withdraw <cantidad>   - Retirar dinero como billete físico
```

## Soporte

- **Versión de Minecraft**: 1.19+
- **Servidor**: Bukkit/Spigot/Paper
- **Base de datos**: SQLite (incluida)
- **Dependencias**: Ninguna obligatoria

## Características Técnicas

- ✅ **Completamente independiente**
- ✅ **Base de datos SQLite integrada**
- ✅ **Sin dependencias obligatorias**
- ✅ **Configuración automática**
- ✅ **Scoreboard en tiempo real**
- ✅ **Sistema de protecciones**
- ✅ **Interfaz gráfica**
- ✅ **Código optimizado**
- ✅ **Fácil instalación**
- ✅ **Encantamientos custom únicos**

---

**¡El plugin está listo para usar sin necesidad de instalar nada más!**

Te deseo suerte!!!! Atte. Becmxx09

*El plugin ha sido desarrollado en Bolt.new*