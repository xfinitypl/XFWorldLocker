# XFWorldLocker

Advanced world management plugin for CosmicSMP developed for PaperSpigot 1.21.5

## 📋 Main Features

### 🌍 Area Management
- **Boundary definition**: Configure rectangular areas using X and Z coordinates
- **Automatic teleportation**: Players are sent to world spawn when leaving the allowed area
- **Multiverse integration**: Uses Multiverse commands for teleportation

### 🐾 Mob Control
- **Configurable spawning**: Enable/disable mob spawning per world
- **Automatic cleanup**: Automatic removal of existing mobs (except villagers and Armor Stands)
- **Protected entities**: Villagers, Armor Stands, Item Frames and NPCs are always protected

### 🔨 Building Permissions
- **Break blocks**: Configure if players can break blocks
- **Place blocks**: Configure if players can place blocks
- **Creative mode**: Creative players can always build

### 🎯 Interaction Control
- **Block interactions**: Configure access to chests, doors, barrels, etc.
- **NPCs always accessible**: Villagers and custom NPCs are always interactable
- **Plugin compatibility**: Compatible with FancyNPCs and other NPC plugins

### 💥 Explosion Protection
- **Damage prevention**: Explosions cannot break blocks
- **Creative exception**: If there's a creative player nearby, explosions work normally

## ⚙️ Configuration

### config.yml
```yaml
worlds:
  spawn_world:
    name: "world"               # Exact world name
    area:
      x1: -100                  # Minimum X coordinate
      z1: -100                  # Minimum Z coordinate  
      x2: 100                   # Maximum X coordinate
      z2: 100                   # Maximum Z coordinate
    spawnMobs: false           # Allow mob spawning
    canBreakBlocks: false      # Allow breaking blocks
    canPlaceBlocks: false      # Allow placing blocks
    canInteract: false         # Allow interactions
```

## 🎮 Commands

| Command | Description | Permission |
|---------|-------------|---------|
| `/xfworldlocker reload` | Reload configuration | `xfworldlocker.admin` |
| `/xfworldlocker list` | List all managed worlds | `xfworldlocker.admin` |
| `/xfworldlocker info [world]` | Show world information | `xfworldlocker.admin` |
| `/xfworldlocker check` | Check your current position | `xfworldlocker.admin` |

**Aliases**: `xfwl`, `worldlocker`

## 🔐 Permissions

| Permission | Description | Default |
|---------|-------------|-------------|
| `xfworldlocker.*` | Full access | `op` |
| `xfworldlocker.admin` | Admin commands | `op` |
| `xfworldlocker.bypass` | Bypass all restrictions | `false` |

## 📦 Installation

1. **Download dependencies**: Make sure you have Multiverse-Core installed
2. **Compile**: Run `mvn clean package`
3. **Install**: Place the JAR in the `plugins/` folder
4. **Configure**: Edit `plugins/XFWorldLocker/config.yml`
5. **Restart**: Restart the server or use `/xfworldlocker reload`

## 🔧 Dependencies

- **PaperSpigot 1.21.5** (or compatible)
- **Multiverse-Core 4.3.1+**
- **Java 17+**

## 📝 Important Notes

### Special Behaviors
- **Y coordinates**: Not considered, only X and Z define the area
- **Case Sensitive**: World names must match exactly
- **Creative Mode**: Can always build, regardless of configuration
- **Protected Entities**: Villagers, Armor Stands and Item Frames are never removed

### Compatibility
- ✅ **FancyNPCs**: NPCs with custom names are always interactable
- ✅ **Multiverse**: Full integration for teleportation
- ✅ **WorldEdit/WorldGuard**: Compatible (doesn't interfere)

## 🚀 Technical Features

- **Modular architecture**: Classes organized by functionality
- **Efficient management**: Automatic mob cleanup every 60 seconds
- **Optimized**: Only checks movement when block position changes
- **Informative logs**: Logging system with XF prefix
- **Hot configuration**: Reload without server restart

## 👥 Support

For technical support or bug reports, contact the CosmicSMP development team.

---

**Developed by**: CosmicSMP Development Team  
**Version**: 1.0.0  
**Compatible with**: PaperSpigot 1.21.5
