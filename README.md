````markdown
# Tower of Odyssey: Maze Adventure

**Homer’s Circle** presents an immersive multi‑level console maze game built in C++ with SFML-powered audio.

---

## 📖 Description

**Tower of Odyssey** is a three‑floor maze challenge where the player navigates increasingly complex labyrinths, collects points, and races against time to reach the exit on each level. Your performance is tracked: scores are displayed in real‑time, top scores are saved between sessions, and you can continue an in‑progress game at your last completed floor :contentReference[oaicite:0]{index=0}.

---

## 🎮 Features

- **Three Distinct Levels**  
  - Level 1 (15×15), Level 2 (17×17), Level 3 (19×19) mazes  
- **Smooth Console Animation**  
  - Only the changed portions of the maze are re‑drawn using Windows console cursor positioning  
- **Real‑Time Scoring & Persistence**  
  - Current score updates on every move  
  - High score stored to a file and loaded at startup  
  - Option to continue from last saved floor  
- **Responsive Controls**  
  - Non‑blocking keyboard input with `_kbhit()` / `_getch()` (no “press Enter” delays)  
- **Rich Audio Feedback**  
  - Sound effects for walking, collecting items, and level completion using SFML Audio  
- **Clean Code Architecture**  
  - Dynamic 2D array mazes with `initializeMaze`, `populateMazeX`, and `deleteMaze` routines  
  - Clear separation of game‑logic, rendering, and I/O  
- **Cross‑Platform Foundations**  
  - While optimized for Windows console, core logic is portable C++ and SFML

---

##  Getting Started

### Prerequisites

- **Windows** (for console cursor control)  
- **C++17** compatible compiler (e.g. MSVC, MinGW)  
- **SFML 2.x** (System, Window, Audio modules)

### Building

1. **Clone the repo**  
   ```bash
   git clone https://github.com/<your‑username>/tower‑of‑odyssey.git
   cd tower‑of‑odyssey
````

2. **Configure SFML**

   * Ensure SFML include/lib paths are set for your compiler or IDE.
3. **Compile**

   ```bash
   g++ -std=c++17 src/*.cpp -o TowerOfOdyssey -I<sfml‑include> -L<sfml‑lib> -lsfml-system -lsfml-window -lsfml-audio
   ```
4. **Run**

   ```bash
   ./TowerOfOdyssey
   ```

---

##  Controls

* **W / ↑** : Move Up
* **S / ↓** : Move Down
* **A / ←** : Move Left
* **D / →** : Move Right
* **Q**       : Quit Game
* **Enter**   : Confirm “Continue?” prompt

---

##  Repository Structure

```
/
├─ src/  
│  ├─ main.cpp           # Entry point, game loop  
│  ├─ maze.cpp/.h        # Maze generation & rendering  
│  ├─ player.cpp/.h      # Player state & movement  
│  ├─ score.cpp/.h       # Scoring & high‑score file I/O  
│  └─ audio.cpp/.h       # SFML audio management  
├─ assets/  
│  └─ sounds/            # .wav/.ogg files for footsteps, win jingle, etc.  
├─ TowerOfOdyssey.pdf    # Full design document and feature list :contentReference[oaicite:1]{index=1}  
├─ demo.mp4              # Gameplay walkthrough video  
└─ README.md             # (You are here!)  
```

---

## 🏗 Technical Highlights

* **Dynamic Memory**

  * Maze stored as a `char**`, sized per level constants (`MAZE_SIZE_LEVELx`).
* **Efficient Redrawing**

  * Only cells that change (player move, exit reveal) are re‑printed, minimizing flicker.
* **Persistent State**

  * High score saved in `highscore.dat`; game state (current level, score) saved on exit for continuation.
* **Audio Integration**

  * Footstep, collect, and level‑up sounds managed via SFML’s `SoundBuffer` and `Sound` classes.
* **Cross‑Module Design**

  * Each subsystem (maze, player, scoring, audio) lives in its own pair of `.cpp/.h` for clarity and reuse.

---

## 🛠 Challenges & Learning

* **Console UX**

  * Achieved smooth animations in a text console using native Win32 cursor APIs.
* **State Management**

  * Balancing between in‑memory structs and on‑disk persistence for a “save & continue” feature.
* **Audio Sync**

  * Integrating SFML audio without blocking the main game loop.

---

## 🔗 Third‑Party Libraries

* [**SFML**](https://www.sfml-dev.org/) — Multimedia library for C++ (System, Window, Audio)&#x20;

---

## 🎥 Demo

> [![Watch the demo video](https://img.youtube.com/vi/VIDEO_ID/0.jpg)](demo.mp4)

*(Or see `demo.mp4` in this repo for a quick gameplay walkthrough.)*

---

## 🙏 Thank You for Playing!

We hope **Tower of Odyssey** tests your maze‑navigating skills and inspires you to explore console game development further. Pull requests, stars, and feedback are always welcome!
Happy coding & happy exploring!

---

```
```
