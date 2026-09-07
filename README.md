# Network Route Optimizer

An interactive, mobile-friendly demonstration of Dijkstra's shortest-path algorithm for finding the lowest-cost route through a weighted network.

## Overview

Network Route Optimizer is a Design and Analysis of Algorithms (DAA) mini project. It turns the shortest-path calculation into a visual walkthrough so that learners can see how a greedy graph algorithm selects nodes, relaxes edges, and builds the final route.

The demo uses a four-node weighted graph. Starting from node `A`, Dijkstra's algorithm evaluates the available routes and finds the shortest path to node `D`: `A -> C -> D`, with a total cost of `3`.

## Why This Project

Shortest-path algorithms are used in navigation, computer networks, logistics, and many other systems. The arithmetic behind Dijkstra's algorithm is straightforward, but the order of its decisions can be difficult to follow in a static code listing. This project provides a compact visual model that connects the graph, the distance table, the execution log, and the source code in one page.

## Features

- Displays a weighted graph with four nodes and labeled edges.
- Animates Dijkstra's algorithm one decision at a time with **Step Forward**.
- Runs the complete algorithm with **Run Full Algorithm (A -> D)**.
- Resets the graph, tentative distances, and execution log with **Reset**.
- Highlights node visits and distance updates during execution.
- Shows the final shortest route and total route cost.
- Includes the distance-update sequence and time-complexity comparison.
- Provides an expandable C++ implementation that mirrors the visual algorithm.
- Lists common applications, including maps, internet routing, logistics, and smart-city systems.
- Works directly in a browser with no package installation, build process, or backend.

## How Dijkstra's Algorithm Works

The implementation uses non-negative edge weights and follows the standard greedy approach:

1. Set the source distance to `0` and every other distance to infinity.
2. Select the unvisited node with the smallest tentative distance.
3. Mark that node as visited.
4. For each neighbor, calculate a possible shorter distance through the selected node.
5. Replace a neighbor's distance when the new route is shorter.
6. Repeat until the graph has been processed.

For the example graph, the relevant edge weights are:

| Edge | Weight |
| --- | ---: |
| `A -> B` | 4 |
| `A -> C` | 2 |
| `B -> D` | 5 |
| `C -> D` | 1 |

The direct route through `B` costs `4 + 5 = 9`, while the route through `C` costs `2 + 1 = 3`. The visualizer therefore selects `A -> C -> D`.

## Complexity

The included educational implementation uses an array-based search for the next minimum-distance node, giving it a time complexity of `O(V^2)`. A priority-queue implementation can improve this to `O((V + E) log V)` for a sparse graph, where `V` is the number of vertices and `E` is the number of edges.

## Getting Started

### Clone the repository

```bash
git clone https://github.com/mayankswaraj18cr-cmd/Semester--5-Project-.git
cd Semester--5-Project-
```

### Open the demo

Open [index.html](index.html) in any modern web browser. No installation or development server is required.

For a local static server, one option is:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000` in a browser.

## Project Structure

```
.
├── index.html                                  # Complete interactive demo
├── src/                                        # Reserved for extracted source modules
├── assets/                                     # Images and other project assets
├── docs/
│   ├── Dijkstra_Route_Optimizer_Research_Paper.pdf
│   └── Dijkstra_Route_Optimizer_Presentation.pptx
├── .gitignore
├── LICENSE
└── README.md
```

The current demo is intentionally self-contained in `index.html`, including its styles, SVG graph, interface controls, algorithm trace, and JavaScript logic. The `src/` and `assets/` directories are available for future modularization and supporting media.

## Documentation

- [Research Paper](docs/Dijkstra_Route_Optimizer_Research_Paper.pdf) — research, background, and problem framing.
- [Presentation](docs/Dijkstra_Route_Optimizer_Presentation.pptx) — project overview and supporting slides.

## Branches

The repository uses separate branches for stable work, development, documentation, and focused feature work:

- `main` — stable project branch.
- `develop` — integration branch for changes before release.
- `docs/updates` — README, research, and project-documentation updates.
- `feature/graph-controls` — planned graph editing and route-selection controls.
- `feature/visual-improvements` — planned animation and interface improvements.

Create a local feature branch from `develop` before starting a focused change:

```bash
git checkout develop
git pull
git checkout -b feature/your-change
```

## Contributing

1. Create a focused branch from `develop`.
2. Keep changes small and describe the behavior they add or change.
3. Test the page in a desktop and mobile-sized browser window.
4. Confirm that the shortest-path result and reset behavior still work.
5. Update the README when controls, algorithms, or project structure change.
6. Open a pull request against `develop`.

Because the project is dependency-free, a contribution should be testable by opening the page directly or serving the repository with a simple static server.

## Roadmap

- [ ] Allow users to add, remove, and edit graph edges.
- [ ] Add selectable source and destination nodes.
- [ ] Support larger graphs and custom node labels.
- [ ] Add a priority-queue implementation for comparison.
- [ ] Separate the HTML, CSS, and JavaScript into `src/` modules.
- [ ] Add automated browser checks for route results and reset behavior.

## License

MIT — see [LICENSE](LICENSE).

## Contact

Mayank Swaraj — [mayankswaraj18cr@gmail.com](mailto:mayankswaraj18cr@gmail.com)