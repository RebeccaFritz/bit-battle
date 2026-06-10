# Bit Battle

A competitive 2-player browser game combining Pong mechanics with a hex-to-binary conversion challenge. Players choose a target and convert the hexadecimal number that appears on it to binary. If they convert the number correctly, they will launch a projectile towards the target which will accelerate it towards the opposite player. A new hexadecimal number will then be generated for the target and either player can try to send it back at the other player. Once a target reaches the opposite player, that player will lose a life. Whoever loses all five lives first loses the game. 

> 🎮 [Watch the demo](BitBattle_Demo.mp4)

---

## Prerequisites

Before running the project for the first time, make sure you have the following installed:

- [Go](https://go.dev/dl/) (v1.24 or later)
- [Node.js & npm](https://nodejs.org/)

To verify your installs:
```bash
go version
node --version
npm --version
```

---

## First-Time Setup

### 1. Clone the repository
```bash
git clone https://github.com/RebeccaFritz/bit-battle.git
cd bit-battle
```

### 2. Install client dependencies
```bash
cd client
npm install
cd ..
```

### 3. Initialize the database
The database table needs to be created on the first run. Open `server/main.go` and uncomment this line:

```go
create_table(db) // uncomment this if you have never built the app before
```

Then run the server once (see [Running the Project](#running-the-project) below). After the server starts successfully, **comment that line back out** to avoid re-initializing the table on future runs:

```go
//create_table(db) // uncomment this if you have never built the app before
```

---

## Running the Project

### Option A — Run both servers with one command (Linux/Mac/WSL)
From the project root:
```bash
./r.sh
```

If you get a permission error, make the script executable first:
```bash
chmod +x r.sh
./r.sh
```

### Option B — Run servers separately (Windows or manual)

**Terminal 1 — Start the backend:**
```bash
cd server
go run .
```

**Terminal 2 — Start the frontend:**
```bash
cd client
npm start
```

Once both are running, open your browser to **http://localhost:1234**.

---

## Multiplayer on a Local Network

By default the server only accepts connections from the same machine (`localhost`). To play with someone else on the same Wi-Fi network:

1. Find your computer's local IP address — run `ipconfig` in PowerShell and look for the **IPv4 Address** (e.g. `192.168.1.x`)
2. In `client/App.js`, replace:
   ```js
   const socket = new WebSocket('ws://localhost:8080/ws');
   ```
   with:
   ```js
   const socket = new WebSocket('ws://192.168.1.x:8080/ws');
   ```
   (substituting your actual IP address)
3. Restart the client (`npm start`)

The second player can then open `http://192.168.1.x:1234` in their browser to connect.

---

## Controls

Each player connects from their own machine and uses the same keys on their own keyboard.

| Action | Key |
|--------|-----|
| Move left | `A` |
| Move right | `D` |
| Toggle binary bits | `1` `2` `3` `4` `5` `6` `7` `8` |
| Submit answer / shoot | `Space` |

---

## Demo

https://github.com/user-attachments/assets/Bit-Battle-Local-Host.mp4

---

## Tech Stack

- **Frontend:** JavaScript, React, Parcel
- **Backend:** Go, Gorilla WebSocket
- **Database:** SQLite (`glebarez/go-sqlite`)

---

## Contributors

This was a team project. See [contributors](https://github.com/RebeccaFritz/SWE-Project-2025/graphs/contributors) for the full list.