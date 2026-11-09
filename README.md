# Space Habitat Designer

An interactive 2D aerospace architecture simulator built with Phaser.js. Design, configure, and evaluate life-support habitats across microgravity and planetary surface mission profiles.

## Overview

Space Habitat Designer provides an interactive canvas where space architects can arrange specialized habitat modules inside pressurized hull enclosures. The application features real-time collision detection, structural boundary verification, life-support metrics calculation, and an automated engineering advisory system that enforces mission viability constraints.

## Key Features

- **Interactive Drag-and-Drop Canvas**: Real-time placement and repositioning of modular habitat compartments powered by the Phaser 3 game framework.
- **Dynamic Boundary & Collision Validation**: Real-time Euclidean distance and bounding-box validation preventing module overlaps and hull breach placements.
- **Real-Time Architectural Feedback**:
  - Valid placements highlight with an active green outline and glow.
  - Invalid placements (overlapping modules or hull breaches) highlight in red.
- **Engineering Metrics Engine**:
  - **Crew Supported**: Cumulative crew capacity calculated from validly deployed modules.
  - **Valid Module Count**: Tally of structurally compliant compartments.
  - **Floor Area Utilization**: Percentage of total usable hull interior area consumed.
  - **Crew Efficiency**: Calculated ratio of crew capacity to active module count.
- **Rule-Based Design Advisory System**:
  - Warns when essential compartments (such as Sleep Pods or Command Centers) are missing.
  - Flags hazardous environmental proximities (such as hygiene facilities within 100px of food preparation areas).
  - Evaluates readiness when maximum crew capacity is reached.

## Mission Profiles

The designer includes three pre-configured mission scenarios, each with distinct geometry and environmental constraints:

| Mission | Environment | Geometry | Dimensions | Description |
| :--- | :--- | :--- | :--- | :--- |
| **Transit Station** | Microgravity | Circular Hull | Radius: 250 px | Optimized for orbital platforms and deep-space interplanetary transit vehicles. |
| **Moon Base** | Lunar Surface ($1/6g$) | Rectangular Hull | $400 \times 300$ px | Low-gravity lunar surface outpost layout. |
| **Mars Base** | Martian Surface ($3/8g$) | Rectangular Hull | $500 \times 350$ px | High-volume habitat designed for long-duration expeditionary crews. |

## Module Specifications

Each module fulfills a specialized operational function with designated dimensions and crew accommodation ratings:

| Module | Function | Dimensions | Crew Capacity |
| :--- | :--- | :--- | :--- |
| **Sleep Pod** | Crew quarters and circadian rest stations | $60 \times 60$ px | +2 Crew |
| **Command Center** | Mission avionics, navigation, and external telemetry | $50 \times 50$ px | +1 Crew |
| **Exercise Area** | Zero-gravity cardiovascular and musculoskeletal countermeasure rigs | $55 \times 55$ px | +1 Crew |
| **Kitchen** | Food storage, hydration, and meal preparation galley | $50 \times 50$ px | +1 Crew |
| **Hygiene** | Waste management, water recovery, and personal sanitation | $40 \times 40$ px | +1 Crew |
| **Storage** | Consumables, spare avionics, and life-support buffer stock | $45 \times 45$ px | +0 Crew |

## Architecture & Technical Stack

- **Game Engine**: [Phaser.js 3.70.0](https://phaser.io/) via CDN
- **Rendering Context**: HTML5 Canvas (`Phaser.AUTO`)
- **UI & HUD**: Monospaced HUD overlays rendered dynamically on the Phaser canvas, with external DOM controls for mission selection and state resets.
- **Dependencies**: Zero build dependencies, bundlers, or package installations required.

## Project Structure

```text
space-habitat-designer/
├── index.html    # Complete application (Phaser canvas, logic, UI styles, and simulation rules)
├── README.md     # Project documentation
└── LICENSE       # Project license
```

## Getting Started

### Prerequisites

A modern web browser with HTML5 Canvas and WebGL support (e.g., Google Chrome, Mozilla Firefox, Microsoft Edge, or Safari).

### Local Execution

1. **Clone the repository**:
   ```bash
   git clone https://github.com/K4l1C0d3x/space-habitat-designer.git
   cd space-habitat-designer
   ```

2. **Launch the simulator**:
   - Open `index.html` directly in any web browser, or
   - Serve using a local static file server:
     ```bash
     # Using Python
     python -m http.server 8000
     ```
     Navigate to `http://localhost:8000` in your browser.

## How to Use

1. **Select Mission Profile**: Use the dropdown menu in the top-left control panel to switch between **Transit Station**, **Moon Base**, or **Mars Base**.
2. **Add Modules**: Click any colored module icon in the right-hand palette to spawn a compartment into the center of the habitat.
3. **Position Modules**: Click and drag modules into position inside the habitat boundaries.
4. **Monitor Feedback**:
   - Ensure outlines turn **green** (valid position).
   - Check the **Metrics HUD** on the left for crew capacity and floor area usage.
   - Follow recommendations displayed in the **Design Advice** panel to resolve safety and mission-readiness warnings.
5. **Reset**: Use the **Reset** button in the control panel to clear all placed modules.

## Credits

Designed and developed by **Kalidas kj & christy abraham**.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
