# Hercule - Action Roguelike Game

A 2D action roguelike game developed in Java with libGDX, playing as Hercules in a procedural dungeon filled with enemies and challenges.

## Technologies

- **Language**: Java 21
- **Framework**: libGDX (Desktop LWJGL3)
- **Build**: Gradle 8.x
- **Assets**: 2D sprites, animations, sound effects
- **Architecture**: MVC pattern, component system

## Features

### Gameplay
- Fluid movement and dash dodge
- Melee combat system with impact animations
- Weapon management (multiple swords with different stats)
- Health and damage system with visual feedback
- Inventory with health potions and equipment
- Enemy AI with chase and attack behaviors
- Door system and room progression

### Combat System
- Melee weapons with configurable range and damage
- Attack manager (`AttackManager`) for isolated logic
- Visual impact animations (6 frames)
- Sword sounds and audio effects
- Advanced collision detection
- Attack cooldown and timing

### Graphics & Animations
- Character animations (4 directions: up, down, left, right)
- Enemy animations (Orcs with idle, run, attack)
- Dash visual effects
- Custom animation system (`AnimationHandler`, `SbireAnimationHandler`)
- User interface with health bars and visual inventory
- High-resolution assets for map and elements

### Audio
- Menu and game music
- Game over sound
- Combat sound effects (sword swing, impacts)
- Configurable volume control
- Multi-track management (menu/game/gameover)

### Interface
- Main menu screen
- Pause screen
- Key binding configuration system
- HUD display (health points, inventory)
- Game over screen

### Debugging
- Integrated debug console (`GameDebugger`)
- Real-time logs
- On-the-fly enemy stats modification
- Teleportation and developer commands
- Hitbox and state visualization

## Installation

### Prerequisites

- **JDK 21** or higher
- **Gradle** (included via wrapper)

### Build

```bash
# Clone repository
git clone https://github.com/Alex-Amedro/Projet-long-java.git
cd Projet-long-java

# Build project
./gradlew build

# Run game
./gradlew lwjgl3:run
```

### Executable JAR Build

```bash
# Generate standalone JAR
./gradlew lwjgl3:jar

# JAR located in lwjgl3/build/libs/
java -jar lwjgl3/build/libs/lwjgl3-*.jar
```

## Usage

### Default Controls

- **WASD**: Movement (Up, Down, Left, Right)
- **Space**: Dash/Dodge
- **Left Click**: Attack
- **E**: Open inventory
- **Escape**: Pause

*Keys are remappable in options*

### Gameplay

1. Explore dungeon room by room
2. Fight enemies (Orcs)
3. Collect potions and equipment
4. Manage inventory strategically
5. Use dash to dodge attacks
6. Progress through doors to advance

### Audio Configuration

Adjust volumes in settings:
- Menu music volume: 0.0 - 1.0
- Game sounds volume: 0.0 - 1.0

## Project Structure

```
Projet-long-java/
├── core/src/main/java/projet/java/
│   ├── Main.java              # Game entry point
│   ├── entite/                # Entities (Character, Minion, Weapons)
│   │   ├── Personnage.java
│   │   ├── Sbire.java
│   │   ├── ArmeMelee.java
│   │   └── ComportementSbire.java
│   ├── combat/                # Combat system
│   │   └── AttackManager.java
│   ├── animation/             # Animation handlers
│   │   ├── AnimationHandler.java
│   │   ├── SbireAnimationHandler.java
│   │   └── ImpactEffect.java
│   ├── Map/                   # Map generation and management
│   │   ├── Map.java
│   │   └── Chambre.java
│   ├── Inventaire/            # Inventory system
│   │   ├── Inventaire.java
│   │   ├── Item.java
│   │   └── Potion.java
│   ├── Menu/                  # UI screens
│   │   ├── MenuScreen.java
│   │   └── PauseScreen.java
│   └── debug/                 # Debugging tools
│       └── GameDebugger.java
├── lwjgl3/                    # Desktop platform
├── assets/                    # Resources (sprites, sounds, fonts)
│   ├── Hercule_*.png          # Hero sprites
│   ├── Orc1/                  # Enemy animations
│   ├── map/                   # Map tiles
│   ├── *.mp3, *.wav           # Audio
│   └── *.png                  # UI, items, effects
└── build.gradle               # Gradle configuration
```

## Gradle Tasks

```bash
./gradlew build              # Build entire project
./gradlew lwjgl3:run         # Run game
./gradlew lwjgl3:jar         # Generate executable JAR
./gradlew clean              # Clean builds
./gradlew idea               # Generate IntelliJ project
./gradlew eclipse            # Generate Eclipse project
./gradlew test               # Run tests
```

## Architecture

### Entity System
- **Entite**: Base class for all characters
- **Personnage**: Playable hero (Hercules)
- **Sbire**: Enemies with AI
- **ComportementSbire**: AI patterns (chase, attack)

### Weapon System
- **ArmeBase**: Abstract class for all weapons
- **ArmeMelee**: Swords and melee weapons
- Stats: damage, range, cooldown

### Animation System
- Multi-directional animations
- State machines for fluid transitions
- Visual effects (impacts, dash)

## License

MIT License - see [LICENSE](LICENSE)

## Author

**Alex Amedro** - Looking for M1 internship in Computer Graphics / Game Development
**Lilian Dez**
**Julien Puech**
**Noé Rigolleti**
**Raphael Landry**
**Mathis Magron**

GitHub: [@Alex-Amedro](https://github.com/Alex-Amedro)

---

## Technical Notes

### Performance
- Use of `SpriteBatch` for optimized rendering
- FitViewport for adaptive scaling
- Object pooling to reduce garbage collection

### Future Extensions
- Procedural dungeon generation
- More enemy types
- Boss fights
- Progression/leveling system
- Ranged weapons
- Power-ups and buffs
