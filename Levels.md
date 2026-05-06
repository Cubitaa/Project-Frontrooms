## 🗂️ List of Levels

The game features a mix of **procedural**, **finite procedural**, and **hand-crafted levels**. Some areas are fully infinite, while others are bounded but still procedurally generated.

This is the planned list for the **Beta release** (subject to changes during development).

---

## ♾️ Procedural & Infinite Levels

- Level 0  
- Level 2  
- Level 5 *(may change)*  
- Level 8  
- Level 10  
- Level 37  
- Level 922337… *(infinite along Y-axis only)*  
- Level FUN *(non-procedural but infinite structure)*  

---

## 🧱 Finite / Non-Procedural Levels

- Level 1  
- Level 3  
- Level 4  
- Level 6  
- Level 7 *(may include dual boss encounters)*  
- Level 9  
- Level 11  
- Level 34 *(thank god)*  
- Level 188  
- Level !  
- The End  
- The Hub  
- Level 3999  
- The Grave  

---

## ⚡ Locations

- The void
- The broken
- The FrontRooms *(you can only play it on the first run with a cutsceen)*

---

## 🧠 Level 0

Over the past few months, I’ve been developing a **chunk-based procedural generation system** using pre-built modules.

After **3 months**, **7 prototypes**, over **200 hours of work**, and more than **1,000 lines of code**, I’ve reached a system design I’m genuinely satisfied with.

### ⚙️ Key Features

- ♾️ Optimized procedural generation designed for low-end hardware  
- 🎲 Weighted randomness for biomes, chunks, and special structures  
- 🌍 Smooth biome continuity and transitions  
- 💾 Persistent world state (chunks remain consistent when revisited)  
- 🌱 Unique server seeds (each server generates a different world)  
- 🔄 Random chunk rotation for increased variation  
- 🌀 Non-Euclidean player-based map perception (no collisions or visual bugs)  
- 💡 Dynamic lighting and ambient system  
- 🔊 Environmental sound system (still expanding)  
- 🧱 ~20 chunk types and 3 main biomes: *Rooms*, *Pillars*, *Darkness*  

---

You can watch an **8-minute showcase of Level 0 here:**  
https://www.youtube.com/watch?v=DmJVvz0M5Xw  

---

### 📸 Level 0 Showcase

| | | |
|:-:|:-:|:-:|
| <img src="https://github.com/user-attachments/assets/91a0e5b7-b048-4adc-9197-376ccec41556" width="300"/> | <img src="https://github.com/user-attachments/assets/1ff9eb9b-6446-406c-8ccb-a656c93d4b1b" width="300"/> | <img src="https://github.com/user-attachments/assets/51d74110-f5c7-45a7-abb4-753836f76ede" width="300"/> |
| <img src="https://github.com/user-attachments/assets/b1573a14-02cf-4a9a-8a7c-1bd7de8fcd0d" width="300"/> | <img src="https://github.com/user-attachments/assets/3ee421b8-f96b-4e56-b111-a6e882c0a04f" width="300"/> | <img src="https://github.com/user-attachments/assets/df60d6cf-1779-471c-9682-03c66e96a87b" width="300"/> |

> ⚠️ The Darkness biome currently doesn’t look fully accurate in screenshots due to temporary flashlight lighting limitations.

---

## 🧠 Generation System Overview

The world generation is based on a **chunk-based procedural system** using weighted selection, circular biome regions, and dynamic streaming with caching.

The world operates on an invisible **100x100 stud grid**, where each standard chunk occupies one cell. Special chunks follow strict size rules (200x200, 300x300, etc.) and always remain square.

---

## ⚙️ Core Systems

### 🧱 Grid-Based Generation
- Spatial partitioning system
- Chunk-based world construction
- Deterministic placement per seed

### 📡 Chunk Streaming (Player-Based)
- Generates only nearby chunks
- Destroys distant chunks automatically
- Limits active memory usage

### 🌱 Seeded RNG
- Each server has a unique seed
- Fully deterministic generation per world

### 🎲 Weighted Selection System
- Controls rarity of chunks and biomes
- Enables structured randomness

### 🌍 Circular Biomes (No Perlin Noise)
- Biomes defined as circular regions
- Random centers with radius constraints
- Overlapping biome layers allowed
- Smooth transitions between zones

### 🌫️ Biome Blending
- Smooth interpolation between biomes
- Prevents abrupt visual changes

### 🧩 Multi-Chunk Structures
- Large structures occupy multiple grid cells
- Prevent overlap via spatial locking

### 🗑️ LRU Cache System
- Removes least-used chunks first
- Optimizes memory usage during exploration

---

## 🧪 Level 1 (WIP)
Currently in early development. No screenshots available yet.

---

## 🧪 Level 2 (WIP)
Procedural generation completed. Minor bugs and path modeling still in progress.

---

## 🧪 Level 3 (WIP)
Finite procedural generation system in development. Still being finalized.

**Reference videos:**

👉 https://youtu.be/0xQQPq23MrY?si=7Ew0ofM3XhB8OA7P  
👉 https://www.youtube.com/shorts/vqjHLxMW7Kg  

---

## 🔦 Level 6

“Lights Out” level designed as a near-total visibility environment.

The player uses a **LiDAR scanner** instead of light sources, due to lore constraints.

### Scanner data:
- ⚪ White = normal points  
- 🌈 Multi-color = exits  
- 🔴 Dark red = corpses  
- 🟥 Red = danger/blood  
- 🟠 Orange-red = internal body structures  
- 🔵 Blue = tools (non-usable)  
- ⚫ Grey = obstacles  

> ⚠️ System has been improved since the recorded footage (better performance + more scan points).

https://github.com/user-attachments/assets/b5f89c69-5d7f-481c-bb81-d05440731cea  

| | | | 
|:-:|:-:|:-:| 
| <img src="https://github.com/user-attachments/assets/fadde364-d614-47ed-9c2a-60acb755c210" width="300"/> | <img src="https://github.com/user-attachments/assets/fdbe0f55-6a2c-4c8d-a1aa-ae4cab471cfe" width="300"/> 
<img src="https://github.com/user-attachments/assets/015f2cf4-7fb9-4af3-b042-564c9f7a862c" width="300"/> | <img src="https://github.com/user-attachments/assets/787a8604-cb66-4fa9-9584-4f959730e52d" width="300"/>

**Reference map: **

<img src="https://github.com/user-attachments/assets/cbf15e89-e120-4b1f-aafd-205ddbc45f50" width="300"/>

> This is the reference map used (slightly modified for gameplay purposes).

My only doubt is whether to add entities like smilers at this level or not, since according to the wiki it is unknown if there are any entities (If you have any suggest, write me!)

---

## 🏠 Level 9

---

## 🗺️ Level 10
I created a script that generates infinite terrain as you walk (for optimization), as well as multiple assets like forest, barns, wheat fields or lakes, as the wiki mentions. 

All that’s left is to create the barn, use the forest as a model and lower the sand level around the lake.

<img width="516" height="256" alt="image" src="https://github.com/user-attachments/assets/3d366c07-90d1-4dc8-9d80-fa7d64d38cbc" /> <img width="517" height="256" alt="image" src="https://github.com/user-attachments/assets/ccb545b7-19bf-4d57-84d7-9f10fa3b55bd" />

---

## 🌐 The Hub
Currently in progress, the hub’s function will be to use key levels to freely access unlocked levels.
