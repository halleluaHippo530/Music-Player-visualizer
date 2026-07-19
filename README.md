# CityTone

A single-file music player and audio visualizer that transforms your music into a living, breathing pixel-art cityscape. Buildings pulse to the beat, weather shifts dynamically, seasons cycle, the sun rises behind mountains, and hidden easter eggs drift across the skyline.

## Preview

| Day | Night | Dawn | Rain | Autumn | Winter |
|-----|-------|------|------|--------|--------|
| ![Day](screenshots/01_default_view.png) | ![Night](screenshots/02_night.png) | ![Dawn](screenshots/03_dawn.png) | ![Rain](screenshots/04_rain.png) | ![Autumn](screenshots/05_autumn.png) | ![Winter](screenshots/06_winter_snow.png) |

## Quick Start

1. Open `index.html` in any modern browser
2. Click **Playlist** or **Play** to open the drop zone
3. Drag audio files onto the scene or click **Browse Files**
4. Music starts and the cityscape reacts to every beat

No build tools, no dependencies, no installation. Everything runs in a single HTML file.

## Features

### Music-Reactive Cityscape

- 5 parallax layers of buildings scrolling at independent speeds, each assigned to one of 8 audio frequency bands
- Buildings smoothly animate between 30% and 250% of their base height based on their frequency's energy
- Window lights flicker and illuminate dynamically with the music
- Dense random overlap with zero-gap filling — the skyline stretches 2.5x the screen width

### Day/Night Cycle

- Smooth sun arc across the sky with spherical radial gradient, sunspots, and corona shimmer
- Sun rises from behind the mountain horizon with glow intensifying through Gaussian proximity
- Detailed moon with soft blue-white glow, maria regions, craters, ray system, and accurate phase shadows
- Rotating star field with twinkling and trailing streaks
- 9 sunset/dawn palettes cycling through rose-magenta, tropical gold, volcanic red, and more
- Cosine-eased transitions for silky-smooth day-to-night shifts

### Dynamic Weather

- 10 cloud types with unique size, shape, position, and speed
- 16 weather conditions with natural transitions: clear sky, rain, snow, fog, thunderstorms, dust storms, hail
- Rain with diagonal wind-angled streaks, splash dots, and mist
- Snow with star-shaped flakes, wind gusts, and whiteout overlay in blizzards
- Snow accumulation on building rooftops
- Rainy weather causes flooding with water level rise
- Lightning strikes with screen shake

### Seasons

- Spring, summer, autumn, winter with smooth blending transitions
- Autumn shortens daytime hours; winter brightens nighttime illumination
- Season-specific particles: cherry blossoms, falling leaves, frost sparkles
- Vegetation changes: green canopies, golden leaves, bare branches with snow
- Street trees and parks with 5 distinct tree shapes respond to seasonal changes

### Ships on the Water

- **Spanish Galleon Flagship**: 3-masted square-rigger with dramatically billowing white sails, ornate stern castle with gallery windows, forecastle with bowsprit, 10 gunports, rigging lines, and a red flag — sails respond with multi-frequency wind gusts and bezier-curved belly shapes
- **Modern Cruise Liner**: Navy blue hull, white superstructure with 8 passenger decks, twin funnels with navy caps and dynamic smoke puffs, turquoise swimming pool with sun loungers, orange lifeboats, bridge with angled windshield and wings, forward and aft masts
- Ships face their travel direction and follow randomized water surface tracks
- Only 1 cruise liner at a time; up to 2 galleons simultaneously

### Ferris Wheel

- Giant observation wheel randomly appearing near the waterfront in the foreground layer
- Bright white structure with 16 spokes, double rim, and concentric hub
- 16 enclosed white gondola cabins with warm window glow at night
- Animated LED light shows: 64 outer rim lights (3-color chasing), 32 mid-ring lights, 16 inner ring lights, hub ring lights, and support leg lights
- Parallax scrolling with the foreground layer
- Idle rotation speed increases when music is playing
- Water reflections at night

### Easter Eggs

- **Famous buildings**: Oriental Pearl Tower, Tokyo TV Tower, Burj Khalifa, CCTV Headquarters, Golden Gate Bridge, Eiffel Tower, Forbidden City, Summer Palace — randomly placed when city-pop music plays
- **UFO** with tractor beam abducting road vehicles
- **Airplanes** with contrails and blinking navigation lights
- **Asteroids** with fiery tails
- **Zeppelin** with silver envelope and gondola cabin
- **Fireworks** with rockets, multi-color explosions, and flash glow
- **Modern arch bridges** in 3 styles: cable-stayed, parabolic, tied-arch
- Famous buildings feature night flashing lights and laser beams

### Holiday Events

- **Mid-Autumn Festival**: Brightest full moon, bird couple silhouette, V-formation flock
- **Christmas Eve**: Santa Claus with reindeer, sleigh, gift bag, and magic dust trail

### Urban Details

- High-speed bullet train with aerodynamic nose on elevated viaduct, catenary poles
- Multi-lane roads with traffic, headlights, and taillights
- Street lamps with light cones at night
- Parks with season-responsive trees, bushes, benches, and paths
- TV towers with blinking aviation beacons
- Jetties with wooden decks, railings, and mooring posts
- Seawalls with stone block pattern and drainage pipes

### Water

- Composite wave surface with slow tides
- Water reflections of buildings and celestial bodies
- Sky reflection band, sun sparkles, and expanding ripples

### Aurora Borealis

- Animated aurora curtains visible only during winter night under clear sky
- 5-8 independent curtain straps with unique wave frequency, hue, and drift
- Multi-frequency wave motion for organic flowing movement
- Music energy brightens aurora intensity by up to 35%

### Audio Player

- Full playlist management with drag-and-drop file support
- Large drop zone for easy file adding
- Shuffle and repeat modes
- Volume control and track name display
- Save/Load playlist to localStorage

## Technical Architecture

- **Rendering**: HTML5 Canvas 2D — `fillRect`, `arc`, `bezierCurveTo`, gradient fills, pixel-art scale
- **Audio**: Web Audio API `AnalyserNode` for real-time FFT frequency data (8 bands)
- **Performance**: Gradient caching, `fillRect` batching by color, stroke path batching
- **Weather State Machine**: Weighted adjacency graph with cosine-eased transitions
- **Season System**: Sequential cycle with smooth blend interpolation
- **Parallax**: 5 cityscape layers with independent scroll speeds, endless wrapping
- **Celestial Mechanics**: Sun rises from behind mountains, moon follows star disk

## File Structure

```
index.html                  Main application (CityTone)
LaunchPulse.html            Source file (Pulse of Time variant)
screenshots/                Preview images
citytone-intro/             Intro page with screenshots
development-guide/         Development guide
```

## Browser Support

- Chrome 80+
- Firefox 80+
- Safari 14+
- Edge 80+

## License

MIT
