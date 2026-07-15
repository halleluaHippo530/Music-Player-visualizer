# CityTone

A music-reactive cityscape visualizer that transforms your audio into a living, breathing urban panorama. Buildings pulse to the beat, weather shifts dynamically, seasons change, and hidden easter eggs drift across the skyline.

## Features

**Music-Reactive Skyline**
- Buildings across 5 parallax layers respond to 8 frequency bands from the audio spectrum
- Each building is assigned a specific frequency range and smoothly animates between 30% and 250% of its base height
- Window lights flicker and illuminate dynamically with the music's energy
- Every building type reacts: skyscrapers, factories, construction cranes, harbors, TV towers, parks, jetties, and seawalls

**Dynamic Weather System**
- 16 weather conditions with natural transitions: clear sky, rain, snow, fog, thunderstorms, dust storms, hail, and more
- Enhanced rain: diagonal wind-angled streaks, splash dots on water, mist streaks in heavy weather
- Enhanced snow: star-shaped flakes, wind gusts, whiteout overlay in blizzards
- Tyndall effect (crepuscular god rays) during rain, fog, and cloudy conditions
- Layered volumetric fog with moving wisps and ground-level density
- Rain splashes, hail bouncing, snow drifting, and lightning strikes with screen shake

**Seasons**
- Spring, summer, autumn, winter cycle with smooth blending transitions
- 5 distinct tree shapes in parks: round, conical, columnar, weeping willow, flat-topped
- Vegetation changes: green canopies in summer, golden leaves in autumn, bare branches with snow in winter
- Sky colors, ambient lighting, and overall mood shift with each season
- Season-specific particles: cherry blossoms, falling leaves, frost sparkles

**Easter Eggs**
- UFO with tractor beam that abducts road vehicles
- Commercial airplanes with contrails and blinking navigation lights
- Glowing asteroids with fiery tails
- Gigantic cruise ship with astonishing nighttime illumination (48 cabin windows, deck lights, spotlight beams)
- Cargo ship with colored shipping containers and crane boom
- Tourist cruiser with glass observation decks and blue LED promenade
- Ferry with car deck, vehicle ramp, and tiny cars
- Zeppelin airship with silver envelope, gondola cabin, and tail fins
- Ferris wheel with 8 colored gondolas, rotating rim lights
- Fireworks display with rockets, explosions, and full-screen flash glow
- Modern arch bridges (3 styles: cable-stayed, parabolic, tied-arch)
- All appear randomly and add surprise moments to the scene

**Day/Night Cycle**
- Smooth sun arc across the sky with a large detailed sun (corona, sunspots)
- Detailed moon with craters, maria, and phase shadow
- Rotating star field around the moon with magnitude distribution and trailing streaks
- 6 randomized sunset/dawn palettes: Rose-Magenta, Tropical Gold-Pink, Volcanic Red-Violet, Arctic Teal-Lavender, Desert Amber-Rose, Twilight Violet-Indigo
- Golden hour warm overlay at dawn and dusk

**Urban Details**
- High-speed bullet train with aerodynamic nose on elevated viaduct
- Multi-lane roads with traffic, headlights, and taillights
- Street lamps on all roads with light cones at night
- Parks with season-responsive trees, bushes, benches, and paths
- TV towers with blinking aviation beacons
- Jetties with wooden decks, railings, mooring posts, and small boats
- Seawalls with stone block pattern, drainage pipes, chain fences, and algae

**Water**
- 5 ship types cruising on water: small, medium, large, speedboat, sailboat
- Expanding ripples with 4 shapes (circles, wide ellipses, tall ellipses, diamonds)
- Tides with slow rise/fall and composite wave surface
- Water reflections of buildings and celestial bodies
- Sky reflection band on wave surface
- Sparkles on water during sunny conditions

**Audio Player**
- Full playlist management with drag-and-drop file support
- Large drop zone for easy file adding when playlist is empty
- "Add Music" quick bar always visible when playlist has tracks
- Auto-opens playlist panel when first tracks are added
- Shuffle and repeat modes
- Volume control
- Track name display
- Save/Load playlist to localStorage

## How to Use

1. Open `index.html` in any modern browser
2. Press **Play** or click **Playlist** -- a drop zone appears for adding music
3. Drag audio files onto the scene or the playlist panel, or click **Browse Files**
4. Music starts automatically, and the cityscape reacts to every beat

No build tools, no dependencies, no installation. A single HTML file.

## Technical Architecture

- **Rendering**: HTML5 Canvas 2D, all drawing done with `fillRect`, `arc`, `bezierCurveTo`, and gradient fills
- **Audio**: Web Audio API `AnalyserNode` for real-time FFT frequency data
- **Performance**: Caches gradients by key, uses seeded RNG for deterministic city generation, throttles weather particle updates
- **State Machine**: Weather transitions follow a weighted neighbor graph, seasons cycle sequentially
- **Parallax**: 5 cityscape layers with independent scroll speeds (0.05x to 0.5x)

## Browser Support

- Chrome 80+
- Firefox 80+
- Safari 14+
- Edge 80+

## License

MIT
