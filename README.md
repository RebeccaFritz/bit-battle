# Bit Battle

A competitive 2-player browser game combining Pong mechanics with a hex-to-binary conversion challenge. Players choose a disk and convert the hexadecimal number that appears on it to binary. If they convert the number correctly, they will launch a projectile towards the disk which will accelerate it towards the opposite player. A new hexadecimal number will then be generated for the disk and either player can try to send it back at the other player. Once a disk reaches the opposite player, that player will lose a life. Whoever loses all five lives first loses the game.

> 🎮 [Watch the demo](https://youtu.be/T1ehQzwyTp8)

*Demo shows both players on the same machine for demonstration purposes. In a real game, each player connects from their own device.*

---

## Branches

This repository has two branches depending on how you want to run the game:

| Branch | Description |
|---|---|
| `remote-hosting` | Containerized with Docker, deployed to Fly.io. **Play now at [hexapong.fly.dev](https://hexapong.fly.dev)** — no installation required. |
| [`local-hosting`](https://github.com/RebeccaFritz/bit-battle/tree/local-hosting) | Run the game locally using Go and Node.js. Supports same-network multiplayer. See the branch README for setup instructions. |

---

## Controls

Each player connects from their own machine and uses the same keys on their own keyboard.

| Action | Key |
|--------|-----|
| Move left | `A` |
| Move right | `D` |
| Toggle binary bits | `1` `2` `3` `4` `5` `6` `7` `8` |
| Submit answer / shoot | `Space` |

## Tech Stack

- **Frontend:** JavaScript, React, Parcel
- **Backend:** Go, Gorilla WebSocket
- **Database:** SQLite (`glebarez/go-sqlite`)
- **Hosting:** Fly.io 
- **Containerization:** Docker

---

## Contributors

- [Luke Dulworth](https://github.com/LukeDul)
- [Rebecca Fritz](https://github.com/RebeccaFritz)
- [Nathaniel Morris](https://github.com/nathaniel-w-morris)
