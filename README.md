# Claude Logo Animation

An interactive, organic star logo animation built with vanilla HTML, CSS, and JavaScript. The logo features dynamically generated rays that respond to mouse movement with smooth scaling animations and realistic physics-based interactions.

![Claude Logo Animation Demo](https://img.shields.io/badge/Demo-Interactive-brightgreen)

## Features

- **Procedural Ray Generation**: 14 unique rays with organic variations in length, width, and curvature
- **Interactive Mouse Response**: Rays extend and contract based on cursor proximity and alignment
- **Smooth Physics**: Distance-based falloff and angular relationship calculations for natural movement
- **Organic Design**: Each ray has unique characteristics for visual diversity
- **Performance Optimized**: Efficient SVG rendering with CSS transforms
- **Responsive**: Maintains consistent behavior across different container sizes

## Demo

Simply open `claude-logo-animation.html` in any modern web browser to see the animation in action. Move your mouse around the logo to watch the rays dynamically respond to your cursor position.

## Technical Implementation

### Core Animation System

The animation system is built around three key concepts:

1. **Interaction Zones**: Three distinct behavioral regions based on distance from center
   - Inside star radius: No reaction (stable core)
   - Between star and influence radius: Dynamic scaling
   - Outside influence radius: No reaction (out of range)

2. **Ray Alignment Detection**: Uses dot product calculations to determine which ray most closely aligns with the mouse direction vector

3. **Organic Scaling**: Primary, neighboring, and opposite rays scale differently based on their relationship to the cursor

### Key Components

- **Procedural Generation**: SVG paths are mathematically generated using perpendicular vectors for consistent width
- **Organic Variations**: Each ray has unique multipliers for length, width, and curvature
- **Coordinate Transformation**: Seamless conversion between DOM and SVG coordinate spaces
- **Smooth Animations**: CSS transitions with optimized easing for natural movement

## Browser Compatibility

- **Chrome**: 60+
- **Firefox**: 55+
- **Safari**: 12+
- **Edge**: 79+

Requires support for:
- SVG 1.1
- CSS transforms
- ES6 features (const, let, arrow functions)

## File Structure

```
├── claude-logo-animation.html    # Main application file
└── README.md                     # Project documentation
```

## Customization

### Animation Parameters

Modify these constants in the JavaScript section to customize the behavior:

```javascript
const maxExtension = 40;        // Maximum ray extension in pixels
const influenceRadius = 160;    // Mouse influence range
const rayCount = 14;            // Number of rays
const baseRayLength = 70;       // Base length of each ray
```

### Visual Styling

Update the CSS variables to change the appearance:

```css
.star-line {
    fill: #e07b53;              /* Ray color */
    transition: all 0.15s ease-out; /* Animation timing */
}

body {
    background: #1a1a1a;        /* Background color */
}
```

### Ray Variations

Modify the `rayVariations` array to change the organic characteristics:

```javascript
{ lengthMult: 1.2, widthMult: 0.9, curve: 0.3 }
```

- `lengthMult`: Length multiplier (0.7-1.3 recommended)
- `widthMult`: Width multiplier (0.7-1.3 recommended)  
- `curve`: Curvature factor (-0.4 to 0.4 recommended)

## Performance Notes

- Uses CSS transforms for hardware acceleration
- Minimal DOM manipulation during animations
- Efficient mathematical calculations with cached values
- Optimized for 60fps performance on modern devices

## Development

The project uses vanilla web technologies with no build process required. Simply edit the HTML file and refresh your browser to see changes.

### Code Structure

- **HTML**: Minimal semantic structure with SVG container
- **CSS**: Responsive layout with custom cursor and smooth transitions
- **JavaScript**: Modular functions for ray generation, mouse tracking, and animation logic

## License

MIT License - feel free to use this code in your own projects.

## Acknowledgments

- Anthropic lol
