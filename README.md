# Web Raycasting Engine

A browser-based raycasting engine that brings the classic 3D rendering technique to the web. This project implements a Wolfenstein 3D-style raycaster entirely in JavaScript, allowing you to experience retro 3D graphics directly in your browser.

## 🎮 Demo

**Live Demo**: [https://web-raycasting-engine.vercel.app/](https://web-raycasting-engine.vercel.app/)

**GitHub Repository**: [https://github.com/Euclidae/Web-Raycasting-Engine](https://github.com/Euclidae/Web-Raycasting-Engine)

## 🚀 Features

- **Pure JavaScript Implementation**: Built with p5.js for graphics and canvas manipulation
- **Real-time Rendering**: Smooth 60fps raycasting performance
- **Interactive Controls**: WASD movement and mouse look
- **Textured Walls**: Support for wall textures and sprites
- **Minimap**: 2D overhead view for navigation
- **Configurable Maps**: Easy-to-modify level layouts
- **Cross-platform**: Runs in any modern web browser

## What is Raycasting?

Raycasting is a rendering technique that creates a 3D perspective from a 2D map by casting rays from the player's position to determine what should be drawn on each vertical line of the screen. This technique was famously used in early 3D games like Wolfenstein 3D and Doom, making it possible to achieve 3D graphics on limited hardware.

## 🎓 Educational Acknowledgment

This project was inspired by and builds upon the excellent educational content provided by **Gustavo Pezzi**. His comprehensive raycasting course on Pikuma provides an outstanding foundation for understanding the mathematics and implementation details behind raycasting engines.

**Recommended Learning Resource:**
- [Raycasting Engine Programming with JavaScript](https://pikuma.com/courses/raycasting-engine-tutorial-algorithm-javascript) by Gustavo Pezzi
- Gustavo Pezzi's website: [pikuma.com](https://pikuma.com/)

Gustavo Pezzi is a university lecturer in London, UK, who has won multiple education awards as a teacher and is the founder of pikuma.com. His courses are known for being beginner-friendly while never skipping the mathematical foundations.

## Technical Foundation

This web implementation uses **p5.js** for graphics rendering and canvas manipulation, providing a clean and intuitive API for drawing operations and input handling.

**p5.js**: A JavaScript library that makes coding accessible for artists, designers, educators, and beginners. Learn more at [p5js.org](https://p5js.org/)

## Implementation Notes

This web implementation is based on concepts from **[Raycaster-RS](https://github.com/Euclidae/raycaster-rs)**, a Rust-based desktop raycasting engine that I implemented independently. The core algorithms and mathematical foundations remain consistent between both implementations, with this version adapted specifically for web browsers using p5.js for graphics handling.

The Rust version serves as a desktop application, while this JavaScript implementation brings the same raycasting technology to the web with an accessible, browser-based interface.

## 🛠Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Euclidae/Web-Raycasting-Engine.git
   cd Web-Raycasting-Engine
   ```

2. **Serve the files:**
   Since this uses ES6 modules, you'll need to serve the files through a web server:
   ```bash
   # Using Python 3
   python -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server
   
   # Using PHP
   php -S localhost:8000
   ```

3. **Open in browser:**
   Navigate to `http://localhost:8000` in your web browser.

## 🎮 Controls

- **W, A, S, D**: Move forward, left, backward, right
- **Arrow Keys**: Look left and right
- **Mouse**: Look around (click to enable mouse look)
- **M**: Toggle minimap visibility
- **ESC**: Release mouse lock

## 🔧 Technical Details

### Core Components

- **Ray Casting Algorithm**: Implements DDA (Digital Differential Analyzer) for efficient wall detection
- **Texture Mapping**: Applies textures to walls with proper perspective correction
- **Sprite Rendering**: Renders 2D sprites in 3D space with depth sorting
- **Player Movement**: Smooth movement with collision detection
- **Minimap System**: Real-time 2D representation of the player's position and orientation

### Performance Optimizations

- **Efficient Ray Casting**: Only casts rays for visible screen columns
- **Texture Caching**: Pre-loads and caches all textures for smooth rendering
- **Collision Detection**: Fast grid-based collision system
- **Frame Rate Management**: RequestAnimationFrame for smooth 60fps rendering

## Project Structure

```
Web-Raycasting-Engine/
├── index.html              # Main HTML file with p5.js integration
├── raycast.js              # Core raycasting engine implementation
├── p5.js                   # p5.js library for graphics and input
├── styles.css              # Basic styling for the web interface
└── README.md
```


### Creating Custom Maps

Maps are defined as 2D arrays where:
- `0` represents empty space
- `1-9` represent different wall types
- Higher numbers can represent different textures

```javascript
const customMap = [
    [1,1,1,1,1,1,1,1],
    [1,0,0,0,0,0,0,1],
    [1,0,2,0,0,3,0,1],
    [1,0,0,0,0,0,0,1],
    [1,1,1,1,1,1,1,1]
];
```


## Contributing

Contributions are welcome! Whether it's bug fixes, performance improvements, new features, or documentation updates, feel free to submit a pull request.

##  Learning Resources

If you're interested in learning more about raycasting and game development:

- [Gustavo Pezzi's Raycasting Course](https://pikuma.com/courses/raycasting-engine-tutorial-algorithm-javascript)
- [Lode's Computer Graphics Tutorial](https://lodev.org/cgtutor/raycasting.html)
- [Wolfenstein 3D's Source Code](https://github.com/id-Software/wolf3d)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Gustavo Pezzi** for his excellent educational content on raycasting algorithms at [Pikuma](https://pikuma.com/)
- **p5.js Foundation** for creating an accessible and powerful graphics library
- **id Software** for pioneering the raycasting technique in Wolfenstein 3D
- **Lode Vandevenne** for the comprehensive raycasting tutorial
- The game development community for continued innovation in retro rendering techniques

---

*Built with ❤️ for the web and the love of retro gaming*
