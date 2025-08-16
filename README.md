# Maploc_src
# Realtime Device Tracker

A real-time device tracking application using **Node.js**, **Express**, **Socket.IO**, and **Leaflet.js**. This app lets you share your location live on a map, perfect for multi-user tracking use cases like delivery or fleet management.

---

## 🚀 Features

- **Live Location Tracking**  
  Continuously send client geolocation to the server and broadcast updates to all other clients.

- **Interactive Map with Leaflet**  
  The frontend renders a dynamic map using Leaflet, updating user markers in real time.

- **Multi-User Support**  
  Tracks multiple users simultaneously, representing each with a unique marker that’s updated or removed upon connection/disconnection.

- **Automatic Marker Cleanup**  
  When a user disconnects, their marker is removed from all connected clients.

---

## 🛠️ Stack & Technologies

- **Node.js & Express** — Backend server and HTTP handling.
- **Socket.IO** — Real-time, bidirectional communication (WebSockets).
- **Leaflet.js** — Mapping and marker display on the client.
- **EJS** (Embedded JavaScript) — Server-side template rendering for the frontend view.
- **Geolocation API** — Browser-based GPS data retrieval.

---

## 📂 Project Structure

```text
├── app.js                # Express server setup and socket logic
├── package.json         # Project metadata & dependencies
├── public/
│   ├── scripts.js       # Client-side logic (geolocation, map, socket)
│   └── styles.css       # CSS for the map and UI
├── views/
│   └── index.ejs        # HTML template for the map page
└── README.md            # Project description and setup (this file)
```

---

## ⚡ Getting Started

### Prerequisites
- Node.js and npm installed on your system.
- Basic familiarity with JavaScript and web development.

### Installation Steps
```bash
git clone <https://github.com/abhijeethkargeddamdev-in/Maploc_src.git>
cd realtime-device-tracker
npm install
```

### Run the Application
```bash
node app.js
```

Visit `http://localhost:3000` in your browser to see the live map.

---

## 🔧 How It Works

### Server (`app.js`):
- Initializes an Express app and integrates Socket.IO.
- Serves the client-side assets (HTML, JS, CSS).
- Handles WebSocket events:
  - **`send-location`**: Receives location from a client, broadcasts it to all.
  - **`disconnect`**: Informs other clients to remove the user's marker.

### Client (`scripts.js`):
- Establishes a Socket.IO connection.
- Uses browser’s Geolocation API to watch position and emit updates.
- Initializes a Leaflet map to render markers:
  - Moves existing markers if user ID matches.
  - Creates new markers as needed.
  - Cleans up markers on user disconnection.

### Frontend (`views/index.ejs`):
- Renders a full-screen Leaflet map.
- Loads necessary scripts and initializes the mapping canvas.

---

## 🚀 Potential Enhancements

- **Add usernames** or device identifiers for clarity.
- **Use custom icons** to distinguish users or types (e.g., driver vs passenger).
- **Implement user authentication** or private rooms.
- **Store historical paths** and replay user movements.
- **Mobile optimization** for better performance on phones.

---

## ✅ Summary

This project demonstrates how quickly you can build a **real-time, multi-user location tracking app** using modern JavaScript stack components. It’s ideal for learning how WebSockets, geolocation, and live mapping work together—and serves as a foundation for advanced features like chat, routing, or usage analytics.
